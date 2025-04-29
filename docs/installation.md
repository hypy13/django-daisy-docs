# Installation Guide

This section will guide you through installing Django Daisy into your existing Django project.

## Compatibility
Tested on latest django version 5.1.1
<br>
Django Daisy is compatible with Django versions 3.4 and above, and has been successfully tested on Django 5.1.1. This ensures compatibility across a wide range of Django versions, including the latest releases.

## Step 1: Install Django Daisy

You can install the Django Daisy package directly via `pip`:

```bash
pip install -U django-daisy
```

This will install the latest version of Django Daisy along with its dependencies.

## Step 2: Update `INSTALLED_APPS`

After installation, add `django_daisy` and `django.contrib.humanize` to your `INSTALLED_APPS` in the Django settings file.  

```python
INSTALLED_APPS = [
    'django_daisy',
    'django.contrib.admin',
    'django.contrib.humanize',  # Required for django-daisy
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
