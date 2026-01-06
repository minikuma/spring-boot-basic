### Build Systems
---     
* Maven
* Gradle
* Ant  

스프링 부트는 지원하는 의존성 리스트를 제공해 준다. 예를 들어 빌드 설정에서 의존성 버전에 대해 특별하게 작성하지 않아도 된다. 버전은 스프링 부트에서 관리한다. 이 의존성 리스트에는 스프링 모듈 뿐 아니라 외부 라이브러리까지 포함하고 있다. Bill of Meterials (BOM)을 통해 사용가능하다.        

> ```spring-boot-dependencies```에는 사실 버전에 대한 정보만 있다. 예를 들어 파이썬의 ```requirement.txt``` 파일로 버전을 관리하는 거와 비슷하다. 일종의 명세서라고 생각하자.         

1. BOM 사용하기      
스프링 부트 플러그인을 쓰면 자동으로 BOM을 사용할 수 있다.       
예) 아래 implement 를 보면 버전 정보가 없다.     

```json
plugins {
    id("org.springframework.boot") version "3.2.1"
    id("io.spring.dependency-management") version "1.1.4"
    id("java")
}

dependencies {
    implementation("org.springframework.boot:spring-boot-starter-web")
    implementation("com.fasterxml.jackson.core:jackson-databind") // 버전 없음
}
```   

플러그인 사용하지 않으려면 platform 명령어를 사용한다.     

```json
dependencies {
    implementation(platform("org.springframework.boot:spring-boot-dependencies:3.2.1"))

    implementation("org.springframework:spring-web")
    implementation("com.fasterxml.jackson.core:jackson-databind")
}
```    

2. Starter는 무엇인가?     
```Starter```라는 이름이 붙은 의존성들이 있는데, 이것은 스프링 부트에서 필요한 라이브러리를 미리 패키지해 놓은 거라 보면 된다. 사용자는 하나하나 의존성들을 몰라도 복잡한 설정 없이 바로 사용이 가능하다.         

```json
implementation("org.springframework.boot:spring-boot-starter-web")
```      

```spring-boot-starter-web```이라는 Starter만 추가해도 WEB을 실행하기 위한 Tomcat과 같은 웹 서버 모듈들이 추가된다.    




