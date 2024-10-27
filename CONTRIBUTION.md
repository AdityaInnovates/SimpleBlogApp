# Contribution Guide

Thank you for considering contributing to this project! Follow these guidelines to make your contribution seamless and beneficial for everyone.

## How to Contribute

### 1. Add a Blog Post

1. **Create a Unique Blog ID**:
   - Generate a unique ID for your blog post.
   
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

3. **Create Content in Markdown**:
   - In the `blogs` folder, create a new markdown file named after your blog ID (e.g., `unique_blog_id.md`).
   - Write the main content of your blog post within this file.

### 2. Contribute to Frontend

If you have coding experience, feel free to improve the frontend:
- Edit **HTML**, **CSS**, and **JavaScript** as needed.
- Ensure the website is responsive and user-friendly.

### 3. Suggest New Features

1. **Create an Issue**: Describe the feature, label it appropriately, and await approval before working on it.
2. **Submit a Pull Request**: Once the feature or fix is complete, submit a pull request with a clear description of your changes.

### Submitting Pull Requests

- Ensure your pull request is descriptive and links to any related issues.
- Follow the template in `PULL_REQUEST_TEMPLATE.md` for consistency.

Happy contributing!
