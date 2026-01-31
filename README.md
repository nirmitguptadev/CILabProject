This **README.md** is the first thing your evaluator will see. It needs to be professional, clean, and provide a clear "map" of your project.

CILabProject: Automated CI/CD Pipeline with Jenkins
===================================================

Project Overview
----------------

This project demonstrates a complete **Continuous Integration** environment using Jenkins, Maven, and Git. It automates the lifecycle of a Java-based Calculator application, including compilation, unit testing, and artifact archiving.

Repository Structure
--------------------

Plaintext

Plain textANTLR4BashCC#CSSCoffeeScriptCMakeDartDjangoDockerEJSErlangGitGoGraphQLGroovyHTMLJavaJavaScriptJSONJSXKotlinLaTeXLessLuaMakefileMarkdownMATLABMarkupObjective-CPerlPHPPowerShell.propertiesProtocol BuffersPythonRRubySass (Sass)Sass (Scss)SchemeSQLShellSwiftSVGTSXTypeScriptWebAssemblyYAMLXML`   CILabProject/  ├── src/main/java/com/muj/ci/Calculator.java    # Application Logic  ├── src/test/java/com/muj/ci/CalculatorTest.java # JUnit Test Suite  ├── pom.xml                                     # Maven Configuration  ├── Jenkinsfile                                 # Multibranch Pipeline Definition  ├── docker/                                     # Deployment Artifacts  │   └── Dockerfile  ├── scripts/                                    # Automation Scripts  │   ├── build.bat                               # Windows Build Script  │   └── deploy.sh                               # Linux Deployment Script  └── README.md                                   # Documentation   `

Technical Setup
---------------

*   **Jenkins Version:** LTS
    
*   **JDK:** 17
    
*   **Build Tool:** Apache Maven 3.9.12
    
*   **Platform:** Windows 11 (Local Installation)
    

Jenkins Configuration Details
-----------------------------

### 1\. Tools & Paths

To ensure compatibility with the Windows environment, absolute paths were utilized in the Global Tool Configuration:

*   **Maven Home:** D:\\maven\\apache-maven-3.9.12
    
*   **Python Home:** D:\\Python\\python.exe
    

### 2\. CI/CD Jobs

*   **Freestyle Project:** Configured to poll SCM every 5 minutes. It executes scripts\\build.bat, which triggers the Maven lifecycle.
    
*   **Multibranch Pipeline:** Utilizes the Jenkinsfile to handle branch-specific logic:
    
    *   **Main Branch:** Full Build, Test, and "Deployment" simulation.
        
    *   **Release Branches:** Includes a placeholder for Security Scanning.
        
    *   **Feature Branches:** Restricted to Unit Testing to ensure fast feedback.
        

How to Run
----------

1.  **Clone the Repository:**git clone https://github.com/nirmitguptadev/CILabProject.git
    
2.  **Jenkins Setup:**
    
    *   Create a new **Multibranch Pipeline** job.
        
    *   Point to this repository and provide GitHub credentials.
        
3.  **Triggering Builds:**
    
    *   Manual: Click "Build Now."
        
    *   Automated: Push any change to the main branch.
        

Troubleshooting
---------------

If the build fails with mvn not recognized, verify that the path in scripts/build.bat matches your local Maven installation directory.
