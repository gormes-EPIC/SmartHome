# Object Lab

## Smart Home

The starter file contains three classes:
- `Lightbulb` which represent a smart lightbulb
- `SmartHome` which represents a smart home which contains a collection of lightbulbs
- `Main` which contains the main method and is used to test your code.

Step 1: The `Lightbulb` class contains three **private instance variables**.
- `String name` - the name of the device
- `boolean isOn` - true if the light is on, false otherwise
- `int powerUsage` - the amount of power the light draws

Step 2: Then, create a **constructor** for the `Lightbulb` class.  The constructor should take in three variables, one for each instance variable.

Step 3: Now, create these methods:

| access modifier | return type | name          | arguments   | description                                           |
| --------------- | ----------- | ------------- | ----------- | ----------------------------------------------------- |
| public          | String      | getName       | ()          | Returns the name of the device                        |
| public          | boolean     | getIsOn       | ()          | Returns the value of isOn                             |
| public          | int         | getPowerUsage | ()          | Returns the power usage value of the light            |
| public          | void        | turnOn        | ()          | Turns on the lightbulb and sets `isOn` appropriately  |
| public          | void        | turnOff       | ()          | Turns off the lightbulb and sets `isOn` appropriately |
| public          | void        | setPowerUsage | (int power) | Changes the power usage to value of `power`           |

Step 4: Test your program using the following main method in the `Main` class
```java
Lightbulb light1 = new Lightbulb("Kitchen", false, 60);
Lightbulb light2 = new Lightbulb("Dining Room", false, 80);

System.out.println(light1.getName()); // Kitchen

light1.turnOn();
System.out.println(light1.getIsOn()); // true
light1.turnOff();
System.out.println(light1.getIsOn()); // false

System.out.println(light2.getPowerUsage()); // 80
```


Step 5: Move to the `SmartHome` class. Start by creating its instance variable: an array of `Lightbulb` objects.

Step 6: Now add a constructor that initializes your array to a size given by the argument `slots`.

Step 7: Create the methods below:

| access modifier | return type | name     | arguments                   | description                                                                                                                                                                            |
| --------------- | ----------- | -------- | --------------------------- |----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| public          | void        | add      | (Lightbulb light, int slot) | Adds the light to the smart home in the slot given. If the slot number is greater than the number of total slots. If there is already something the slot, replace it with the new item.|
| public          | int         | sumTotal | ()                          | Returns the total power usage of the entire `SmartHome`                                                                                                                                 |

Step 8: Test your code with the following main.

```java
SmartHome home = new SmartHome(3);

Lightbulb light1 = new Lightbulb("Kitchen", false, 60);
Lightbulb light2 = new Lightbulb("Dining Room", false, 80);
Lightbulb light3 = new Lightbulb("Living Room", false, 40);

home.add(light1, 0);
home.add(light2, 1);

System.out.println(home.sumTotal()); // 140

home.add(light3, 2);

System.out.println(home.sumTotal()); // 180

Lightbulb light4 = new Lightbulb("Bedroom", false, 40);
home.add(light4, 3); // Throws ArrayIndexOutOfBounds exception
```