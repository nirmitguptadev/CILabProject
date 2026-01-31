# CILabProject: Jenkins CI/CD Implementation
**Nirmit Gupta** | **Enrollment: 23FE10CSE00802**

## 🏗 Repository Structure

CILabProject/
├── src/main/java/com/muj/ci/Calculator.java    # Source Code
├── src/test/java/com/muj/ci/CalculatorTest.java # JUnit Tests
├── pom.xml                                     # Maven Config
├── Jenkinsfile                                 # Pipeline Definition
├── docker/Dockerfile                           # Containerization
└── scripts/build.bat                           # Build Script
#🛠 Jenkins Setup
Build Tool: Apache Maven 3.9.12 (Path: D:\maven\...)

Job 1 (Freestyle): Executes scripts/build.bat on SCM poll.

Job 2 (Multibranch): Automated pipeline execution via Jenkinsfile.

#🚀 Execution
Push code to the main branch.

Jenkins triggers the Build & Test stage.

Maven executes JUnit tests and packages the .jar artifact.

Jenkins archives the build artifacts and records test results.
