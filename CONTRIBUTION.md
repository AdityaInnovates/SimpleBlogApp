# Contribution Guide

Thank you for considering contributing to this project! Follow these guidelines to make your contribution seamless and beneficial for everyone.

## How to Contribute

### 1. Add a Blog Post

1. **Create a Unique Blog ID**:
   - Generate a unique ID for your blog post([Random ID Generator](https://www.uuidgenerator.net/)).

2. **Update `blogslist.json`**:
   - Add your blog's metadata to `blogslist.json` in the following format:
     ```json
     {
       "id": "unique_blog_id",
       "image": "path/to/image",
       "title": "Blog Title",
       "description": "Short Description"
     }
     ```

3. **Create Content in Markdown**([Markdown Editor](https://pandao.github.io/editor.md/en.html "Markdown Editor")):
   - In the `blogs` folder, create a new markdown file named after your blog ID (e.g., `unique_blog_id.md`).
   - Write the main content of your blog post within this file.

### 2. Contribute to Frontend

If you have coding experience, feel free to improve the frontend:
- Edit **HTML**, **CSS**, and **JavaScript** as needed.
- Ensure the website is responsive and user-friendly.

### 3. Suggest New Features

1. **Create an Issue**: Describe the feature, label it appropriately, and await approval before working on it.
2. **Submit a Pull Request**: Once the feature or fix is complete, submit a pull request with a clear description of your changes.

## How to Raise a Pull Request (PR)

To submit your contribution, follow these steps to raise a pull request:

1. **Fork the Repository**:
   - Click on the "Fork" button at the top of this repository to create your own copy.

2. **Clone the Forked Repository**:
   - Clone the repository to your local machine using:
     ```bash
     git clone https://github.com/your_github_username/your_repo_name.git
     ```

3. **Create a New Branch**:
   - Navigate to your cloned repository and create a new branch for your changes:
     ```bash
     git checkout -b feature-or-bugfix-description
     ```

4. **Make Your Changes**:
   - Add or edit files as per your contribution type.

5. **Commit Your Changes**:
   - Stage your changes:
     ```bash
     git add .
     ```
   - Commit with a descriptive message:
     ```bash
     git commit -m "Description of the changes made"
     ```

6. **Push the Branch**:
   - Push your branch to your forked repository:
     ```bash
     git push origin feature-or-bugfix-description
     ```

7. **Create a Pull Request**:
   - Go to the original repository on GitHub, and you should see an option to create a pull request from your forked repository.
   - Select your branch and submit a pull request with a clear description of the changes you've made. Follow the template provided in `PULL_REQUEST_TEMPLATE.md`.

8. **Review and Approval**:
   - Once submitted, your pull request will be reviewed by project maintainers. Make any necessary changes if requested.

Thank you for contributing to this project and helping make it valuable for everyone!

Happy contributing!
