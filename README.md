# CodeAlpha_JenkinsRemoting

## 📘 Project Overview
This project demonstrates how to set up a Jenkins Master-Agent configuration using JNLP (Java Network Launch Protocol) to enable remote job execution. It was completed as part of the CodeAlpha DevOps Internship to showcase hands-on experience in distributed builds and CI/CD concepts.

---

## 🧠 What is Jenkins?
**Jenkins** is an open-source automation server that enables continuous integration and continuous delivery (CI/CD) of software projects. It automates parts of the software development process, such as building, testing, and deploying code.

---

## 🧠 What is Java JDK?
The **Java Development Kit (JDK)** is a software development environment used to develop and run Java applications. Jenkins requires the JDK to run since it is a Java-based application.

---

## 🔧 Tools Used
- Jenkins (LTS)
- Java JDK 21
- Windows 11 (used for both master and agent)
- GitHub
- Command Prompt / PowerShell

---

## ⚙️ Jenkins Setup Steps

### 1. Installed Java JDK 21 on Windows
- Downloaded JDK 21 from [Adoptium.net](https://adoptium.net/)
- Installed it on Windows 11
- Configured the system **PATH** variable to include the `bin` folder
- Verified Java installation using:
```bash
java -version



2. Installed Jenkins using WAR File
Downloaded jenkins.war from the Jenkins official website

Ran Jenkins using:

java -jar jenkins.war
Opened Jenkins in browser via:
http://localhost:8080

Unlocked Jenkins using the administrator password from:

C:\Program Files\Jenkins\.jenkins\secrets\initialAdminPassword
Installed the recommended plugins: Git, Pipeline, SSH

3. Created a Jenkins Agent Node
Navigated to: Manage Jenkins > Nodes > New Node

Named the node: RemoteAgent

Selected: Permanent Agent

Set:

Number of executors: 1

Remote root directory: C:\JenkinsAgent

Labels: remote

Launch method: Launch agent by connecting it to the controller (JNLP)

4. Connected the Agent via JNLP
Downloaded agent.jar from the agent page in Jenkins

Ran the following command in Command Prompt:

java --enable-native-access=ALL-UNNAMED -jar agent.jar -jnlpUrl http://localhost:8080/computer/RemoteAgent/jenkins-agent.jnlp -secret <secret-key> -workDir "C:\JenkinsAgent"
The agent successfully connected and showed Online in Jenkins

🧪 Created a Freestyle Job to Test the Agent
Created a Freestyle project named RemoteAgentTest

Enabled “Restrict where this project can be run”

Entered label: remote

Added a Windows batch command in the Build Step:

cmd
Copy
Edit
echo Running on remote agent
Built the job and verified output in the Console:

Job ran on the agent and printed: Running on remote agent
