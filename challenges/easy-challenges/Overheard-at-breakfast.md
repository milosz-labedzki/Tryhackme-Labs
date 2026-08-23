# Overheard at Breakfast Walkthrough

### Tools Used

- Browser
- Gravatar
- CyberChef

### Step-by-Step Methodology

- **Step 1** - Download the task file and open the conversation screenshot.
- **Step 2** - Carefully read the entire chat between Ponzi and Lambo. Extract two key pieces of information:
  - The email address mentioned by Lambo
  - The mention of a free tool starting with the letter “G” that was used for profile pictures
- **Step 3** - Identify the tool as Gravatar (a service that generates avatars based on email hashes).
- **Step 4** - Generate the MD5 hash of the email address (lowercase, no extra spaces):
  ```bash
  echo -n "email@example.com" | md5sum
  ```
- **Step 5** - Visit the Gravatar profile using the hash:
  ```bash
  https://gravatar.com/<MD5_HASH>
  ```
- **Step 6** - On the Gravatar profile, find the Base64-encoded string in the bio.
- **Step 7** - Decode the Base64 string using CyberChef to obtain the flag.
