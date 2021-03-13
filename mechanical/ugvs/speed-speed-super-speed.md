# Speed car super speed

The Speed Car Super Speed \(SCSS\) ~~is~~ was a four wheeled prototype UGV which took 10 minutes to build and 50 hours to figure out how to use and debug. Much of the [Mission Planner documentation](../../software-1/programming/mission-planner.md) and this page are a testament to the tough work of getting things to function as expected. Some key takeaways are described at the bottom of this page.

![](../../.gitbook/assets/image%20%2849%29.png)

Takeaways:

* 4 wheels is not the move because it's not space effective, prone to bottoming out, low to the ground, and more!
* The placement of the GPS in such a tight space is super important, but location also matters. Some places at certain times just don't have good connection. Always place the GPS away from other components and as high as possible.
* The battery and the bottle are the heaviest objects and almost entirely influence the COM.
* For small vehicles, grass is the main enemy. Even short grass can create a soft bed on which it is impossible to progress. Mesh wheels do not work. Compliant wheels do not work. Hard wheels do not work. See the [SPARTA \(Servo Powered Autonomous Rough Terrain Automobile\)](sparta-servo-powered-autonomous-rough-terrain-automobile.md) page to learn more about how we partially solve this.
* The wiring is basically standard, so you shouldn't need to change anything between one UGV and another.
* The transmitter/receiver is very strong, so you shouldn't worry about losing connection with it.
* Thing that interfere with GPS signals include rough terrain, buildings, anything that visually blocks your line of sight of the sky. This GPS module has peaked around 17 or 18 satellites, with 10 being the bare minimum to have the accuracy we desire.



