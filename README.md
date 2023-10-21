# -Calculator-Assignment

#  the Calculator Class

public class Calculator {
    public int add(int a, int b) {
        return a + b;
    }

    public int subtract(int a, int b) {
        return a - b;
    }

    public int divide(int a, int b) {
        if (b == 0) {
            throw new ArithmeticException("Cannot divide by zero");
        }
        return a / b;
    }

    public int modulo(int a, int b) {
        if (b == 0) {
            throw new ArithmeticException("Modulo by zero is undefined");
        }
        return a % b;
    }
}




# JUnit Test Cases


import org.junit.jupiter.api.Test;
import static org.junit.jupiter.api.Assertions.*;

public class CalculatorTest {
    Calculator calculator = new Calculator();

    @Test
    public void testAddPositiveNumbers() {
        int result = calculator.add(5, 3);
        assertEquals(8, result);
    }

    @Test
    public void testSubtractNegativeNumbers() {
        int result = calculator.subtract(-5, -3);
        assertEquals(-2, result);
    }

    @Test
    public void testDivideByZero() {
        assertThrows(ArithmeticException.class, () -> calculator.divide(10, 0));
    }

    @Test
    public void testModuloPositiveNumbers() {
        int result = calculator.modulo(10, 3);
        assertEquals(1, result);
    }

    @Test
    public void testAddNegativeAndPositiveNumbers() {
        int result = calculator.add(-5, 3);
        assertEquals(-2, result);
    }

    @Test
    public void testSubtractPositiveAndNegativeNumbers() {
        int result = calculator.subtract(5, -3);
        assertEquals(8, result);
    }
}

