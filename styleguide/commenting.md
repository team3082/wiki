# Programming Styleguide

## Commenting
Comments are an extremely important part of programming, especially on a team. Since many people will read your code, you need to make it very clear what you are doing, within reason. Here are some examples (with placeholder functions):

### Bad Example \#1

```java
if (button.isPressed()) {
  if (!shooter.isFullSpeed) {
    shooter.spinUp();
    loader.stop();
  }
  else {
    loader.load();
  }
}
else {
  shooter.stop();
  loader.stop();
}
```
The person who wrote this program has no comments! It may be hard to know why they chose to keep the loader off until the shooter is at full speed.

### Bad Example \#2

```java
if (button.isPressed()) { // check if the button is pressed
  if (!shooter.isFullSpeed) { // check if the shooter is at full speed
    shooter.spinUp(); // if it is not at full speed, then spin it up
    loader.stop();  // and stop the loader so that the robot doesn't shoot balls when it's not ready
  }
  else { // if the shooter is ready
    loader.load(); // load balls into it
  }
}
else { // if the button is not pressed
  shooter.stop(); // stop the shooter
  loader.stop(); // and the loader, since the operator doesn't want to shoot right now.
}
```
The person who wrote this clearly had good intentions. It is quite obvious what they want to do, since they have explained all of their logic. But don't you think that it's a bit much? We know what the statement `if (button.isPressed())`, for example, means, so it doesn't have to be explained.

### Good Example
```java
if (button.isPressed()) {
  if (!shooter.isFullSpeed) {
    shooter.spinUp();
    loader.stop(); // stop the loader so we don't shoot when the flywheel is not up to speed
  }
  else {
    loader.load(); // load balls only when the shooter is spinning fast enough
  }
}
else {
  shooter.stop(); // stop both when the operator doesn't want to shoot
  loader.stop();
}
```
This is much more concise, and gets the important logic (specifically the loader logic) across without being superfluous. It's hard to define what the right amount of commenting is, but a general guideline is to keep it within reason, and assume that your readers have at the very least a basic understanding of common programming paradigms.
