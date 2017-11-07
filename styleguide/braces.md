# Programming Styleguide

## Braces
Braces are somewhat controversial. It's a cosmetic argument, and not really much else. There are a lot of ways of approaching them, and the one that we will be using is just one of the many available options.

### What we will use
```java 
double speed = joystick.getRawAxis(0);  // get y axis from left stick on the controller
if (speed < 0) {
  motor.set(speed);
}
else {
  motor.set(0);
}
```
The important thing to notice is that braces (aka curly braces) that start the scope, `{`, are on the same line as the statement that starts the scope. For example, `if (speed < 0) {` has the curly brace on the same line as the `if` statement. On the other hand, braces that close a scope, `}`, get their own line, even when followed by an associated statement. For example, notice that the `else` statement is on a different line from the `}` from the previous `if` statement.

**You can stop reading here, but continue on if you are curious about other common ways that braces are used.** You may see these in other places, but not in Team 3082's code!

### Alternative 1
```java 
double speed = joystick.getRawAxis(0);  // get y axis from left stick on the controller
if (speed < 0) 
{
  motor.set(speed);
}
else 
{
  motor.set(0);
}
```
This is probably the most common alternative. Essentially, `{` and `}` are both given their own line. It uses extra space, but it is extra clear where scopes start and end.

### Alternative 2
```java 
double speed = joystick.getRawAxis(0);  // get y axis from left stick on the controller
if (speed < 0) {
  motor.set(speed);
} else {
  motor.set(0);
}
```

In this case, the `}` doesn't have its own line when followed by an else statement. However, the word `else` is not aligned with the word `if`, which can be a bit annoying.
