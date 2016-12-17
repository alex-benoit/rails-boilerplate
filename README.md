My default Rails Boilterplate for AWS Elastic Beanstalk.
Default Rails template with postgres as a db engine, no turoblinks, the sass-rails gem, and some development debugging gems.

If not done already, install the AWS Elastic Beanstalk cli:
```
sudo pip install awsebcli
```

Initialize the repository for git: 
```
git init
```

Create a repository on Github (using Hub gem or manually on Github):
```
hub create <<<MY_RAILS_APP>>>
```

Push to Github:
```
git add .
git commit -m "first commit"
git push origin master
```

Initialize the repository for eb (and select region, provide aws credentials and select app): 
```
eb init
```

Create an Elastic Beanstalk environment for the app with postgres as database engine (~6 minutes):
```
eb create <<<MY_ENVIRONMENT_NAME>>> --database.engine postgres 
```

Set the app secret for the app environment:
```
rails secret
eb setenv SECRET_KEY_BASE=<<<OUTPUT_OF_RAILS_SECRET>>>
```

Deploy to Elastic Beanstalk:
```
eb deploy
```
