
import java.awt.Color;
import java.awt.EventQueue;
import javax.swing.JFrame;
import javax.swing.JLabel;
import javax.swing.JMenu;
import javax.swing.JMenuBar;
import javax.swing.JPanel;
import javax.swing.JTabbedPane;
import javax.swing.border.EmptyBorder;

public class DrawFrame extends JFrame {
	private JPanel contentPane;
	public DrawFrame() {
            setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
		setBounds(100, 100, 971, 750);
		
		JMenuBar menuBar = new JMenuBar();
		setJMenuBar(menuBar);
		
		JMenu mnFile = new JMenu("File");
		menuBar.add(mnFile);
		contentPane = new JPanel();
		contentPane.setBorder(new EmptyBorder(5, 5, 5, 5));
		setContentPane(contentPane);
		contentPane.setLayout(null);
		
		JTabbedPane tabbedPane = new JTabbedPane(JTabbedPane.TOP);
		tabbedPane.setBounds(12, 12, 935, 586);
		contentPane.add(tabbedPane);
		
		JPanel panelQuestionOne = new JPanel();
		tabbedPane.addTab("Question 1", null, panelQuestionOne, null);
		panelQuestionOne.setLayout(null);
		
		DrawPanelTwo diagramPanel = new DrawPanelTwo();
		diagramPanel.setBackground(Color.WHITE);
		diagramPanel.setBounds(1, 131, 646, 410);
		panelQuestionOne.add(diagramPanel);
		
		CodeGeneratorPanel codePanel = new CodeGeneratorPanel();
		codePanel.setBackground(Color.WHITE);
		codePanel.setBounds(610, 1, 345, 540);
		panelQuestionOne.add(codePanel);
		
		DrawPanelOne shapePanel = new DrawPanelOne();
		shapePanel.setBackground(Color.WHITE);
		shapePanel.setBounds(1, 1, 646, 130);
		panelQuestionOne.add(shapePanel);
		
		JPanel panelQuestionTwo = new JPanel();
		tabbedPane.addTab("Question 2", null, panelQuestionTwo, null);
		
		JPanel panel = new JPanel();
		panel.setBackground(Color.LIGHT_GRAY);
		panel.setBounds(12, 610, 935, 75);
		contentPane.add(panel);
		
		JLabel lblResponsiveGhostPanel = new JLabel("Responsive ghost panel");
		panel.add(lblResponsiveGhostPanel);
        }
        
        public static void main(String[] args) {
		EventQueue.invokeLater(new Runnable() {
			public void run() {
				try {
					DrawFrame frame = new DrawFrame();
					frame.setVisible(true);
				} catch (Exception e) {
					e.printStackTrace();
				}
			}
		});
	}

}
