#Deploy q2a to Heroku

##1. Create Heroku app

`$ heroku apps:create {appName} --region {region}`



##2. Add MySQL add-on

`$ heroku addons:create cleardb`

Why ClearDB ? Looks like it's the only one with a real free tier

##3. Get DB Config

```
$ heroku config | grep CLEARDB 
$ heroku config:set DB_HOST={{host}} DB_USER={{user}}, DB_PASSWORD={{db}}, DB_NAME={{dbname}}
```

##4. Create an empty composer.json file

```
$ touch composer.json
$ git add composer.json
$ git commit -m "Add composer file for heroku compatibility"
```

##5. Deploy to heroku

`$ git push heroku master`