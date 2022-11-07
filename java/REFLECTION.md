# Reflection

> reflection is about reading the class itself, reading the blueprint, at runtime

Java object exists only inside JVM, it is programming lanugage construct,     

<ins>Serialization</ins>: convert java object to bytes, (storage to disk or send over network)    
<ins>deserializaiton</ins>: convert bytes to java object    

        Class objClass = o.getClass();
objclass is an object, a reference to a class itself, a place in memory which has the definition of class itself

the blueprint itself can be object and can be passsed around, we can refer to the blueprint as an object, pointn to it, pass around
