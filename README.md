# Heroku buildpack for meteor

## Usage

```
% heroku create --stack cedar-14 --buildpack https://github.com/mintdigital/heroku-buildpack-meteor.git
```

## Example

Create a sample app with 'meteor'

```
% meteor create --example wordplay
wordplay: created.

To run your new app:
   cd wordplay
   meteor
```

Put it in git.

```
% cd wordplay
% git init
Initialized empty Git repository in /tmp/a/wordplay/.git/
% git add .
% git commit -m "Sample wordplay app!"
```

Create your heroku app

```
% heroku create --stack cedar-14 --buildpack https://github.com/mintdigital/heroku-buildpack-meteor.git
```

Set up a MongoDB you can connect to
```
% heroku addons:add mongolab:sandbox
```

Configure your ROOT_URL and MONGO_URL settings
```
% heroku config:add ROOT_URL=<insert_url_created_above_here>
% heroku config:add MONGO_URL=<value_of_MONGOLAB_URI>
```

Deploy it

```
% git push heroku
```

Enjoy!
