Perlin Noise Wave Project
This project visualizes a dynamic 2D wave on an OLED display using Perlin noise. A sound sensor modifies the wave's intensity based on detected audio levels.
• ESP32 reads sound sensor values to determine the wave height.
• Perlin noise generates a smooth, natural wave instead of random jagged lines.
• The OLED display continuously updates, creating an animated effect.
• Offset shifts over time, making the wave move across the screen.

This code visualizes a smooth 2D wave on an OLED display, using Perlin noise to generate natural-looking variations. The sound sensor modulates the wave's intensity.

•  Adafruit_SSD1306.h: Handles the OLED display.
•  "PerlinNoise.h": A simple Perlin noise generator for smooth waves.
•  Defines OLED screen size.
•  offsetX shifts the Perlin noise over time for animation.

Wave Drawing Function
•  Generates Perlin noise at each x position.
•  Maps noise value to a y position for wave height.
•  Uses drawLine() to prevent gaps, ensuring a smooth wave.

Main Loop (Updates Display & Reads Sound Sensor)
  Reads sound sensor data.
  Maps sound level to wave intensity.
  Clears & redraws the Perlin noise wave for animation.

Adjust Delay (Prevent Skipping Frames)
Try adding a small delay in loop():
delay(10); // Helps stabilize frame updates

lastY variable stores the previous wave height at each x position
lastY allows drawing a continuous wave by connecting each point to the previous one.
Without it, the display would show disconnected dots instead of a smooth waveform.

