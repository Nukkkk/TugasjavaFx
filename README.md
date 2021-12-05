# TugasjavaFx
Berikut adalah tugas mata kuliah pemrograman berorientasi objek, memgenai java fx
package JavaFX;

import javafx.application.Application;
import javafx.geometry.Insets;
import javafx.scene.Scene;
import javafx.scene.control.Button;
import javafx.scene.control.Label;
import javafx.scene.control.PasswordField;
import javafx.scene.control.TextField;
import javafx.scene.layout.StackPane;
import javafx.scene.layout.VBox;
import javafx.stage.Stage;



public class JavaFX extends Application  {
    private final StackPane root = new StackPane();
    private Stage stage;

    @Override
    public void init() {
        Button btn = new Button("OPEN");
        VBox vert= new VBox();

        vert.setSpacing(8);
        vert.setPadding(new Insets(12,12,12,12));
        vert.getChildren().addAll(
                new Label("First Name "),
                new TextField(),
                new Label("Last Name "),
                new TextField(),
                new Label("E-Mail Adress "),
                new TextField(),
                new Label("Contact No "),
                new TextField(),
                new Label("Password"),
                new PasswordField(),
                new Label("Confirm  Password"),
                new PasswordField(),
                new Button("Selesai"));
        root.getChildren().addAll(vert);

        btn.setOnAction(actionEvent-> {
            if(stage!=null){
                stage.requestFocus();
                return;
            }
            stage = new Stage();
            StackPane sp = new StackPane();
            stage.setScene(new Scene(sp, 700,700));
            stage.show();
        });
    }

    @Override
    public void start(Stage primaryStage) {
        Scene scn = new Scene(root,700,700);
        primaryStage.setScene(scn);
        primaryStage.show();
        primaryStage.setTitle("Tugas Java FX");
        primaryStage.setAlwaysOnTop(true);
    }


    public static void main(String[] args) {
        launch(args);
    }
}
