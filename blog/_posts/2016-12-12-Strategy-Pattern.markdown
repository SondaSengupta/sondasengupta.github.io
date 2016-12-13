---
layout: post
category: blog
title: "C# Design Patterns: The Strategy Pattern"
img: "/images/macbook.jpg"
homeimage: "blog/blog-img/windows.jpg"
excerpt: "If you are just starting out as a developer, you may have noticed that the majority of people have macbooks. What gives?"
date: 2016-12-12
---

## The Scenario
Congratulations! You just won a contract to code out an app for your city zoo. You specifically are in charge of adding the full inventory of Bear logic, so they can keep track of how to feed the animals. The Zoo wants you to focus on 3 types of bears: Grizzly Bears, Panda Bears, and Teddy Bears and what they eat.

So how would you code it? You can have a bear abstract class that has an abstract method of eat(), in which each bear has to implement a different form of the eat() method like below ...

```C#
using System;
					
public class Program
{
	public static void Main()
	{
		Bear grizzlyBear = new GrizzlyBear();
		grizzlyBear.Eat();
		
		Bear pandaBear = new PandaBear();
		pandaBear.Eat();
	}
}

public abstract class Bear {
	public virtual void Eat()
	{
		Console.WriteLine("I eat Meat!");
	}
}

public class GrizzlyBear : Bear {
	//I will use the default implementation of the eat method inherited from Bear.
	
}

public class PandaBear : Bear {
	public override void Eat()
	{
		Console.WriteLine("I eat Bamboo!");
	}
}

public class TeddyBear : Bear {
	public override void Eat()
	{	
		Console.WriteLine("I don't Eat!");
	
	}
}

CONSOLE OUTPUT:
I eat Meat!
I eat Bamboo!

```

However, the Zoo knows they will be adding more bears soon and many of them eat the same thing (grizzlies and polar bears both eat fish). If each bear owns its own implementation of eat, you know you'll have duplicate code which would be a pain to rework if the Zoo decides to changes their diets.


So how can you write different implementations that are completely decoupled from its clients? The Strategy Pattern, of course!

## The Strategy Pattern: What it Solves and When to Use it
The Strategy Pattern is design to mitigate the chief concern of coupled code. The strategy pattern encapsulates a family of algorithms making them interchangeable and allows these algorithms to vary independently from the client that uses them. 

Advantages of using the strategy pattern include decoupled, encapsulated concrete functionality (strategies). Strategies can be shared and reused over multiple clients. Strategies are easy to update without the client having to know anything about it.

The biggest disadvantage is that it is a bit more setup. If you know for a fact that functionality will never be shared among clients, and you have a small application, then using the pattern may seem like overengineering.

## How it Works
A concrete family of functions all inherit from an interface. This interface is used in the client, which allows each concrete implementation of the client to have the function it needs available for use.

It uses composition, rather than inheritance where the client has-a behavioral strategy as opposed to owning the behavioral strategy itself or inheriting it from a parent.

## Back to the Scenario


