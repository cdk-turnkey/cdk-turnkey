# cdk-turnkey
CDK Turnkey is a collection of repos that satisfy the Turnkey Principles.

## The Turnkey Principles
The following are a mixture of general principles and principles that apply to specific implementations of these principles using AWS and GitHub Actions. The principles should be revised so that other implementations are possible.

1. The Turnkey Principles apply to apps hosted in AWS.
1. The domain name should not be in source control.
2. Configuration information should be read from SSM Parameter Store params at deploy time. The best example is the domain name of the app.
3. Apps deployed without a domain name in the params should be deployed behind an AWS-generated URL that is output by the stack.
4. Web apps should live behind a single domain. Requests should be routed to the frontend or backend(s) via the path.
5. You cannot deploy an app to multiple regions in the same account. Global resources like CloudFront need collide on CDK-determined names. If you want to switch regions, you have to delete your stack from the region where you've already deployed.
6. There is no local development. Develop the app by deploying it to a dev account.
7. The app should deploy on every push once AWS credentials are added to GitHub Actions Secrets.
8. The `scripts` property of `package.json` should present the public interface of the project. CI and local dev should interact with the project by calling `npm` scripts.
