# extra_analytics

Extra Analytics is a Django app to collect extra information on where users are on your website
We will also track what OS the user is visiting, and the amount of requests they made total.


Quick start
-----------
Some optional settings are:

    ANALYTICS_BLOCKED_PATHS: 
        List of paths that should not be tracked
        Can be set to None

    ANALYTICS_BLOCKED_ROOT_PATH: 
        Single path that should not be tracked
        Can be set to None

    ANALYTICS_DISALLOW_REQUESTS_TO_FILES: 
        If True, requests to files will not be tracked
        Can be set to None
        Default is True

    ANALYTICS_REQUEST_TYPE_BLOCK_LIST: 
        List of request methods that should not be tracked
        Can be set to None
        Default is ['POST']

    BLOCK_AJAX_REQUESTS: 
        If True, AJAX requests will not be tracked
        Can be set to None
        Default is True

You can put these settings in your settings.py file.

1. Add "extra_analytics" to your INSTALLED_APPS setting like this::

    INSTALLED_APPS = [
        ...
        'extra_analytics',
    ]

    Add extra_analytics.middleware.TrackMiddleware to your Middleware.
    MIDDLEWARE = [
        ...
        'extra_analytics.middleware.TrackMiddleware',
    ]

3. Run ``python manage.py makemigrations`` and ``python manage.py migrate`` to create the needed models.

4. Start the development server and visit http://127.0.0.1:8000/admin/
   Now head to Extra Analytics, and enjoy!
