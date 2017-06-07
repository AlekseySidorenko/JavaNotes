Serialization
=============

* All objects linked with serializable object must implement Serializable
* some object's fields can't be saved with whole object:
```java
transient String field;
```




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

Serializable class sample:
--------------------------
```java
public class Box implements Serializable {
    private int width;
    private int height;

    public void setWidth() { ... }
    public void setHeight() { ... }
}

public static void main(String[] args) {
    Box box = new Box();
    box.setWidth(50);
    box.setHeight(40);

    try {
      FileOutputStream fs = new FileOutputStream("save.sv");
      ObjectOutputStream os = new ObjectOutputStream(fs);
      os.writeObject(box);
      os.close;
    } catch (Exception e) {
      e.printStackTrace;
    }
}
```

Deserialization
===============

Make object that will work with file:
```java
FileInputStream fileStream = new FileInputStream("Save.sv");
```
Make object that will work with serializable objects and get it from FileInputStream object :
```java
ObjectInputStream objectStream = new ObjectInputStream(fileStream);
```
Read object:
```java
Object one = objectStream.readObject();
```

Cast object:
```java
SomeType someType = (SomeType) one;
```

Close ObjectInputStream:
```java
objectStream.close();
```
