# boggle.cc Key System

This website provides a key generation service that integrates with Linkvertise to ensure secure access. Follow the steps below to use the service.

## Features
- Generates a unique key for users who complete the Linkvertise process.
- Bans IPs that attempt to bypass the system.
- Keys are valid for 24 hours.

## Prerequisites
- A web server with PHP support.
- `keys.json` and `banned-ip.json` files in the root directory (these will be created automatically if they don't exist).
- A valid Linkvertise token.

## Setup
1. Clone this repository to your web server:
   ```bash
   git clone https://github.com/your-repo/key-system.git
   ```
2. Navigate to the project directory:
   ```bash
   cd key-system
   ```
3. Ensure the web server has write permissions for `keys.json` and `banned-ip.json`:
   ```bash
   chmod 666 keys.json banned-ip.json
   ```
4. Replace `ANTI_BYPASSING_TOKEN` in `index.php` with your actual Linkvertise token.
5. Replace `LINKVERTISE_URL` in `index.php` with your Linkvertise target URL.

## Usage
1. Open the website in your browser.
2. Complete the Linkvertise process to obtain a key.
3. If successful, a unique key will be displayed on the page.

## Notes
- Keys are stored in `keys.json` with associated IP addresses and expiration times. You can change the name for more security, just make sure to edit the php too.
- If an invalid or expired key is used, the IP will be banned and added to `banned-ip.json`. You can change the name for more security, just make sure to edit the php too.
- Banned IPs will see a message indicating they are permanently banned.

## License
This project is licensed under the MIT License.