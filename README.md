## Calculator Division Application
This repository contains a simple Java application that provides basic division functionality, along with unit tests to ensure the correctness of the implementation. The code is primarily designed to demonstrate concepts in Software Verification and Validation.

### Project Structure
The project is structured as follows:

### Calculator.java: 
This is the main class that contains the divide method, which performs the division of two numbers.
### CalculatorTest.java: 
This class contains unit tests written using JUnit to test the divide method in Calculator.java.
### Calculator Class
The Calculator class provides a method to divide two double numbers:
```
public double divide(double a, double b) {
    if (b == 0) throw new IllegalArgumentException("Divide by zero exception.");
    return a / b;
}
```
### Method Details:
divide(double a, double b):
### Parameters:
a - Dividend (the number to be divided)
b - Divisor (the number by which the dividend is divided)
### Returns: 
The quotient of the division.
### Throws: 
IllegalArgumentException if the divisor b is zero, to prevent division by zero.
### Unit Tests
Unit tests are written in CalculatorTest.java using JUnit 5. The tests validate the behavior of the divide method in the Calculator class.

### Test Cases:
### Parameterized Test:
This test checks various division scenarios using a set of predefined input values and their expected results.
Example cases include dividing 20 by 2 (expected result: 10), and 15 by 5 (expected result: 3).
```
@ParameterizedTest
@CsvSource({
    "20, 2, 10",
    "15, 5, 3",
    "10, 4, 2.5",
    "30, 2.5, 12",
    "45, 2.5, 18"
})
```
```
void testDivision(double dividend, double divisor, double expectedQuotient) {
    Calculator calculator = new Calculator();
    double result = calculator.divide(dividend, divisor);
    Assertions.assertEquals(expectedQuotient, result);
}
```
### Division by Zero Test:
This test checks if the divide method correctly throws an IllegalArgumentException when attempting to divide by zero.
@Test
void testDivisionByZero() {
    Calculator calculator = new Calculator();
    Exception exception = Assertions.assertThrows(
        IllegalArgumentException.class,
        () -> calculator.divide(22, 0),
        "IllegalArgumentException expected."
    );
}
### How to Run
* Clone the Repository:
git clone https://github.com/cebo54/Software-Verification-Validation.git
* Navigate to the Project Directory:
cd Software-Verification-Validation

### Build and Run Tests:
Use Maven or any other build tool compatible with JUnit to compile the project and run the tests.

### Check Results:
The test results will indicate whether the division functionality works as expected.

### Author
* Student Name: Cebrail Kaya
* Student ID: B201202016
* Course Name: Software Verification and Validation
