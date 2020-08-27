/**
 * CS 2110 Fall 2019 HW2
 * Part 2 - Coding with bases
 *
 * @author Anusha Prasad
 *
 * Global rules for this file:
 * - You may not use more than 2 conditionals per method. Conditionals are
 *   if-statements, if-else statements, or ternary expressions. The else block
 *   associated with an if-statement does not count toward this sum.
 * - You may not use more than 2 looping constructs per method. Looping
 *   constructs include for loops, while loops and do-while loops.
 * - You may not use nested loops.
 * - You may not declare any file-level variables.
 * - You may not declare any objects, other than String in select methods.
 * - You may not use switch statements.
 * - You may not use the unsigned right shift operator (>>>)
 * - You may not write any helper methods, or call any other method from this or
 *   another file to implement any method.
 * - The only Java API methods you are allowed to invoke are:
 *     String.length()
 *     String.charAt()
 * - You may not invoke the above methods from string literals.
 *     Example: "12345".length()
 * - When concatenating numbers with Strings, you may only do so if the number
 *   is a single digit.
 *
 * Method-specific rules for this file:
 * - You may not use multiplication, division or modulus in any method, EXCEPT
 *   decimalStringToInt.
 * - You may declare exactly one String variable each in intToBinaryString and
 *   and intToHexString.
 */
public class Bases
{
    /**
     * Convert a string containing ASCII characters (in binary) to an int.
     * You do not need to handle negative numbers. The Strings we will pass in will be
     * valid binary numbers, and able to fit in a 32-bit signed integer.
     *
     * Example: binaryStringToInt("111"); // => 7
     */
    public static int binaryStringToInt(String binary)
    {

        int intSum = 0;
        int binaryPower = 0;
        for (int i = binary.length()-1; i > -1; i--) {
            //when equivalent to 1 will add power of 2 to sum
            if (binary.charAt(i) == '1') {
                intSum += (0x1 << binaryPower);
            }
            //increments power while traversing string
            binaryPower++;
        }
        return intSum;
    }

    /**
     * Convert a string containing ASCII characters (in decimal) to an int.
     * You do not need to handle negative numbers. The Strings we will pass in will be
     * valid decimal numbers, and able to fit in a 32-bit signed integer.
     *
     * Example: decimalStringToInt("123"); // => 123
     *
     * You may use multiplication, division, and modulus in this method.
     */
    public static int decimalStringToInt(String decimal)
    {
        int intSum = 0;
        int deciPower = 1;
        //keeping track of integer values for string characters
        int intVal = 0;
        for (int i = decimal.length()-1; i > -1; i--) {
            //to obtain integer value of character
            intVal = decimal.charAt(i) - 48;
            //multiplied by multiples of 10 to match with decimal place
            intSum += intVal * deciPower;
            //to increase to ones, tenths, hundreths, etc. place (i.e. decimal place)
            deciPower *= 10;
        }
        return intSum;
    }

    /**
     * Convert a string containing ASCII characters (in hex) to an int.
     * The input string will only contain numbers and uppercase letters A-F.
     * You do not need to handle negative numbers. The Strings we will pass in will be
     * valid hexadecimal numbers, and able to fit in a 32-bit signed integer.
     *
     * Example: hexStringToInt("A6"); // => 166
     */
    public static int hexStringToInt(String hex)
    {
        int intSum = 0;
        int hexPower = 0;
        //keeping track of integer values for hexadecimal characters
        int intVal = 0;
        for (int i = hex.length() - 1; i > -1; i--) {
            intVal = hex.charAt(i);
            //must account for both 0 - 9 and A - F
            if (intVal <= 64) {
                //for characters NOT including A - F (i.e. numbers 0 - 9)
                intSum += ((intVal - 48) << hexPower);
            } else {
                //for uppercase characters A - F
                intSum += ((intVal - 55) << hexPower);
            }
            //to add to sum by a power including multiples of 4 (i.e. base 16 = 2^4)
            hexPower += 4;
        }
        return intSum;
    }

    /**
     * Convert a int into a String containing ASCII characters (in binary).
     * You do not need to handle negative numbers.
     * The String returned should contain the minimum number of characters necessary to
     * represent the number that was passed in.
     *
     * Example: intToBinaryString(7); // => "111"
     *
     * You may declare one String variable in this method.
     */
    public static String intToBinaryString(int binary)
    {
        String binaryString = "";
        int amountRemain = 0;

        //complex case
        if (binary != 0) {
            for (int i = binary; i > 0; i >>= 1) {
                amountRemain = i & 0x1;
                binaryString = amountRemain + binaryString;
            }
            return binaryString;
        }
        return "0";
    }
    /**
     * Convert a int into a String containing ASCII characters (in hexadecimal).
     * The output string should only contain numbers and uppercase letters A-F.
     * You do not need to handle negative numbers.
     * The String returned should contain the minimum number of characters necessary to
     * represent the number that was passed in.
     *
     * Example: intToHexString(166); // => "A6"
     *
     * You may declare one String variable in this method.
     */
    public static String intToHexString(int hex)
    {
        String hexString = "";
        int amountRemain = 0;

        //complex case
        if (hex != 0) {
            for (int i = hex; i > 0; i >>= 4) {
                amountRemain = (i - ((i >> 4) << 4));
                if (amountRemain >= 10) {
                    //to obtain character letters between A - F
                    hexString = ((char)(amountRemain + 55)) + hexString;
                } else {
                    //to obtain character numbers between 0 - 9
                    hexString = ((char)(amountRemain + 48)) + hexString;
                }
            }
            return hexString;
        }
        return "0";
    }
}
