##  Calling a Group of Tasks

    from my_app.tasks import make_things
    from celery import group

    tasks = [make_things.s(i) for i in xrange(5)]
    group_result = group(tasks).apply_async()