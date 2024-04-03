# Date with java.time

## Initialisation

```java

        //LocalDate -> Nur Datum
        LocalDate localDate = LocalDate.now();
        System.out.println("localDate : " + localDate);
        

        //LocalDateTime -> Datum & (Uhr)Zeit
        LocalDateTime localDateTime = LocalDateTime.now();
        System.out.println("LocalDateTime : " + localDateTime);
        

        //ZonedDateTime -> Datum & (Uhr)Zeit & Zeitzone
        ZonedDateTime zonedDateTime = ZonedDateTime.now();
        System.out.println("ZonedDateTime : " + zonedDateTime);
        

        //Instant = Zulu Zeitpunkt
        Instant instant = Instant.now();
        System.out.println("Instant : " + instant);

```
Answer :
```
localDate : 2024-03-27
LocalDateTime : 2024-03-27T14:29:09.002329
ZonedDateTime : 2024-03-27T14:29:09.002683+01:00[Europe/Berlin]
Instant : 2024-03-27T13:29:09.002759Z

Process finished with exit code 0
```

## Converstion in differante Format  
```java
        //Unwandlung Instant in LocalDateTime
        ZoneId zoneId = ZoneId.of("Europe/Berlin");   // ZoneId.systemDefault()
        LocalDateTime converted = instant.atZone(zoneId).toLocalDateTime();
        System.out.println("Converted Instant to LocalDateTime : "+converted);

        //UnwandlungbLocalDateTime in Instant
        Instant convertedInstant = localDateTime.atZone(zoneId).toInstant();
        System.out.println("Converted LocalDateTime to Instant : "+convertedInstant);


        //Format der Zeitangabe anpassen
        //d = Tag / M = Monat / y = Jahr / H = Stunde / m = Minute / s = Sekunde / n = Nano
        DateTimeFormatter formatter = DateTimeFormatter.ofPattern("EEEE  dd.MMM.yyyy  : HH:mm:ss:nn");

        String formattedDate = LocalDateTime.now().format(formatter);
        System.out.println("Umgewandelt mit Formatter : " + formattedDate);
```
Answer :

```
Converted Instant to LocalDateTime : 2024-03-27T14:52:45.950537
Converted LocalDateTime to Instant : 2024-03-27T13:52:45.949822Z
Umgewandelt mit Formatter : Wednesday  27.Mar.2024  : 14:52:45:957311000

Process finished with exit code 0

```

## Differance between two hours
```java
     //Errechnen der Diff. zwichen zwei Zeitpunkten
        LocalDateTime start = LocalDateTime.of(2024,1,12,9,10,0);
        LocalDateTime finish = LocalDateTime.of(2024,2,12,11,0,0);

        long hoursBetween = ChronoUnit.HOURS.between(start,finish);
        System.out.println(hoursBetween);
```
Answer : 
```
745

Process finished with exit code 0
```
