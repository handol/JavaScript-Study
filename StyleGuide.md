# 들여쓰기
- 각 들여쓰기 단계는 4개의 공백을 사용하고 탭은 사용하지 않습니다.

     if (true) {
         doSomething();
     }

# 줄 길이
- 한 줄은 최대 80자입니다. 줄 길이가 80자보다 길어지면 연산자 이후에서 줄을 끝어 다음 줄에 작성합니다. 다음 줄에 작성한 코드는 이전 줄을 기준으로 두 단계 들여쓰기(공백 8개)합니다.

     doSomething(argument1, argument2, argument3, argument4,
               argument5);

# 기본 리터럴
- 문자열은 반드시 작은따옴표가 아닌 큰따옴표를 사용하고 한 줄로 작성합니다.

     var name = “Nicholas”;

- 숫자는 꼭 10진수 정수, 지수 표기법을 사용한 정수, 16진수 정수 또는 부동 소수점 10진수만 사용하고 소수점 앞이나 뒤에 숫자가 최소 하나는 있어야 합니다.

     var count = 10;
     var price = 10.0;
     var num = 0xA2;

- null 값은 반드시 다음 상황에서만 사용합니다.
     @ 객체 값을 나중에 할당할 변수를 초기화할 때
     @ 초기화된 변수에 객체 값이 할당되었는지 비교할 때
     @ 객체를 인자로 넘겨야 하는 함수를 호출할 때
     @ 함수에서 객체를 반환해야 할 때

     var person = null;

     function getPerson() {
          if (condition) {
               return new Person(“Nicholas”);
          } else {
               return null;
          }
     }

     var person = getPerson();
     if (person !== null) {
          doSomething();
     }

- undefined는 절대로 사용해서는 안됩니다. 변수가 정의되었는지 확인하려면 typeof 연산자를 사용합니다.

     if (typeof variable === “undefined”) {
          // 실행할 코드
     }

# 연산자에 공백 넣기
- 연산자를 두 개의 피연산자에 사용할 때는 연산자 앞뒤에 공백을 하나씩 추가해 표현식이 명확하게 보이도록 합니다.

     var found = (values[i] === item);

     if (found && (count > 10)) {
          doSomething();
     }

     for (i = 0; i < count; i++) {
          process(i);
     }

# 괄호에 공백 넣기
- 괄호를 사용할 때, 여는 괄호 바로 다음과 닫는 괄호 바로 앞에는 공백이 없어야 합니다.

     var found = (values[i] === item);

# 객체 리터럴
- 객체 리터럴은 다음 형식으로 작성합니다.
     @ 여는 중괄호는 중괄호를 연 문장과 같은 줄에 있어야 한다.
     @ 각 프로퍼티-값 쌍은 여는 중괄호 다음 줄부터 작성하며 여는 중괄호가 있는 문장을 기준으로 한 단계 들여쓰기 한다.
     @ 각 프로퍼티-값 쌍 형식은 따옴표로 감싸지 않고 프로퍼티 이름을 입력하고 그 다음에 공백 없이 콜론을 입력한 뒤 값을 입력한다.
     @ 값이 함수라면 프로퍼티명 다음에 한 줄로 길게 입력하지 않고 또한 함수 이전 줄과 다음 줄에 공백을 넣어야 한다.
     @ 관련된 프로퍼티를 묶거나 가독성을 높이기 위해 빈 줄을 추가해도 된다.
     @ 닫는 중괄호는 별도의 줄에 있어야 한다.

     var object = {

          key1: value1,
          key2: value2,

          func: function() {
               // 필요한 로직 수행
          },

          key3: value3
     };

     doSomething({
          key1: value1,
          key2: value2
     });

# 주석
- 다음 경우에 주석을 사용합니다.
     @ 이해하기 어려운 코드
     @ 에러로 오해하기 쉬운 코드
     @ 로직이 명확하지 않은, 특정 브라우저를 위한 코드
     @ 문서 생성에 필요한 객체, 메서드, 프로퍼티
- 한 줄 주석
     @ 하단의 코드를 설명하기 위해 독립된 줄에 주석을 작성한다.
     @ 주석 앞의 코드를 설명하기 위해 줄 끝에 주석을 작성한다.
     @ 한 줄 주석으로 여러 줄의 코드를 주석 처리한다.

     if (condition) {
          // 이 줄이 실행된다면 모든 보안 검사가 통과되었다는 의미입니다.
          allowed();
     }

     var result = something + somethingElse;     // somethingElse는 절대 null이면 안됩니다.

     // if (condition) {
     //      doSomething();
     // }

- 여러 줄 주석
     @ 첫 번째 줄은 /*을 입력해 주석을 연다. 이 줄에는 그 외 다른 텍스트가 있으면 안된다.
     @ 그 다음 줄부터는 *를 입력하는데 첫 번째 줄의 *과 열을 맞춘다. 이 줄부터는 텍스트를 입력해도 된다.
     @ 마지막 줄은 */을 입력하는데 이전 줄과 열을 맞춘다. 이 줄에는 그 외 다른 텍스트가 있으면 안된다.

     if (condition) {
          /*
           * 이 줄이 실행된다면
           * 모든 보안 검사가 통과되었다는 의미입니다.
           */
          allowed();
     }

- 주석 어노테이션: 코드에 추가적인 설명을 하기 위해 사용. 한 단어이며 그 뒤에 콜론이 붙습니다.
     @ TODO: 코드를 아직 다 작성하지 않았음을 의미합니다. 다음에 작업할 내용에 대한 정보가 반드시 있어야 합니다.
     @ HACK: 임시변통의 방법을 사용한 코드를 의미합니다. 핵을 왜 사용했는지에 대한 정보가 반드시 있어야 합니다. 나중에 더 나은 방법으로 문제를 해결할 수도 있다는 뜻입니다.
     @ XXX: 코드에 문제가 있어 가능한 빨리 수정해야 함을 의미합니다.
     @ FIXME: 코드에 문제가 있어 곧 수정해야 함을 의미합니다. XXX 보다는 덜 중요합니다.
     @ REVIEW: 변경 가능성이 있어 리뷰가 필요한 코드를 의미합니다.

     // TODO: 더 빠르게 처리하는 방법을 찾아보겠습니다.
     doSomething();

     /*
      * HACK: IE를 위한 코드입니다. 나중에 시간이 날 때
      * 다시 한번 보겠습니다.
      */
     if (document.all) {
          doSomething();
     }

     // REVIEW: 더 좋은 방법이 있을까요?
     if (document.all) {
          doSomething();
     }

# 변수 선언
- 보든 변수는 반드시 사용하기 전에 선언되어야 합니다. 변수는 한 개의 var 문을 이용해 변수마다 한 줄씩 함수 맨 윗 줄에 선언해야 합니다. 첫 번째 줄 다음 줄부터는 한 단계 들여쓰기해서 변수명의 열을 맞춥니다. 변수는 가능하면 선언할 때 초기화해야 하며 대입 연산자는 들여쓰기 단계를 똑같이 맞춰야 합니다. 초기화된 변수는 반드시 초기화되지 않은 변수보다 앞에 와야 합니다.

     var count     = 10,
           name     = “Nicholas”,
           found     = false,
           empty;

# 함수 선언
- 함수는 반드시 사용하기 전에 선언되어야 합니다.
- 함수가 객체에 선언된 메서드가 아니라면 반드시 함수 선언 형식을 지켜야 합니다.
- 함수명과 여는 괄호 사이에는 공백을 넣지 않습니다.
- 닫는 괄호와 여는 중괄호 사이에는 공백을 한 칸 넣습니다.
- 여는 중괄호는 반드시 function 키워드와 같은 줄에 둡니다.
- 여는 괄호 다음과 닫는 괄호 전에는 공백을 넣지 않습니다.
- 인자를 입력할 때에는 콤마 다음에 한칸 공백을 두며 콤마 앞에는 공백을 입력하지 않습니다.
- 함수 본체는 한 단계 들여쓰기합니다.

     function doSomething(arg1, arg2) {
          return arg1 + arg2;
     }

- 다른 함수 안에 선언되는 함수는 반드시 var 문 다음에 바로 선언되어야 합니다.

     function outer() {
          var count     = 10,
                name     = “Nicholas”;

          function inner() {
               // 코드
          }

          // inner()를 사용하는 코드
     }

- 익명 함수는 객체 메서드를 할당할 때 사용하거나 다른 함수에 인자로 전달할 때 사용합니다. 이 때 function 키워드와 여는 괄호 사이에는 공백이 없어야 합니다.

     object.method = function() {
          // 코드
     };

- 선언 후 바로 호출하는 함수는 함수 전체를 괄호로 감싸야 합니다.

     var value = (function() {

          // 함수 전체

          return {
               message: “Hi"
          }
     }());

# 이름 규칙
- 변수명은 낙타 표기법을 사용하고 첫 문자는 소문자로 하며 새로운 단어의 첫 번째 문자는 대문자로 표기합니다.
- 변수명의 첫 번째 단어는 반드시 명사를 사용해서 함수와 쉽게 구분할 수 있게 합니다.
- 밑줄 문자는 변수명에 절대로 사용하지 않습니다.

     var accountNumber = “8401-1”;

- 함수명도 역시 낙타 표기법을 사용합니다.
- 함수명의 첫 번째 단어는 동사를 사용하여 변수와 쉽게 구분할 수 있게 합니다.
- 함수명에도 절대 밑줄 문자를 사용하지 않습니다.

     function doSomething() {
          // 코드
     }

- 생성자 함수는 new 연산자를 이용해 새로운 객체를 생성할 때 사용되는 함수로 낙타 표기법을 사용하며 첫 문자는 대문자로 시작합니다.
- 생성자 함수는 new를 이용해 객체 인스턴스를 생성하는 데 사용되므로 동사로 시작하지 않아야 합니다.

     function MyObject() {
          // 코드
     }

- 변수를 값이 변하지 않는 상수처럼 사용하려면 이름의 모든 문자를 대문자로 하고 단어마다 밑줄을 하나 넣습니다.

     var TOTAL_COUNT = 10;

- 객체 프로퍼티는 변수와 같은 이름 규칙을 따르며 객체 메서드는 함수와 같은 이름 규칙을 사용합니다.
- 프로퍼티나 메서드를 private으로 선언하려면 밑줄을 맨 앞에 붙입니다.

     var object = {
          _count: 10,

          _getCount: function() {
               return this._count;
          }
     };

# strict 모드
- strict 모드는 함수 안에서만 사용해야 하며 절대로 전역으로 사용하지 않습니다.

     function doSomething() {
          “use strict”;
          // 코드
     }

     (function () {
          “use strict”;

          function doSomething() {
               // 코드
          }
            ...
     }());

# 할당
- 변수에 할당할 값이 비교 연산 표현식이면 비교 연산 표현식을 괄호로 감싸도록 합니다.

     var flag = (i < count);

# 동등 연산자
- == 와 != 대신 ===와 !==를 사용해서 타입 강제 변환으로 인한 에러가 발생하지 않게 합니다.

     var same = (a === b);

# 삼항 연산자
- 삼항 연산자는 조건에 따라 값을 할당하기 위한 용도로만 사용하며 절대로 if 문을 대신해서 사용하면 안됩니다.

     var value = condition ? value1 : value2;

# 문장
- 각 줄은 단 한개의 문장만 있어야 하며 모든 간단한 문장은 세미콜론으로 마쳐야 합니다.

     count++;
     a = b;

- return 문에서 반환하는 값은 더 명확한 표현을 위한 부득이한 경우가 아니라면 괄호를 사용하지 않습니다.

     return;

     return collection.size();

     return (size > 0 ? size : defaultSize);

- 복합문
     @ 중괄호 안의 문장은 복합문에서 한 단계 이상 들여쓰기해야 한다.
     @ 복합문의 시작을 알리는 여는 중괄호는 줄 끝에 있어야 하고 닫는 중괄호는 줄 맨 앞에 있어야 한다. 또한 닫는 중괄호는 복합문과 들여쓰기 단계가 같아야 한다.
     @ if 문이나 for 문과 같은 제어문에서 사용할 때 문장이 단 하나라 하더라도 중괄호는 모든 문장을 감싸야 한다. 이 규칙은 문장을 추가할 때 중괄호를 빠뜨려 실수에 의한 에러가 발생하는 것을 방지하게 한다.
     @ if 문과 같이 키워드로 시작하는 문장은 키워드 다음에 공백이 하나 있어야 하며 여는 중괄호 앞에도 공백이 있어야 한다.

     if (condition) {
          // statements
     }

     if (condition) {
          // statements
     } else {
          // statements
     }

     if (condition) {
          // statements
     } else if (condition) {
          // statements
     } else {
          // statements
     }

     for (i=0, len=10; i < len; i++) {
          // 코드
     }

- for … in 문을 사용할 때는 hasOwnProperty()를 사용해서 객체 멤버를 걸러낼 필요가 있는지 꼭 재확인해야 합니다.

     while (조건식) {
          // 문장
     }

     do {
          // 문장
     } while (조건식);

- case는 switch를 기준으로 한 단계 들여쓰기합니다. 첫 번째 case를 제외한 나머지 case와 default는 이전 줄에 반드시 빈 줄이 있어야 합니다.
- switch에 default 케이스가 필요 없다면 주석으로 남겨놓아야 합니다.

     switch (value) {
          case 1:
               /* 다음 case 문에서 처리 */

          case 2:
               doSomething();
               break;

          case 3:
               return true;

          default:
               throw new Error(“여기까지 실행되면 안됩니다.”);
     }

- try 문

     try {
          // 문장
     } catch (변수) {
          // 문장
     } finally {
          // 문장
     }

# 공백
- 빈 줄 두 개는 다음 상황에서만 사용해야 합니다.
     @ 소스 파일 부분 사이
     @ 클래스와 인터페이스 정의 사이
- 한 줄 공백은 다음 상황에서만 사용해야 합니다.
     @ 메서드 사이
     @ 메서드의 지역 변수와 첫 번째 문장 사이
     @ 여러 줄 주석이나 한 줄 주석 이전
     @ 메서드 내에서 가독성 향상을 위해 논리적으로 나눈 그룹 사이
- 공백은 다음 상황에서만 사용해야 합니다.
     @ 괄호 앞에 오는 키워드는 공백을 넣어 괄호와 구분한다.
     @ 인자가 여러 개일 떄는 콤마 다음에 공백을 넣는다.
     @ 점(.)을 제외한 모든 이항 연산자는 공백을 넣어 피연산자와 구분한다. 단일 마이너스(-), 증가(++), 감소(--)와 같은 단항 연산자에는 공백을 사용하지 않는다.
     @ for 문의 표현식은 공백을 넣어 구분한다.

# 유의 사항
- String과 같은 기본 래퍼 타입은 새로운 객체 생성에 사용하지 않는다.
- eval()은 절대 사용하지 않는다.
- with문을 절대 사용하지 않는다.





