# OhSINT Walkthrough

### Tools Used
- `exiftool` – to read the image's metadata
- Google / Twitter (X) / GitHub – to search by username
- WiGLE.net – to geolocate via BSSID/SSID of the WiFi network

### Step-by-Step Methodology

- **Step 1** – Download the image file (`WindowsXP_....jpg`) provided in the task.
- **Step 2** – Run `exiftool filename.jpg` to extract the EXIF metadata.
- **Step 3** – In the metadata you'll find a username (author/comment field) – this is your starting point for further OSINT.
- **Step 4** – Google that username – you'll find an associated Twitter/X account.
- **Step 5** – On the Twitter profile, check the avatar (answers the "avatar of?" question) and browse through the tweets.
- **Step 6** – One of the tweets mentions the BSSID of a WiFi network.
- **Step 7** – Paste that BSSID into WiGLE.net (a BSSID lookup/search tool) – you'll get a geographic location, which answers the "what city" question.
- **Step 8** – Zooming in on the map in WiGLE, you'll also find the SSID of the network he connected to.
- **Step 9** – Keep searching by the username – you'll also find a blog (e.g. WordPress) linked to this person.
- **Step 10** – The email address usually isn't shown directly on Twitter or the blog – check GitHub with the same username; the email is often listed in the profile or in commits.
- **Step 11** – On the blog you'll find where the person went on holiday (usually in a blog post/article).
- **Step 12** – The password usually isn't visible at a glance – check the blog page's source code (Ctrl+U / "View Page Source"), it's often left in an HTML comment or in the page metadata.
