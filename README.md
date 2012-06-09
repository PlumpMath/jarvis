# jarvis

Jarvis enables you to easily create web aplications that use speech
recogniton.

## Running Locally

Must have redis and postgres installed (locally or somewhre that can
be hit by local processes)
Set the following environment variables

* POSTGRES_URL "jdbc:postgresql://my.host:port/database?user=username&password=mahpass&ssl=true"
* REDIS_URL    "redis://username:password@my.host:port"


## Organization

There are 3 parts to the "platform"

* jarvis-web is the web page and admin panal for the system. Consumes
the API.
* jarvis-lib is the javascript library that uses the system.
* Everything else has to do with the API, runs on heroku.

## API

Clojure app running on heroku
Bishop frontend,
rendering and matching logic runs on worker nodes
redis queue used for communication internally
postgres database used for app and user data

endpoints for

* setting up and managing apps and rules
* sending speech
* retrieving results (long polling probably for now)

## TODO
The first main steps that need to be accomplished before anything else
can be done.

* Get Sphinx4 working well in clojure.
* Capture audio from javascript and send it to the server in a form
that can be used by cmuSphinx.

Then later all the fun can come,

* Control panel for setting up apps.
* Make a heroku app that does the stt and the rule matching.
* Flesh out the javascript library.
* Profit!

## License

Copyright © 2012 FIXME

Distributed under the Eclipse Public License, the same as Clojure.
