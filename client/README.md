ympd
========

> FIXME

Development
-----------

### Depedencies

For a full blown development environment, you need
[Leinigen](http://leiningen.org/), [NPM](http://npmjs.com/), and
[watchdog](https://pypi.python.org/pypi/watchdog).  If you are going
to run a development environment, you may want to do this first time
you checkout too:

```
make prepare
```

### Compile

```
make
```

### Serving

**TL;DR** run this and go to:
[localhost:8746/debug/](http://localhost:8746/debug/)

```
make dev
```

#### Long version

```
make figwheel
```

Now you have a server on
[http://localhost:3449](http://localhost:3449) that autoupdates
whenever you touch a file.  When touching the Sass files, one should
do as well:

```
make watch-sass
```

Alternatively, it is possible to `npm install` and then run a local
server with:

```
make serve
```

This creates a server in [localhost:8746](http://localhost:8746) that
also serves the release version of the application.  The debug version
is available on [localhost:8746/debug/](http://localhost:8746/debug/)

### Deployment

```
make upload
```

License
-------

![license](http://www.gnu.org/graphics/agplv3-155x51.png)

> Copyright (c)  FIXME
>
> This file is part of ympd.
>
> ympd is free software: you can redistribute it and/or modify
> it under the terms of the GNU Affero General Public License as
> published by the Free Software Foundation, either version 3 of the
> License, or (at your option) any later version.
>
> ympd is distributed in the hope that it will be useful, but
> WITHOUT ANY WARRANTY; without even the implied warranty of
> MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the GNU
> Affero General Public License for more details.
>
> You should have received a copy of the GNU Affero General Public
> License along with Mittagessen.  If not, see
> <http://www.gnu.org/licenses/>.
