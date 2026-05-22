# Student Grade Calculator

A Java Maven web application for calculating student final marks and grades according to VUT grading rules.

## Grading Rules

- Final Mark = Semester Mark × 0.4 + Exam Mark × 0.6
- Exam admission requires Semester Mark ≥ 40
- Distinction: 80–100
- Merit: 70–79
- Credit: 60–69
- Pass: 50–59
- Fail: 0–49
- Supplementary exam eligibility: 45–49
- Valid mark range: 0–100 inclusive

## Run Locally

```bash
mvn clean test
mvn clean package
```

The WAR file is created in `target/grade-calculator.war`.

## Run with Docker

```bash
mvn clean package
docker build -t student-grade-calculator .
docker run -p 8080:8080 student-grade-calculator
```

Open: `http://localhost:8080`

## CI/CD

This project includes:

- Jenkinsfile for Jenkins CI/CD
- Dockerfile for Tomcat containerisation
- GitHub Actions CI workflow
- GitHub Actions deploy workflow that triggers Render using `RENDER_DEPLOY_HOOK_URL`
