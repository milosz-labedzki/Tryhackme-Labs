* `Double File Extensions` - Malware disguises itself using a second, hidden extension, exploiting Windows' default setting that conceals known file extensions from the user:
invoice.pdf.exe


* `System Binary Impersonation` - Malware adopts filenames that closely resemble legitimate system processes to exploit user trust; defenders should allowlist by full file path, not filename alone:
scvhost.exe


* `High-Entropy Filenames` - Random, meaningless-looking filenames suggest automated packing or polymorphic malware generation, common in high-volume phishing campaigns:
jh8F21.exe


* `Masquerading` - Malware uses routine-looking filenames or single-character substitutions to blend in and reduce suspicion while appearing visually legitimate:
backup-2300.exe


* `File Hashing (Windows - CMD)` - Compute a file's SHA256 hash for threat intel lookup:
certutil -hashfile bl0gger.exe SHA256


* `File Hashing (Windows - PowerShell)` - Compute a file's SHA256 hash using the native cmdlet:
Get-FileHash -Algorithm SHA256 bl0gger.exe


* `File Hashing (Linux)` - Compute a file's SHA256 hash using the standard utility:
sha256sum bl0gger.exe


* `VirusTotal` - Online multi-engine service; submit a file hash to check detection results across dozens of AV/EDR vendors at once.


* `Sandbox` - Isolated analysis environment used to safely detonate a suspicious file and observe its behavior without risking the host system.
