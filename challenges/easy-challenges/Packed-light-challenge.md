# Packed Light Walkthrough

### Tools Used
- Wireshark - filtering HTTP traffic, Follow TCP Stream, reading Cookie headers
- CyberChef - From Base64 + XOR to recover the flag

### Step-by-Step Methodology

- **Step 1** - Open `traffic.pcapng` in Wireshark and apply the filter:
  ```
  http
  ```
  You'll immediately see two different things: one normal `GET /temp/updates.py` request (frame 16, response `text/x-python` in frame 19), followed by hundreds of repeated small `GET / HTTP/1.1` requests to the same host (`34.41.103.191`, i.e. `byte-lotus-hotel.thm:8080`) — that's suspicious, since it fires roughly once per second.

- **Step 2** - Right-click any packet from that conversation → **Follow → TCP Stream**. The stream shows:
  - the request that downloaded `updates.py`,
  - the server's response containing the full Python source of that script.

  The key part of the code:
  ```python
  def getkey():
      p1 = "H0t3lSt@ff0Nly"
      p2 = "K3epS3cr3t!"
      return p1 + p2
  ```
  So the XOR key is `p1 + p2` concatenated together: `H0t3lSt@ff0NlyK3epS3cr3t!`. Further down, the script is clearly a `pynput`-based keylogger — every keystroke gets XORed with this key, Base64-encoded, and sent as `Cookie: hotel_sess_state=<base64>` in a `GET /` request to the same host.

  **This is where the `H` comes from:** look at the XOR loop in the script —
  ```python
  def xor(data: bytes, key: bytes) -> bytes:
      return bytes(b ^ key[i % len(key)] for i, b in enumerate(data))
  ```
  The function `sendltr()` encrypts **one character at a time**, so `data` is always length 1. That means in the loop `i` is always `0`, so `key[i % len(key)]` always resolves to `key[0]` — the **very first character of the key string** you just read in the Follow TCP Stream window (`H0t3lSt@ff0Nly...`). That first character is `H`. The other 24 characters of the key are never actually used, because no message is ever long enough to reach them.

- **Step 3** - Close the stream window and change the filter to:
  ```
  http.cookie contains "hotel_sess_state"
  ```
  This isolates only the exfiltration requests — one per keystroke, in chronological order (frame 391, 428, 520, 585...).

- **Step 4** - Click through these packets one by one and expand **Hypertext Transfer Protocol → Cookie** in the detail pane to read the exact value, e.g.:
  ```
  Cookie: hotel_sess_state=HA==\r\n
  ```
  Going frame by frame (order matters — it's the order the victim typed), write down just the base64 values (without `hotel_sess_state=`) and string them together, comma-separated:
  ```
  HA==, AA==, BQ==, Mw==, Hg==, ew==, Og==, fA==, Fw==, eQ==, Ow==, Fw==, Pw==, fA==, PA==, Kw==, IA==, eQ==, Jg==, Lw==, Fw==, eA==, Pg==, LQ==, Gg==, Fw==, MQ==, eA==, PQ==, NQ==
  ```

- **Step 5** - Paste that whole string into CyberChef's Input, and build a two-operation recipe:
  1. **From Base64** - alphabet `A-Za-z0-9+/=`, with **Remove non-alphabet chars** checked (this is what lets you paste everything at once — the commas and spaces get stripped, and each 4-character group still decodes cleanly to its own 1 byte thanks to the `==` padding).
  2. **XOR** - Key: `H`, type `UTF8`, Scheme: `Standard`.

- **Step 6** - The Output pane now shows the reconstructed flag, character by character, in the exact order the victim typed it — no `Fork`/`Merge` needed, since `From Base64` already splits the concatenated string correctly on its own thanks to the padding in each group.
