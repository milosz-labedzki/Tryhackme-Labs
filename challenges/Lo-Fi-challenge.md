# Lo-Fi Walkthrough

### Tools Used

- `curl` - Used to fetch page content and test LFI payloads from the terminal.
- `Firefox` - Browser used to explore the web application and test the vulnerable parameter.

### Step-by-Step Methodology

- **Step 1** - Access the target web application at `http://<IP>`.
- **Step 2** - Click on any link in the Discography section (e.g. Relax) and observe the URL parameter `?page=`.
- **Step 3** - Test for Local File Inclusion by requesting `/etc/passwd` using path traversal:?page=../../../../etc/passwd
- **Step 4** - Confirm LFI works by reading the content of `/etc/passwd`.
- **Step 5** - Retrieve the flag located in the root of the filesystem: ?page=../../../../flag.txt
