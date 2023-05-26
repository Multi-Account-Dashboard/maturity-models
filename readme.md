# Authentication Maturity Models

## Maturity Model for Primary Authentication

| **Level** | **Mechanism**                                                   | **Exemplary security risks**                                                                                    | **Exemplary accessibility risks**                                     |
|-----------|-----------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------|
| A5        | Passwordless AuthN                                              | Social engineering, extortion, and cryptographic issues                                                         | Lost/broken device and fallback method failure                        |
| A4        | Token-based 2FA                                                 | Social engineering (e.g., phishing) and stolen token                                                            | Lost or broken device and buggy implementation                        |
| A3        | App-based 2FA                                                   | Device compromise, malicious app, and social engineering                                                        | Lost or broken device, broken app, and fallback method failure        |
| A2        | SMS-based 2FA                                                   | SIM-swapping, SMS-hijacking, stolen device, and social engineering                                              | Lost or broken device, lost or broken SIM card, and delivery failures |
| A1        | Password                                                        | Password dumps, credential stuffing, shared passwords, easy passwords, social engineering, and insecure storage | Forgotten password, broken password manager, and errors during typing |
| SF        | Risk-based (e.g., location, user pattern, and former passwords) | Impersonation due to malware, guessable/social engineering, or too loose                                        | Too strict by requesting 2FA or more almost every time                |


## Maturity Model for Fallback Authentication

| **Level** | **Mechanism group** | **Mechanism**                                         | **Exemplary security risks**                                                                   | **Exemplary accessibility risks**                                        |
|-----------|---------------------|-------------------------------------------------------|------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------|
| F5        | Token-based         | Backup token                                          | Token swap or attack on underlying security / applied software                                 | Lost, broken, or otherwise currently unavailable token                   |
| F4        | Recovery code-based | Backup code                                           | Device or storage compromise                                                                   | Forgotten, deleted, or never remembered code                             |
| F3        | Trustee-based       | Code or AuthN via several mostly pre-defined trustees | Social engineering or man in the middle                                                        | Not possible (e.g., forgotten) or available                              |
| F2        | SMS-based           | Code via SMS                                          | SIM-swapping or hijacking, stolen device, or social engineering                                | Lost device, forgotten PIN noticed during reboot, or device lockout      |
|           | Email-based         | Reset emails with old/new password or URL link        | Credential stuffing, general account takeover, device compromise, or other human-in-the-middle | Deleted/deactivated email account or delay in delivery during each usage |
| F1        | Question-based      | Security question(s) or puzzle                        | Social engineering, found on the Internet or otherwise guessable                               | Forgotten answer or wrong semantic                                       |

