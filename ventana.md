package calculadoras;

import java.awt.BorderLayout;
import java.awt.Component;
import java.awt.GridLayout;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;
import javax.swing.ImageIcon;
import javax.swing.JButton;
import javax.swing.JFrame;
import javax.swing.JPanel;
import javax.swing.JTextField;

/**
 *
 * @author s204e1
 */
public class ventana extends JFrame {
    
    JPanel panel_caja;
    JPanel panel_botones;
    JTextField caja;
    String Operacion;
    PilaCalculadora <String> pilacalcu = new PilaCalculadora<String>();
    String pila[];
    public ventana() {
        setTitle("Calculadora UDEM");
        setSize(350, 350);
        setResizable(false);
        setLocationRelativeTo(null);
        setIconImage(new ImageIcon(getClass().getResource("../Imagenes/calculadora2.jpg")).getImage());
        setDefaultCloseOperation(EXIT_ON_CLOSE);
        Elementos();        
        setVisible(true);
        EscuchaBotones ();
        
        
        
    }
    
    private void Elementos() {
        
        panel_caja = new JPanel();
        panel_caja.setLayout(new BorderLayout()); // contenedor para los botones dado espacio norte sur este 

        caja = new JTextField();
        panel_caja.add("North", caja);
        
        panel_botones = new JPanel();
        panel_botones.setLayout(new GridLayout(5, 4, 8, 8));
        insertarBotones();
        
        panel_caja.add("Center", panel_botones);
        getContentPane().add(panel_caja);
        //getContentPane().add(panel_botones);
        
    }
    
    JButton boton[];

    private void insertarBotones() {
        
        boton = new JButton[17];
        boton[0] = new JButton("0");
        boton[1] = new JButton("1");
        boton[2] = new JButton("2");
        boton[3] = new JButton("3");
        boton[4] = new JButton("4");
        boton[5] = new JButton("5");
        boton[6] = new JButton("6");
        boton[7] = new JButton("7");
        boton[8] = new JButton("8");
        boton[9] = new JButton("9");
        boton[10] = new JButton("+");
        boton[11] = new JButton("-");
        boton[12] = new JButton("*");
        boton[13] = new JButton("/");
        boton[14] = new JButton(".");
        boton[15] = new JButton("=");
        boton[16] = new JButton("C");
        
        for (int i = 0; i <boton.length; i++) {
            panel_botones.add(boton[i]);
        }
        
    }

    private void EscuchaBotones() {
        boton[0].addActionListener(
        new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
               caja.setText(caja.getText()+"0");
               pilacalcu.push("0");
            }
        }                
        );
        boton[1].addActionListener(
        new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
               caja.setText(caja.getText()+"1");
                pilacalcu.push("1");
                               
            }
        }                
        );
        boton[2].addActionListener(
        new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
               caja.setText(caja.getText()+"2");
                   pilacalcu.push("2");             
            }
        }                
        );
        boton[3].addActionListener(
        new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
               caja.setText(caja.getText()+"3");
                   pilacalcu.push("3");             
            }
        }                
        );
        boton[4].addActionListener(
        new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
               caja.setText(caja.getText()+"4");
                   pilacalcu.push("4");             
            }
        }                
        );
        boton[5].addActionListener(
        new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
               caja.setText(caja.getText()+"5");
                    pilacalcu.push("5");            
            }
        }                
        );
        boton[6].addActionListener(
        new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
               caja.setText(caja.getText()+"6");
                   pilacalcu.push("6");             
            }
        }                
        );
        boton[7].addActionListener(
        new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
               caja.setText(caja.getText()+"7");
                pilacalcu.push("7");
                               
            }
        }                
        );
        boton[8].addActionListener(
        new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
               caja.setText(caja.getText()+"8");
                  pilacalcu.push("8");              
            }
        }                
        );
        boton[9].addActionListener(
        new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
               caja.setText(caja.getText()+"9");
                   pilacalcu.push("9");             
            }
        }                
        );
        boton[10].addActionListener(
        new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
               caja.setText(caja.getText()+"+");
                   pilacalcu.push("+");             
            }
        }                
        );
        boton[11].addActionListener(
        new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
               caja.setText(caja.getText()+"-");
                     pilacalcu.push("+");           
            }
        }                
        );
        boton[12].addActionListener(
        new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
               caja.setText(caja.getText()+"*");
                       pilacalcu.push("*");         
            }
        }                
        );
        boton[13].addActionListener(
        new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
               caja.setText(caja.getText()+"/");
                       pilacalcu.push("/");         
            }
        }                
        );
        boton[14].addActionListener(
        new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
               caja.setText(caja.getText()+".");
                        pilacalcu.push(".");        
            }
        }                
        );
        
        
        boton[15].addActionListener(
        new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
                pilacalcu.push(caja.getText());
                //if (Operacion.equals("+"));
                String aux=pilacalcu.pop();
                // muestra los elementos que hay en la pila
                System.out.println(caja.getText());
               //caja.setText(caja.getText()+"=");
                        //pilacalcu.push("=");        
            }
        }                
        );
        
        
      boton[16].addActionListener(
        new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
               caja.setText(caja.getText()+"C");
                        pilacalcu.push("C");     
                        while (pilacalcu.isEmpty())
                            System.out.println(pilacalcu.peek());
            }
        }                
        );
    
    }
    
}

© 2015 Microsoft Terms Privacy & cookies Developers English (United States)

     
