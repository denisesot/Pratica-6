# Pratica-6
Construir um circuito que faça acender o LED ao pressionar um botão. Ao pressionar novamente, o LED deve desligar. A checagem do estado do botão deve ser feito por pooling. 

int flag = 0, flagTemp = flag;

void setup()
{
  pinMode(13, OUTPUT);
  pinMode(2, INPUT);
  Serial.begin(9600);
}

void loop(){
  
  if (digitalRead(2) == HIGH){
    if (flagTemp != flag) return;
  	flag = !flag;
  }else{
  	flagTemp = flag;
  }
  
  if (flag) {
    digitalWrite(13, HIGH);
    Serial.println("Led ligada.");
  }else {
    digitalWrite(13, LOW);
    Serial.println("Led desligada.");
  }
    
} 
