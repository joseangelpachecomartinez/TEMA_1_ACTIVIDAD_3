# TEMA_1_ACTIVIDAD_3
EJERCICIO DEL PROYECTO IMAGEN
__________________________________

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
