# wkhtmltopdf Buildpack

This is a [Heroku buildpack][0] for bundling a compatible [wkhtmltopdf][1]
binary with your environment.

## Versions

* Buildpack:   `0.2`
* wkhtmltopdf: `0.12.4` by default

## Usage

This buildpack only installs wkhtmltopdf, it isn't very useful by itself. You'll
probably want to use it as part of a multi-buildpack. Here is an example using
the Ruby buildpack.

```bash
$ heroku buildpacks:set 'https://github.com/heroku/heroku-buildpack-multi.git'
$ echo 'https://github.com/heroku/heroku-buildpack-ruby.git' >> .buildpacks
$ echo 'https://github.com/dscout/wkhtmltopdf-buildpack.git' >> .buildpacks
$ git add .buildpacks
$ git commit -m 'Add multi-buildpack'
```

If you want to use a wkhtmltopdf version other than 0.12.4, set
`WKHTMLTOPDF_VERSION`:

```bash
heroku config:set WKHTMLTOPDF_VERSION="0.12.4"
```

### Clearing Repo Cache

Remember to clean your repository cache if you are updating the version of
buildpack. To do that, run:

```bash
$ heroku plugins:install https://github.com/heroku/heroku-repo.git
$ heroku repo:purge_cache -a appname
```

## Troubleshooting

If you run into issues when trying to deploy with this buildpack, make sure your
app is running on `cedar-14` or `heroku-16`. You can check this with:

```bash
$ heroku stack
```

[0]: http://devcenter.heroku.com/articles/buildpacks
[1]: http://wkhtmltopdf.org/
