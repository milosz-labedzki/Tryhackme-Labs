# Corridor Walkthrough

### Tools Used

- Firefox - Browser used to explore the corridor and access different doors.
- `echo` + `md5sum` - Used to generate the MD5 hash of the number 0.

### Step-by-Step Methodology

- **Step 1** - Access the target website and observe the corridor with multiple doors.
- **Step 2** - Click on any door and notice that the URL contains a long hexadecimal string (MD5 hash).
- **Step 3** - Identify that the hashes correspond to MD5 values of numbers 1 through 13.
- **Step 4** - Generate the MD5 hash of the number `0` using the command:
  ```bash
  echo -n "0" | md5sum
- **Step 5** - Navigate to the URL containing the hash of 0 (cfcd208495d565ef66e7dff9f98764da) to retrieve the flag.
