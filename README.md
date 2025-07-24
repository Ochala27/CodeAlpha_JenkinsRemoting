# CodeAlpha_JenkinsRemoting

##  Project Overview
This project demonstrates how to set up a Jenkins Master-Agent configuration using JNLP (Java Network Launch Protocol) to enable remote job execution. It was completed as part of the CodeAlpha DevOps Internship to showcase hands-on experience in distributed builds and CI/CD concepts.

---

##  What is Jenkins?
**Jenkins** is an open-source automation server that enables continuous integration and continuous delivery (CI/CD) of software projects. It automates parts of the software development process, such as building, testing, and deploying code.

---

##  What is Java JDK?
The **Java Development Kit (JDK)** is a software development environment used to develop and run Java applications. Jenkins requires the JDK to run since it is a Java-based application.

---

##  Tools Used
- Jenkins (LTS)
- Java JDK 21
- Windows 11 (used for both master and agent)
- GitHub
- Command Prompt / PowerShell

---

##  Jenkins Setup Steps

### 1. Installed Java JDK 21 on Windows
- Downloaded JDK 21 from [Adoptium.net](https://adoptium.net/)
- Installed it on Windows 11
- Configured the system **PATH** variable to include the `bin` folder
- Verified Java installation using:
```bash
java -version

