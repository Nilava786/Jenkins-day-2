<<<<<<< HEAD
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
TASK 1: Automate Code Deployment Using CI/CD Pipeline (GitHub Actions)
Objective: Set up a CI/CD pipeline to build and deploy a web app.
Tools: GitHub, GitHub Actions, Node.js, Docker
Deliverables: GitHub repo with .yml CI/CD workflow
------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

Steps to work for this problem is as :-

1. Create a Node.js app with server.js, package.json, and other necessary files. Install express too for better experience with node js.
2. Create a Dockerfile in your project root to containerize the app.
3. Create .github/workflows/main.yml to define the CI/CD workflow.
4. Add build and deployment jobs in the main.yml:
      Checkout code
      Setup Node.js
      Install dependencies
      Run tests
      Login to DockerHub
      Build Docker image
      Push image to DockerHub
5. Create DockerHub repository to store your app image.
6. Add GitHub secrets to your repository:
      DOCKER_USERNAME
      DOCKER_PASSWORD
7. Push your code to the main branch of GitHub.
8. GitHub Actions will trigger the workflow and automatically build, test, and deploy your app to DockerHub.
# jenkins
=======
# Jenkins-day-2
Day-2 Task Of Elevate Labs Internship
>>>>>>> b9e5c13201eb91e3e15e3b79dd70ac1e9be71c8b
