# supreme-octo-tribble
Converter


import java.awt.EventQueue;

import javax.swing.JFrame;
import javax.swing.JLabel;
import javax.swing.JOptionPane;

import java.awt.Color;
import javax.swing.JTextField;
import javax.swing.JComboBox;
import javax.swing.JButton;
import javax.swing.DefaultComboBoxModel;
import javax.swing.AbstractAction;
import java.awt.event.ActionEvent;
import javax.swing.Action;
import java.awt.event.ActionListener;

public class TestPro {

	private JFrame frame;
	private JTextField txtAmount;
	

	/**
	 * Launch the application.
	 */
	public static void main(String[] args) {
		EventQueue.invokeLater(new Runnable() {
			public void run() {
				try {
					TestPro window = new TestPro();
					window.frame.setVisible(true);
				} catch (Exception e) {
					e.printStackTrace();
				}
			}
		});
	}

	/**
	 * Create the application.
	 */
	public TestPro() {
		initialize();
	}

	/**
	 * Initialize the contents of the frame.
	 */
	private void initialize() {
		frame = new JFrame();
		frame.setForeground(new Color(0, 255, 255));
		frame.getContentPane().setForeground(new Color(138, 43, 226));
		frame.setBounds(100, 100, 450, 300);
		frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
		frame.getContentPane().setLayout(null);
		
		JLabel lblNewLabel = new JLabel("Enter the Amount:");
		lblNewLabel.setForeground(new Color(0, 0, 255));
		lblNewLabel.setBounds(10, 11, 96, 14);
		frame.getContentPane().add(lblNewLabel);
		
		JLabel lblNewLabel_1 = new JLabel("From:");
		lblNewLabel_1.setForeground(new Color(0, 0, 255));
		lblNewLabel_1.setBounds(10, 92, 46, 14);
		frame.getContentPane().add(lblNewLabel_1);
		
		JLabel lblNewLabel_2 = new JLabel("To:");
		lblNewLabel_2.setForeground(new Color(0, 0, 255));
		lblNewLabel_2.setBounds(10, 184, 46, 14);
		frame.getContentPane().add(lblNewLabel_2);
		
		txtAmount = new JTextField();
		txtAmount.setBounds(130, 8, 142, 20);
		frame.getContentPane().add(txtAmount);
		txtAmount.setColumns(10);
		
		final JComboBox txtFrom = new JComboBox();
		txtFrom.setModel(new DefaultComboBoxModel(new String[] {"USD"}));
		txtFrom.setBounds(130, 88, 142, 22);
		frame.getContentPane().add(txtFrom);
		
		final JComboBox txtTo = new JComboBox();
		txtTo.setModel(new DefaultComboBoxModel(new String[] {"EURO", "Indian Rupees", "Srilankan Rupees"}));
		txtTo.setBounds(130, 180, 142, 22);
		frame.getContentPane().add(txtTo);
		
		JButton btnNewButton = new JButton("Convert");
		btnNewButton.addActionListener(new ActionListener() {
			public void actionPerformed(ActionEvent e) {

				Double tot; 
				
				Double amount = Double.parseDouble(txtAmount.getText()); 
				
				if(txtFrom.getSelectedItem().toString() == "USD" && txtTo.getSelectedItem().toString() == "EURO")
				{
					tot = amount / 1.25; 
					JOptionPane.showInputDialog("Your amount will be: " + tot.toString());
				}
				else if(txtFrom.getSelectedItem().toString() == "USD" && txtTo.getSelectedItem().toString() == "Indian Rupees")
				{
					tot = amount * 70.50; 
					JOptionPane.showInputDialog( "Your amount will be: " + tot.toString());
				}
				else if(txtFrom.getSelectedItem().toString() == "USD" && txtTo.getSelectedItem().toString() == "Srilankan Rupees")
				{
					tot = amount * 179.50; 
					JOptionPane.showInputDialog( "Your amount will be: " + tot.toString());
				}
				
			}
		});
		btnNewButton.setBounds(335, 216, 89, 23);
		frame.getContentPane().add(btnNewButton);
	}
}
