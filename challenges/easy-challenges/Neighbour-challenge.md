# Neighbour Walkthrough

### Tools Used

- Firefox - Browser used to access the web application and view page source.
- Ctrl + U - Used to inspect the HTML source code of the login page.

### Step-by-Step Methodology

- **Step 1** - Access the target at `http://<IP>` and open the login page.
- **Step 2** - View the page source (Ctrl + U) and find the hardcoded credentials `guest:guest` in an HTML comment.
- **Step 3** - Log in using the credentials `guest:guest`.
- **Step 4** - After logging in, observe the URL parameter `?user=guest`.
- **Step 5** - Change the parameter to `?user=admin` to exploit the IDOR vulnerability and retrieve the flag.
