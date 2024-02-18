
# GO POST !

This Go program automates the process of posting JSON log data to a specified server endpoint securely. It reads log files, sanitizes the data to escape HTML/PHP tags, signs the data with an HMAC SHA512 signature for integrity verification, and posts the data over HTTPS.

## Features
- **Secure Data Transmission**: Uses HTTPS to ensure data is encrypted in transit.
- **Data Integrity**: Applies HMAC SHA512 to log data ensuring integrity and authenticity.
- **HTML/PHP Tag Sanitization**: Escapes HTML/PHP tags in log data to prevent injection attacks.
- **Flexible Configuration**: Supports specifying multiple log files and custom post variables through a configuration file.

## Configuration
The program reads its configuration from a file named `post.cfg` located either in the current directory or in `/etc/cybersupervisor/`. The configuration file should be in JSON format, specifying the server URL, the HMAC secret for signing the data, and the log files to process. It supports multiple log files.

### Example Configuration

```json
{
  "url": "https://example.com/post",
  "logSources": [
    {"path": "/path/to/log1.json", "postVar": "logData1"},
    ...
  ],
  "hmacsecret": "your_hmac_secret_here"
}
```

## License

This project is licensed under the GNU Lesser General Public License v2.1.
---
