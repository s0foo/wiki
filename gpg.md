# Encryption
- Encrypt a file: `gpg --encrypt --armor -r <receiver_id> <file_to_encrypt>`

# Decryption
- Decrypt a file: `gpg <file_to_decrypt>`

# Key Management
- Export public key: `gpg --armor --output <key.gpg> <email_address>`

# Misc.
- Clear the cache: `gpgconf --kill gpg-agent`
