# GitAction-CI-CD-workflow
This GitHub Actions workflow automates the continuous deployment process for a web application hosted on AWS Lightsail. Triggered on pushes to the master branch, it deploys the client-side and server-side components, manages dependencies, and ensures synchronization with GitHub.
# Continuous Deployment Repository

This repository contains the GitHub Actions workflow for continuous deployment of a web application hosted on AWS Lightsail. The workflow is triggered on pushes to the master branch, automating the deployment process and ensuring synchronization with GitHub.

## Workflow Overview

### Workflow Steps

1. **Checkout Repository:**
   - Clones the repository to the GitHub Actions runner.

2. **Set up Node.js:**
   - Configures the Node.js environment for the build.

3. **Install Dependencies on client locally:**
   - Installs client-side dependencies using npm.

4. **Build:**
   - Builds the client-side application.

5. **Set up SSH for host key verification:**
   - Sets up SSH authentication for secure connections.

6. **Deploy to Lightsail:**
   - Copies the client-side and server-side builds to the specified Lightsail server.

7. **Install Dependencies on server side in Lightsail:**
   - Installs server-side dependencies on the Lightsail server and restarts Apache.

8. **Download "uploads" folder:**
   - Retrieves the "uploads" folder from the Lightsail server.

9. **Configure Git:**
   - Sets Git configurations for user email and name.

10. **Set up SSH for GitHub:**
    - Configures SSH authentication for GitHub.

11. **Push changes to GitHub:**
    - Commits and pushes changes, specifically the downloaded "uploads" folder, to a designated branch on GitHub.

### Environment Variables

- `SSH_PRIVATE_KEY`: SSH private key for Lightsail server authentication.
- `SSH_PRIVATE_KEY_GIT_ACTION`: SSH private key for GitHub authentication.
- Other environment variables for email, username, GitHub repository, and Lightsail server IP address.

### Usage

1. Ensure that the necessary secrets (SSH private keys, etc.) are set in the GitHub repository settings.
2. Customize the workflow variables (email, username, GitHub repository, IP address, etc.) as per your project requirements.

### Important Note

- Replace placeholders such as `EMAIL_ADDRESS`, `USERNAME`, `GIT_REPOSITORY`, and `IP_ADDRESS` in the workflow with your actual values.

## License

This project is licensed under the [MIT License](LICENSE).


Feel free to clone and adapt this repository to suit your own continuous deployment needs. If you have any questions or suggestions, please open an issue or submit a pull request. Happy coding!
