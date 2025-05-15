## Contributing to High Performance Computing Laboratory - SPPU

🎉 First off, thank you for considering contributing to the HPC Lab repository! 🎉

We welcome contributions from everyone, especially fellow students and those interested in high-performance computing concepts. Your help is valuable in making this resource better for all students learning these topics.

This document provides guidelines for contributing to this project.

## How Can I Contribute?

There are several ways you can contribute:

*   **🐛 Reporting Bugs:** If you find a bug in an existing implementation, an error in the documentation, or an issue with how a practical is set up, please [open an issue](https://github.com/kunalPisolkar24/HPC_Lab/issues) on GitHub.
    *   Clearly describe the issue, including steps to reproduce it if it's a bug.
    *   Specify the practical number or file involved.
*   **✨ Suggesting Enhancements or New Examples:** If you have ideas for improving an existing practical, adding an alternative solution, or suggesting a new relevant example, please [open an issue](https://github.com/kunalPisolkar24/HPC_Lab/issues) to discuss it first.
*   **📝 Improving Documentation:** If you find parts of the READMEs (main or for individual practicals) unclear, or think they could be improved, feel free to suggest changes or submit a pull request.
*   **💻 Code Contributions (Pull Requests):** If you've fixed a bug, implemented an enhancement, or added a new piece of code related to the lab assignments, please submit a pull request!

## Making Code Contributions (Pull Requests)

If you'd like to contribute code, please follow these general steps:

1.  **Fork the Repository:**
    Click the "Fork" button at the top right of the [HPC_Lab repository page](https://github.com/kunalPisolkar24/HPC_Lab). This creates your own copy of the project under your GitHub account.

2.  **Clone Your Fork:**
    Clone your forked repository to your local machine:
    ```bash
    git clone https://github.com/YOUR_USERNAME/HPC_Lab.git
    cd HPC_Lab
    ```
    Replace `YOUR_USERNAME` with your actual GitHub username.

3.  **Create a New Branch:**
    Create a descriptive branch for your changes. This keeps your changes organized and separate from the `main` branch.
    ```bash
    # For a new feature or example
    git checkout -b feature/your-descriptive-feature-name

    # For a bug fix
    git checkout -b fix/brief-description-of-fix
    ```

4.  **Make Your Changes:**
    *   Implement your fix, feature, or improvement.
    *   Ensure your code is clear, well-commented, and follows the general style of the existing code.
    *   If you're working on a specific practical, make changes within the relevant directory (e.g., `Practical_1/`, `Mini_Project/`).
    *   **Test your changes thoroughly** to ensure they work as expected and don't break existing functionality. For HPC, this might involve checking for correct parallel execution, expected outputs, and performance considerations if applicable.

5.  **Commit Your Changes:**
    Write clear and concise commit messages. A good commit message explains *what* changed and *why*.
    ```bash
    git add .
    git commit -m "feat: Add CUDA implementation for vector addition (Practical 4)"
    # or
    git commit -m "fix: Correct race condition in parallel BFS OpenMP"
    # or
    git commit -m "docs: Clarify steps for running mini-project"
    ```
    Using conventional commit prefixes like `feat:`, `fix:`, `docs:`, `style:`, `refactor:`, `test:` is good practice but not strictly enforced here.

6.  **Push to Your Fork:**
    Push your committed changes to your forked repository on GitHub:
    ```bash
    git push origin feature/your-descriptive-feature-name
    ```

7.  **Open a Pull Request (PR):**
    *   Go to the original `kunalPisolkar24/HPC_Lab` repository on GitHub.
    *   You should see a prompt to "Compare & pull request" for your recently pushed branch. Click it.
    *   If you don't see the prompt, go to the "Pull requests" tab and click "New pull request." Choose your fork and branch to compare with the original repository's `main` branch.
    *   **Fill out the PR template:**
        *   Provide a clear and descriptive title for your PR.
        *   In the description, explain the changes you've made and why they are beneficial.
        *   If your PR addresses an open issue, link to it using `Closes #issue_number` (e.g., `Closes #12`).

## Pull Request Guidelines

To help us review your PR efficiently, please ensure:

*   **Clear Purpose:** Your PR should address a specific issue or add a well-defined feature/improvement.
*   **Descriptive Title & Description:** As mentioned above, make it easy to understand your contribution.
*   **Working Code:** Your code should compile and run without errors. For HPC assignments, ensure it behaves correctly in a parallel environment if applicable.
*   **Readability:** Write clean, well-commented code. Follow the existing style of the project where possible.
*   **Focused Changes:** Keep PRs focused. If you have multiple unrelated changes, submit them as separate PRs.

## Code Style

While there isn't a strict automated linter enforced for this lab repository, please try to:

*   Maintain a consistent coding style with the existing codebase.
*   Write clear, readable, and adequately commented code. This is especially important for understanding complex parallel algorithms.
*   Use meaningful variable and function names.

## Questions or Discussions

If you're unsure about something or want to discuss a potential contribution before starting work, please feel free to [open an issue](https://github.com/kunalPisolkar24/HPC_Lab/issues) and tag the repository maintainer (`@kunalPisolkar24`).

---

Thank you for contributing to the HPC Lab! Your efforts help create a valuable learning resource.