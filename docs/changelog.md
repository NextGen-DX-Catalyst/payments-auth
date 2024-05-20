## Changelog

### Version 1.3.0

**Release Date: 2024-05-20**

- **New Features:**
  - Introduced `/transactions/get` endpoint to fetch detailed transaction histories for accounts.
  - Added support for pagination in the `/auth/get` endpoint to handle large datasets efficiently.
  - Enhanced security with the implementation of rate limiting on all endpoints.

- **Improvements:**
  - Optimized database queries to reduce latency for `/bank_transfer/event/list` and `/bank_transfer/event/sync`.
  - Improved error messages for better clarity and debugging.
  - Updated API documentation to include detailed examples and use cases for new endpoints.

- **Bug Fixes:**
  - Fixed an issue where `/auth/get` would sometimes return outdated account information.
  - Resolved a bug that caused incorrect timestamps in the `/bank_transfer/event/sync` responses.
  - Corrected a problem where API key validation was case-sensitive, leading to authentication errors.

### Version 1.2.0

**Release Date: 2024-04-15**

- **New Features:**
  - Introduced webhook support for real-time notifications on micro-deposit verification status changes.
  - Added `/accounts/update` endpoint to allow users to update their account details.

- **Improvements:**
  - Enhanced logging capabilities for better tracking and troubleshooting.
  - Improved the performance of the `/bank_transfer/event/list` endpoint by implementing query caching.
  - Refined API rate limiting algorithm to provide a more balanced load distribution.

- **Bug Fixes:**
  - Fixed an issue where certain special characters in account names caused errors in the `/auth/get` endpoint.
  - Resolved a synchronization issue in the `/bank_transfer/event/sync` endpoint that caused delays in status updates.

### Version 1.1.0

**Release Date: 2024-03-10**

- **New Features:**
  - Added multi-language support for responses, starting with Spanish and French.
  - Introduced `/accounts/delete` endpoint for soft deletion of accounts, ensuring data retention policies are met.

- **Improvements:**
  - Enhanced the security of the API key management system with additional encryption layers.
  - Updated the user interface of the API management portal for better usability and accessibility.
  - Increased the maximum allowable payload size for POST requests.

- **Bug Fixes:**
  - Fixed a bug that caused duplicate entries in the micro-deposit verification logs.
  - Resolved an issue with the `/auth/get` endpoint where the account status was incorrectly displayed as inactive.
  - Corrected API response headers to include proper caching directives.

### Version 1.0.0

**Release Date: 2024-01-25**

- **Initial Release:**
  - Implemented core endpoints for fetching account information and handling micro-deposit verification updates.
    - **GET /auth/get:** Retrieve account information.
    - **GET /bank_transfer/event/list:** Search for micro-deposit verification updates.
    - **GET /bank_transfer/event/sync:** Get updates on micro-deposit verification statuses.
  - Set up basic server infrastructure using Express.js.
  - Introduced API key-based authentication for secure access.

### Version 0.9.0 (Beta)

**Release Date: 2023-12-01**

- **Beta Features:**
  - Initial beta release with foundational features and endpoints.
  - Implemented basic logging and error handling mechanisms.
  - Provided a sandbox environment for early testers to interact with the API.

- **Known Issues:**
  - Some endpoints may experience latency under high load.
  - API key management interface is minimal and lacks advanced features.
  - Limited support for complex query parameters in the initial beta endpoints.

### Version 0.8.0 (Alpha)

**Release Date: 2023-10-15**

- **Alpha Release:**
  - Released initial alpha version for internal testing and feedback.
  - Established core infrastructure and basic API endpoints.
  - Implemented fundamental security measures and access controls.

- **Known Issues:**
  - High potential for breaking changes in future updates.
  - Incomplete documentation and limited example use cases.
  - Basic error handling in place, but lacks detailed error reporting.

This detailed changelog provides a comprehensive history of updates, improvements, and fixes, showcasing the continuous development and enhancement of the Payments Auth Microservice. For more details on specific changes or to provide feedback, please contact our support team.