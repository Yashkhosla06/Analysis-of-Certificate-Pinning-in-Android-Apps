# Analysis of Certificate Pinning in Android Apps

## Overview
This project focuses on the implementation and analysis of TLS certificate pinning in Android applications to enhance security against man-in-the-middle (MITM) attacks. The report investigates both static and dynamic analysis techniques to detect certificate pinning in 100 distinct Android apps.

## Certificate Pinning
Certificate pinning is a security procedure that binds an SSL/TLS certificate or public key to a specific server or domain. This process prevents MITM attacks by ensuring that the client application only accepts connections from servers with the predefined certificate or key.

### Types of Certificate Pinning
1. **HPKP (HTTP Public Key Pinning)**: A deprecated security standard where web servers send headers to the client's browser, specifying the public keys that should be used to validate the server's certificate.
2. **CA Pinning**: Involves hardcoding a trusted Certificate Authority's (CA) public key or hash into the client’s code or relying on the client's trust store to ensure only certificates signed by the trusted CA are accepted.

### Implementation Methods
- **Hard Pinning**: Hardcoding the server’s certificate’s public key or hash into the client’s code.
- **Soft Pinning**: Relying on the client's trust store to verify the server’s certificate chain is signed by a trusted CA.

## Methodology
### Static Analysis
- **Download APK Files**: Obtained from the web.
- **Extract Build Files**: Using `apktool` on Kali Linux to inspect network configurations.
- **Code Inspection**: Searching for certificates using extensions like `.pem`, `.cer`, `.cert`, `.crt`, `.drt`, and `.dert` or keywords like “begin certificate”.

### Dynamic Analysis
- **Tools**: Burp Suite Community Edition and Android Emulator API.
- **Setup**: Configured proxy settings in Burp Suite, installed and configured the Android emulator with manual proxy settings.
- **Procedure**: Installed and tested apps to detect certificate pinning by observing behavior such as error codes or network errors upon login attempts.

## Findings and Conclusion
The analysis revealed the presence and effectiveness of certificate pinning in preventing MITM attacks across various Android applications. Certificate pinning, while a robust security measure, presents operational challenges such as maintaining up-to-date certificates and avoiding service disruptions. The report concludes that certificate pinning should be part of a comprehensive security strategy rather than a standalone solution.

## Authors
- Deep Bhavesh Gajiwala
- Devina Shah
- Meet Rakeshbhai Patel
- Pratiksha Ashok Kumar Pole
- Rohan Yogeshkumar Modi
- Simran Kaur
- Snehpreet Kaur
- Yash Khosla



## Acknowledgments
Special thanks to Dr. Amr Youssef for guidance and support throughout this project.

---

For more detailed information, please refer to the full report.
