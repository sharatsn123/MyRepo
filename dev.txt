
import java.awt.Toolkit;
import java.util.Scanner;
import java.util.concurrent.TimeUnit;

//import javax.swing.JFrame;
import javax.swing.JOptionPane;
import javax.swing.JPanel;

public class EyeCareReminder {

	public static void main(final String[] args) throws InterruptedException {
		//final JFrame parent = new JFrame();
		JPanel panel = new JPanel();
		int minutes;
		if (args.length > 0 && args[0] != null) {
			minutes = Integer.parseInt(args[0]);
		} else {
			Scanner scanner = new Scanner(System.in);
			System.out.print("Minutes : ");
			minutes = scanner.nextInt();
			scanner.close();
		}
		int c = 0;
		while (c == 0) {
			Toolkit.getDefaultToolkit().beep();
			c = JOptionPane.showConfirmDialog(panel, "Continue?", "Rest", JOptionPane.YES_NO_OPTION);
			TimeUnit.MINUTES.sleep(1);
			Toolkit.getDefaultToolkit().beep();
			TimeUnit.MINUTES.sleep(minutes);
		}
		
		System.exit(0);
	}
}

