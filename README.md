# EagerQuerySet
An analog to the Django QuerySet where all possible data has already been loaded

# Why

The current QuerySet collection in Django offers very helpful functions for navigating data for a collection of models. It doesn't fare well, however, when working in an asynchronous context. The general workaround is to start a thread, retrieve your data, and add the fully loaded models into a list before exiting the thread. This works well _until_ you want to use a function that would typically be on the queryset, like `first` or `distinct` or `order_by`. To get around this obstacle, the `EagerQuerySet` will operate like a sequence/iterable but provide an interface like Django's queryset, allowing uniform collection interaction within and without asynchronous contexts.
