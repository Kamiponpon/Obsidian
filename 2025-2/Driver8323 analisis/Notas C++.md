
# Class
las variables de _Class_ son similar a la estructura, pero hacen son mas simples de utilizar

aqui un ejemplo por gepetes:

```GEPETE EJEMPLO CLASS
class led {
public:
	Led(PinName pin) : led(pin) {} // <- estructura por la cual se setea la variable
	void on() { led = 1; } //<- "PinName"
}
```