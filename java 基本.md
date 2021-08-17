


# [fuckingNB](#a)
# [JDBC在TOMCAT的](#jdbc)
# [String.format](#String.format)
# [foreach](#foreach)
# [getResourceAsStream的路徑解釋](#getResourceAsStream)

## <a name="a">here</a>

##<a name="jdbc">要在tomcat的lib, C:\tomcat\apache-tomcat-9.0.50\lib 中放入mssql的jar檔案!</a>


## <a name="String.format">String.format用法</a>
```java=
String format = "Your name is %s"; // 格式化字串
String arg = "Bill"; // 格式化字串的參數
String yourNameIs = String.format(format, arg); // 使用格式化字串搭配參數組成格式化的字串

System.out.print(yourNameIs); // Your name is Bill

```

## <a name="foreach">foreach用法</a>

```
package ttt;

import java.util.Arrays;
import java.util.List;
import java.util.function.Consumer;

public class Test {
	
	
	public static void main(String[] args) {

        List<String> list =  Arrays.asList("matt","john","gary");

        // 使用for loop
        for(int i = 0 ; i < list.size() ; i++ ) {
            System.out.println(list.get(i));
        }

        // 使用for-each loop
        for(String s : list) {
            System.out.println(s);
        }

        // 使用Java 8 forEach()
        list.forEach(new Consumer<String>() {
            @Override
            public void accept(String s) {
                System.out.println(s);
            }
        });

        // 使用Java 8 forEach() 搭配 Lambda語法
        list.forEach(s -> System.out.println(s));

        // 使用Java 8 forEach() 搭配 Lambda 及 Method References語法
        list.forEach(System.out::println);

    }

}

```

## <a name="getResourceAsStream">getResourceAsStream路徑用法</a>

https://www.itread01.com/content/1545629431.html

