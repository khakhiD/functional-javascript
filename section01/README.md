# 함수형 프로그래밍 정의, 순수함수
> 인프런 '자바스크립트로 알아보는 함수형 프로그래밍 (ES5)' 강의를 수강하며 정리한 내용입니다.


## 성공적인 프로그래밍
- 모든 프로그래밍 패러다임은 성공적인 프로그래밍을 위해 존재
- 성공적인 프로그래밍은 좋은 프로그램을 만드는 일
- 좋은 프로그램은 사용성, 성능, 확장성, 기획 변경에 대한 대응력이 좋음
- 이것들을 효율적이고 생산적으로 이루는 일이 성공적인 프로그래밍


## 함수형 프로그래밍
성공적인 프로그래밍을 위해 부수 효과를 미워하고 조합성을 강조하는 프로그래밍 패러다임
- 부수 효과(Side Effect)를 미워한다. => 순수 함수를 만든다.


### **`순수 함수`**
> - 부수효과가 없는 함수, 수학적 함수
> - 함수가 받은 인자 외 다른 외부의 인자 상태에 영향을 끼치지 않는 함수
> - 리턴 값 외에는 외부와 소통하는 것이 없는 함수
> - 동일한 입력에는 항상 같은 값을 반환해야 하는 함수
> - 함수의 실행이 프로그램의 실행에 영향을 미치지 않아야하는 함수
> - 함수 내부에서 인자의 값을 변경하거나 프로그램 상태를 변경하는 Side Effect(부수효과)가 없는 것
> - 언제 평가되어도 상관이 없는 것 - 평가 시점을 개발자가 다룰 수 있게 함


### **순수 함수의 예**
```
let num = 1;
function add(a){
    return a+num;
}
```
위 예제는 `add` 함수 안에서 전역 선언된 num 변수를 참조하기 때문에 순수함수라고 볼 수 없다.
```
//순수함수
function add(a,b){
    return a+b
}
const result = add(2,3)
```
위와 같이 `add`의 함수가 프로그램 실행에 영향을 미치지 않고 입력 값에 대해서만 값의 변환이 있으므로 순수함수이다.

> 순수 함수는 프로그램의 변화없이 입력 값에 대한 결과를 예상할 수 있어 테스트에 용이하다.

- **조합성**을 강조한다. => 모듈화 수준을 높인다.
- 순수 함수 => 오류를 줄이고 안정성을 높인다.
- **모듈화 수준**이 높다. => 생산성을 높인다.


### **요즘 개발 이야기**
- 재미 / 실시간성 : 라이브 방송, 실시간 댓글, 협업, 메신저
- 독창성 / 완성도 : 애니메이션, 무한 스크롤, 벽돌UI, 플립보드UI
- 더 많아져야하는 동시성 : 비동기 I/O, CSP, Actor, STM(Soft Transaction Memory) ...
- 더 빨라야하는 반응성 / 고가용성 : ELB, Auto Scaling, OTP Supervisor ...
- 대용량 / 정확성 / 병렬성 : MapReduce, Clojure Reducers ...
- 복잡도 / MSA / ... : 많아지고 세밀해지는 도구들

`그렇지만 타협할 수 없는 생산성` => 이 모든 것들을 구현하면서도 생산성을 높여야 한다.

#### 점점 다가오는 FP(Functional Programming)
- 좋아지는 하드웨어 성능
- 좋아지는 컴파일러
- 함수형 프로그래밍 기술
- 좋아지는 분산 / 리액티브 환경
- 동시성 + 병렬성 관련 기술
- 성공적인 적용 사례와 영향들이 나오는 추세

> "함수형 프로그래밍은 애플리케이션, 함수의 구성요소, 더 나아가서 언어 자체를 함수처럼 여기도록 만들고, 이러한 함수 개념을 가장 우선순위에 놓는다.", "함수형 사고방식은 문제의 해결 방법을 동사(함수)들로 구성(조합)하는 것" - 마이클 포거스 [클로저 프로그래밍의 즐거움]에서 ...

왜? 보다는 어떻게? 명사에서 동사로 전환


> 고가용성 : 죽지 않는 서비스


---

### **Thoughts**
> 정신나간 것 같다. 이렇게도 프로그래밍할 수 있구나 싶은게 충격적이네...