# offline-text-encryption
Secure Offline Password Generation and Text Encryption Tool
This is a free, offline tool for generating secure passwords and encrypting/decrypting text locally.
Fully browser-based: simply open the HTML file, no installation or server required.
All operations are performed locally; no data is transmitted over the Internet.
Designed for secure communication over insecure channels such as QQ, WeChat, or other platforms without built-in end-to-end encryption.
This project uses TweetNaCl.js under the MIT License.

Feel free to use, modify, and distribute it.

How This Project Achieves Secure Offline End-to-End Encryption
Building a Universally Usable Offline Program
Every modern operating system — Windows, macOS, Linux, iOS, Android — has a web browser that adheres to common standards. By using pure HTML, JavaScript, and CSS, the tool can be used directly by simply opening the HTML file in any browser, without any installation or server dependency.

Constructing Secure Passwords
Passwords must be generated randomly and include uppercase letters, lowercase letters, numbers, spaces, and special symbols. Human-created passwords tend to be predictable due to memory habits, making them vulnerable to social engineering attacks. Therefore, I developed a "31 Days × 24 Hours" password book generator. Each password is randomly generated, and the system recommends rotating passwords daily — or even hourly — to ensure Forward Secrecy.

Secure Key Exchange and Protection Against MITM Attacks
The ideal method is offline exchange via physical media (e.g., a USB drive). However, when offline exchange is impractical (e.g., in different cities), the project uses RSA-4096 to generate public/private key pairs.

Each participant generates a key pair locally.

The public key is sent electronically, and the fingerprint is verified over a secure voice call to prevent Man-in-the-Middle (MITM) attacks.

I encrypt the password book (compressed in a 7z archive) using the recipient's public key, and send both the encrypted archive and the RSA-encrypted password separately.

The recipient decrypts it locally using their private key.

Encrypting and Decrypting Text Messages
Text communication is encrypted using AES-256-GCM with passwords sourced from the password book. All encryption and decryption operations happen locally, ensuring end-to-end security even over insecure platforms like QQ and WeChat.

This approach successfully implements manual, offline, end-to-end encryption for communications over unsafe channels.
