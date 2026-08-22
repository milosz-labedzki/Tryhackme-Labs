* `hydra` - A popular parallelized network logon cracker used by security auditors and penetration testers to perform brute-force attacks against network authentication services.

* `hydra (syntax)` - `hydra [[-l LOGIN|-L FILE] [-p PASS|-P FILE]] [options] [target] [service]`

* `hydra ssh login (syntax)` - `hydra -l <user> -P <passlist.txt> <target_ip> ssh`

* `-l option` - A Hydra command-line argument used to specify a single static target username for the authentication attack.

* `-p option` - A Hydra command-line argument used to specify a single static target password for the authentication attack.

* `-t option` - A Hydra command-line argument used to set the number of parallel tasks or execution threads running concurrently against the target.

* `(Post web form)` - An HTTP authentication mechanism where user login credentials are transmitted to the server inside the body of an HTTP POST request.

* `-hydra post web form (syntax)` - `hydra -l <user> -P <passlist.txt> <target_ip> http-post-form "<path>:<login_credentials>:<invalid_response>"`

* `-l` - Hydra flag used to supply a single specific username parameter for authentication attempts.

* `-p` - Hydra flag used to supply a single specific password parameter for authentication attempts.

* `http-post-form` - The Hydra module designator used to target web-based authentication forms that send credentials via the HTTP POST method.

* `<path>` - The URL path component in an `http-post-form` module string specifying the exact endpoint script where POST credentials are submitted (e.g., `/login.php`).

* `<login_creditials>` - The body parameter template in an `http-post-form` module string defining POST variables with replacement placeholders (e.g., `username=^USER^&password=^PASS^`).

* `<invalid_response>` - The string pattern in an `http-post-form` module string that Hydra searches for in the HTTP response body to recognize a failed authentication attempt (e.g., `F=Invalid password`).

* `-V` - A Hydra command-line flag enabling verbose mode to display every tested credential pair and detailed execution output in real-time.
