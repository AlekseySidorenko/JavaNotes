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
}
```
