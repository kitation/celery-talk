##  Calling a Task

    from my_app.tasks import make_things

    result = make_things.delay(1)

    result = make_things.apply_async(
    	args=(1,),
    	task_id="myrandomtaskid"
    )

    result = make_things.apply_async(
    	(1,),
    	link=my_callback.s()
    )