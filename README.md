Heroku buildpack: FFmpeg with LAME
==================================

This is a [Heroku buildpack](http://devcenter.heroku.com/articles/buildpacks) for using [ffmpeg](http://www.ffmpeg.org/) compiled with LAME.

Usage
-----

To use this buildpack you'll first need to set `heroku-buildpack-multi` as your custom buildpack:

    $ heroku config:add BUILDPACK_URL=https://github.com/heroku/heroku-buildpack-multi.git

From here you will need to create a `.buildpacks` file which contains (in order) the buildpacks you wish to run when you deploy:

    $ cat .buildpacks
    https://github.com/craftsmen/heroku-buildpack-ffmpeg-lame
    https://github.com/heroku/heroku-buildpack-ruby

Deploy your app like usual:

    $ git push heroku master
    ...

You can verify ffmpeg is available by running the following command:

    $ heroku run "ffmpeg -version"
