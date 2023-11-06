import javax.swing.JButton;
import javax.swing.JFrame;
import javax.swing.JLabel;
import javax.swing.JPanel;
import javax.swing.JTextField;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;

public class InterfazGrafica extends JFrame {

    private JTextField textField;
    private JLabel label;
    private JButton button;

    public InterfazGrafica() {
        // Configurar la ventana principal
        setTitle("Ejemplo de Interfaz Gráfica");
        setSize(300, 200);
        setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);

        // Crear componentes
        textField = new JTextField(20);
        label = new JLabel("Texto:");
        button = new JButton("Mostrar");

        // Crear un panel y establecer el diseño
        JPanel panel = new JPanel();
        panel.add(label);
        panel.add(textField);
        panel.add(button);

        // Agregar el panel a la ventana
        add(panel);

        // Agregar un ActionListener al botón
        button.addActionListener(new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
                mostrarTexto();
            }
        });
    }

    private void mostrarTexto() {
        String texto = textField.getText();
        System.out.println("Texto ingresado: " + texto);
    }

    public static void main(String[] args) {
        // Crear y mostrar la interfaz gráfica
        InterfazGrafica ventana = new InterfazGrafica();
        ventana.setVisible(true);
    }
}
