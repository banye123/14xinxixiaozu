# 14xinxixiaozu
package Experience5;
 
import java.awt.BorderLayout;
import java.awt.Component;
import java.awt.GridBagConstraints;
import java.awt.GridBagLayout;
import java.awt.GridLayout;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;
 
 
import javax.swing.*;
 
public class SimpleCalculator extends JFrame implements ActionListener{
    JTextField jText;
    Boolean state=false;
    double firstOperator,secondOperator;
    int operate;
    int count=0;
     
    //控件的定义
    JPanel jUpPanel;
    JPanel jDownPanel;
    GridBagLayout gbLayout;
    GridBagConstraints gbConstraints;
    String[] jButNames={"7","8","9","/","4","5","6","*","1","2","3","-","0",".","=","+"};
    JButton[] jButs =new JButton[16];
     
    public static void main(String args[])
    {
        SimpleCalculator calculator=new SimpleCalculator();
    }
     
    public SimpleCalculator()
    {
        super("A Simple Calculator");
         
 
        //窗体的设定
        this.setSize(400, 300);
        this.setDefaultCloseOperation(EXIT_ON_CLOSE);
        //this.pack();
        this.setVisible(true);
         
        //框架的定义
        jUpPanel=new JPanel();          
        jDownPanel=new JPanel();
        gbLayout=new GridBagLayout();
        gbConstraints=new GridBagConstraints();
        this.getContentPane().setLayout(gbLayout);
         
        gbConstraints.weightx = 1;
        gbConstraints.weighty = 0;
        gbConstraints.fill = GridBagConstraints.BOTH;
        gbConstraints.gridx=0;
        gbConstraints.gridy=0;
        gbConstraints.gridheight=1;
        gbConstraints.gridwidth=4;
        gbLayout.setConstraints(jUpPanel, gbConstraints);
        this.getContentPane().add(jUpPanel);
        gbConstraints.weighty = 1;
        gbConstraints.gridx=0;
        gbConstraints.gridy=1;
        gbConstraints.gridheight=4;
        gbConstraints.gridwidth=4;
        gbLayout.setConstraints(jDownPanel, gbConstraints); 
        this.getContentPane().add(jDownPanel);
        /*
        gbConstraints.weightx = 1;
        gbConstraints.weighty = 0;
        gbConstraints.fill = GridBagConstraints.BOTH;
        addComponent(jUpPanel, gbLayout, gbConstraints, 0, 0, 4, 1);
        gbConstraints.weighty = 1;
        addComponent(jDownPanel, gbLayout, gbConstraints, 1, 0, 4, 4);  
        this.getContentPane().setLayout(gbLayout);
        */
 
         
        //jUpPanel内容的填充
        jText=new JTextField();
        jText.setHorizontalAlignment(JTextField.RIGHT);
        jText.setEnabled(false);
        jText.setText("本计算器支持连续操作,即1+3-4+5=这样的操作");
