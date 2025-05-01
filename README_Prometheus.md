# IFTTT Webhook Resolver: Streamline IFTTT Webhook Interactions in Node.js

## Project Overview

IFTTT Webhook Resolver is a lightweight Node.js module designed to simplify interactions with IFTTT (If This Then That) webhooks. It provides a straightforward way to trigger IFTTT webhooks programmatically by transforming input data into the required format.

### Key Features
- Seamless integration with IFTTT Maker Webhooks
- Automatic data transformation for webhook payloads
- Simple, promise-based interface for triggering webhook actions
- Supports dynamic webhook trigger types and API keys

### Purpose
The module solves the challenge of programmatically sending data to IFTTT webhooks by:
- Automatically converting input data into IFTTT's expected `value1`, `value2`, etc. format
- Handling the HTTP request to IFTTT's webhook endpoint
- Providing a clean, easy-to-use method for triggering webhook events

### Benefits
- Reduces boilerplate code for IFTTT webhook interactions
- Handles payload formatting automatically
- Returns promise-based results for easy error handling and integration

## Getting Started, Installation, and Setup

### Prerequisites

- Node.js (version 10.x or higher)
- npm (Node Package Manager)

### Installation

Install the package using npm:

```bash
npm install ifttt-webhook-resolver
```

### Usage

#### Basic Example

```javascript
const IFTTTWebhook = require('ifttt-webhook-resolver');

// Parameters: webhookAction, apiKey, data array
IFTTTWebhook.call('your_webhook_name', 'your_api_key', ['data1', 'data2', 'data3']);
```

### Configuration

To use this module, you'll need:
- An IFTTT account
- An IFTTT Webhook API key
- A configured webhook in your IFTTT applets

### Important Notes

- The module transforms input data into IFTTT's expected format (value1, value2, etc.)
- Supports up to 3 data values per webhook call
- Returns a promise with success status and result

### Troubleshooting

- Ensure your IFTTT Webhook API key is correct
- Verify your webhook is properly configured in IFTTT
- Check network connectivity when making webhook calls

## API Reference

### IFTTT Webhook Functions

#### `call(webhookAction, apiKey, data)`

Sends a webhook call to IFTTT with the specified parameters.

##### Parameters
- `webhookAction` (string): The name of the IFTTT webhook trigger to invoke
- `apiKey` (string): Your IFTTT Webhooks API key
- `data` (array): An array of values to be passed to the webhook (max 3 values)

##### Returns
A Promise that resolves to an object with the following structure:
- `success` (boolean): Indicates whether the webhook call was successful
- `result` (object): The response from the IFTTT Webhooks service

##### Example Usage
```javascript
const iftttWebhook = require('ifttt-webhook-resolver');

iftttWebhook.call('my_trigger', 'YOUR_API_KEY', ['value1', 'value2', 'value3'])
  .then(response => {
    if (response.success) {
      console.log('Webhook triggered successfully');
    } else {
      console.error('Webhook failed', response.result);
    }
  });
```

##### Notes
- The function automatically maps the input data to `value1`, `value2`, etc.
- Supports up to 3 data values in the webhook payload
- Requires the `request-promise` package as a dependency

## Project Structure

The project is a compact Node.js module for interacting with IFTTT Webhooks. It consists of the following key files:

#### Root Files
- `index.js`: The main module file containing the core functionality for making IFTTT webhook calls
- `package.json`: Defines project metadata, dependencies, and npm scripts
- `README.md`: Project documentation and usage instructions

#### Key Components
- The module exports a `call` function that facilitates sending data to IFTTT webhooks
- Utilizes `request-promise` for making HTTP requests to the IFTTT Maker Webhooks endpoint
- Transforms input data into the required IFTTT webhook format (value1, value2, etc.)

#### Project Configuration
- The `package.json` specifies basic project information:
  - Name: ifttt-webhook-resolver
  - Version: 1.0.0
  - Main entry point: index.js

The project maintains a minimalist structure focused on providing a straightforward interface for triggering IFTTT webhooks.

## Technologies Used

### Language
- JavaScript (Node.js)

### Core Libraries and Dependencies
- `request-promise`: A simplified HTTP request library with Promise support

### Platforms and Services
- IFTTT Webhooks API
- Maker Webhooks platform

### Development Tools
- npm (Node Package Manager)

## Additional Notes

### IFTTT Webhook Limitations

When using this module to trigger IFTTT webhooks, be aware of the following constraints:

- The module supports up to three data values per webhook trigger
- Data values are automatically mapped to `value1`, `value2`, and `value3` in the IFTTT payload
- Ensure your IFTTT applet is configured to handle the specific webhook trigger and payload format

### Error Handling

The webhook call returns an object with two properties:
- `success`: Boolean indicating whether the webhook call was successful
- `result`: Contains either the successful response or the error details

### Security Considerations

- Keep your IFTTT Webhooks API key confidential
- Do not expose the API key in client-side code or public repositories
- Use environment variables or secure configuration management for storing sensitive credentials

### Compatibility

- Requires Node.js with `request-promise` module
- Compatible with IFTTT Webhooks service
- Works with any IFTTT applet that accepts webhook triggers

### Logging and Debugging

The module includes a console log when a webhook is triggered, which can be helpful for initial debugging and verification of webhook calls.

## Contributing

We welcome contributions to the IFTTT Webhook Resolver project! By contributing, you help improve this module for the entire community.

### How to Contribute

1. **Fork the Repository**: Start by forking the repository on GitHub.

2. **Clone Your Fork**: 
   ```
   git clone https://github.com/your-username/IFTTT-Webhook-Resolver.git
   cd IFTTT-Webhook-Resolver
   ```

3. **Create a Branch**: 
   ```
   git checkout -b feature/your-feature-name
   ```

### Contribution Guidelines

#### Code Contributions
- Ensure your code follows clear and consistent formatting
- Add or update tests to cover any new functionality
- Update documentation to reflect any changes

#### Reporting Issues
- Use the GitHub Issues section to report bugs or suggest enhancements
- Provide a clear and detailed description of the issue
- Include steps to reproduce the problem, if applicable

#### Pull Request Process
- Ensure all tests pass before submitting a pull request
- Provide a clear description of your changes in the pull request
- Link any related issues in the pull request description

### Development Setup
- Ensure you have Node.js installed
- Run `npm install` to install development dependencies
- Use `npm test` to run tests

### Note
This project is maintained by the community. All contributions are appreciated and will be reviewed carefully.

## License

This project is licensed under the ISC License. 

### License Details
The ISC License is a permissive free software license published by the Internet Systems Consortium (ISC). It is functionally equivalent to the MIT License and is typically used for open-source software.

A copy of the full license text can be found in the standard ISC License documentation. For specific details about permissions, limitations, and conditions, please refer to the complete license text.

### Permissions
- Commercial use
- Modification
- Distribution
- Private use

### Conditions
- License and copyright notice must be included

### Limitations
- No liability
- No warranty