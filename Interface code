

import javax.swing.*;
import java.awt.*;
import java.awt.event.*;
import java.sql.*;

public class Interface 
{
	JFrame f;
	JRadioButton jb,jb1;
	JPanel p1,p2;
	JButton bSubmit;
	JDialog d,d1;
	
	ButtonGroup b=new ButtonGroup();
	Connection con;
	Statement stmt;
	ResultSet rs;
	Interface() throws Exception
	{
		try
		{
			try
			{
					Class.forName("org.relique.jdbc.csv.CsvDriver");
					con=DriverManager.getConnection("jdbc:relique:csv:C:\\Users\\Pritam Negi\\Desktop\\project\\names");  
			 		stmt=con.createStatement();    
			}catch(Exception e)
			{
				JOptionPane.showMessageDialog(null,e,"Error", JOptionPane.ERROR_MESSAGE);
				System.out.println(e);
				System.exit(0);
			}

		f=new JFrame("Interface");
		p1=new JPanel(new GridLayout(2,1));
		p2=new JPanel(new FlowLayout());
		bSubmit=new JButton("Submit");
		f.setSize(400,140);f.setResizable(false);f.setLayout(new GridLayout(2,1));
		jb=new JRadioButton("Popular Names by Birth Year",true);
		b.add(jb);p1.add(jb);
		jb1=new JRadioButton("Popular of a name that has changed over the year");
		b.add(jb1);	p1.add(jb1);f.add(p1);
		p2.add(bSubmit);
		bSubmit.addActionListener(new ActionListener()
		{
			public void actionPerformed(ActionEvent e) 
			{		
				
				if(jb.isSelected())
				{
					JPanel p1=new JPanel();
					JPanel p2=new JPanel();
					JPanel p3=new JPanel();
					JPanel p4=new JPanel();
					final JRadioButton male;
					final JRadioButton fe;
					final JRadioButton bth;
					JButton bSu=new JButton("Submit");
					ButtonGroup b=new ButtonGroup();
					male=new JRadioButton("Male",true);
					b.add(male);
					fe=new JRadioButton("Female");
					b.add(fe);
					bth=new JRadioButton("Both");
					b.add(bth);
					p3.add(male);
					p3.add(fe);
					p3.add(bth);
					p4.add(bSu);
					p1.setLayout(new FlowLayout());
					p2.setLayout(new FlowLayout());
					p3.setLayout(new FlowLayout());
					p4.setLayout(new FlowLayout());
					JLabel l1=new JLabel("Year");
					JLabel l2=new JLabel("Top");
					l1.setForeground(Color.blue);
					l2.setForeground(Color.blue);
					final JTextField tf1=new JTextField(15);
					final JTextField tf2=new JTextField(15);
					p1.add(l1);p1.add(tf1);
					p2.add(l2);p2.add(tf2);
					d=new JDialog();
					d.setTitle("INPUT");
					d.setSize(300,200);
					d.setResizable(false);
					d.setLayout(new GridLayout(4,1));
					d.setLocationRelativeTo(null);
					
					d.add(p1);
					d.add(p2);
					d.add(p3);
					d.add(p4);
					bSu.addActionListener(new ActionListener()
					{String s1,s2;
					
						public void actionPerformed(ActionEvent arg0) 
						{
							byte flag=0;
							TextArea ta;
							try {
									
									s1=tf1.getText();
									s2=tf2.getText();
									if(male.isSelected())
										rs = stmt.executeQuery("SELECT * FROM male_cy"+s1+"_top LIMIT "+Integer.parseInt(s2));
									else if(fe.isSelected())
										rs = stmt.executeQuery("SELECT * FROM female_cy"+s1+"_top LIMIT "+Integer.parseInt(s2));
									else if(bth.isSelected()){
										rs = stmt.executeQuery("SELECT * FROM female_cy"+s1+"_top LIMIT "+Integer.parseInt(s2));
										flag=1;
									}
								}0
							 catch (SQLException e) {
								JOptionPane.showMessageDialog(null,e,"Error", JOptionPane.ERROR_MESSAGE);
							}
							JDialog d1=new JDialog();
							d1.add(ta=new TextArea());
							d1.setTitle("RESULT");
							d1.setSize(300,300);
							d1.setResizable(false);
							d1.setVisible(true);
							d1.setDefaultCloseOperation(d1.DISPOSE_ON_CLOSE);
							try {
								while(rs.next() )
									ta.append("        "+rs.getString(1)+"\n");	
								if(flag==1)
								{
									rs = stmt.executeQuery("SELECT * FROM male_cy"+s1+"_top LIMIT "+Integer.parseInt(s2));
								while(rs.next() )
									ta.append("        "+rs.getString(1)+"\n");
								}} catch (SQLException e) {
								e.printStackTrace();
							}
						}
					});
					d.setVisible(true);
				}
				else
				{
					JPanel p1=new JPanel();
					JPanel p2=new JPanel();
					JPanel p3=new JPanel();
					JPanel p4=new JPanel();
					final JRadioButton male;
					final JRadioButton fe;
					final JRadioButton bth;
					JButton bSu=new JButton("Submit");
					ButtonGroup b=new ButtonGroup();
					male=new JRadioButton("Male",true);
					b.add(male);
					fe=new JRadioButton("Female");
					b.add(fe);
					bth=new JRadioButton("Both");
					b.add(bth);
					p3.add(male);
					p3.add(fe);
					p3.add(bth);
					p4.add(bSu);
					p1.setLayout(new FlowLayout());
					p2.setLayout(new FlowLayout());
					p3.setLayout(new FlowLayout());
					p4.setLayout(new FlowLayout());
					JLabel l1=new JLabel("Name");
					JLabel l2=new JLabel("Year");
					l1.setForeground(Color.blue);
					l2.setForeground(Color.blue);
					final JTextField tf1=new JTextField(15);
					final JTextField tf2=new JTextField(15);
					p1.add(l1);p1.add(tf1);
					p2.add(l2);p2.add(tf2);
					d1=new JDialog();
					d1.setTitle("INPUT");
					d1.setSize(300,200);
					d1.setResizable(false);
					d1.setLayout(new GridLayout(4,1));
					d1.setLocationRelativeTo(null);
					d1.add(p1);
					d1.add(p2);
					d1.add(p3);
					d1.add(p4);
					d1.setVisible(true);
					bSu.addActionListener(new ActionListener() 
					{
						public void actionPerformed(ActionEvent arg0) 
						{ 
							TextArea ta;
							String s1,s2;
							s1=tf1.getText();
							s2=tf2.getText();
							JDialog d1=new JDialog();
							d1.setTitle("RESULT");
							d1.add(ta=new TextArea());
							d1.setLayout(new GridLayout(1,3));
							d1.setSize(300,300);
							d1.setResizable(false);
							d1.setVisible(true);
							int i,sum,f=0;
							d1.setDefaultCloseOperation(d1.DISPOSE_ON_CLOSE);
							int n=Integer.parseInt(s2);
							for(i=n,sum=0,f=0;i<=2013;i++)
							{
								try {
								s1=tf1.getText();
								s2=tf2.getText();
								ta.setEditable(false);
								if(male.isSelected()){
									rs = stmt.executeQuery("SELECT * FROM male_cy"+i+"_top");
									while(rs.next())
									{if(s1.equalsIgnoreCase(rs.getString(1)))
										{f++;sum+=rs.getInt(2);ta.append(f+" " );ta.append(s1 );ta.append(" "+rs.getInt(2)+"  ");ta.append(rs.getInt(3)+" ");ta.append(i+"\n");}}}
								else if(fe.isSelected()){
									rs = stmt.executeQuery("SELECT * FROM female_cy"+i+"_top");
									while(rs.next())
									{if(s1.equalsIgnoreCase(rs.getString(1)))
										{f++;sum+=rs.getInt(2);ta.append(f+" " );ta.append(s1 );ta.append(" "+rs.getInt(2)+"  ");ta.append(rs.getInt(3)+" ");ta.append(i+"\n");}}}
								else if(bth.isSelected()){
									rs = stmt.executeQuery("SELECT * FROM female_cy"+i+"_top");
									while(rs.next())
									{if(s1.equalsIgnoreCase(rs.getString(1)))
										{f++;sum+=rs.getInt(2);ta.append(f+" " );ta.append(s1 );ta.append(" "+rs.getInt(2)+"  ");ta.append(rs.getInt(3)+" ");ta.append(i+"\n");}}
									rs = stmt.executeQuery("SELECT * FROM male_cy"+i+"_top");
									while(rs.next())
									{if(s1.equalsIgnoreCase(rs.getString(1))){
										f++;sum+=rs.getInt(2);ta.append(f+" " );ta.append(s1 );ta.append(" "+rs.getInt(2)+"  ");ta.append(rs.getInt(3)+" ");ta.append(i+"\n");}};
										
								}
								}catch (SQLException e) {
									JOptionPane.showMessageDialog(null,"Somthing Wrong!!!","Error", JOptionPane.ERROR_MESSAGE);
								}}ta.append("Total Amount="+sum);
						}
					});
				}
			}});
		f.add(p2);
		f.addWindowListener(new WindowAdapter()
		{
			public void windowClosing(WindowEvent we)
			{
        	 	int n=JOptionPane.showConfirmDialog(null, "Do you want to continue?", "Meassage",JOptionPane.YES_NO_OPTION);
	    		if(n==JOptionPane.YES_OPTION) {try {
					con.close();
				} catch (SQLException e) {
					e.printStackTrace();
				}System.exit(0);} else
					try {
						new Interface();
					} catch (Exception e) {
						e.printStackTrace();
					} 
			}
     });
		f.setVisible(true);
		}catch(Exception e)
		{JOptionPane.showMessageDialog(null,e,"Error", JOptionPane.ERROR_MESSAGE);}
}
	public static void main(String[] args)
	{
		try {
			new Interface();
		} catch(Exception e) {
			
			JOptionPane.showMessageDialog(null,"Program Stopped Working","Error", JOptionPane.ERROR_MESSAGE);
		}
	}
}
