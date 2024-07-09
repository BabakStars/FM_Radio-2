#include <Wire.h>
//#include <radio.h>
#include <TM1637Display.h>
#include <TEA5767.h>


TEA5767 radio = TEA5767();
// Define the connections pins
#define CLK 2
#define DIO 3

#define A 6
#define B 7


float f = 88.0;
// Create a display object of type TM1637Display
TM1637Display display = TM1637Display(CLK, DIO);
/*
// Create an array that turns all segments ON
const uint8_t allON[] = {0xff, 0xff, 0xff, 0xff};
 
// Create an array that turns all segments OFF
const uint8_t allOFF[] = {0x00, 0x00, 0x00, 0x00};
 
// Create an array that sets individual segments per digit to display the word "dOnE"
const uint8_t done[] = {
  SEG_B | SEG_C | SEG_D | SEG_E | SEG_G,           // d
  SEG_A | SEG_B | SEG_C | SEG_D | SEG_E | SEG_F,   // O
  SEG_C | SEG_E | SEG_G,                           // n
  SEG_A | SEG_D | SEG_E | SEG_F | SEG_G            // E
};
 
// Create degree celsius symbol
const uint8_t celsius[] = {
  SEG_A | SEG_B | SEG_F | SEG_G,  // Degree symbol
  SEG_A | SEG_D | SEG_E | SEG_F   // C
};
**/
void setup() {
    Wire.begin();
    Serial.begin(9600);
    display.setBrightness(5);
    radio.setFrequency(f);
    pinMode(A,INPUT);
    pinMode(B,INPUT);
}
 
void loop() {
  
  if(digitalRead(A) == digitalRead(B))
  {
    
  }
  else if(digitalRead(A) == 1 && digitalRead(B) == 0)
  {
    while(digitalRead(A) == 1 && digitalRead(B) == 0)
    {
      
    }
    if(digitalRead(A) == 1 && digitalRead(B) == 1)
    {
      f+=0.1;
      radio.setFrequency(f);
      Serial.println(f);
      //display.showNumberDec(f*10);
    }
  }
  
  else if(digitalRead(A) == 0 && digitalRead(B) == 1)
  {
    while(digitalRead(A) == 0 && digitalRead(B) == 1)
    {
      
    }
    if(digitalRead(A) == 1 && digitalRead(B) == 1)
    {
      f-=0.1;
      radio.setFrequency(f);
      Serial.println(f);
      //display.showNumberDec(f*10);
    }
  }
  else
  {
    
  }

  if(f < 88.0)
  {
    f = 88.0;
  }
  if(f > 108.0)
  {
    f = 108.0;
  }
  display.showNumberDec(f*10);


}
