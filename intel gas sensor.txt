int Value = 0;
int LED_1r = 6;
int LED_2g = 7;
int LED_3b = 8;
int buzz = 9;

void setup()
{
  Serial.begin(9600);
  pinMode(LED_1r, OUTPUT);
  pinMode(LED_2g, OUTPUT);
  pinMode(LED_3b, OUTPUT);
  pinMode(buzz, OUTPUT);
}

void loop()
{
  Value = analogRead(0);
  Serial.println(Value);
  if (Value < 300)
  {
    digitalWrite(LED_1r, LOW);
    digitalWrite(LED_2g, HIGH);
    digitalWrite(LED_3b, LOW);
    digitalWrite(buzz, LOW);
  }
  
  else if (Value < 500)
  {
    digitalWrite(LED_1r, LOW);
    digitalWrite(LED_2g, LOW);
    digitalWrite(LED_3b, HIGH);
    digitalWrite(buzz, LOW);
  }

  else if (Value < 700)
  {
    digitalWrite(LED_1r, HIGH);
    digitalWrite(LED_2g, LOW);
    digitalWrite(LED_3b, LOW);
    digitalWrite(buzz, HIGH);
  }
}