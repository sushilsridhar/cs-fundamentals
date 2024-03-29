# Reflection

> reflection is about reading the class itself, reading the blueprint, at runtime

Java object exists only inside JVM, it is programming lanugage construct,     

<ins>Serialization</ins>: convert java object to bytes, (storage to disk or send over network)    
<ins>deserializaiton</ins>: convert bytes to java object    

> final variable in java can be changed using reflection

<ins>Class class</ins>          

```
Class objClass = o.getClass();
```
objClass is an object, a reference to a class itself, a place in memory which has the definition of class itself,               
the blueprint itself can be refered as object and can be pointed to, passsed around             

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
    
Field: age value: 2
Field: name value: john
Field: color value: red
Field: wheels value: 4    
```

<ins>GSON library</ins>         
Gson know what fields are inside the Person object by using reflection, 

```
        Gson gson = new Gson();

        Person person = new Person(2, "john");
        String json = gson.toJson(person);
        System.out.println("json: "+json);

        Person p = gson.fromJson("{\"age\":2,\"name\":\"john\"}", Person.class);
        System.out.println("obj: "+p.age +" "+ p.name);
        
        json: {"age":2,"name":"john"}
        obj: 2 john
```

<ins>Jackson library</ins>              
uses reflection for conversion,         

```
        Vehicle vehicle = new Vehicle(4, "white");

        ObjectMapper mapper = new ObjectMapper();
        String pJson = mapper.writeValueAsString(vehicle);
        System.out.println(pJson);

        Vehicle vObjMapper = mapper.readValue("{\"color\":\"white\",\"wheels\":4}", Vehicle.class);
        System.out.println(vObjMapper.wheels+" "+ vObjMapper.color);
        
        {"color":"white","wheels":4}
        4 white
```


# GSON vs Jackson   

<ins>Gson</ins>         
to use just import single library,              
> does not require getters and setters for bean class, hence simple to use      

<ins>Jackson</ins>              
to use, need multiple libraries, jackson core, jackson databind, etc,           
> require getters, setters and default public constructor for bean class, making it complex than gson 

Throws error, if fields are missing in Bean, on conversion from json to Bean,               

