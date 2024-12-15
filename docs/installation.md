# Installation Guide

This section will guide you through installing Django Daisy into your existing Django project.

## Compatibility
Tested on latest django version 5.1.1
<br>
Django Daisy is compatible with Django versions 3.4 and above, and has been successfully tested on Django 5.1.1. This ensures compatibility across a wide range of Django versions, including the latest releases.

## Step 1: Install Django Daisy

You can install the Django Daisy package directly via `pip`:

```bash
pip install django-daisy
```

Or install as an editable GitHub source

```bash
pip install -e git+https://github.com/hypy13/django-daisy.git#egg=django-daisy
```

This will install the latest version of Django Daisy along with its dependencies.

## Step 2: Update `INSTALLED_APPS`

In your Django project's `settings.py` file, add `daisyui_dashboard` to your `INSTALLED_APPS` list. Be sure to comment out the default Django admin app `django.contrib.admin` to avoid conflicts:

```python
INSTALLED_APPS = [
    'daisyui_dashboard', # on top of default django admin 
    'django.contrib.admin',
    ...
]
```

This change will enable the modern DaisyUI dashboard as your primary admin interface, replacing the default Django admin panel.


## Step 3: Run Your Server

Once the setup is complete, you can start your development server:

```bash
python manage.py runserver
```

Visit `http://127.0.0.1:8000` to access your new Django Daisy dashboard!

---
Easy-peasy :)