---
title: 'Single Responsibility Principle and Encapsulating Responsibilities'
date: Sun, 08 Sep 2013 16:00:31 +0000
draft: false
tags: ['Code', 'SOLID', ]
---

As the name suggests, the single responsibility principle states that a class should have a single responsibility and also that it's responsibility should be entirely encapsulated by the class.

For example, let's say we are writing a class that sends messages. We could write something like this

> public class MessageSender
> 
> {
> 
> public void SendInstantMessage(Message message) { ... }  
> public void SendEmail(Email email) { ... }
> 
> }

I like to think of responsibilities as reasons to change, so this class has two reasons to change: 

1.  To change how we send emails
2.  To change how we send instant messages

Clearly this violates the SRP. Instead we could write something like this

> public class InstantMessageSender
> 
> {
> 
> public void SendInstantMessage(Message message) { ... }
> 
> }
> 
> public class EmailSender
> 
> {
> 
> public void SendEmail(Email email) { ... }
> 
> }

This code satisfies both parts of the definition: each class only has one responsibility and the responsibilities are fully encapsulated within each class. 

Now let's say that our next requirement is a user sign up process. If as part of this we were to add some code that sends a confirmation email, then we would be breaking the SRP unless we were to use our EmailSender class. If we were to add the code to send the email without using the EmailSender class then the responsibility would not be fully encapsulated by our class. It would mean that if we needed to change how we connect to our email server for example, then we would have to remember to make changes in several places.

Making changes like this makes our code less maintainable. At some point someone will forget to update one of the places and the system will end up broken. Let's try and avoid breaking things and keep things SOLID.