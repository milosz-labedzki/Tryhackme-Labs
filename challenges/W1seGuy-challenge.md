# W1seGuy Walkthrough

### Tools Used

- `netcat` (`nc`) - Used to connect to the service on port 1337.
- CyberChef - Used to perform XOR decryption and recover the key.

### Step-by-Step Methodology

- **Step 1** - Connect to the target service using:
  ```bash
  nc <IP> 1337
- **Step 2** - Receive the XOR-encoded hexadecimal string along with the question asking for the encryption key.
- **Step 3** - Recover the first 4 characters of the key by XORing the first 4 bytes of the ciphertext with the known plaintext prefix THM{.
- **Step 4** - Brute-force the 5th character of the key (uppercase/lowercase letters and digits) until a clean and readable flag is obtained in the output.
- **Step 5** - Submit the complete 5-character key back into the netcat session to receive Flag 2.
