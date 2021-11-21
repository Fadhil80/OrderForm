# OrderForm
package replit;


import javafx.application.Application;
import javafx.geometry.HPos;
import javafx.geometry.Insets;
import javafx.stage.Stage;
import javafx.scene.Scene;
import javafx.scene.control.Label;
import javafx.scene.control.TextField;
import javafx.scene.control.Button;
import javafx.geometry.Pos;
import javafx.scene.text.Text;
import javafx.scene.layout.GridPane;
import javafx.scene.paint.Color;

public class Main extends Application {

    @Override
    public void start(Stage primaryStage) {
        Text orderForm = new Text(" Pizza Order");
        orderForm.setFont(javafx.scene.text.Font.font("Arial", javafx.scene.text.FontWeight.BOLD, 20));
        Label user_id = new Label("Name:");
        Label password = new Label("ID:");
        Label price = new Label("Price:");
        TextField tf1 = new TextField();
        TextField tf2 = new TextField();
        TextField tf3 = new TextField();
        Button b = new Button("Print Order");
        b.setAlignment(Pos.CENTER);
        GridPane root = new GridPane();
        root.addRow(0, orderForm);
        root.addRow(1, user_id);
        root.addRow(2, tf1);
        root.addRow(3, password);
        root.addRow(4, tf2);
        root.addRow(5, price);
        root.addRow(6, tf3);
        //adding b to column 0, row 7, occupying width of 2 columns and height
        //of 1 row
        root.add(b, 0, 7, 2, 1);
        //center aligning button
        GridPane.setHalignment(b, HPos.CENTER);

        //adding action listener for the button
        b.setOnAction(e -> {
            //disabling the button once clicked.
            b.setDisable(true);
        });

        //adding some padding space around the gridpane to make it more visually
        //appealing. ignore this if not needed
        root.setPadding(new Insets(20));

        Scene scene = new Scene(root, Color.GRAY);
        primaryStage.setScene(scene);
        primaryStage.setTitle(" Online Order Form");
        primaryStage.show();

    }

    public static void main(String[] args) {
        launch(args);
    }
}

