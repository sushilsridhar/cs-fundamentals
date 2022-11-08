# Reflection

> reflection is about reading the class itself, reading the blueprint, at runtime

Java object exists only inside JVM, it is programming lanugage construct,     

<ins>Serialization</ins>: convert java object to bytes, (storage to disk or send over network)    
<ins>deserializaiton</ins>: convert bytes to java object    

<ins>Class class</ins>          

        Class objClass = o.getClass();
objClass is an object, a reference to a class itself, a place in memory which has the definition of class itself,               
the blueprint itself can be refered as object and can be pointed to, passsed around             


<ins>GSON library</ins>         
Gson know what fields are inside the Person object by using reflection, 

```
        Gson gson = new Gson();

        Person person = new Person(2, "john");
        String json = gson.toJson(person);
        System.out.println("json: "+json);

        Person p = gson.fromJson("{\"age\":2,\"name\":\"john\"}", Person.class);
        System.out.println("obj: "+p.age +" "+ p.name);
```

<ins>Example of reading Fields using reflection</ins>           
```
    printFields(person);
    printFields(new Vehicle(4, "red"));

    static void printFields(Object o) throws IllegalAccessException {
        Class c = o.getClass();
        for(Field field: c.getDeclaredFields()) {
            String value = "";
            if (field.getType().equals(int.class)) {
                value = String.valueOf(field.getInt(o));
            }

            if (field.getType().equals(String.class)) {
                value = field.get(o).toString();
            }

            System.out.println("Field: " + field.getName() + " value: " + value);
        }
    }
```
