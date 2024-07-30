# Monify-API-Reserved-Account-And-Webhook-Notification-Handling

## Customer Reserved Account Generation

This API allows you to request new account numbers from multiple banks. Follow these steps to use the API:

*Step 1: Access Token Request*

Obtain an access token by sending a request to the token endpoint.

*Step 2: New Account Number Request*

Send a request with the following parameters:

- accessToken : the obtained access token
- `contractCode`: the contract code for the request
- `apiKey`: the API key for authentication
- `secretKey`: the secret key for authentication

If `getAllAvailableBanks` is not set to `false`, the response will include account numbers from multiple banks.

*Step 3: Response Handling*

Handle the response containing up to 10 account numbers from different banks.

*Important*

- Ensure you have the required credentials before making requests.
- Use the `getAllAvailableBanks` parameter to control the response behavior.

## Webhook Notification Handling



Contact me for the source code or use the uploaded file, for that you need to decrypt it.

To decrypt the files, you'll need to create a corresponding decryption script. Here's an explanation of the decryption process:

1. *Retrieve the IV and encrypted data*: Read the contents of the encrypted file (e.g., `monify/file.txt.enc`).
2. *Extract the IV*: Use `substr` to extract the IV from the beginning of the encrypted data, the length is iv generated using aes-256-cbc as the length or parameter.
3. *Decrypt the data*: Use `openssl_decrypt` with the extracted IV, the encrypted data, the same `$key` (webdev-php) and `$cipher` (aes-256-cbc) used during encryption.
4. *Save the decrypted data*: Write the decrypted data to a new file, without the `.enc` extension.
