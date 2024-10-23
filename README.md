Sure! Here’s the continuation of the C# programs along with their descriptions, implementations, and examples, covering all the requested algorithms and tasks.

---

### C# Programs

### 1. Prime Number
- **Description**: Checks if a given number is prime.
- **Implementation**:
```csharp
using System;

class PrimeNumber
{
    static void Main()
    {
        Console.Write("Enter a number: ");
        int num = int.Parse(Console.ReadLine());
        bool isPrime = true;

        if (num < 2)
            isPrime = false;
        else
        {
            for (int i = 2; i <= Math.Sqrt(num); i++)
            {
                if (num % i == 0)
                {
                    isPrime = false;
                    break;
                }
            }
        }

        Console.WriteLine(isPrime ? $"{num} is a prime number." : $"{num} is not a prime number.");
    }
}
```
- **Example**:
  - Input: `7`
  - Output: `7 is a prime number.`

---

### 2. Fibonacci Sequence
- **Description**: Generates the Fibonacci sequence up to a specified number.
- **Implementation**:
```csharp
using System;

class Fibonacci
{
    static void Main()
    {
        Console.Write("Enter the number of terms: ");
        int terms = int.Parse(Console.ReadLine());
        int a = 0, b = 1;

        Console.WriteLine("Fibonacci Series:");
        for (int i = 0; i < terms; i++)
        {
            Console.Write(a + " ");
            int next = a + b;
            a = b;
            b = next;
        }
    }
}
```
- **Example**:
  - Input: `5`
  - Output: `Fibonacci Series: 0 1 1 2 3`

---

### 3. Factorial
- **Description**: Computes the factorial of a given number.
- **Implementation**:
```csharp
using System;

class Factorial
{
    static void Main()
    {
        Console.Write("Enter a number: ");
        int num = int.Parse(Console.ReadLine());
        long factorial = 1;

        for (int i = 1; i <= num; i++)
        {
            factorial *= i;
        }

        Console.WriteLine($"Factorial of {num} is {factorial}.");
    }
}
```
- **Example**:
  - Input: `5`
  - Output: `Factorial of 5 is 120.`

---

### 4. Armstrong Number
- **Description**: Checks if a number is an Armstrong number (sum of its own digits each raised to the power of the number of digits).
- **Implementation**:
```csharp
using System;

class Armstrong
{
    static void Main()
    {
        Console.Write("Enter a number: ");
        int num = int.Parse(Console.ReadLine());
        int originalNum = num;
        int sum = 0;
        int digits = num.ToString().Length;

        while (num > 0)
        {
            int digit = num % 10;
            sum += (int)Math.Pow(digit, digits);
            num /= 10;
        }

        Console.WriteLine(sum == originalNum ? $"{originalNum} is an Armstrong number." : $"{originalNum} is not an Armstrong number.");
    }
}
```
- **Example**:
  - Input: `153`
  - Output: `153 is an Armstrong number.`

---

### 5. LCM (Least Common Multiple)
- **Description**: Calculates the LCM of two numbers.
- **Implementation**:
```csharp
using System;

class LCM
{
    static void Main()
    {
        Console.Write("Enter first number: ");
        int num1 = int.Parse(Console.ReadLine());
        Console.Write("Enter second number: ");
        int num2 = int.Parse(Console.ReadLine());

        int lcm = (num1 * num2) / GCD(num1, num2);
        Console.WriteLine($"LCM of {num1} and {num2} is {lcm}.");
    }

    static int GCD(int a, int b)
    {
        while (b != 0)
        {
            int temp = b;
            b = a % b;
            a = temp;
        }
        return a;
    }
}
```
- **Example**:
  - Input: `4, 5`
  - Output: `LCM of 4 and 5 is 20.`

---

### 6. GCD (Greatest Common Divisor)
- **Description**: Calculates the GCD of two numbers using the Euclidean algorithm.
- **Implementation**:
```csharp
using System;

class GCD
{
    static void Main()
    {
        Console.Write("Enter first number: ");
        int num1 = int.Parse(Console.ReadLine());
        Console.Write("Enter second number: ");
        int num2 = int.Parse(Console.ReadLine());

        int gcd = GCD(num1, num2);
        Console.WriteLine($"GCD of {num1} and {num2} is {gcd}.");
    }

    static int GCD(int a, int b)
    {
        while (b != 0)
        {
            int temp = b;
            b = a % b;
            a = temp;
        }
        return a;
    }
}
```
- **Example**:
  - Input: `48, 18`
  - Output: `GCD of 48 and 18 is 6.`

---

### 7. Sorting (Bubble Sort)
- **Description**: Sorts an array of integers using the Bubble Sort algorithm.
- **Implementation**:
```csharp
using System;

class Sorting
{
    static void Main()
    {
        int[] arr = { 64, 34, 25, 12, 22, 11, 90 };
        int n = arr.Length;

        for (int i = 0; i < n - 1; i++)
        {
            for (int j = 0; j < n - i - 1; j++)
            {
                if (arr[j] > arr[j + 1])
                {
                    // Swap arr[j] and arr[j + 1]
                    int temp = arr[j];
                    arr[j] = arr[j + 1];
                    arr[j + 1] = temp;
                }
            }
        }

        Console.WriteLine("Sorted array:");
        foreach (var item in arr)
        {
            Console.Write(item + " ");
        }
    }
}
```
- **Example**:
  - Input: `64, 34, 25, 12, 22, 11, 90`
  - Output: `Sorted array: 11 12 22 25 34 64 90`

---

### 8. Reverse Number
- **Description**: Reverses the digits of a given number.
- **Implementation**:
```csharp
using System;

class ReverseNumber
{
    static void Main()
    {
        Console.Write("Enter a number: ");
        int num = int.Parse(Console.ReadLine());
        int reversed = 0;

        while (num != 0)
        {
            int digit = num % 10;
            reversed = reversed * 10 + digit;
            num /= 10;
        }

        Console.WriteLine($"Reversed number is {reversed}.");
    }
}
```
- **Example**:
  - Input: `12345`
  - Output: `Reversed number is 54321.`

---

### 9. Palindrome
- **Description**: Checks if a given string is a palindrome.
- **Implementation**:
```csharp
using System;

class Palindrome
{
    static void Main()
    {
        Console.Write("Enter a string: ");
        string str = Console.ReadLine();
        string reversed = "";

        for (int i = str.Length - 1; i >= 0; i--)
        {
            reversed += str[i];
        }

        Console.WriteLine(str.Equals(reversed, StringComparison.OrdinalIgnoreCase) ? $"{str} is a palindrome." : $"{str} is not a palindrome.");
    }
}
```
- **Example**:
  - Input: `madam`
  - Output: `madam is a palindrome.`

---

### 10. Leap Year
- **Description**: Checks if a given year is a leap year.
- **Implementation**:
```csharp
using System;

class LeapYear
{
    static void Main()
    {
        Console.Write("Enter a year: ");
        int year = int.Parse(Console.ReadLine());

        bool isLeap = (year % 4 == 0 && year % 100 != 0) || (year % 400 == 0);
        Console.WriteLine(isLeap ? $"{year} is a leap year." : $"{year} is not a leap year.");
    }
}
```
- **Example**:
  - Input: `2020`
  - Output: `2020 is a leap year.`

---

### 11. Second Greatest Number from Array
- **Description**: Finds the second greatest number in an array.
- **Implementation**:
```csharp
using System;

class SecondGreatest
{
    static void Main()
    {
        int[] arr = { 1, 2, 3, 4, 5 };
        int first = int.MinValue, second = int.MinValue;

        foreach (var number in arr)
        {
            if (number > first)
            {
                second = first;
                first = number;
            }
            else if (number > second && number != first)
           

 {
                second = number;
            }
        }

        Console.WriteLine($"Second greatest number is {second}.");
    }
}
```
- **Example**:
  - Input: `1, 2, 3, 4, 5`
  - Output: `Second greatest number is 4.`

---

### 12. FizzBuzz
- **Description**: Prints numbers from 1 to 100, replacing multiples of 3 with "Fizz", multiples of 5 with "Buzz", and multiples of both with "FizzBuzz".
- **Implementation**:
```csharp
using System;

class FizzBuzz
{
    static void Main()
    {
        for (int i = 1; i <= 100; i++)
        {
            if (i % 3 == 0 && i % 5 == 0)
                Console.WriteLine("FizzBuzz");
            else if (i % 3 == 0)
                Console.WriteLine("Fizz");
            else if (i % 5 == 0)
                Console.WriteLine("Buzz");
            else
                Console.WriteLine(i);
        }
    }
}
```
- **Example**:
  - Output: `1, 2, Fizz, 4, Buzz, Fizz, ...`

---

### 13. Anagram Checker
- **Description**: Checks if two strings are anagrams of each other.
- **Implementation**:
```csharp
using System;

class AnagramChecker
{
    static void Main()
    {
        Console.Write("Enter first string: ");
        string str1 = Console.ReadLine();
        Console.Write("Enter second string: ");
        string str2 = Console.ReadLine();

        char[] char1 = str1.ToLower().ToCharArray();
        char[] char2 = str2.ToLower().ToCharArray();

        Array.Sort(char1);
        Array.Sort(char2);

        bool isAnagram = new string(char1) == new string(char2);
        Console.WriteLine(isAnagram ? $"{str1} and {str2} are anagrams." : $"{str1} and {str2} are not anagrams.");
    }
}
```
- **Example**:
  - Input: `listen`, `silent`
  - Output: `listen and silent are anagrams.`

---

### 14. Sum of Digits of a Number
- **Description**: Calculates the sum of digits of a given number.
- **Implementation**:
```csharp
using System;

class SumOfDigits
{
    static void Main()
    {
        Console.Write("Enter a number: ");
        int num = int.Parse(Console.ReadLine());
        int sum = 0;

        while (num != 0)
        {
            sum += num % 10;
            num /= 10;
        }

        Console.WriteLine($"Sum of digits is {sum}.");
    }
}
```
- **Example**:
  - Input: `123`
  - Output: `Sum of digits is 6.`

---

### 15. Matrix Multiplication
- **Description**: Multiplies two matrices.
- **Implementation**:
```csharp
using System;

class MatrixMultiplication
{
    static void Main()
    {
        int[,] matrix1 = { { 1, 2, 3 }, { 4, 5, 6 } };
        int[,] matrix2 = { { 7, 8 }, { 9, 10 }, { 11, 12 } };
        int rows1 = matrix1.GetLength(0), cols1 = matrix1.GetLength(1);
        int rows2 = matrix2.GetLength(0), cols2 = matrix2.GetLength(1);

        if (cols1 != rows2)
        {
            Console.WriteLine("Matrix multiplication not possible.");
            return;
        }

        int[,] result = new int[rows1, cols2];

        for (int i = 0; i < rows1; i++)
        {
            for (int j = 0; j < cols2; j++)
            {
                for (int k = 0; k < cols1; k++)
                {
                    result[i, j] += matrix1[i, k] * matrix2[k, j];
                }
            }
        }

        Console.WriteLine("Resultant Matrix:");
        for (int i = 0; i < rows1; i++)
        {
            for (int j = 0; j < cols2; j++)
            {
                Console.Write(result[i, j] + " ");
            }
            Console.WriteLine();
        }
    }
}
```
- **Example**:
  - Input: Matrix1: `1 2 3`, Matrix2: `7 8`, `9 10`, `11 12`
  - Output: Resultant Matrix: 
    ```
    58 64
    139 154
    ```

---

### 16. Merge Two Sorted Arrays
- **Description**: Merges two sorted arrays into one sorted array.
- **Implementation**:
```csharp
using System;

class MergeSortedArrays
{
    static void Main()
    {
        int[] arr1 = { 1, 3, 5 };
        int[] arr2 = { 2, 4, 6 };
        int[] merged = new int[arr1.Length + arr2.Length];

        int i = 0, j = 0, k = 0;
        while (i < arr1.Length && j < arr2.Length)
        {
            if (arr1[i] < arr2[j])
                merged[k++] = arr1[i++];
            else
                merged[k++] = arr2[j++];
        }

        while (i < arr1.Length)
            merged[k++] = arr1[i++];

        while (j < arr2.Length)
            merged[k++] = arr2[j++];

        Console.WriteLine("Merged array:");
        foreach (var item in merged)
        {
            Console.Write(item + " ");
        }
    }
}
```
- **Example**:
  - Input: Array1: `1, 3, 5`, Array2: `2, 4, 6`
  - Output: `Merged array: 1 2 3 4 5 6`

---

### 17. Finding the Largest and Smallest Numbers in an Array
- **Description**: Finds the largest and smallest numbers in an array.
- **Implementation**:
```csharp
using System;

class LargestSmallest
{
    static void Main()
    {
        int[] arr = { 3, 5, 1, 8, 2 };
        int largest = int.MinValue, smallest = int.MaxValue;

        foreach (var number in arr)
        {
            if (number > largest)
                largest = number;
            if (number < smallest)
                smallest = number;
        }

        Console.WriteLine($"Largest number is {largest}.");
        Console.WriteLine($"Smallest number is {smallest}.");
    }
}
```
- **Example**:
  - Input: `3, 5, 1, 8, 2`
  - Output: 
    ```
    Largest number is 8.
    Smallest number is 1.
    ```

---

### 18. Caesar Cipher (Encryption and Decryption)
- **Description**: Implements Caesar Cipher for encryption and decryption.
- **Implementation**:
```csharp
using System;

class CaesarCipher
{
    static void Main()
    {
        Console.Write("Enter a string: ");
        string input = Console.ReadLine();
        Console.Write("Enter shift value: ");
        int shift = int.Parse(Console.ReadLine());

        string encrypted = Encrypt(input, shift);
        Console.WriteLine($"Encrypted: {encrypted}");

        string decrypted = Decrypt(encrypted, shift);
        Console.WriteLine($"Decrypted: {decrypted}");
    }

    static string Encrypt(string text, int shift)
    {
        char[] result = new char[text.Length];

        for (int i = 0; i < text.Length; i++)
        {
            char c = text[i];
            if (char.IsLetter(c))
            {
                char offset = char.IsUpper(c) ? 'A' : 'a';
                result[i] = (char)((((c + shift) - offset) % 26) + offset);
            }
            else
                result[i] = c;
        }

        return new string(result);
    }

    static string Decrypt(string text, int shift)
    {
        return Encrypt(text, 26 - shift);
    }
}
```
- **Example**:
  - Input: `HELLO`, Shift: `3`
  - Output: 
    ```
    Encrypted: KHOOR
    Decrypted: HELLO
    ```

---

### 19. Tower of Hanoi
- **Description**: Solves the Tower of Hanoi puzzle recursively.
- **Implementation**:
```csharp
using System;

class TowerOfHanoi
{
    static void Main()
    {
        int n = 3; // Number of disks
        SolveHanoi(n, 'A', 'C', 'B'); // A, B and C are names of rods
    }

    static void SolveHanoi(int n, char source, char destination, char auxiliary)
    {
        if (n == 1)
        {
            Console.WriteLine($"Move disk 1 from {source} to {destination}");
            return;
        }

        SolveHanoi(n - 1, source, auxiliary, destination);
        Console.WriteLine($"Move disk {n} from {source} to {destination}");
        SolveHanoi(n - 1, auxiliary, destination, source);
    }
}
```
- **Example**:
  - Output:


    ```
    Move disk 1 from A to C
    Move disk 2 from A to B
    Move disk 1 from C to B
    Move disk 3 from A to C
    Move disk 1 from B to A
    Move disk 2 from B to C
    Move disk 1 from A to C
    ```

---

### 20. Fibonacci Series
- **Description**: Generates the Fibonacci series up to a given number of terms.
- **Implementation**:
```csharp
using System;

class FibonacciSeries
{
    static void Main()
    {
        Console.Write("Enter the number of terms: ");
        int terms = int.Parse(Console.ReadLine());
        int a = 0, b = 1;

        Console.WriteLine("Fibonacci Series:");
        for (int i = 0; i < terms; i++)
        {
            Console.WriteLine(a);
            int temp = a;
            a = b;
            b = temp + b;
        }
    }
}
```
- **Example**:
  - Input: `5`
  - Output:
    ```
    Fibonacci Series:
    0
    1
    1
    2
    3
    ```
