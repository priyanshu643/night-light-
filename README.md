# night-light-
// arduino project 
//requirmens arduino, ldr, led 
// connect a LED to the pin number 13 of arduino unoR 3
//connect 10k resister and analog pin in same line of bread boardwith ldr analog pin number A1
//now connect 5v vcc to ldr 
//now connect of boath led and ldr 
int LDR = A1;          // LDR (Light Dependent Resistor) connected to A1
int LED = 13;          // LED connected to pin 13
int threshold = 60;    // Threshold value to control the LED state

void setup() {
  Serial.begin(9600);  // Initialize Serial communication at 9600 baud rate
  pinMode(LED, OUTPUT); // Set the LED pin as an output
}

void loop() {
  int data = analogRead(LDR); // Read the analog value from the LDR
  Serial.print(data);         // Print the analog value to the Serial Monitor

  if (data <= threshold) {    // If the LDR value is below the threshold
    digitalWrite(LED, HIGH);  // Turn the LED on
  } else {
    digitalWrite(LED, LOW);   // Turn the LED off
  }

  delay(100); // Small delay to avoid flooding the Serial Monitor with data
}
