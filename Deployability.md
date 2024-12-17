Deployability is a critical [[Quality Attributes]] of a software system. It refers to the ease and efficiency with which a software system can be deployed, configured, updated, and maintained in its operational environment.

Deployability has gained prominence due to the need for frequent releases in modern software development. Deployability enables:
- Faster bug fixes.
- Incremental feature release without waiting for major updates.

## Continuous Deployment and Delivery
- **Continuous Deployment:** Fully **automated** deployment process with no human intervention.
- **Continuous Delivery:** Automated processes **up to production deployment**, requiring manual intervention for final deployment.
## Deployment Environments
- **Development Environment:** Code is developed, tested, and committed to version control.
- **Integration Environment:** Builds executables and runs unit tests for all modules.
- **Staging Environment:** Tests for system qualities (e.g., performance, security).
- **Production Environment:** The live system is monitored to ensure quality.

## DevOps
![[devops]]


## Tactics for Deployability

Tactics for improving deployability includes:
- **Managing the Deployment Pipeline:**
    - **Scaled Rollouts:** Gradual deployment to a subset of users.
    - **Rollbacks:** Reverting to a previous version if issues arise.
    - **Scripted Deployments:** Automated and version-controlled deployment processes.
- **Managing the Deployed System:**
    - **Service Interaction Management:** Supporting multiple service versions simultaneously.
    - **Packaging Dependencies:** Deploying services with consistent dependencies.
    - **Feature Toggles:** Disabling problematic features dynamically.



