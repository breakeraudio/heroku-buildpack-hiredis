heroku-buildpack-hiredis
========================

Installing hiredis to the slug, and passing the paths to subsequent buildpacks.
You need to use https://github.com/mojodna/heroku-buildpack-multi.git#build-env as a buildpack.

Since above buildpack doesn't pass the new envfile argument to compile as the third arg (rebase is needed), if your app depends on the config variables during the slug compile, the compile may fail.

How to use
----------

### Specify buildpack

```
heroku config:add BUILDPACK_URL=https://github.com/mojodna/heroku-buildpack-multi.git#build-env
```

### Add .buildpacks

```
cat << EOF > .buildpacks
https://github.com/keiko713/heroku-buildpack-hiredis.git
https://github.com/heroku/heroku-buildpack-ruby.git
EOF
```
