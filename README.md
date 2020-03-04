


# baelx's starter-snake-python

A simple [Battlesnake](http://play.battlesnake.com) written in Python.

This AI client uses the [bottle web framework](http://bottlepy.org/docs/dev/index.html) to serve requests and the [gunicorn web server](http://gunicorn.org/) for running bottle on Heroku. Dependencies are listed in [requirements.txt](requirements.txt).

This fork uses the bottle.run flag reloader=True for "live-reloading" development support. 

## Prerequisites

- A working [Python 3.7](https://www.python.org/downloads/) development environment
  - [MacOS](http://hackercodex.com/guide/python-development-environment-on-mac-osx/)
  - [Windows](https://docs.battlesnake.com/tutorials/python)
- [pip](https://pip.pypa.io/en/latest/installing.html) to install Python dependencies

## Running the Snake Locally

1. Git clone or fork(this project itself forked from the original starter-snake-python project)

2. Install dependencies using [pip](https://pip.pypa.io/en/latest/installing.html):

    ```shell
    pip install -r requirements.txt
    ```
3. Install pyngrok tunnel service:

    ```shell
    pip install pyngrok
    ```
    This will make the ngrok shell command available which we'll run below.

4. Run local bottle server:

    ```shell
    python app/server.py
    ```
    This should spin up a simple web server and API(defined in server.py). It will reload when changes to that file are made for easy development.

5. Test your snake by opening your snake server in your browser. This will very likely be at localhost:8080 unless that port is already open.

6. *(Optional)* If you wish to be able to add this local dev version of your snake to the BS servers for testing, get an ngrok tunnel going:

    ```shell
    ngrok http 8080
    ```

    This will need to be run in a separate tab. It'll output the public url of the tunnel and some nice, simple logging.

## Deploying to Heroku

1. Create a new Heroku app:

    ```shell
    heroku create [APP_NAME]
    ```

2. Deploy code to Heroku servers:

    ```shell
    git push heroku master
    ```

3. Open Heroku app in browser:

    ```shell
    heroku open
    ```

or visit [http://APP_NAME.herokuapp.com](http://APP_NAME.herokuapp.com).

4. View server logs with the `heroku logs` command:

    ```shell
    heroku logs --tail
    ```

## Questions?

Email [hello@battlesnake.com](mailto:hello@battlesnake.com), or tweet [@battlesnakeio](http://twitter.com/battlesnakeio).
