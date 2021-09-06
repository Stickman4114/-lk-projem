import java.util.Random;
import java.awt.*;
import java.awt.event.*;
import java.util.Scanner;
import javax.swing.*;


public class Main {

    public static void main(String[] args) {
        JFrame frame = new JFrame("Push Counter");
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        frame.getContentPane().add(new PushCounterPanel());
        frame.pack();
        frame.setVisible(true);

    }
}

        class PushCounterPanel extends JPanel {
            private Random gen;
            private int randomNum;
            private JButton push;
            private JLabel label;

            public PushCounterPanel() {
                Random gen = new Random();
                randomNum = 0;
                push = new JButton("Random sayı at");
                push.addActionListener(new ButtonListener());
                label = new JLabel("Random = " + randomNum);
                add(push);
                add(label);
                setPreferredSize(new Dimension(500, 400));
                setBackground(Color.gray);
            }

            private class ButtonListener implements ActionListener {


                public void actionPerformed(ActionEvent event) {
                    Scanner scan = new Scanner(System.in);
                    System.out.print("Sayı giriniz = ");
                    double sayi2 = scan.nextInt();
                    double sayi1 = (Math.random() * sayi2);
                    label.setText("Random sayı = " + sayi1);
                }
            }
        }
