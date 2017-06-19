# Template Pattern

### A. The Problem 

Think back to our discussion about composition.  Imagine we have a driver and sometimes he drives a car and other times he drives a bicycle.

```ruby
class Driver
	attr_reader :vehicle 
	
	def vehicle=(vehicle)
		@vehicle = vehicle
	end
	
	def drive
		if vehicle.class == Bicycle
			vehicle.pedal
		else
			car.press_gas
		end
	end
end
	
class Bicycle
	def pedal
		puts "I'm pedaling"
	end
end

class Car
	def press_gas
		puts "My ankle's tired"
	end
end 
```  

Lots of time with code, a code smell lies with an if else statement.  This is an example of this.  The problem is that the code calls different methods for the different types of objects, when it should really be calling the same method: drive.  

Here is the code refactored.  

```ruby
class Driver
	attr_reader :vehicle 
	
	def vehicle=(vehicle)
		@vehicle = vehicle
	end
	
	def drive
		vehicle.drive
	end
end
	
class Bicycle
	def drive
		puts "I'm pedaling"
	end
end

class Car
	def drive
		puts "My ankle is tired"
	end
end      
```

We see this pattern of having two different objects respond to the same methods in the template pattern, and a related pattern, called duck typing.

### Solution 

* [Template Pattern](https://github.com/nslocum/design-patterns-in-ruby#template-method)
* [Duck Typing](https://robots.thoughtbot.com/back-to-basics-polymorphism-and-ruby)
* [Template Pattern Metz Talk](https://www.youtube.com/watch?v=8bZh5LMaSmE&list=PLFQBiiaZoyrcTBYAGAUjvEUI6TUrp110W)

### Additional Resources

* *Practical Object Oriented Design in Ruby* - Chapters 4, 5
* *Design Patterns in Ruby* - Chapter 3

<p class='util--hide'>View <a href='https://learn.co/lessons/duck-typing-template-pattern'>Duck Typing Template Pattern</a> on Learn.co and start learning to code for free.</p>
