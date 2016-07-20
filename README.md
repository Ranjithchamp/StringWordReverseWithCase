# StringWordReverseWithCase
import java.util.Scanner;

public class New {
	static int input1 = 1;

	public static void main(String[] args) {

			Scanner cc=new Scanner(System.in);
			System.out.println("Enter the String");
			String s = cc.nextLine();

			String q[] = s.split(" ");
			StringBuffer y[] = new StringBuffer[q.length];
			for (int i = 0; i < q.length; i++) {
				y[i] = new StringBuffer(q[i]);
			}
			StringBuffer qq = new StringBuffer();
			for (int i = 0; i < q.length; i++) {
				qq = qq.append(y[i].reverse() + " ");
			}
			String nnew = new String(qq);
			nnew = nnew.trim();
			char pp[] = nnew.toCharArray();
			for (int count = 0; count < pp.length; count++) {
				if ((s.charAt(count) < 91 && s.charAt(count) > 64)
						|| (s.charAt(count) < 123 && s.charAt(count) > 97)
						&& ((pp[count] > 64 && pp[count] < 91) || (pp[count] > 96 && pp[count] < 123))) {
					if (s.charAt(count) < 91) {
						if (pp[count] > 96)
							pp[count] = (char) (pp[count] - 32);
					} else if (pp[count] < 96) {
						pp[count] = (char) (pp[count] + 32);
					}
				} else if (s.charAt(count) > 91 && s.charAt(count) < 64
						&& s.charAt(count) > 123 && s.charAt(count) < 97) {
					pp[pp.length - 1 - count] = s.charAt(count);
				}
			}
			String ran = new String(pp);
			System.out.println(ran);
		}
	}

