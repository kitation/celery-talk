##  Making a Task

### 
	#celery.py
    app = Celery("celery_test")
    app.config_from_object("django.conf:settings")
    app.autodiscover_tasks(lambda: settings.INSTALLED_APPS)

### 
	#tasks.py
    from models import Thing, SubThing
    from celery_test.celery import app

    @app.task
    def make_things(number):
        s = SubThing.objects.create(number=SubThing.objects.count() + 1)
        t = Thing(name=str(number), subthing=s)
        t.save()
        return t.id