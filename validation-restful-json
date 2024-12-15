Ini fungsi untuk memvalidasi requests restful API format JSON
silahkan gunakan, dan kembangkan

public String validateRequest(Object cls, Map<String, Object> map) throws NoSuchFieldException {
        String atribut = "";
        String status = "";
        for (Field m : cls.getClass().getDeclaredFields()) {
            //System.out.println(m.getName());
            Column optional = m.getAnnotation(Column.class);
            int maxLength = cls.getClass().getDeclaredField(m.getName()).getAnnotation(Column.class).length();
            //System.out.println("optional : "+optional.nullable());
            if (optional.nullable() == false) { //hanya Field Mandatory
                if (map.get(m.getName()) == null) { //kondisi field yang tidak dikirim
                    atribut = m.getName();
                    status ="missing";
                } else {       
                    //jika melebihi length maksimal
                    String dd = (String) map.get(m.getName());
                    if (dd.length() > maxLength) { //request dikirim lebih dari batas maksimal
                        atribut = m.getName();
                        status ="invalid";
                    }else if(dd.length()==0){ //request dikirim value kosong / ""
                        atribut = m.getName();
                        status ="invalid";
                    }
                }
            }
        }
        //System.out.println(hasil);
        return atribut + "," + status;
    }

//testing
public static void main(String[] args) throws NoSuchFieldException {
        Map<String, Object> map = new HashMap<>();
        map.put("field1", "111"); //Field Mandatory dan value sudah sesuai - max 17
        map.put("field2", "222"); //Field Optional dan value lebih dari 1 digit
        map.put("field3", "333"); //Field Mandatory dan value sudah sesuai - max 10
        ObjectMapper objectMapper = new ObjectMapper();
        Person req = objectMapper.convertValue(map, Person.class);
        String dd =new ValidateException().validateRequest(req, map);
        System.out.println(dd);
        String[] rcMap = dd.split(",",-1);
        System.out.println((rcMap[1]));
    }

//example model pojo
public class Person{
  @Column(length=17, nullable=false)
  private field1;
  @Column(length=1, nullable=true)
  private field2;
  @Column(length=10, nullable=false)
private field3;
}
