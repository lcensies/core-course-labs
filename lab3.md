# Continuous Integration Lab

In this lab assignment, you will delve into continuous integration (CI) practices by focusing on code testing, setting up Git Actions CI, and optimizing workflows. Additionally, you will have the opportunity to explore bonus tasks to enhance your CI knowledge. Follow the tasks below to complete the lab assignment.

## Task 1: Code Testing and Git Actions CI

**To achieve a grade of 6/10**, follow these steps:

1. Code Testing:
   - Begin by researching and implementing best practices for code testing.
   - Write comprehensive unit tests for your application.
   - In the `PYTHON.md` file, describe the unit tests you've created and the best practices you applied.
   - Enhance the `README.md` file by adding a "Unit Tests" section.

2. Set Up Git Actions CI:
   - Create a CI workflow using GitHub Actions to build and test your Python project. Refer to the [official GitHub Actions documentation](https://docs.github.com/en/actions/automating-builds-and-tests/building-and-testing-python) for guidance.
   - Ensure your CI workflow includes at least three essential steps: Dependencies, Linter, and Tests.
   - Integrate Docker-related steps into your CI workflow, at least two steps Login, Build & Push. You can refer to the [Docker GitHub Actions documentation](https://docs.docker.com/ci-cd/github-actions/) for assistance.
   - Update the `README.md` file to provide information about your CI workflow.

3. Create a Pull Request (PR):
   - Submit a PR to the main branch of your forked repository.
   <!-- - Encourage your teammates to review your PR and engage in the review process. -->

4. **Create a PR in your own repository**:
   - From the `lab3` branch to the `main` branch in your own repository.
   - This PR will aid in grading your assignment.

## Task 2: CI Workflow Improvements

**To earn an additional 4 points**, follow these steps:

1. Workflow Enhancements:
   - Add a workflow status badge to your repository for visibility.
      - In order to add a badge, we need to go to the [action page](https://github.com/lcensies/core-course-labs/actions/workflows/unpyclock.yml) -> `...` -> Create status badge  
   - Dive into best practices for CI workflows and apply them to optimize your existing workflow.
   - Utilize build cache to enhance workflow efficiency.
   - Create a `CI.md` file and document the best practices you've implemented.

2. Implement Snyk Vulnerability Checks:
   - Integrate Snyk into your CI workflow to identify and address vulnerabilities in your projects. You can refer to the [Python example](https://github.com/snyk/actions/tree/master/python-3.8) for guidance.
      - We need to obtain our Snyk API token [in the snyk account settings](https://app.snyk.io/account)


## Bonus Task

**To earn an additional 2.5 points:**

1. Follow the Main Task Steps:
   - Apply the same steps as in the primary CI task to set up CI workflows for an extra application. You can find useful examples in the [GitHub Actions starter workflows](https://github.com/actions/starter-workflows/tree/main/ci).

2. CI Workflow Improvements:
   1. Python App CI: Configure the CI workflow to run only when changes occur in the `app_python` folder.
   2. Extra Language App CI: Configure the CI workflow to run only when changes occur in the `app_<language>` folder.

### Guidelines

- Use proper Markdown formatting and structure for all documentation files.
- Organize files within the lab folder with suitable naming conventions.
- Create pull requests (PRs) as needed: from your fork to the main branch of this repository, and from your fork's branch to your fork's master branch.

> Note: Implement CI best practices, optimize your workflows, and explore bonus tasks to deepen your understanding of continuous integration.