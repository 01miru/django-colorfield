=================
django-colorfield
=================

Simple colorfield for django (optimized for grappelli)

Installation
============

Using PIP:

    pip install git+https://github.com/01miru/django-colorfield.git

Add ``colorfield`` to your ``INSTALLED_APPS``.

Then in your models, you can use it like this:

.. code-block:: python

    from django.db import models
    from colorfield.fields import ColorField

    class Show(ExtendedModel):
        title = models.CharField(u'Title', max_length=250)
        color = ColorField(default='ffffff')


And an example for the admin:

.. code-block:: python

    from django.contrib import admin
    from models import Show
    
    ShowAdmin(admin.ModelAdmin):
        list_display = ('title', 'color',)
        list_editable = ('color',)
        
    admin.site.register(Show, ShowAdmin)
