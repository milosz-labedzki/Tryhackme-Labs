# MD2PDF Walkthrough

### Tools Used

- `nmap` - Used for initial port scanning and service detection.
- `Firefox` - Browser used to interact with the web application and download the generated PDF.
- `exiftool` - Used to inspect PDF metadata and identify the conversion engine (`wkhtmltopdf`).

### Step-by-Step Methodology

- **Step 1** - Scan the target with nmap to discover open ports (80 and 5000).
- **Step 2** - Explore the Markdown to PDF converter and generate a test PDF.
- **Step 3** - Inspect the PDF metadata with `exiftool` and identify `wkhtmltopdf`.
- **Step 4** - Discover the restricted `/admin` page (accessible only from localhost:5000).
- **Step 5** - Inject an iframe payload pointing to `http://localhost:5000/admin` and convert it to PDF to retrieve the flag.
