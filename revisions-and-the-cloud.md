# Reflecting and Discussing 

## Class 3 - Revisions and the Cloud

GitHub is a popular platform for hosting and collaborating on software projects. One key aspect of GitHub is its support for version control, (DVCS) which allows developers to keep track of changes and revisions to their codebase and collaborate with others on the same project through the cloud.

One common workflow for using GitHub is to create a remote repository on the platform and push your local code changes to the remote repository. This allows you to access your code from anywhere and collaborate with other developers on the same project.

For example, let's say you have a project on your local computer that you want to upload to GitHub. First, you would create a new repository on GitHub and then use the `git` command-line tool to push your local code to the remote repository. This would look something like this:

```
# initialize a local git repository
~ git init

# add all files in the current directory to the repository
~ git add .

# commit the changes to the local repository
~ git commit -m "Initial commit"

# add the remote repository on GitHub as a remote for your local repository
~ git remote add origin https://github.com/username/repository-name.git

# push the code and changes from your local repository to the remote repository on GitHub
~ git push origin master

```

This is just one way to use GitHub for version control and collaboration. There are many other features and tools on the platform that can help streamline your workflow and make it easier to work with others on your project.


>Resources:
>
>[Git Tutorial: A Comprehensive Guide](https://blog.udemy.com/git-tutorial-a-comprehensive-guide/#7)

## Things I want to know more about:
* A better understanding of git stashes
* More understanding on troubleshooting git issues