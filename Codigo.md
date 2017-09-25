import javax.swing.ImageIcon;
import javax.swing.JFrame;
import javax.swing.JLabel;


public class Carros extends JFrame {

// Criação dos icones de imagem    
        JLabel lCarro1 = new JLabel (new ImageIcon(getClass().getResource("carro1.png")));
   
       
    public Carros(){
        editarJanela();
        new Movimento().start();
    }    
    
    public void editarJanela(){
        setDefaultCloseOperation(EXIT_ON_CLOSE);
        setSize(1400,350); // tamanhao da tela
        setLocationRelativeTo(null); // iniciar no meio da tela
        setVisible(true); // mostrar o componente 
        setLayout(null); // centalização absoluta 
        
        //Adicionar imagem na Janela
        //                x , y, larg, altura
        lCarro1.setBounds(0, 0, 200, 100);
       
        add(lCarro1);
     
    }
    
    public class Movimento extends Thread{
    
        public void run(){
            while(true){
                try {sleep (20);} catch (Exception erro){}
                lCarro1.setBounds(lCarro1.getX()+1, 0, 200, 100);
         
            
            }
        
        }
    }
    public static void main(String[] args) {
       new Carros();
    }
    
}
