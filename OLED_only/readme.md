# Wire up and drive an OLED display

![fritzing diagram](OLED_only_fritzing.png)

```cpp
#include <Adafruit_CharacterOLED.h>

/*
	Wiring Guide:

	OLED pin  <-->   ESP32 pin
		4 (rs)          14
		5 (rw)          32
		6 (en)          15
		11 (d4)          33
		12 (d5)          27
		13 (d6)          12
		14 (d7)          13

	Adafruit_CharacterOLED lcd(OLED_V2, version, rs, rw, en, d4, d5, d6, d7);
*/
Adafruit_CharacterOLED lcd(OLED_V2, 14, 32, 15, 33, 27, 12, 13);

void setup()
{
	Serial.println();
	Serial.println("In setup");
	
	Serial.begin(115200);
	delay(100);

	lcd.begin(16, 2);
	lcd.clear();
	lcd.setCursor(0,0);
	lcd.print("The LCD works");
}


void loop()
{
	delay(5000);

	Serial.println("another pass through the loop");
	lcd.clear();
	lcd.setCursor(0,0);
	lcd.print("Still working!");
}
```
