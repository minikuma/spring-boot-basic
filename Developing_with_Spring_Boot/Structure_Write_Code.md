### Sturcture Write Code
---      

Default Package는 사용하지 말자.

스프링 부트는 ```@SpringBootApplication``` 애노테이션 기준으로 하위 패키지에 대해서만 스캔한다. 이러한 특징 때문에 Default Package를 사용하지 않는다. 추가로 Default Package에 만들어진 클래스는 다른 패키지에서 import 즉, 참조할 수 없다. 이거는 Java 언어의 제약이다.        

* 용도 별로 패키지 경계를 두는 게 좋다.
* 무엇보다 Default Package 는 다른 패키지에서 참조되지 않는다.
* Spring Boot는 애노테이션을 스캔할 때 특정 패키지 기준 하위로 스캔한다.

(JDK 21)         
> Classes in the unnamed package cannot be referenced explicitly by classes in named packages

https://docs.oracle.com/en/java/javase/21/language/implicitly-declared-classes-and-instance-main-methods.html?utm_source=chatgpt.com