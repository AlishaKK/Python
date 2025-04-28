
### What is dependency injection?
Let’s see what the dependency injection is.

Dependency injection is a principle that helps to decrease coupling and increase cohesion.

../_images/coupling-cohesion.png
What is coupling and cohesion?

Coupling and cohesion are about how tough the components are tied.

High coupling. If the coupling is high it’s like using superglue or welding. No easy way to disassemble.

High cohesion. High cohesion is like using screws. Quite easy to disassemble and re-assemble in a different way. It is an opposite to high coupling.

Cohesion often correlates with coupling. Higher cohesion usually leads to lower coupling and vice versa.

Low coupling brings flexibility. Your code becomes easier to change and test.

How to implement the dependency injection?

Objects do not create each other anymore. They provide a way to inject the dependencies instead.
