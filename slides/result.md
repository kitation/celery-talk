##  Result!

    result.status
    >>> "PENDING"
    result.status
    >>> "SUCCESS"
    result.ready()
    >>> True

    result.get()
    >>> 1

    group_result.completed_count()
    >>> 3
    group_result.waiting()
    >>> True