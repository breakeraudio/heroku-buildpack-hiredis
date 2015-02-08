heroku-buildpack-hiredis
========================

If a gem is depending on hiredis during `gem install` (such as [recommendify](https://rubygems.org/gems/recommendify)), `git push heroku master` fails since Heroku slug compiler doesn't have hiredis by default. In this case, you need to add hiredis first and setup proper PATHs before you run `bundle install`. This buildpack is in charge of doing it.

How to use
----------

### Specify buildpack

```
heroku config:add BUILDPACK_URL=https://github.com/ddollar/heroku-buildpack-multi.git
```

### Add .buildpacks

```
cat << EOF > .buildpacks
https://github.com/keiko713/heroku-buildpack-hiredis.git
https://github.com/heroku/heroku-buildpack-ruby.git
EOF
```
