# VSC-JavaFX-Setup
Visual Studio Code JavaFX Setup

## Prerequisites
- **JDK** (*If already installed then you would not have any problems*)  
  https://www.oracle.com/eg/java/technologies/downloads/

- **JavaFX**  
  https://gluonhq.com/products/javafx/  
  - Select your operating system 
  - Find the SDK type 
  - Click download
![chrome_t1HoVyrBkw](https://user-images.githubusercontent.com/39243722/226172033-4b1818e8-dfc5-4031-84dd-55442b11fa70.png)

## Getting Started
1. Open Visual Studio Code
2. Open the Palette by selecting one of the following options:  
   - `View` > `Command Palette`
   - Press `Ctrl + Shift + P`  
   - Press `F1`
![Code_nK6koKg8qW](https://user-images.githubusercontent.com/39243722/226171441-12f06003-c3fb-4c85-92c9-ed25eb69dbba.png)

3. Type `Create Java Project` and select it:<br>
(If missing make sure to install `Java Extenstion`:
https://marketplace.visualstudio.com/items?itemName=vscjava.vscode-java-pack)
![Code_evkBW929o8](https://user-images.githubusercontent.com/39243722/226171486-8099adf5-d07a-46ea-b3eb-bfd8edc32240.png)

4. Choose `No build tools`
![Code_7favwgZOdh](https://user-images.githubusercontent.com/39243722/226171607-9ef158af-d936-4a7a-a75e-dae918c51f17.png)

5. Search for or create a new path for your project
![Code_2ekfUnPjks](https://user-images.githubusercontent.com/39243722/226171684-60a30eae-5080-44c9-a5f1-0de4f23ee582.png)

6. Name your project, for example: `TestingApp`
![image](https://user-images.githubusercontent.com/39243722/226171718-5743cad9-4b0d-410b-ab6e-f96ea63caffa.png)

7. A new Visual Studio window will appear, expand the `JAVA PROJECTS` section
![image](https://user-images.githubusercontent.com/39243722/226171748-c3fceaaf-eccc-458a-bf73-6465abebdfc7.png)

---

1. Find your project app
2. Expand the `JAVA PROJECTS`
3. Click on the plus button from the `Reference Libraries`:
![image](https://user-images.githubusercontent.com/39243722/226171869-70f089d2-63f2-4b11-91b7-a0de78bb807d.png)
4. Select the lib subdirectory from the `JavaFX zip` file you downloaded > select all libs, and then hit select:
![Code_0DkdFUqDOX](https://user-images.githubusercontent.com/39243722/226172281-be298fc5-6b84-4d53-b4a7-916bcb8e0628.png)
Then your Libraries will look like this:
![image](https://user-images.githubusercontent.com/39243722/226172307-dc77b020-b4e7-4de8-bdd4-f4e1f4b86957.png)

## Creating a JavaFX Application
1. Open your `App.java` file 
2. Paste the following code:
```java
import javafx.application.Application;
import javafx.event.ActionEvent;
import javafx.event.EventHandler;
import javafx.scene.Scene;
import javafx.scene.control.Button;
import javafx.scene.layout.StackPane;
import javafx.stage.Stage;

public class App extends Application {
    @Override
    public void start(Stage primaryStage) {
        Button btn = new Button();
        btn.setText("Say 'Hello World'");
        btn.setOnAction(new EventHandler<ActionEvent>() {
            @Override
            public void handle(ActionEvent event) {
                System.out.println("Hello World!");
            }
        });
        StackPane root = new StackPane();
        root.getChildren().add(btn);

        Scene scene = new Scene(root, 300, 250);

        primaryStage.setTitle("Hello World!");
        primaryStage.setScene(scene);
        primaryStage.show();
    }

    public static void main(String[] args) {
        launch(args);
    }
}
```

# Adding JavaFX VM Arguments
- Click on `Run` and select `Add Configuration...`
![Code_YuKLqD5oik](https://user-images.githubusercontent.com/39243722/226172430-8ac4f8d6-a292-44d7-af88-9ae15089b38e.png)

- Add the following line to your launch request:
```
"vmArgs": "--module-path C:/Users/<NAME>/<FILE>/javafx-sdk-19.0.2.1/lib --add-modules=javafx.controls,javafx.fxml",
```
*Note: Replace `<NAME>/<FILE>` with the path where you installed and extracted JavaFX.
![explorer_6VRNC0ORUG](https://user-images.githubusercontent.com/39243722/226173361-2521cbae-8a85-4e10-a947-419235e1bdca.png)
![Code_6YrG30UzoG](https://user-images.githubusercontent.com/39243722/226173113-43ba63cd-a73b-4894-bbba-a24ada610398.png)

# Testing
When you have completed the preceding configuration, select the 'Run' button in the upper right area.
It should open a new window with the 'Hello World' icon, indicating that the configuration was successful:
![Code_g2yRiaDuMy](https://user-images.githubusercontent.com/39243722/226172687-500c2dcc-e423-4eb0-a23d-21e5f862e8d4.png)
