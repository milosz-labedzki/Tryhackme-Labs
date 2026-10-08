* `Digital Identity` - The digital representation of a user, service account, or bot, including context like IP address, user behavior, credentials, tokens, and access permissions.


* `Sign-in Logs` - M365 authentication logs analyzed in SOC to detect password attacks, such as brute-force attempts indicated by multiple failed sign-ins followed by a single successful login.


* `M365 Sign-in Logs Query` - Search specifically for Azure Active Directory / Entra ID sign-in events within a specific dataset index in Splunk:
index=scenario sourcetype="azure:aad:signin"
