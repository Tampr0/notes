
### HEROKU


- `heroku login` - will redirect you to heroku login page
- `heroku apps` - shows deployed apps.
- `heroku create`
- `heroku deploy:jar build/libs/chat-0.0.1.jar -a suhe-chat` - To deploy using .jar file type:
- `heroku buildpacks:set heroku/jvm` - installs chosen buildpacks
- `heroku apps:info -a suhe-chat` - complete info about app
- `heroku logs --tail` - check the LOGS





java -jar build/libs/chat-0.0.1.jar
    - it builds and runs application

    java -Dserver.port=$PORT -jar build/libs/chat-0.0.1.jar
