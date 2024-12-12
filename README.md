# vttp-ssf-resources
- Convert Long to LocalDate and vice versa
public class LocalDateConverter {
    public LocalDateConverter(){

    }

    public LocalDate convert(long epoch){
        return Instant.ofEpochMilli(epoch).atZone(ZoneId.of("UTC")).toLocalDate();
    }

    public String convertStringDateToLong(String date){
        LocalDateTime localDateTime = LocalDateTime.parse(date + " 00:00:00",
        DateTimeFormatter.ofPattern("yyyy-MM-dd HH:mm:ss"));
        ZoneId zoneId = ZoneId.of("UTC");
        long epochMilli = localDateTime.atZone(zoneId).toInstant().toEpochMilli();
        return String.valueOf(epochMilli);
    }
}
