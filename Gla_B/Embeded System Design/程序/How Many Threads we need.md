
~~~text
thread_1 :
	SR04 -> no pet Food -> Servo Engine move to fill food
thread_2 :
	Press Button -> Pump start to fill water
thread_3 : 
	Bluetooth receive data -> Some actions were taken
		Actions example: Pump works/Servo Engine works
thread_4:
	Bluetooth chip send data to the Phone
thread_5:
	The camera works.
thread_6:
	The weight sensor -> throw the pet food
	Human sensor -> Stop the engine throwing food when cats are there.
~~~