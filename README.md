# TEMA_1_ACTIVIDAD_3
EJERCICIO DEL PROYECTO IMAGEN
__________________________________

CARGAR IMAGEN

//Realizar un programa en Java que al presionar un botón pueda insertar una imagen de fondo a un JLabel.
package cargarimagen;

    import javax.swing.JFrame;
    public class CargarImagen {
    public static void main(String[] args) {
       VentanaBoton btn = new VentanaBoton(); //llamar la clase boton 
       btn.setVisible(true); //hacrelo visible
       btn.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);//al cerrar la ventana el programa se termina de ejecutar
      
    }
    }


VENTANA BOTON

    package cargarimagen;
    //librerias importadas
    import java.awt.*;
    import java.awt.event.*;
    import javax.swing.*;

    public class VentanaBoton extends JFrame{
    //crear ventana de boton
    public VentanaBoton(){
    setTitle("Cargar una imagen"); //nombre de la ventana
    setSize(300,80); //tamaño de la ventana
    setLocationRelativeTo(null); //ventana este centrada
    
    LaminaBoton lamina = new LaminaBoton();//mandar a llamar la lamina
    add(lamina); //agregar la lamina
    }
    }
    //crear lamina
    class LaminaBoton extends JPanel implements ActionListener{
    //crear una variable tipo boton
    JButton btnIm = new JButton("Cargar Imagen");
    
    //crear boton
    public LaminaBoton (){
        add(btnIm); //llamar boton
        btnIm.addActionListener(this);
    }
    public void actionPerformed (ActionEvent e){
        VentanaImagen Img = new VentanaImagen();//llamar la ventana imagen y crear su variable
        Img.setVisible(true); //para que la ventana sea visible
        Img.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);//para cerrar el programa
    }
    }
---------------------------------------
VENTANA IMAGEN


    package cargarimagen;

    import java.awt.Graphics;
    import java.awt.Image;
    import java.io.File;
    import java.io.IOException;
    import javax.imageio.ImageIO;
    import javax.swing.*;

    public class VentanaImagen extends JFrame{
    public VentanaImagen(){
        setTitle("Cargar una Imagen");
        setSize(287, 287);
        setLocationRelativeTo(null);
        
        LaminaImagen LaIm = new LaminaImagen();
        add(LaIm);
    }
    }

    class LaminaImagen extends JPanel{
    
    public void paintComponent (Graphics g) {
    super.paintComponent(g);
    //crear una variable tipo imagen
                            //direccion de imagen
    File LaImagen = new File("src/cargarimagen/kd7.png");
    try{
    imagen = ImageIO.read(LaImagen);//leer la imagen
    }catch(IOException e){ //crear exepcion 
            System.out.println("La imagen no ha sido encontrada"); //imprimir el error o exepcion
    }
    
    g.drawImage(imagen, 5, 5, null); //dibujar la imagen
    }
     private Image imagen; // crear una variable tipo imagen
    }
