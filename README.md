# the-robot-to-run-on-a-path-shaped-like-infinity
int left_wheelA = 27; int left_wheelB = 26;
int right_wheelA = 25; int right_wheelB = 33;
int EN_L = 14; int EN_R = 32;
const int freq = 5000;
const int Channel_1 =0;
const int Channel_2 = 1;
const int resolution=8;
void setup(){
pinMode(left_wheelA, OUTPUT); pinMode(left_wheelB, OUTPUT);
pinMode(left_wheelB, OUTPUT); pinMode(left_wheelA, OUTPUT);
pinMode(right_wheelA, OUTPUT); pinMode(right_wheelB, OUTPUT);
// configure PWM functionalitites
ledcSetup(Channel_1, freq, resolution);
ledcSetup(Channel_2, freq, resolution);
// attach the channel to the GPIO to be controlled
ledcAttachPin(left_wheel_EN, Channel_1);
ledcAttachPin(right_wheel_EN, Channel_2);
delay(2000); } void loop() {
ledcWrite(Channel_1000);
ledcWrite(Channel_1200);digitalWrite(left_wheelA, HIGH); digitalWrite(left_wheelB,LOW);
digitalWrite(right_wheelA, LOW); digitalWrite(right_wheelB, HIGH);
delay(2000);
ledcWrite(Channel_1, 200);
ledcWrite(Channel_2, 100);
digitalWrite(left_wheelA, LOW); digitalWrite(left_wheelB, LOW);
digitalWrite(right_wheelA, LOW); digitalWrite(right_wheelB, HIGH);
delay(1000);
ledcWrite(Channel_1, 450);
ledcWrite(Channel_2, 450);
digitalWrite(left_wheelA, HIGH); digitalWrite(left_wheelB,LOW);
digitalWrite(right_wheelA, LOW); digitalWrite(right_wheelB, HIGH);
delay(2000);
ledcWrite(Channel_1, 200);
ledcWrite(Channel_2, 200);
digitalWrite(left_wheelA, HIGH); digitalWrite(left_wheelB, LOW );
digitalWrite(right_wheelA, LOW); digitalWrite(right_wheelB, LOW);
delay (1000);
}
