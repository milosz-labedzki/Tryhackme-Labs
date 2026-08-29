* `Cryptographic Failures` - A security risk category (formerly Sensitive Data Exposure) resulting from the lack of or improper implementation of cryptographic controls, leading to the exposure of sensitive data in transit or at rest.

* `How to Prevent Cryptographic Failures` - Classify data, encrypt all sensitive data in transit (TLS 1.3) and at rest (AES-256), use strong password hashing functions with salting (Argon2, bcrypt), and properly manage cryptographic keys.

* `Injection` - A class of security vulnerabilities occurring when untrusted user input is directly concatenated into an interpreter command or query (e.g., SQL, Command, LDAP), leading to unauthorized code execution.

* `How to Prevent Injection` - Use parameterized queries and prepared statements, utilize Object-Relational Mapping (ORM) frameworks, validate and sanitize all user input against strict allowlists, and enforce least privilege.

* `Software/Data Integrity Failures` - Vulnerabilities related to code and infrastructure that fail to protect against unauthorized modifications, such as unverified software updates, untrusted CI/CD pipelines, or insecure deserialization.

* `How to Avoid Software/Data Integrity Failures` - Enforce digital signatures to verify software source and package integrity, implement strong access controls and security checks in CI/CD pipelines, and avoid deserializing untrusted data.
