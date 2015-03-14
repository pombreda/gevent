## This page has been migrated to https://github.com/surfly/gevent/wiki/Projects ##

This is an (incomplete) list of projects that use Gevent.
If you like to be included, please mail to the [Google group](http://groups.google.com/group/gevent). We also maintain a [Compatibility page](https://code.google.com/p/gevent/wiki/Compatibility) that lists some popular libraries and their compatibility status with Gevent.

# Database drivers #

  * [ultramysql](https://github.com/esnme/ultramysql) A fast MySQL driver written in pure C/C++
  * [ultramemcache](https://github.com/esnme/ultramemcache) Ultra fast memcache client written in highly optimized C++ with Python bindings
  * [gevent-db](https://github.com/gordonc/gevent-db) database thread pool
  * [gevent-memcache](http://github.com/hjlarsson/gevent-memcache) A gevent adaption of Memcache from the Concurrence framework.
  * [gevent-MySQL](http://github.com/mthurlin/gevent-MySQL): Asynchronous mysql driver from Concurrence adapted to gevent.
  * [psycogreen](http://bitbucket.org/dvarrazzo/psycogreen/): An example how to use [psycopg2](https://www.develer.com/gitweb/pub?p=users/piro/psycopg2.git;a=shortlog;h=refs/heads/green) with gevent. See also [examples/psycopg2\_pool.py](https://bitbucket.org/denis/gevent/src/tip/examples/psycopg2_pool.py).


# Web servers #

  * [gunicorn](http://gunicorn.org/): HTTP/WSGI Server for UNIX designed to serve fast clients or sleepy applications.
  * [pastegevent](http://pypi.python.org/pypi/pastegevent): Run WSGI applications with PasteDeploy and gevent.


# Applications #

  * [atami](https://github.com/liris/atami) RSS/Atom feed aggregator/filter
  * [django-rpg](http://github.com/batiste/django-rpg): A simple framework to create RPG with gevent and Django.
  * [indygo](https://github.com/indygemma/indygo) pastescript template for a complete django project with pip+virtualenv, fabric, a gevent-based wsgi server and various helpers scripts.
  * [locust](http://locust.io/): An easy-to-use user load testing tool
  * [logglyproxy](http://pypi.python.org/pypi/logglyproxy/)A syslog proxy server forwarding messages to Loggly via HTTPS.
  * [mixevent](https://github.com/timbull/mixevent) A gevent and REDIS based queue for creating a MixPanel event with Python.
  * [radiator](https://github.com/coopernurse/radiator) STOMP broker in python/gevent.
  * [sec-wall](http://sec-wall.gefira.pl/) A feature packed high-performance security proxy.
  * [Shaveet](https://github.com/urielka/shaveet) is a zero-config JSONP/CORS long-polling(AKA comet) server.
  * [tproxy](https://github.com/benoitc/tproxy) is a simple TCP routing proxy (layer 7) that lets you configure the routine logic in Python.
  * [hroute](https://github.com/benoitc/hroute) simple HTTP proxy based on tproxy.
  * [uurl](https://github.com/gleicon/uurl/) URL shortener built with gevent, redis, bottle
  * [livestream](https://bitbucket.org/mhahnenberg/livestream) A simple Django app that uses gevent and long polling to add the capability of including live event streams in other Django applications.
  * [kaylee](https://github.com/sdiehl/kaylee) Distributed MapReduce with ZeroMQ
  * [miyamoto](https://github.com/progrium/miyamoto) fast, clusterable task queue inspired by Google App Engine's task queue.


# Clients and protocol implementations #

  * [close.consumer](http://pypi.python.org/pypi/close.consumer/): Gevent based Streaming API consumer
  * [geventhttpclient](https://github.com/gwik/geventhttpclient): A high performance, concurrent HTTP client library for python using gevent.
  * [geventirc](https://github.com/gwik/geventirc) A simple IRC client using gevent.
  * [gevent\_stomp](https://bitbucket.org/victorlin/gevent_stomp) Stomp library for gevent
  * [gevent-websocket](http://pypi.python.org/pypi/gevent-websocket/): Websocket implementation for gevent
  * [websocket](http://bitbucket.org/denis/websocket) fork of gevent-websocket which also includes websocket client
  * [pydoozer](https://github.com/progrium/pydoozer) A Python client for Doozerd using gevent


# Tools extending Gevent #

  * [gevent\_request\_profiler](https://github.com/tellapart/gevent_request_profiler) enables the discovery of blocking/non-yielding code in request-handling servers.
  * [gevent-playground](http://bitbucket.org/denis/gevent-playground/): Random utilities for gevent.
  * [gevent-profiler](http://github.com/srlindsay/gevent-profiler): Profiler for gevent.
  * [gevent-subprocess](https://bitbucket.org/eriks5/gevent-subprocess) A gevent based version of subprocess.Popen.
  * [gevent-tools](https://github.com/progrium/gevent-tools) gevent tools for creating services
  * [gevent-curl](https://bitbucket.org/denis/gevent-curl) Integration with pycurl.
  * [gevent-utils](http://traviscline.github.com/gevent-utils) BlockingDetector.


# Libraries #

  * [gevent-socketio](http://bitbucket.org/Jeffrey/gevent-socketio) socket.io backend
  * [mwlib](http://code.pediapress.com/): a library for parsing MediaWiki articles.
  * [pykka](https://github.com/jodal/pykka) implements the actor model for concurrent programming.
  * [Restkit](http://pypi.python.org/pypi/restkit): an HTTP resource kit for Python. It allows you to easily access to HTTP resource and build objects around it.
  * [plivo](https://github.com/plivo/plivo) Rapid Telephony Application Development Framework
  * [pyramid\_socketio](http://pypi.python.org/pypi/pyramid_socketio/) Gevent-based Socket.IO pyramid integration and helpers
  * [kiss.py](http://pypi.python.org/pypi/kiss.py) MVC web framework in Python with Gevent, Jinja2, Werkzeug


# Integration with other network libraries #

  * [gTornado](http://github.com/wil/gtornado): run Tornado on gevent's event loop.
  * [gevent-zeromq](https://github.com/traviscline/gevent-zeromq/) Wrapper of pyzmq to make it compatible with gevent.
  * [Geventreactor](http://wiki.inportb.com/wiki/Projects:Python:Geventreactor) Twisted reactor using gevent.core loop.


# Tutorials #
http://www.stephendiehl.com/?p=309
http://sontek.net/pycon-sprints-part-1-the-realtime-web-with-gevent