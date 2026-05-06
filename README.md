task#1:
public class HarshadCheck {

    public static int harshadNumber(int x) {
        int sum = 0;
        int temp = x;

        // Calculate sum of digits
        while (temp > 0) {
            sum += temp % 10;
            temp /= 10;
        }

        // Check Harshad condition
        if (x % sum == 0) {
            return sum;
        } else {
            return -1;
        }
    }

    public static void main(String[] args) {
        int x1 = 18;
        int x2 = 23;

        System.out.println(harshadNumber(x1)); // Output: 9
        System.out.println(harshadNumber(x2)); // Output: -1
    }
}




harshad problem :

import java.util.Scanner;

public class HarshadNumbers {

    // Function to check Harshad number
    static boolean isHarshad(int num) {
        int sum = 0, temp = num;

        while (temp > 0) {
            sum += temp % 10;
            temp /= 10;
        }

        return num % sum == 0;
    }

    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);

        int t = 5; // number of test cases

        while (t-- > 0) {
            int m = sc.nextInt(); // lower bound
            int n = sc.nextInt(); // upper bound

            int maxLen = 0;
            int currentLen = 0;

            for (int i = m; i <= n; i++) {
                if (isHarshad(i)) {
                    currentLen++;
                    if (currentLen > maxLen) {
                        maxLen = currentLen;
                    }
                } else {
                    currentLen = 0; // reset if not Harshad
                }
            }

            System.out.println(maxLen);
        }

        sc.close();
    }
}
