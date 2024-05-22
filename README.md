# spring-typeconverter
롬복의 @EqualsAndHashCode 를 넣으면 모든 필드를 사용해서 equals() , hashcode() 를 생성한다. 따라서
모든 필드의 값이 같다면 a.equals(b) 의 결과가 참이 된다.

참고
스프링은 용도에 따라 다양한 방식의 타입 컨버터를 제공한다
```
Converter 기본 타입 컨버터
ConverterFactory 전체 클래스 계층 구조가 필요할 때
GenericConverter 정교한 구현, 대상 필드의 애노테이션 정보 사용 가능
ConditionalGenericConverter 특정 조건이 참인 경우에만 실행
자세한 내용은 공식 문서를 참고하자.
https://docs.spring.io/spring-framework/docs/current/reference/html/core.html#core-convert
```

참고
스프링은 문자, 숫자, 불린, Enum등 일반적인 타입에 대한 대부분의 컨버터를 기본으로 제공한다. IDE에서
Converter , ConverterFactory , GenericConverter 의 구현체를 찾아보면 수 많은 컨버터를 확인할
수 있다

뷰 템플릿에 컨버터 적용
```
변수 표현식 : ${...}
컨버전 서비스 적용 : ${{...}}
타임리프의 th:field 는 앞서 설명했듯이 id , name 를 출력하는 등 다양한 기능이 있는데, 여기에 컨버전 서비스
도 함께 적용된다.
```

스프링이 제공하는 기본 포맷터
```
@NumberFormat : 숫자 관련 형식 지정 포맷터 사용, NumberFormatAnnotationFormatterFactory
@DateTimeFormat : 날짜 관련 형식 지정 포맷터 사용,
Jsr310DateTimeFormatAnnotationFormatterFactory
```
참고
@NumberFormat , @DateTimeFormat 의 자세한 사용법이 궁금한 분들은 다음
링크를 참고하거나 관련 애노테이션을 검색해보자.
https://docs.spring.io/spring-framework/docs/current/reference/html/core.html#format-CustomFormatAnnotations