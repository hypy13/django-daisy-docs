# Tab and Inline Admin Customization

Django Daisy allows you to easily customize inline admin layouts using **DaisyUI tabs**. For tabbed inline admins, extend the `NavTabMixin` from `django_daisy.mixins` to add tabbed navigation to your inline forms.

### Example: Adding Tabs to Inline Admins

To create a tabbed inline admin interface, use the following structure:

```python
from django.contrib import admin
from django_daisy.mixins import NavTabMixin

class ChoiceInline(admin.TabularInline, NavTabMixin):  # or use admin.StackedInline for a different layout
    model = Choice
    extra = 1

@admin.register(Poll)
class PollAdmin(admin.ModelAdmin):
    list_display = ["text", "owner", "pub_date", "active", "created_at"]
    search_fields = ["text", "owner__username"]
    list_filter = ["active", "created_at", "pub_date"]
    date_hierarchy = "pub_date"
    inlines = [ChoiceInline]
```

### Explanation:
- **NavTabMixin**: Extends the inline admin to be displayed as tabs.
- **ChoiceInline**: Defines the tabbed form for `Choice` model using `TabularInline` or `StackedInline`.
- **PollAdmin**: Registers the `Poll` model with its custom inline form.

With this setup, inline forms are neatly organized into tabs, enhancing the user experience in the admin panel.