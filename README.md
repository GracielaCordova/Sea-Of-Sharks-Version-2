# Sea-Of-Sharks-Version-2
Codigo Sea of Sharks
package application;
	
import javafx.application.Application;
import javafx.event.EventHandler;
import javafx.stage.Stage;
import javafx.scene.Group;
import javafx.scene.Scene;
import javafx.scene.control.Button;
import javafx.scene.image.Image;
import javafx.scene.image.ImageView;
import javafx.scene.text.Font;
import javafx.scene.text.FontPosture;
import javafx.scene.text.FontWeight;

public class Main extends Application {
	@Override
	public void start(Stage Stage) {
		Group root = new Group();
		Scene scene = new Scene(root,1460,775);

		Image fondo = new Image("PortadaInicio.jpg");
	    ImageView fndo= new ImageView();
		fndo.setImage(fondo);
		fndo.setFitWidth(1390);
		fndo.setFitHeight(730);

		Button botonStart = new Button("START");
		botonStart.setFont(Font.font("verdana",FontWeight.NORMAL, FontPosture.REGULAR,50));
		
		botonStart.setLayoutX(550);
		botonStart.setLayoutY(600);
		botonStart.setOnMouseClicked(new EventHandler<javafx.scene.input.MouseEvent>()
		{
			public void handle(javafx.scene.input.MouseEvent l)
			{
				EscenarioNivel1 escenario = new EscenarioNivel1();
				escenario.CrearEscenario(Stage);
			}
		}
		);
		root.getChildren().addAll(fndo,botonStart);
		Stage.setScene(scene);
		Stage.show();
	}
	public static void main(String[] args) {
		launch(args);
	}
}

package application;

public class Barco {
double PBX,PBY,PGX,PGY;
	

	public Barco()
	{
	
	}
	public double PosicionBarcoX()
	{
		PBX=10;
		return PBX;
	}
	
	public double PosicionBarcoY ()
	{
		PBY =84;
		return PBY;
	}
	public double PosicionGaviotaX()
	{
		PGX =600;
		return PGX;
	}
	
	public double PosicionGaviotaY()
	{
		PGY =10;
		return PGY;
	}
}

package application;

import javafx.event.EventHandler;
import javafx.scene.Scene;
import javafx.scene.control.Button;
import javafx.scene.image.Image;
import javafx.scene.image.ImageView;
import javafx.scene.layout.Pane;
import javafx.scene.text.Font;
import javafx.scene.text.FontPosture;
import javafx.scene.text.FontWeight;
import javafx.stage.Stage;

public class EscenarioNivel1 {
	Barco P = new Barco();
	double PBX = P.PosicionBarcoX();
	double PBY = P.PosicionBarcoY();
	double PGX = P.PosicionGaviotaX();
	double PGY = P.PosicionGaviotaY();
	TiburonesNivel1 T=new TiburonesNivel1();
	ImageView shrk = T.Tiburon();
	ImageView shrk1 = T.Tiburon1();
	ImageView shrk2 = T.Tiburon2();
	ImageView shrk3 = T.Tiburon3();
	ImageView shrk4 = T.Tiburon4();
	ImageView shrk5 = T.Tiburon5();
	ImageView shrk6 = T.Tiburon6();
	ImageView shrk7 = T.Tiburon7();
	ImageView shrk8 = T.Tiburon8();
	ImageView shrk9 = T.Tiburon9();
	ImageView shrk10 = T.Tiburon10();
	ImageView shrk11 = T.Tiburon11();
	ImageView shrk12 = T.Tiburon12();
	ImageView shrk13 = T.Tiburon13();
	ImageView shrk14 = T.Tiburon14();
	ImageView shrk15 = T.Tiburon15();
	ImageView shrk16 = T.Tiburon16();
	ImageView shrk17 = T.Tiburon17();
	ImageView shrk18 = T.Tiburon18();
	ImageView shrk19 = T.Tiburon19();
	ImageView shrk20 = T.Tiburon20();
	
	Pane root = new Pane();

	public void CrearEscenario(Stage stage2)
	{
		Pane root = new Pane();
		Scene scene = new Scene(root,1390,7300);
		
		Image fondo = new Image("Mar.gif");
	    ImageView fndo= new ImageView();
	    fndo.setImage(fondo);
	    fndo.setFitWidth(1390);
	    fndo.setFitHeight(900);
	    
		Image gaviota=new Image("Gaviota.gif");
		ImageView gvt=new ImageView();
		gvt.setImage(gaviota);
		gvt.setFitWidth(150);
		gvt.setFitHeight(0);
		gvt.setTranslateX(PGX);
		gvt.setTranslateY(PGY);
		
	    Image boat=new Image("Barco.gif");
		ImageView bt = new ImageView();
		bt.setImage(boat);
		bt.setFitWidth(100);
		bt.setFitHeight(140);
		bt.setTranslateX(PBX);
		bt.setTranslateY(PBY);
		
		Image island=new Image("Isla.png");
		ImageView slnd= new ImageView();
	    slnd.setImage(island);
	    slnd.setFitWidth(100);
	    slnd.setFitHeight(100);
	    slnd.setTranslateX(1300);
	    slnd.setTranslateY(100);
		
		 scene.setOnKeyPressed(event -> {
	            switch (event.getCode()) {
	                case UP:
	                	if(bt.getTranslateY()>=155) {
	                    	bt.setTranslateY(bt.getTranslateY() - 100);
	                    	System.out.println("Arriba");
	                    }   
	                	break;
	                	
	                case DOWN:
	                	if(bt.getTranslateY()<=580) {
	                		bt.setTranslateY(bt.getTranslateY() + 100);
	                		System.out.println("Abajo");
	                	}
	                	break;
	                	
	                case LEFT:
	                	if(bt.getTranslateX()>=10) {
	                		bt.setTranslateX(bt.getTranslateX() - 10);
	                		System.out.println("Izquierda");
	                	}
	                		break;
	                    
	                case RIGHT:
	                	if(bt.getTranslateX()<=1255) {
	                		bt.setTranslateX(bt.getTranslateX() + 10);
	                		System.out.println("Derecha");
	                	}
	                    break;
	                    
	                default:
	                    break;
	            	}
	        });
		Button botonSalir = new Button("SALIR");
		botonSalir.setFont(Font.font("verdana",FontWeight.NORMAL, FontPosture.REGULAR,20));
		botonSalir.setLayoutX(1250);
		botonSalir.setLayoutY(20);
		botonSalir.setOnMouseClicked(new EventHandler<javafx.scene.input.MouseEvent>()
		{
			public void handle(javafx.scene.input.MouseEvent l)
			{
			System.exit(0);
			}
		}
	);
	    root.getChildren().addAll(fndo,slnd,shrk,shrk1,shrk2,shrk3,shrk4,shrk5,shrk6,shrk7,shrk9,shrk10,shrk11,shrk12,shrk13,shrk14,shrk15,shrk16,shrk17,shrk18,shrk19,shrk20,gvt,bt,botonSalir);
	    stage2.setScene(scene);
		stage2.show();
	}
}

package application;

import javafx.scene.image.Image;
import javafx.scene.image.ImageView;

public class TiburonesNivel1 {
	Image shark=new Image("Tiburon.png");
public ImageView Tiburon () {
	
    ImageView shrk=new ImageView();
	shrk.setImage(shark);
	shrk.setFitWidth(150);
	shrk.setFitHeight(80);
	shrk.setTranslateX(50);
	shrk.setTranslateY(165);
	
	return shrk;
}
public ImageView Tiburon1() {
	
	ImageView shrk1=new ImageView();
	shrk1.setImage(shark);
	shrk1.setFitWidth(150);
	shrk1.setFitHeight(80);
	shrk1.setTranslateX(20);
	shrk1.setTranslateY(365);
	
	
	return shrk1;
}
public ImageView Tiburon2() {
		
		ImageView shrk2=new ImageView();
		shrk2.setImage(shark);
		shrk2.setFitWidth(150);
		shrk2.setFitHeight(80);
		shrk2.setTranslateX(50);
		shrk2.setTranslateY(365);
		
		return shrk2;
}	
public ImageView Tiburon3() {
	
	ImageView shrk3=new ImageView();
	shrk3.setImage(shark);
	shrk3.setFitWidth(150);
	shrk3.setFitHeight(80);
	shrk3.setTranslateX(50);
	shrk3.setTranslateY(465);
	
	return shrk3;
}
public ImageView Tiburon4() {
	
	ImageView shrk4=new ImageView();
	shrk4.setImage(shark);
	shrk4.setFitWidth(150);
	shrk4.setFitHeight(80);
	shrk4.setTranslateX(20);
	shrk4.setTranslateY(565);
	
	return shrk4;
}
public ImageView Tiburon5() {
	
	ImageView shrk5=new ImageView();
	shrk5.setImage(shark);
	shrk5.setFitWidth(150);
	shrk5.setFitHeight(80);
	shrk5.setTranslateX(50);
	shrk5.setTranslateY(465);
	
	return shrk5;
}
public ImageView Tiburon6() {
	
	ImageView shrk6=new ImageView();
	shrk6.setImage(shark);
	shrk6.setFitWidth(150);
	shrk6.setFitHeight(80);
	shrk6.setTranslateX(150);
	shrk6.setTranslateY(465);
	
	return shrk6;
}
public ImageView Tiburon7() {
	
	ImageView shrk7=new ImageView();
	shrk7.setImage(shark);
	shrk7.setFitWidth(150);
	shrk7.setFitHeight(80);
	shrk7.setTranslateX(250);
	shrk7.setTranslateY(265);
	
	return shrk7;
}
public ImageView Tiburon8() {
	
	ImageView shrk8=new ImageView();
	shrk8.setImage(shark);
	shrk8.setFitWidth(150);
	shrk8.setFitHeight(80);
	shrk8.setTranslateX(250);
	shrk8.setTranslateY(565);
	
	return shrk8;
}
public ImageView Tiburon9() {
	
	ImageView shrk9=new ImageView();
	shrk9.setImage(shark);
	shrk9.setFitWidth(150);
	shrk9.setFitHeight(80);
	shrk9.setTranslateX(350);
	shrk9.setTranslateY(365);
	
	return shrk9;
}
public ImageView Tiburon10() {

	ImageView shrk10=new ImageView();
	shrk10.setImage(shark);
	shrk10.setFitWidth(150);
	shrk10.setFitHeight(80);
	shrk10.setTranslateX(450);
	shrk10.setTranslateY(165);
	
	return shrk10;
}
public ImageView Tiburon11() {
	
	ImageView shrk11=new ImageView();
	shrk11.setImage(shark);
	shrk11.setFitWidth(150);
	shrk11.setFitHeight(80);
	shrk11.setTranslateX(450);
	shrk11.setTranslateY(465);
	
	return shrk11;
}
public ImageView Tiburon12() {
	
	ImageView shrk12=new ImageView();
	shrk12.setImage(shark);
	shrk12.setFitWidth(150);
	shrk12.setFitHeight(80);
	shrk12.setTranslateX(550);
	shrk12.setTranslateY(165);
	
	return shrk12;
}
public ImageView Tiburon13() {
	
	ImageView shrk13=new ImageView();
	shrk13.setImage(shark);
	shrk13.setFitWidth(150);
	shrk13.setFitHeight(80);
	shrk13.setTranslateX(550);
	shrk13.setTranslateY(265);
	
	return shrk13;
}
public ImageView Tiburon14() {
	
	ImageView shrk14=new ImageView();
	shrk14.setImage(shark);
	shrk14.setFitWidth(150);
	shrk14.setFitHeight(80);
	shrk14.setTranslateX(550);
	shrk14.setTranslateY(465);
	
	return shrk14;
}
public ImageView Tiburon15() {
	
	ImageView shrk15=new ImageView();
	shrk15.setImage(shark);
	shrk15.setFitWidth(150);
	shrk15.setFitHeight(80);
	shrk15.setTranslateX(650);
	shrk15.setTranslateY(165);
	
	return shrk15;
}
public ImageView Tiburon16() {
	
	ImageView shrk16=new ImageView();
	shrk16.setImage(shark);
	shrk16.setFitWidth(150);
	shrk16.setFitHeight(80);
	shrk16.setTranslateX(650);
	shrk16.setTranslateY(465);
	
	return shrk16;
}
public ImageView Tiburon17() {
	
	ImageView shrk17=new ImageView();
	shrk17.setImage(shark);
	shrk17.setFitWidth(150);
	shrk17.setFitHeight(80);
	shrk17.setTranslateX(750);
	shrk17.setTranslateY(365);
	
	return shrk17;
}
public ImageView Tiburon18() {
	
	ImageView shrk18=new ImageView();
	shrk18.setImage(shark);
	shrk18.setFitWidth(150);
	shrk18.setFitHeight(80);
	shrk18.setTranslateX(850);
	shrk18.setTranslateY(265);
	
	return shrk18;
}
public ImageView Tiburon19() {
	
	ImageView shrk19=new ImageView();
	shrk19.setImage(shark);
	shrk19.setFitWidth(150);
	shrk19.setFitHeight(80);
	shrk19.setTranslateX(850);
	shrk19.setTranslateY(365);
	
	return shrk19;
}
public ImageView Tiburon20() {
	
	ImageView shrk20=new ImageView();
	shrk20.setImage(shark);
	shrk20.setFitWidth(150);
	shrk20.setFitHeight(80);
	shrk20.setTranslateX(850);
	shrk20.setTranslateY(465);
	
	return shrk20;
}
}

package application;

import javafx.event.EventHandler;
import javafx.scene.Scene;
import javafx.scene.control.Button;
import javafx.scene.image.Image;
import javafx.scene.image.ImageView;
import javafx.scene.layout.Pane;
import javafx.scene.text.Font;
import javafx.scene.text.FontPosture;
import javafx.scene.text.FontWeight;
import javafx.stage.Stage;

public class EscenarioNivel2 {

	Barco B = new Barco();
	double PBX = B.PosicionBarcoX();
	double PBY = B.PosicionBarcoY();
	double PGX = B.PosicionGaviotaX();
	double PGY = B.PosicionGaviotaY();
	
	TiburonesNivel2 T=new TiburonesNivel2();
	ImageView shrk = T.Tiburon();
	ImageView shrk1 = T.Tiburon1();
	ImageView shrk2 = T.Tiburon2();
	ImageView shrk3 = T.Tiburon3();
	ImageView shrk4 = T.Tiburon4();
	ImageView shrk5 = T.Tiburon5();
	
	Pane root = new Pane();

	public void CrearEscenario(Stage stage2)
	{
		Pane root = new Pane();
		Scene scene = new Scene(root,1390,7300);
		
		Image fondo = new Image("Mar.gif");
	    ImageView fndo= new ImageView();
	    fndo.setImage(fondo);
	    fndo.setFitWidth(1390);
	    fndo.setFitHeight(900);
	    
		Image gaviota=new Image("Gaviota.gif");
		ImageView gvt=new ImageView();
		gvt.setImage(gaviota);
		gvt.setFitWidth(180);
		gvt.setFitHeight(0);
		gvt.setTranslateX(PGX);
		gvt.setTranslateY(PGY);
		
		Image island=new Image("Isla.png");
		ImageView slnd= new ImageView();
	    slnd.setImage(island);
	    slnd.setFitWidth(100);
	    slnd.setFitHeight(100);
	    slnd.setTranslateX(1300);
	    slnd.setTranslateY(100);
		
	    Image boat=new Image("Barco.gif");
		ImageView bt = new ImageView();
		bt.setImage(boat);
		bt.setFitWidth(100);
		bt.setFitHeight(140);
		bt.setTranslateX(PBX);
		bt.setTranslateY(PBY);
		
		 scene.setOnKeyPressed(event -> {
	            switch (event.getCode()) {
	                case UP:
	                	if(bt.getTranslateY()>=155) {
	                    	bt.setTranslateY(bt.getTranslateY() - 100);
	                    	System.out.println("Arriba");
	                    }   
	                	break;
	                	
	                case DOWN:
	                	if(bt.getTranslateY()<=580) {
	                		bt.setTranslateY(bt.getTranslateY() + 100);
	                		System.out.println("Abajo");
	                	}
	                	break;
	                	
	                case LEFT:
	                	if(bt.getTranslateX()>=10) {
	                		bt.setTranslateX(bt.getTranslateX() - 10);
	                		System.out.println("Izquierda");
	                	}
	                		break;
	                    
	                case RIGHT:
	                	if(bt.getTranslateX()<=1255) {
	                		bt.setTranslateX(bt.getTranslateX() + 10);
	                		System.out.println("Derecha");
	                	}
	                    break;
	                    
	                default:
	                    break;
	            	}
	        });
		Button botonSalir = new Button("SALIR");
		botonSalir.setFont(Font.font("verdana",FontWeight.NORMAL, FontPosture.REGULAR,20));
		botonSalir.setLayoutX(1250);
		botonSalir.setLayoutY(20);
		botonSalir.setOnMouseClicked(new EventHandler<javafx.scene.input.MouseEvent>()
		{
			public void handle(javafx.scene.input.MouseEvent l)
			{
			System.exit(0);
			}
		}
	);
	    root.getChildren().addAll(fndo,slnd,shrk,shrk1,shrk2,shrk3,shrk4,shrk5,gvt,bt,botonSalir);
	    stage2.setScene(scene);
		stage2.show();
	}
}
package application;

import javafx.animation.Animation; 
import javafx.animation.TranslateTransition; 
import javafx.scene.image.Image; 
import javafx.scene.image.ImageView; 
import javafx.util.Duration;

	public class TiburonesNivel2 {
	Image Shark = new Image("Barco.gif");
	public ImageView Tiburon () {
		
		ImageView Shrk = new ImageView();
		Shrk.setImage(Shark);
		Shrk.setFitWidth(130);
		Shrk.setFitHeight(100);
		Shrk.setTranslateX(1390);
		Shrk.setTranslateY(100);
		
		TranslateTransition transition = new TranslateTransition ();
		transition.setDuration(Duration.seconds(1.5));
		transition.setToX(0);
		transition.setToY(100);
		transition.setAutoReverse(true);
		transition.setCycleCount(Animation.INDEFINITE);
		transition.setNode(Shrk);
		transition.play();
		
		return Shrk;
	}
	public ImageView Tiburon1 () {
		
		ImageView Shrk = new ImageView();
		Shrk.setImage(Shark);
		Shrk.setFitWidth(130);
		Shrk.setFitHeight(100);
		Shrk.setTranslateX(1390);
		Shrk.setTranslateY(100);
		
		TranslateTransition transition = new TranslateTransition ();
		transition.setDuration(Duration.seconds(1.5));
		transition.setToX(0);
		transition.setToY(100);
		transition.setAutoReverse(true);
		transition.setCycleCount(Animation.INDEFINITE);
		transition.setNode(Shrk);
		transition.play();
		
		return Shrk;
	}
	public ImageView Tiburon2 () {
	
	ImageView Shrk2 = new ImageView();
	Shrk2.setImage(Shark);
	Shrk2.setFitWidth(130);
	Shrk2.setFitHeight(100);
	Shrk2.setTranslateX(1390);
	Shrk2.setTranslateY(400);
	
	TranslateTransition transition = new TranslateTransition ();
	transition.setDuration(Duration.seconds(1.5));
	transition.setToX(0);
	transition.setToY(400);
	transition.setAutoReverse(true);
	transition.setCycleCount(Animation.INDEFINITE);
	transition.setNode(Shrk2);
	transition.play();
	
	return Shrk2;
	}
	public ImageView Tiburon3 () {
	
	ImageView Shrk3 = new ImageView();
	Shrk3.setImage(Shark);
	Shrk3.setFitWidth(130);
	Shrk3.setFitHeight(100);
	Shrk3.setTranslateX(1390);
	Shrk3.setTranslateY(500);
	
	TranslateTransition transition = new TranslateTransition ();
	transition.setDuration(Duration.seconds(1.5));
	transition.setToX(0);
	transition.setToY(500);
	transition.setAutoReverse(true);
	transition.setCycleCount(Animation.INDEFINITE);
	transition.setNode(Shrk3);
	transition.play();
	
	return Shrk3;
	}
	public ImageView Tiburon4 () {
	
	Image Shark = new Image("Tiburon.png");
	ImageView Shrk4 = new ImageView();
	Shrk4.setImage(Shark);
	Shrk4.setFitWidth(130);
	Shrk4.setFitHeight(100);
	Shrk4.setTranslateX(1390);
	Shrk4.setTranslateY(600);
	
	TranslateTransition transition = new TranslateTransition ();
	transition.setDuration(Duration.seconds(1.5));
	transition.setToX(0);
	transition.setToY(600);
	transition.setAutoReverse(true);
	transition.setCycleCount(Animation.INDEFINITE);
	transition.setNode(Shrk4);
	transition.play();
	
	return Shrk4;
	}
	public ImageView Tiburon5 () {

	ImageView Shrk5 = new ImageView();
	Shrk5.setImage(Shark);
	Shrk5.setFitWidth(130);
	Shrk5.setFitHeight(100);
	Shrk5.setTranslateX(1390);
	Shrk5.setTranslateY(700);
	
	TranslateTransition transition = new TranslateTransition ();
	transition.setDuration(Duration.seconds(1.5));
	transition.setToX(0);
	transition.setToY(700);
	transition.setAutoReverse(true);
	transition.setCycleCount(Animation.INDEFINITE);
	transition.setNode(Shrk5);
	transition.play();
	
	return Shrk5;
	}
}




