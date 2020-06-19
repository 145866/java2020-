# java2020-
所选
package java练习;
import java.awt.*;
import java.awt.event.*;
public class 课程七 {
	Frame app = new Frame("TextField 组件");	Label lblName = new Label("UserName:");
	static TextField txtName = new TextField();	Label lblPass = new Label("Password:");
	static TextField txtPass = new TextField();
	public 课程七() {
		Color color=Color.green;
		app.setBackground(color);
		app.setSize(300, 150); 		// 设置窗体尺寸
		app.setLayout(null);		 // 取消窗体的布局管理器
		/* 设置姓名栏对应的标签与文本域的位置与大小 */
		lblName.setBounds(60, 50, 70, 20);	txtName.setBounds(135, 50, 100, 20);
		// 为文本框添加事件侦听器
		txtName.addKeyListener(new keyHandler());
		txtName.addFocusListener(new focusHandler());
		/* 设置密码栏对应的标签与文本域的位置与大小 */
		lblPass.setBounds(60, 90, 70, 20);	txtPass.setBounds(135, 90, 100, 20);
		txtPass.setEchoChar('*'); 		// 设置密码框文本域的回显字符
		// 为密码框添加事件侦听器
		txtPass.addKeyListener(new keyHandler());
		txtPass.addFocusListener(new focusHandler());
		/* 将组件添加到窗体容器内 */
		app.add(lblName);	app.add(txtName);	app.add(lblPass);	app.add(txtPass);
		/* 设置窗体的位置与可见性 */
		app.setLocation(200, 100);
		app.setVisible(true);			} 	
		public static void main(String[] args) {
		       课程七 tft = new 课程七();	}
}
//定义实现keyListener接口的keyEvent事件处理类 
class keyHandler implements KeyListener {
	// 按下某个键时调用此方法
	public void keyPressed(KeyEvent e) {
		// 获取事件对象
		Object ob = e.getSource();
		// 如果事件对象为txtName，并且按下回车键，则在控制台中
		// 显示输入的用户名
		if ((ob == 课程七.txtName) && (e.getKeyCode() == 10)) {
			System.out.println(课程七.txtName.getText());
		}
		
		else if ((ob == 课程七.txtPass) && (e.getKeyCode() == 10)) {
			System.out.println(课程七.txtPass.getText());
		}
	}
	
	public void keyReleased(KeyEvent e) {
	}
	public void keyTyped(KeyEvent e) {
	}
} 

class focusHandler implements FocusListener {
	
	public void focusGained(FocusEvent e) {
	}
	
	public void focusLost(FocusEvent e) {
		
		Object ob = e.getSource();
		
		if (ob == 课程七.txtName) {
			System.out.println(课程七.txtName.getText());
		}
		
		else if (ob == 课程七.txtPass) {
			System.out.println(课程七.txtPass.getText());
		}
	}
}


