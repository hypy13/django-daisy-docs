# Configuration

## Adding Icons To Your Apps

To assign a custom icon to a specific app, you can add the `icon` attribute within the app's `AppConfig` class located
in the `apps.py` file.

### Example:

```python
from django.apps import AppConfig
from django.utils.translation import gettext_lazy as _


class CustomerConfig(AppConfig):
    name = 'apps.customer'
    verbose_name = _('Customers')
    icon = 'fa fa-users-viewfinder'  # Add your icon class here

```

Django Daisy uses **FontAwesome v5 Free icons** for dashboard customization. You can browse and choose from the
available free icons on the [FontAwesome website](https://fontawesome.com/icons).

Refer to the FontAwesome site for the complete list of available icons.

## Adding Icons To Third-party Apps 

Django Daisy offers flexible customization options for installed apps, allowing you to modify their appearance, order,
and behavior in the sidebar without needing direct access to their code. You can achieve this by using
the `APPS_REORDER` setting in your `settings.py` file.

### Example:

```python
APPS_REORDER = {
    # django auth app
    'auth': {
        'app': 'users',
        'icon': 'icon-shield-check',
        'name': _('Authentication'),
        'hide': False,
    },
    
    # social-auth-app-django app
    'social_django': {
        'icon': 'fa-solid fa-users-gear'
    }
}
```

### Explanation:

- **`app`**: The app to modify.
- **`icon`**: Icon name to represent the app in the sidebar.
- **`name`**: Custom name for the app.
- **`hide`**: Set to `True` if you want to hide the app from the sidebar.

With this configuration, you can customize apps without altering their code, ensuring flexibility in the admin interface
layout.