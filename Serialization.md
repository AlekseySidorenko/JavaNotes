Serialization
=============

Make object that will work with file:
```java
FileOutputStream fileStream = new FileOutputStream("Save.sv");
```

Make object that will work with serializable objects and send it to FileOutputStream object to write:
```java
ObjectOutputStream objectStream = new ObjectOutputStream(fileStream);
```

Serialize object:
```java
objectStream.writeObject(someObjectToSerialize);
```

Close ObjectOutputStream:
```java
objectStream.close();
```
