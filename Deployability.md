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

### **Managing the Deployment Pipeline**

These tactics ensure that new changes are deployed in a controlled, efficient, and reversible manner:
#### 1. **Scaled Rollouts**

- **What it is:** Deploying a new version of the software incrementally to a subset of users, instead of all users at once.
- **Purpose:** To minimize risk by observing the impact of the deployment on a smaller group before scaling it up to the entire user base.
- **Example:** A social media app might release a new feature to 5% of its users first, monitor performance and feedback, and then roll it out to the rest of the users.

#### 2. **Rollbacks**

- **What it is:** Reverting the system to its previous state if a deployment introduces defects or fails to meet expectations.
- **Purpose:** To ensure system stability by quickly undoing problematic changes.
- **Key Consideration:** Rollbacks must be seamless, even if multiple components or data are involved in the deployment.
- **Example:** If a bug in a new shopping cart feature causes errors, the system can be rolled back to the last stable version.

#### 3. **Scripted Deployments**

- **What it is:** Using scripts to automate deployment steps instead of performing them manually.
- **Purpose:** To reduce human errors, improve consistency, and make deployments faster and more repeatable.
- **Best Practices:** Scripts should be documented, reviewed, tested, and version-controlled, just like application code.
- **Example:** A script might handle tasks like database migrations, service restarts, and environment configuration during deployment.

---
### **Managing the Deployed System**

These tactics focus on ensuring the smooth functioning of the system after deployment, even with multiple versions or dependencies:

#### 1. **Service Interaction Management**

- **What it is:** Allowing multiple versions of a service to run simultaneously and directing client requests appropriately.
- **Purpose:** To enable gradual upgrades, testing, and phased deprecation of older versions without disrupting users.
- **Example:** During an upgrade, users of version 1 of a payment gateway continue using it, while version 2 is tested with newer users.

#### 2. **Packaging Dependencies**

- **What it is:** Bundling an application with all its required libraries, frameworks, and other dependencies.
- **Purpose:** To ensure that the deployed application functions correctly regardless of the differences between environments (e.g., development, testing, production).
- **Example:** Packaging a web application with its specific version of Node.js and dependent libraries ensures that it runs consistently across environments.

#### 3. **Feature Toggles**

- **What it is:** A mechanism to enable or disable specific features at runtime without redeploying the application.
- **Purpose:** To minimize risk by deploying a feature in a disabled state, then enabling it selectively or turning it off if issues arise.
- **Example:** A new payment method is deployed but remains hidden from users until it passes internal testing. If bugs are found, the toggle can disable it immediately without requiring a rollback.

## Deployability Patterns

### Micro Service Architecture
![[Micro service architecture]]


## **Patterns for Complete Replacement of Services**

These patterns allow replacing a running service with a new version while maintaining system availability.

---

### **Patterns for Complete Replacement of Services**

These patterns allow replacing a running service with a new version while maintaining system availability.

---

### **Blue/Green Deployment**

- **What it is:**
    - A new set of instances (green) is created and populated with the updated version of the service.
    - Once all green instances are ready, the DNS or routing is switched to direct traffic to the green instances, while the old instances (blue) remain idle.
    - If the new version performs well, the old (blue) instances are eventually removed.
- **Use Case:** When rapid switching between old and new versions is required without impacting users.
    
- **Example:**
    - A banking application deploys a new feature to green instances.
    - After ensuring stability, DNS is updated to route user traffic from blue to green, **completing the upgrade without downtime.**

---

### **Rolling Upgrade**

- **What it is:**
    - Instances of the old service are replaced incrementally with the new version, one at a time.
    - This ensures that both old and new versions are available simultaneously during the upgrade process.
- **Use Case:** When minimizing resource usage and maintaining fallback options is important.
    
- **Example:**
    
    - A video streaming platform replaces instances of its recommendation engine one by one, allowing gradual adoption of the new version while monitoring its performance.

---

### **Benefits of Both Patterns**

1. **Increased Availability:**
    - Neither pattern requires taking the system offline, ensuring users experience no downtime.
2. **Controlled Rollout:**
    - Both approaches enable careful testing and monitoring of the new service version during deployment.

---

### **Trade-offs**

1. **Resource Utilization:**
    - **Blue/Green Deployment:** Requires **2N instances** (both blue and green) during the switch, doubling resource requirements temporarily.
    - **Rolling Upgrade:** Requires **N+1 instances** at peak, which is more resource-efficient.
2. **Rollback Complexity:**
    - **Blue/Green Deployment:** If issues arise, rolling back may take significant time since the old (blue) instances may already be deleted.
    - **Rolling Upgrade:** Easier rollback as older instances are still operational during the upgrade process.
3. **Client Experience:**
    - **Blue/Green Deployment:** Users only interact with one version (blue or green) at a time, avoiding mixed behavior.
    - **Rolling Upgrade:** Users might experience mixed behavior as requests can hit either old or new instances during the upgrade.

---

### **Choosing the Right Pattern**

- Use **Blue/Green Deployment** when you have sufficient resources and need rapid switching.
- Opt for **Rolling Upgrade** when you prioritize gradual changes, resource efficiency, or easier rollback mechanisms.


## Practice Problems

### Spring 23
What is Scale Rollout? When do you need this process to manage the deployment pipeline? Give some practical examples.

**Ans:**

- **What it is:** Deploying a new version of the software incrementally to a subset of users, instead of all users at once.
- **Purpose:** To minimize risk by observing the impact of the deployment on a smaller group before scaling it up to the entire user base.
- **Example:** A social media app might release a new feature to 5% of its users first, monitor performance and feedback, and then roll it out to the rest of the users.


### Spring 24
**Suppose you need to replace the slot booking service completely within the minimum budget. What deployability pattern will you choose? Why?**

Hint: [[Micro service architecture]] might be costly.
