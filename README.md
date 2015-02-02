# wkhtmltopdf Buildpack

This is a [Heroku buildpack][0] for bundling a compatible [wkhtmltopdf][1]
binary with your environment.

## Versions

* Buildpack:   `0.2`
* wkhtmltopdf: `0.12.2.1`

## Usage

```bash
$ heroku config:set BUILDPACK_URL=https://github.com/ddollar/heroku-buildpack-multi.git
$ echo 'https://github.com/heroku/heroku-buildpack-ruby.git' >> .buildpacks
$ echo 'https://github.com/dscout/wkhtmltopdf-buildpack.git' >> .buildpacks
$ git add .buildpacks
$ git commit -m 'Add multi-buildpack'
```

[0]: http://devcenter.heroku.com/articles/buildpacks
[1]: http://wkhtmltopdf.org/

## Troubleshooting

If you run into issues when trying to deploy with this buildpack, make sure your app is running on Cedar with Ubuntu 14.04 (`cedar-14`). You can check this with:

```bash
$ heroku stack
```

If you are on an older stack, you can upgrade to `cedar-14` with:

```bash
$ heroku stack:set cedar-14
```
