
# Gradle:

Build environment
- command-line flags `--build-cache` stored in `gradle.properties`
- system properties `systemProp.http.proxyHost=somehost.org`
- gradle properties `org.gradle.caching=true` stored in `gradle.properties` and `GRADLE_USER_HOME`
 - SSH path `git@github.com:Tampr0/notes.git`


































`Load gradle changes` - a button that appears when you change `build.gradle` file
##Vaadin tasks
- `vaadinClean` - deletes all Vaadin files
- `vaadinPrepareFrontend` - triggered while running application
- `vaadinBuildFrontend`

While running application following tasks were executed:

Build deploy: successful

- compileJava
- vaadinPrepareFrontend
- processResources
- classes

Following folders appeared:
- build
- target

After ./gradlew clean they disappeared


In next step I'll try to use ./gradlew clean vaadinPrepareFrontend and 
see if files will be deleted.

- nothing happens

content of the main folder:
- `.gradle`
- `.idea`
- `frontend`
- `gradle`
- `node_modules`
- `src`
- .gitignore
- build.gradle
- gradlew
- gradlew.bat
- package.json
- settings.gradle
- package-lock.json
- webpack.config.js
- `webpack.generated.js`


##Vaadin tasks:
