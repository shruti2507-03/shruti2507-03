import javax.swing.*;
import java.awt.*;
import java.awt.event.ActionEvent;
import java.awt.event.ActionListener;

public class NewYearMessageApp {
    public static void main(String[] args) {
        // Create the main frame
        JFrame frame = new JFrame("Happy New Year!");
        frame.setSize(400, 300);
        frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE);
        frame.setLayout(new BorderLayout());
        frame.setLocationRelativeTo(null);

        // Add message label
        JLabel messageLabel = new JLabel("<html><center><h1>Happy New Year!</h1><br>May we start the new year together?</center></html>", SwingConstants.CENTER);
        messageLabel.setFont(new Font("Serif", Font.BOLD, 18));
        frame.add(messageLabel, BorderLayout.CENTER);

        // Create panel for buttons
        JPanel buttonPanel = new JPanel();
        buttonPanel.setLayout(new FlowLayout());

        // Add "Yes" buttons
        JButton yesButton1 = new JButton("Yes");
        JButton yesButton2 = new JButton("Yes");

        // Add action listeners for buttons
        ActionListener buttonAction = new ActionListener() {
            @Override
            public void actionPerformed(ActionEvent e) {
                JOptionPane.showMessageDialog(frame, "Great! Let's make it a wonderful year ahead!", "Happy New Year!", JOptionPane.INFORMATION_MESSAGE);
            }
        };

        yesButton1.addActionListener(buttonAction);
        yesButton2.addActionListener(buttonAction);

        // Add buttons to the panel
        buttonPanel.add(yesButton1);
        buttonPanel.add(yesButton2);

        // Add the panel to the frame
        frame.add(buttonPanel, BorderLayout.SOUTH);

        // Set the frame visible
        frame.setVisible(true);
    }
}
