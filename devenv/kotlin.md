# kotlin development environment

## gradle with kotlin dsl
처음부터 에러가 나기 시작. 
https://github.com/spring-io/initializr/issues/922

정확히 같은 에러

```kotlin
val snippetsDir by extra {file("build/generated-snippets")}
```

## spring boot starter test with gradle

junit 5의 경우 vintage 라는 모듈으로 junit 4에 대한 api도 제공

annotation name이 같은 경우가 많아서 혼용하는 실수가 빈번하다. 
둘 중 하나로 짜는 게 상책. 
spring boot starter test 의 경우 기본으로 다 묶고 있다. 
따라서 명시적으로 아래와 같이 제외해줘야 한다.
```kotlin
testImplementation("org.springframework.boot:spring-boot-starter-test") {
        exclude(group = "org.junit.vintage", module = "junit-vintage-engine")

    }
```
