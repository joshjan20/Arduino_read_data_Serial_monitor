# Arduino Serial Communication Example

This Arduino project demonstrates how to use serial communication to interact with the user through the **Serial Monitor**. The program prompts the user to enter a number, and once entered, it reads the input, processes it, and displays the entered number back to the user.

## Project Overview

- **`void setup()`**: Initializes the serial communication and prints an initial message to the user.
- **`void loop()`**: Continuously checks if data is available from the Serial Monitor. If data is available, it reads the input number, and then prints the number back to the user.

### Code Explanation

```cpp
void setup() {
  // Start the serial communication at 9600 baud rate
  Serial.begin(9600);
  // Print an initial message
  Serial.println("Enter a number:");
}

void loop() {
  // Check if there's data available from the Serial Monitor
  if (Serial.available() > 0) {
    int number = Serial.parseInt(); // Read the number entered
    Serial.print("You entered: ");
    Serial.println(number);
  }
}
```

### Breakdown:

1. **`Serial.begin(9600);`**  
   - Starts the serial communication at a baud rate of 9600, which is the rate at which data is transmitted over the serial port. The baud rate must match the Serial Monitor setting.

2. **`Serial.println("Enter a number:");`**  
   - Prints a prompt message to the Serial Monitor, asking the user to enter a number.

3. **`Serial.available() > 0`**  
   - Checks if there is any data available in the serial buffer (i.e., if the user has typed something in the Serial Monitor).

4. **`Serial.parseInt()`**  
   - Reads the entered number from the serial buffer and stores it in an integer variable (`number`).

5. **`Serial.print()` and `Serial.println()`**  
   - Outputs the message `"You entered: "` followed by the number entered by the user.

### How to Use:

1. **Upload the code** to your Arduino board using the Arduino IDE.
2. Open the **Serial Monitor** from the Tools menu or by clicking the magnifying glass icon in the Arduino IDE.
3. Set the **baud rate to 9600** (located in the bottom right corner of the Serial Monitor).
4. Enter a number in the Serial Monitor's input field and press "Enter" or "Send."
5. The Serial Monitor will display the message `"You entered: "` followed by the number you typed.

### Example Interaction:

```
Enter a number:
25
You entered: 25
```

### Required Hardware:

- **Arduino Board** (e.g., Arduino Uno)
- **USB Cable** for connecting Arduino to the computer
- **Arduino IDE** for uploading the code and interacting via the Serial Monitor

### Image of Example Setup:

![Arduino Serial Communication](https://www.arduino.cc/en/uploads/Main/ArduinoUnoFront_2.jpg)

### Takeaway:

This basic Arduino program allows you to communicate with the Arduino board via the Serial Monitor, which is useful for debugging, user input, and many other applications involving serial data exchange. The program reads a number entered by the user and responds by printing it back to the Serial Monitor.