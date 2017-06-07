Сериализация
=============

Создаем объект, который будет непосредственно работать с файлом:
```java
FileOutputStream fileStream = new FileOutputStream("Save.sv");
```

Создаем объект, который будет работать с сериализуемыми объектами 
и передавать их для записи в объект FileOutputStream:
```java
ObjectOutputStream objectStream = new ObjectOutputStream(fileStream);
```

Сериализуем объект:
```java
objectStream.writeObject(someObjectToSerialize);
```

Закрываем ObjectOutputStream:
```java
objectStream.close();
```
