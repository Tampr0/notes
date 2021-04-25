###Deploying on Heroku
___
Add inside `build.gradle`
- `vaadin { productionMode = true; }`

Let the application build, simply by running it.

Run in terminal:
- `git init` - creates a local repo, if there was no repo already.
- `git add *` - adds files to the index
- `git commit` - commits files into local repo
- `heroku login` - logs in to Heroku account.
- `heroku create` - creates an app with a default name and automatically adds a path to heroku remote git to your `git config`
- `git push heroku master` - pushes project to heroku git

Next, Heroku starts building the project, and the Application should be running after it finished.
Because application name will start its `url`, it's a good idea to change it.
- `heroku logs --tail` - prints LOG
- `heroku apps:rename -a <old_name> <new_name>` - changes the name of an App but also the heroku's repo url.
- `git remote set-url heroku <path_to_remote_repo>` - changes heroku repo's path.

DONE.



 








