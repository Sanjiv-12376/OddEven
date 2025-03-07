# OddEven

import java.util.Arrays;
import java.util.stream.IntStream;

public class OddEvenSort {

    public static void main(String[] args) {
        int[] numbers = {5, 2, 7, 8, 3, 4, 1, 6};
        int[] sortedNumbers = sortOddEven(numbers);
        System.out.println("Odd numbers first, then even numbers: " + Arrays.toString(sortedNumbers));
    }

    public static int[] sortOddEven(int[] numbers) {
        int[] oddNumbers = Arrays.stream(numbers)
                .filter(n -> n % 2 != 0)
                .sorted()
                .toArray();

        int[] evenNumbers = Arrays.stream(numbers)
                .filter(n -> n % 2 == 0)
                .sorted()
                .toArray();

        return IntStream.concat(Arrays.stream(oddNumbers), Arrays.stream(evenNumbers)).toArray();
    }
}
