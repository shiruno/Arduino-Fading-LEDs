## Breadboard Diagram
![987bad](https://github.com/user-attachments/assets/636bacc9-47b8-4dfc-abd3-c061c9ef03fe)

1. Variables Declaration
   -  `pinArray[]`: An array that holds the pin numbers (3, 5, 6, 9, 10) to which the LEDs are connected.
   -  `brightnessLevel`: A variable to track the current brightness level of the LED (not used effectively in the fadeLED function).
   -  `fadeValue`: The amount by which the brightness level will change in each step of the fade (5).
   -  `pointer`: A variable used as an index in loops.
2. Setup Function
   -  This function runs once when the program starts. It initializes each pin in `pinArray` as an output pin using a loop.
3. Loop Function
   -  The `loop()` function runs continuously. It first fades in each LED connected to the pins in `pinArray` by calling `fadeLED` with `fadeIn` set to `true`.
   -  After all LEDs have faded in, it then fades them out by calling `fadeLED` with `fadeIn` set to `false`.
4. `fadeLED(int pin, bool fadeIn)` Function
   - This function controls the fading of a single LED.
   - It takes two parameters: `pin` (the pin number for the LED) and `fadeIn` (a boolean indicating whether to fade in or out).
   - Inside the function:
     - `brightnessLevel` is initialized to 0 if fading in, or 255 if fading out.
     - `fadeValue` is set to 5 for fading in and -5 for fading out.
     - A `while` loop runs as long as the brightness level is within the valid range (0 to 255) for the specified fade direction.
     - Inside the loop:
       - `analogWrite(pin, brightnessLevel)` sets the brightness of the LED.
       - `brightnessLevel` is updated by adding `fadeValue`.
       - `delay(20)` introduces a short pause to control the speed of the fade.
       - The loop will break if `brightnessLevel` goes out of bounds (less than 0 or greater than 255).

The code creates a smooth fading effect for multiple LEDs connected to specified pins on an Arduino. Each LED fades in to full brightness and then fades out, one after the other, creating a visually appealing effect. The use of analogWrite() allows for varying brightness levels, while the delay() function controls the speed of the fading.
