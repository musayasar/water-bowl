# Water Bowl Showing Water Level


## The Place Of Pets In Our Lives

The bond that humans establish with animals dates back to ancient times. Looking at the research, it is possible to see that animals began to be domesticated by humans about 12 thousand years ago. Today, many people continue to share their home and life with one or more pets. You have probably witnessed or experienced the deep bond and relationship that pet owners have established with their pets over time.
Owning a pet comes with a huge responsibility. Because when you adopt a pet, you determine its quality of life and conditions, and you start making friends with a creature that needs you and loves you. As a result of the bond and communication you establish, your lovely friend also contributes a lot to your life.
![köpek](https://blog.dodomama.com/wp-content/uploads/2018/08/kedi-ve-kopek-mamalari.jpg)
## Dogs Need Water

Since puppies meet their fluid needs from mother's milk, they may consume less water, but this should be checked after breast milk. You should get into the habit of drinking water with the support of your new puppy, that is, his mother. A young dog should drink half a glass of water every 2 hours. Their metabolisms work fast and they are very active, so they need to consume a certain amount of water regularly.

Adult dogs should consume an average of 1.5 liters of water each day, but as we mentioned earlier this average amount depends on your dog's age, size, diet and exercise intensity. If your dog does not drink enough water, this causes the body to become dehydrated, that is, excessive water loss.

## Cats Need Water
In cats, the situation is not much different. Of course, in the face of the conditions brought by domestic life, they need more and more regular water than those in the wild.

Kittens meet their fluid needs from breast milk when they drink breast milk, but they need to drink water regularly after weaning from breast milk. Just like puppies, they drink a lot of water, as they are extremely active and playful, it is always necessary to have a glass of water in a clean and easy-to-drink bowl in the playground.

Adult cats should drink at least 1 glass of water per day. This amount may increase depending on the amount of dry food consumed. He should drink at least 4 times the amount of dry food he eats. Wet foods contain close to 70% liquid, but the rate is 10% in dry foods. For this reason, you should make sure that he is drinking enough water if he is fed with dry food. In addition, if you have a young cat or if he is active despite being old, make sure he drinks at least 1 glass of water a day regularly. This amount may increase if you have a regular medication or a chronic illness. In such a case, you should definitely consult a veterinarian. If your cat does not drink enough water, this will cause dehydration, that is, excessive dehydration of the body, just like in dogs.


## The Goal Of The Project

Sometimes we may be separated from our home and our pets due to certain circumstances. I developed my water bowl sensor project for these situations. I prepared my circuit that alarms when the water level in our pets' containers falls below 25% and constantly displays the current water level.
## Arduino Connection

![arduino](https://maker.robotistan.com/wp-content/uploads/2019/05/yagmur-sensoru_bb-1024x355.jpg)

# Water Sensor

The Water Sensor module is part of the Grove system. It indicates whether the sensor is dry, damp or completely immersed in water by measuring conductivity. The sensor traces have a weak pull-up resistor of 1 MΩ. The resistor will pull the sensor trace value high until a drop of water shorts the sensor trace to the grounded trace. Believe it or not this circuit will work with the digital I/O pins of your Arduino or you can use it with the analog pins to detect the amount of water induced contact between the grounded and sensor traces.
![watersensor](https://maker.robotistan.com/wp-content/uploads/2019/05/su-seviyesi-yagmur-sensoru-water-level-rain-sensor-4120-17-B.jpg) 



## LABVIEW FRONT PANEL

![front panel](https://user-images.githubusercontent.com/106698029/172064324-892d8abd-30e5-4402-875e-c3eae4773a6a.png)
## LABVIEW BLOCK DIAGRAM
![block diagram](https://user-images.githubusercontent.com/106698029/172064417-8525657c-aab7-4b19-9d46-18a0a44bf0ba.png)

## Arduino Code of The System

```
int sensorPin = A0; //Sensörü bağlayacağımız pin
int esikDegeri = 100; //Su miktarı için eşik değeri
int buzzerPin = 8; //Buzzerı bağlayacağımız pin
int veri; //Sensörden okuduğumuz değer

void setup() {
  pinMode(buzzerPin, OUTPUT); //Buzzer bağladığımız pini OUTPUT olarak ayarlıyoruz.  
}
void loop() {
  veri = analogRead(sensorPin); //Sensörden analog veriyi okuyoruz.
  if (veri > esikDegeri) { //Sensör verisi eşik değerini geçerse if içerisindeki kodlar uygulanır.
    digitalWrite(buzzerPin, HIGH);
    delay(100);
    digitalWrite(buzzerPin, LOW);
    delay(100);
  } else { //Sensör verisi eşik değerinden küçük olursa if içerisindeki kodlar uygulanır.
    digitalWrite(buzzerPin, LOW);
  }
}
```
