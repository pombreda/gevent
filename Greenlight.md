This is a [curious project](http://pypi.python.org/pypi/greenlight/)  but it misses the point behind gevent. (See the [discussion](http://concisionandconcinnity.blogspot.com/2010/10/released-greenlight-01-helping-write.html)).

In particular,
  * you don't need additional helpers to "chain" functions in gevent, just call them sequentially;
  * error handling already just works in gevent, no need for any decorators;
  * returning values is done with **return** keyword in gevent, no need for helper functions.

I've translated the examples from [greenlight's README](http://github.com/iancmcc/greenlight/blob/master/README.rst) into not using greenlight below.

### Spawning ###

Greenlight:

```
>>> from greenlight import greenlight
>>> from gevent.greenlet import Greenlet
>>> @greenlight
... def async_squaring(n):
...     "An extremely useful function"
...     return n**2
...
>>> g = async_squaring(10)
>>> isinstance(g, Greenlet)
True
>>> g.get()
100
```


Pure gevent:

```
>>> from gevent import spawn
... def async_squaring(n):
...     "An extremely useful function"
...     return n**2
...
>>> g = spawn(async_squaring, 10)
>>> isinstance(g, Greenlet)
True
>>> g.get()
100
```

### Chaining ###

Greenlight:

```
>>> @greenlight
... def square_thrice(n):
...     squared = yield async_squaring(n)
...     tothe4th = yield async_squaring(squared)
...     tothe8th = yield async_squaring(tothe4th)
...
>>> square_thrice(2).get()
256
```


Pure gevent:

```
>>> def square_thrice(n):
...     squared = async_squaring(n)
...     tothe4th = async_squaring(squared)
...     tothe8th = async_squaring(tothe4th)
...
>>> spawn(square_thrice, 2).get()
256
```

### Returning ###

Greenlight:

```
>>> from greenlight import green_return
>>> @greenlight
... def greater_than_100():
...     a = 2
...     while True:
...         a = yield async_squaring(a)
...         if a>100:
...             green_return(a)
...
>>> greater_than_100().get()
256
```


Pure gevent:

```
>>> from greenlight import green_return
>>> def greater_than_100():
...     a = 2
...     while True:
...         a = async_squaring(a)
...         if a>100:
...             return a
...
>>> spawn(greater_than_100).get()
256
```


### Error handling ###

Greenlight:

```
>>> @greenlight
... def something_bad():
...     raise Exception('O NOES')
...
>>> @greenlight
... def main():
...     try:
...         hundred = yield async_squaring(10)
...         yield something_bad()
...     except Exception, e:
...         print e
...         green_return(None)
...
>>> main().get()
O NOES
```


Pure gevent:

```
>>> def something_bad():
...     raise Exception('O NOES')
...
>>> def main():
...     try:
...         hundred = async_squaring(10)
...         something_bad()
...     except Exception, e:
...         print e
...         return None
...
>>> main().get()
O NOES
```


### Starting a greenlet ###

Greenlight:

```
>>> from greenlight import greenlight_nostart as greenlight
>>> @greenlight
... def squared(n):
...     return n**2
...
>>> g = squared(4)
>>> g.started
False
>>> g.start(); g.get()
16
```


Pure gevent:

```
>>> def squared(n):
...     return n**2
...
>>> g = gevent.Greenlet(squared, 4)
>>> g.started
False
>>> g.start(); g.get()
16
```