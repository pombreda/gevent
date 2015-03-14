This page lists popular libraries and their compatibility status with Gevent. When applicable, it provides replacements.


| **Library** | **Status** | **Replacement** | **Comment**|
|:------------|:-----------|:----------------|:|
| mysql-python | incompatible | ultramysql (not DBAPI), OurSQL, pymysql | N/A |
| pyzmq | compatible | N/A | use pyzmq.green (not released yet) or gevent-zeromq in the interim |
| dateutil | win32: reads registry on win32 | N/A | N/A |
| requests | compatible by using [grequests](https://github.com/kennethreitz/grequests) | N/A | N/A |
| psycopg | works with  [specific setup](http://www.initd.org/psycopg/docs/advanced.html#support-to-coroutine-libraries) | N/A | see [example](https://bitbucket.org/denis/gevent/src/tip/examples/psycopg2_pool.py) |

If you want to correct some information or have a library listed here, send a mail to the [Google group](http://groups.google.com/group/gevent).