# IFTTT Webhook Resolver: A Lightweight Node.js Module for Seamless Web Automation

## Project Overview

A lightweight Node.js module designed to simplify interactions with IFTTT (If This Then That) Webhooks, enabling developers to easily trigger custom web-based automation workflows.

### Purpose
The IFTTT Webhook Resolver provides a streamlined interface for sending data to IFTTT Webhooks, allowing programmatic triggering of complex automation scenarios across various web services and platforms.

### Key Features
- Simple, straightforward API for calling IFTTT Webhook triggers
- Automatic payload transformation to match IFTTT's expected input format
- Supports sending up to three data values per webhook call
- Promise-based response handling with success and error states

### Benefits
- Reduces boilerplate code for IFTTT webhook integrations
- Enables programmatic automation across multiple platforms
- Lightweight and easy to integrate into existing Node.js projects

## API Reference

### Functions

#### `call(webhookAction, apiKey, data)`
Sends a webhook request to IFTTT (If This Then That) platform.

**Parameters:**
- `webhookAction` (string): The name of the IFTTT webhook trigger
- `apiKey` (string): The IFTTT Webhooks API key for authentication
- `data` (array): An array of values to be sent as payload 

**Returns:**
- Promise resolving to an object with:
  - `success` (boolean): Indicates whether the request was successful
  - `result` (object): The response from the IFTTT Webhooks API or error details

**Example Usage:**
```javascript
const iftttWebhook = require('your-library-name');

iftttWebhook.call('my_trigger', 'YOUR_API_KEY', ['value1', 'value2', 'value3'])
  .then(response => {
    if (response.success) {
      console.log('Webhook sent successfully');
    } else {
      console.error('Webhook failed', response.result);
    }
  });
```

**Notes:**
- The function transforms the input array into IFTTT's expected payload format (value1, value2, etc.)
- This function uses the `request-promise` library for making HTTP requests
- The webhook is sent to `https://maker.ifttt.com/trigger/{webhookAction}/with/key/{apiKey}`

## Project Structure

The project is a lightweight Node.js module for interacting with IFTTT Webhooks. It consists of a minimal file structure designed for simplicity and ease of use:

#### Root Directory
- `index.js`: The main module file containing the core webhook calling functionality
- `package.json`: Defines project metadata, dependencies, and npm scripts
- `README.md`: Project documentation and usage instructions

#### Key Files
- `index.js`: Exports a function to make calls to IFTTT Webhooks, handling payload transformation and request processing
- `package.json`: Provides project configuration, including:
  - Project name and version
  - Dependency information
  - Repository and homepage links
  - Licensing details

## Additional Notes

### IFTTT Webhook Compatibility

This module is designed to interact with IFTTT (If This Then That) Webhooks service. When making API calls, keep the following considerations in mind:

#### Payload Transformation
- The module automatically transforms input data into IFTTT-compatible format
- Input data is converted to sequential keys: `value1`, `value2`, `value3`, etc.
- Maximum of 3 data values are supported per webhook trigger

#### Error Handling
- The module returns an object with `success` and `result` properties
- Successful calls return `{ success: true, result: responseData }`
- Failed calls return `{ success: false, result: errorReason }`

#### Security Considerations
- Always keep your IFTTT Webhook API key confidential
- Use environment variables or secure configuration management for storing sensitive credentials

### Limitations
- Requires an active IFTTT account
- Depends on the `request-promise` library for HTTP requests
- No built-in retry or advanced error recovery mechanisms

### Performance Notes
- Network performance depends on IFTTT's webhook endpoint response times
- Recommended for occasional, non-critical background tasks
- Not suitable for high-frequency or time-sensitive integrations

## Contributing

We welcome contributions to the IFTTT Webhook Resolver project! To help maintain code quality and consistency, please follow these guidelines:

### Contribution Process

1. Fork the repository
2. Create a new branch for your feature or bugfix
3. Make your changes
4. Ensure all existing functionality remains intact
5. Submit a pull request with a clear description of your changes

### Code Guidelines

- Follow standard JavaScript coding conventions
- Write clear, concise, and meaningful commit messages
- Maintain consistent code formatting
- Include comments for complex logic

### Reporting Issues

- Use the GitHub Issues section to report bugs or suggest improvements
- Provide detailed information about the issue, including:
  - Steps to reproduce
  - Expected behavior
  - Actual behavior
  - Environment details (Node.js version, etc.)

### Development Setup

- Ensure you have Node.js installed
- Install dependencies using `npm install`
- The project currently lacks a comprehensive test suite, so manual testing is crucial

### Pull Request Requirements

- All code changes must be compatible with the existing functionality of IFTTT webhook calls
- Include comments explaining significant changes
- If adding new features, update the README.md documentation accordingly

### Notes

- The project currently has minimal test coverage
- Contributions that improve testing and documentation are especially welcome

## License

This project is licensed under the ISC License. 

For the full license text, please refer to the license details in the `package.json` file. The ISC License is a permissive free software license written by the Internet Software Consortium (ISC).

Key characteristics of the ISC License include:
- Allows commercial and non-commercial use
- Permits modification and distribution
- Requires preservation of copyright and license notices
- Provides the software "as is" with no warranties

### License Details
- **Type**: ISC License
- **Identified In**: `package.json`
- **Repository**: [GitHub Repository](https://github.com/alexander-morris/IFTTT-Webhook-Resolver)

For the most up-to-date and complete license information, please check the project's repository.