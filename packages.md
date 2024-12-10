# **Packages**

A **package** is a collection of code that can be reused across different projects. It may contain JavaScript code, configuration files, documentation, and more. For example, a package could help with styling, working with databases, or handling user authentication.

## **Dependencies**

A **dependency** is a package that your project needs in order to function properly. When you install a package using `npm install`, it becomes a dependency in your project.

After running `npm install`, npm:

- Updates **[[package.json]]** to list the new package (under **dependencies**).
- Creates or updates **[[package-lock.json]]** to lock the exact versions of **SASS** and its nested dependencies.