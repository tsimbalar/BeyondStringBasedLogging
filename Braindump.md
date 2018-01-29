# Beyond string-based logging

You have probably used ( or even written!) a logging library before ...

And from a developer perspective it probably looked like this 

`log.info("Home page for customer %s loaded in %d ms", customerName, duration)`

and you ended up with log messages that looked like these .... 

```
2012-12-12 11:51:11,332 [main] INFO: App is starting
2012-12-12 11:56:19,643 [Cart] INFO: Customer john@doe.com added 5 items to the cart
2012-12-12 11:56:19,902 [Home] INFO: Home page for customer john@doe.com loaded in 3 ms
2012-12-12 11:57:32,042 [Cart] INFO: Customer john@doe.com added 1 items to the cart
2012-12-12 11:58:17,902 [Home] INFO: Home page for customer paul.smith@gmail.com loaded in 1 ms
2012-12-12 11:59:13,631 [Cain] INFO: Customer paul.smith@gmail.com added 1 items to the cart
2012-12-12 11:59:43,902 [Home] INFO: Home page for customer paul.smith@gmail.com loaded in 4 ms
```

... and that's fine and you happily carry on until your little app is just one component of a bigger distributed system and you are trying to make sense of what is going on 

and then some time later your app is running in production and somebody asked you a question like "Can you list me the customers for which the home page took >3 ms to load today, please ?" 


now you have to extract data from text ...
it can be done, there's lots of tools to in gest log messages, but if you go back up , we had the information, it was separated ! (logstash, kibana ... )

 it's silly, it was well separated in the first place : 

`log.info("Home page for customer %s loaded in %d ms", customerName, duration)`

What if we actually kept that data separated from the message so we can actually access it for processing ?

Log Messages -> Log Events = "structured logging" ... 

+ message template 

(pictures + explanations from messagetemplates.org)


Keep formatting for later


This is the idea behing the open source .NET Library Serilog (but several others on other platforms too ;) )

Standards "sinks" like console, text etc ... but it gets interesting when you can preserve the structure
ex : 
document databases (mongo) , or relational databases like postgres that support json columns , or into centralized logging platforms like Logstash or Splunk .... 












