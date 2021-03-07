# cdk-turnkey
CDK Turnkey is a collection of repos that satisfy the Turnkey Principles.

## The Turnkey Principles
1. You cannot deploy an app to multiple regions in the same account. Global resources like CloudFront need collide on CDK-determined names. If you want to switch regions, you have to delete your stack from the region where you've already deployed.
