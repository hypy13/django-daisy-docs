# Configuration

## Adding Icons To Your Apps
1. App Configuration in apps.py

You can configure app-specific settings in the apps.py file for each application within your Django project. Below is an example of how to customize the Polls app:

```py
class PollsConfig(AppConfig):
    name = 'polls'  # The name of the app
    icon = 'fa fa-square-poll-vertical'  # FontAwesome icon for the app (optional)
    divider_title = "Apps"  # Title of the section divider in the sidebar (optional)
    priority = 0  # Determines the order of the app in the sidebar (higher values appear first, optional)
    hide = False  # Set to True to hide the app from the sidebar menu (optional)
```
### Explanation:
- **name**: The name of the app.
- **icon**: An optional FontAwesome icon to display next to the app name in the sidebar.
- **divider_title**: The title for the section divider, grouping similar apps together (optional).
- **priority**: An optional setting that controls the order of apps in the sidebar; higher values appear at the top.
- **hide**: If set to `True`, the app will be hidden from the sidebar menu.


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

## 2. Global Customizations in `settings.py`

You can define various project-wide settings for customizing the Django admin interface in your `settings.py` file using the `DAISY_SETTINGS` dictionary. Below is an example configuration:

```python
DAISY_SETTINGS = {
    'SITE_TITLE': 'Django Admin',  # The title of the site 
    'SITE_HEADER': 'Administration',  # Header text displayed in the admin panel
    'INDEX_TITLE': 'Hi, welcome to your dashboard',  # The title for the index page of dashboard
    'SITE_LOGO': '/static/admin/img/daisyui-logomark.svg',  # Path to the logo image displayed in the sidebar
    'EXTRA_STYLES': [],  # List of extra stylesheets to be loaded in base.html (optional)
    'EXTRA_SCRIPTS': [],  # List of extra script URLs to be loaded in base.html (optional)
    'LOAD_FULL_STYLES': False,  # If True, loads full DaisyUI components in the admin (useful if you have custom template overrides)
    'SHOW_CHANGELIST_FILTER': False,  # If True, the filter sidebar will open by default on changelist views
    'APPS_REORDER': {
        # Custom configurations for third-party apps that can't be modified directly in their `apps.py`
        'auth': {
            'icon': 'fa-solid fa-person-military-pointing',  # FontAwesome icon for the 'auth' app
            'name': 'Authentication',  # Custom name for the 'auth' app
            'hide': False,  # Whether to hide the 'auth' app from the sidebar (set to True to hide)
            'app': 'users',  # The actual app to display in the sidebar (e.g., rename 'auth' to 'users')
            'divider_title': "Auth",  # Divider title for the 'auth' section
        },
        'social_django': {
            'icon': 'fa-solid fa-users-gear',  # Custom FontAwesome icon for the 'social_django' app
        },
    },
}
```

### Explanation:
- **SITE_TITLE**: Sets the title of your site (visible in the browser tab).
- **SITE_HEADER**: The header displayed at the top of the Django admin interface.
- **INDEX_TITLE**: The title shown on the dashboard page of the admin panel.
- **SITE_LOGO**: Specifies the path to a logo image that appears in the sidebar.
- **EXTRA_STYLES**: A list of additional CSS files to be loaded into the admin interface (useful for custom styling).
- **EXTRA_SCRIPTS**: A list of additional JavaScript files to be loaded into the admin interface.
- **LOAD_FULL_STYLES**: If set to `True`, loads the full DaisyUI library for styling, which can be useful if you have overridden the admin templates.
- **SHOW_CHANGELIST_FILTER**: Controls whether the changelist filter sidebar is shown by default.
- **APPS_REORDER**: This allows you to reorder, customize, and modify third-party apps. For example, you can change the name of the `auth` app to `users`, provide a custom icon, or hide it from the sidebar entirely.
