# Development Guide

## Step 1: Fork the Repository

First, create a fork of the [Django Daisy repository](https://github.com/hypy13/django-daisy.git) on GitHub.

## Step 2: Install Using Git

To install your forked version of Django Daisy, run the following command:

```bash
pip install -e git+https://github.com/$USERNAME/django-daisy.git#egg=django-daisy
```

Make sure to replace `$USERNAME` with your GitHub username.

## Step 3: Navigate to the Source Directory

Navigate to the directory where the package is installed:

```bash
cd $VIRTUAL_ENV/src/django-daisy
```

## Step 4: Install NPM Modules

In the project’s root directory, install the required NPM modules:

```bash
npm i
```

## Step 5: Start Tailwind Watch

Run the following command to start watching for Tailwind CSS changes:

```bash
npm run watch
```

This will activate Tailwind to watch for changes and automatically update styles.

## Step 6: Customizing Styles

For custom styles, you can override the default CSS by editing:

```bash
static/admin/css/styles.css
```

You can make your changes here for further UI customizations.

## Step 7: Push Your Changes

After making your changes, push your updates to your forked repository.

```bash
git push origin main
```

## Step 8: Create a Pull Request

Once your changes are pushed, create a pull request from your forked repository to the main project. I will review the pull request.

Thank you for contributing!
