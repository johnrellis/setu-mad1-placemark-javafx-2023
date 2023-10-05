# Tornado FX compatible Place marks

Note, this is tested using openJDK 20 and gradle 8.4.  Gradle wrapper is used in project

Code is not my own, simply configured it to run via gradle and tornadofx.

Should run via gradle application run straight out of the box.

```bash
➜  setu-mad1-placemark-javafx-2023 git:(main) ./gradlew run

> Task :compileKotlin
w: file:///Users/johnrellis/temp/setu-mad1-placemark-javafx-2023/src/main/kotlin/org/setu/placemark/console/helpers/FileHelpers.kt:25:13 Condition 'inputStreamReader != null' is always 'true'
w: file:///Users/johnrellis/temp/setu-mad1-placemark-javafx-2023/src/main/kotlin/org/setu/placemark/console/main/main.kt:5:10 Parameter 'args' is never used
w: file:///Users/johnrellis/temp/setu-mad1-placemark-javafx-2023/src/main/kotlin/org/setu/placemark/console/views/PlacemarkView.kt:39:12 Condition 'placemark != null' is always 'true'
w: file:///Users/johnrellis/temp/setu-mad1-placemark-javafx-2023/src/main/kotlin/org/setu/placemark/console/views/PlacemarkView.kt:61:13 Condition 'placemark != null' is always 'true'

> Task :run
Oct 05, 2023 5:03:01 PM tornadofx.Stylesheet$Companion detectAndInstallUrlHandler
INFO: Installing CSS url handler, since it was not picked up automatically

BUILD SUCCESSFUL in 10s
2 actionable tasks: 2 executed
```

# Intellij

To run via intelliJ, ensure the TornadoFX plugin is installed.

![](docs/plugin.png)

Download javafx 17 LTS.

```agsl
https://gluonhq.com/products/javafx/
```

Attempt to run `MainApp.kt`

This will create a run configuration that will likely fail.

![](docs/runMainApp.png)

To fix this, edit your run configuration

![](docs/editRunConfiguration.png)

In your run configuration, add to your VM options

![](docs/addVmOptions.png)

```
--module-path "/Users/johnrellis/java/javafx-sdk-17.0.8/lib" --add-modules javafx.controls,javafx.fxml
```

Replacing the path with your javafx-sdk-17.

This is all to just load javafx libs when intellij runs, running with gradle handles this for you.

We love gradle.