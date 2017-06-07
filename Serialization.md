Сериализация:

Создаем объект, который будет непосредственно работать с файлом:
FileOutputStream fileStream = new FileOutputStream("Save.sv");

Создаем объект, который будет работать с сериализуемыми объектами 
и передавать их для записи в объект FileOutputStream:
ObjectOutputStream objectStream = new ObjectOutputStream(fileStream);

Сериализуем объект:
objectStream.writeObject(someObjectToSerialize);

Закрываем ObjectOutputStream:
objectStream.close();