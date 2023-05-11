# 전산 기초

## 좋은 코드란 무엇인가?

* 읽기 쉬운 코드
* 중복이 없는 코드
* 테스트하기 용이한 코드
* 등등...

### ◆ 읽기 쉬운 코드?
읽기 쉬운 코드를 작성하려면 본인에게 <b>익숙한 언어</b>를 사용하면 된다. 주석을 사용하여 해당 코드를 이해할 수 있으나 실제 함수와 일치한다고 할 수 없다.
오히려 한 두가지의 주석이 잘못된 해석을 야기할 수 있다. 유의하도록 하자.   

그러나 각자 개인마다 읽기 쉬운 코드란 다르다. 변수명을 짓는 것도 모호하고 각자의 배경 지식도 일치하지 않을 수 있다. 그래서 아무리 읽기 쉬운 코드로
작성했다고 하더라도 한계가 존재할 수 있다.   

읽기 쉽다는 것은 이해하기 쉽다는 것이 포함되어 있다. 즉, 나무를 보지 말고 숲을 볼 때도 쉬워야 한다.   
항상 <b>"왜 쉬운 코드를 작성해야 하지?"</b>, <b>"어떻게 쉬운 코드로 작성할 수 있을까?"</b> 고민하는 것이 좋다.   

### ◆ 테스트하기 용이한 코드?
테스트가 용이한 코드는 심리적인 안정감과 리팩토링에도 용기가 생긴다.   
<b>"그러나 왜 용이한 테스트 코드를 작성해야 하지?"</b>   

### ◆ 중복이 없는 코드?
개발을 하다 보면 여기에도 있고 저기에도 있는 코드가 불편함을 초래할 수 있다.   
   
<b>"이 불편함은 도대체 어디에서 발생하는 것일까?"</b>   
이전에 작성한 A 함수를 여러 군데에서 사용한 것을 기억하기 힘들다. 그래서 나중에 특정한 A 함수를 수정했을 경우, 에러가 발생한다. 그래서 같은 코드를 사용하는 A 함수를 따로 빼두고 재사용하는 것이 좋다.   

그러나 A 함수를 살짝 고친 A+ 함수가 필요할 때, 중복 코드를 필요에 의해 추출했지만 현재는 아니기 때문에 다시 합치거나 수정을 할 때가 있다. 
<b>목적이 다른 코드를 추출했을 때</b>, 이럴 경우 추가 반영 사항이 있어 비용이 든다.   

### ◆ 좋지 않은 코드를 사용하게 되는 이유?

#### 쓰이지 않는 코드
이전에 사용했다가 현재는 사용하지 않는 코드가 있다. 이를 삭제하기에는 조금 그렇기 때문에 삭제하지 못하는 경우가 있다.   
<b>"불안함때문에 삭제하지 못하는 코드, 이 불안함은 어디서 오는 것일까?"</b>   

* 거리   
코드가 동작하는 위치와 정의된 위치가 멀어서 쉽게 파악할 수가 없는 문제가 있다. 코드가 동작하는 위치와 정의된 위치가 가까울 수록 쉽게 파악할 수 있다.   
* 순수하지 않은 함수   
함수 외부의 어떤 값을 기반으로 동작하는 함수는 쉽게 제어하기 어렵다. 함수의 입·출력만 확인하여 함수 내부를 수정할 수 없다면 이는 매우 까다롭다.
```
function getWage(name) {
  return this.getMySalary(name) / this.getTotalTime(new Date())
}
```
위 getWage란 함수는 name이라는 입력 외에도 getMySalary라는 입력으로 정의되지 않은 입력이 존재하며 new Date()라는 항상 변하는 값에 의존한다.   
   
위의 상황이 발생하여 함수에 입력을 추가하거나 옵션 값을 추가하여 억지로 처리하려고 할 때는 그 코드는 좋은 코드가 될 수 없게 된다.   
이렇게 계속 추가하면 쉽게 이해하기 힘든 코드로 변질된다.   

* 기술 부채
응급 처치가 무조건 좋지 않은 것은 아니다. 당장 해결해야 할 때는 어쩔 수 없이 사용할 수 밖에 없다. 그러나 이는 부채가 되고 꼭 해결해야 의무가 된다.   
   
### ◆ 좋지 않은 코드 줄이기
처음부터 좋은 코드를 작성하는 것이 좋다. 그러나 이는 쉽지 않다. 그래서 이러한 노력을 억지로 하기 보다는 <b>좋지 않은 코드를 줄이자</b>.

### ◆ 추출이 아닌, 추상화
* 추출과 추상화의 차이점이 무엇일까?   
추출은 특별한 기준없이 단순히 밖으로 끌어내는 것이며, 추상화는 어떤 대상의 중요한 요점들을 재해석하여 정리한 것이다.   
   
함수 또는 파일로 추출하는 이유는 여러 개가 있다. 다른 곳에서 재사용하기 위해 분리하고 파일이 커져서 분리한다. 단순히 중복된 코드 덩어리(Chunk)에 대해 
추출하면 재사용하기 어렵다. 오히려 비용만 들 뿐, 잘못 추출한 것이다.   

함수를 분리할 때는 그 역할을 인지하고 하나의 역할만 할 수 있도록 만들어야 한다. 즉, <b>의존성을 드러내기 위함</b>이 추출의 목적이 되어야 한다.   

한 파일에 여러 로직이 얽혀있을  때 각 코드 중 서로 의존 관계에 있는 것들을 추출해야 한다. 이렇게 추상화된 함수는 하나의 역할을 갖고 의미 있는 추출(추상화)이 이루어진다.   
<b>의존 관계가 있는 것들끼리 추상화를 해보자!</b>    

의존 관계가 있는 것들끼리 추상화를 하면 새로운 요구 사항이 있을 때, 응급처치를 하지 않아도 된다. 의존성을 기반으로 분리된 여러 함수들은 
각자의 역할을 하고 있기 때문에 각자의 영역을 침범할 필요가 없다.   

분리된 여러 함수의 <b>조합</b>으로 코드를 구성하면 어떤 변경 사항에 대해 필요한 부분의 함수만 다른 함수로 수정하면 된다.

#### 어디서 분리해야 할까?
단순 컴포넌트를 렌더링하는 함수일 경우, 어느 레벨로 공유될지에 따라 정의되는 위치가 달라진다. 어떤 함수는 도메인과 크게 결합되어 있어 특정 페이지에서만 
재사용될 수 있고 어떤 함수는 의존 관계없이 어디서든 사용할 수 있다.   
<b>목적에 따라 맞는 위치에 정의해주는 것이 중요하다.</b>   

### ◆ 삭제하기 쉬운 코드, 삭제하기 어려운 코드로 분리
아무리 깔끔한 코드를 작성한다고 해도 요구 사항을 맞추다 보면 복잡한 코드를 작성할 수 밖에 없는 상황이 온다. 라이브러리에서 발생한 문제일 수도 있고 
여러 브라우저에 대응하다가 나온 코드일 수도 있다.   

이런 코드는 다른 사람이 읽기 어렵고 섣불리 삭제하기도 힘들다. 복잡한 요구 사항을 담은 코드는 변경에 유연하지 못하여 별도로 분리해두어야 한다.   

좋지 않은 코드가 생산되는 것을 완전히 차단할 수 없다면 제대로 관리할 수 있도록 <b>격리</b>해야 한다.   

이 경우 주석과 함께 격리해두면 기존 코드의 흐름을 끊지 않고 복잡한 코드를 이해할 수 있을 것이다.   

### ◆ 일관성 있는 코드
최소한의 가독성을 보장하는 방법은 일관성 있는 코드를 작성하는 것이다. 일관성은 <b>합의된 규칙</b>을 기반으로 만들어지고 이 규칙은 개개인에게 동일하게 다가간다.   

일관성 있는 코드를 작성하면 예측이 가능하다. 이는 어느 곳에 어떤 코드가 위치되어있든 예상할 수 있다는 것이다. 프로젝트 팀원 간 <b>그라운드 룰(Ground Rule)</b>이 필요한 이유다.   

#### Naming
변수 이름도 중요하지만 작성된 수많은 함수 이름에도 규칙이 있으면 일관성을 지킬 수 있다. React hooks API도 Hooks임을 이름에서부터 드러내기 위해 <b>use-*</b> prefix를 사용한다.   

단순히 이벤트 핸들러를 정의할 때도 Convention을 지켜서 정의한다면 해당 Convention의 함수를 보면 이벤트 핸들러라는 예상이 가능하다.
```
// Case 1.
// prefix: handle
// target: button
// action: click
const handleButtonClick = () => {}

// Case 2.
// prefix: on
// action: click
// target: button
const onClickButton = () => {}
```
위 처럼 일관된 규칙으로 작성되면 함수를 파악하는 데 도움이 된다.   

#### Directory
디렉터리 구조는 '어디에 분리할지'와 관련이 있다.   

디렉터리 구조와 아키텍처는 비교 대상이 아니다. 일관된 디렉터리 구조는 전체적인 구조를 파악하는 데 도움이 되고 컴포넌트 간의 관계를 파악하는 데에도 도움을 준다.   

<b>Top Level</b>의 <b>Directory</b> 구성에 따라 어느 곳에 어떤 모듈 혹은 컴포넌트들이 위치할지 예측이 된다면 코드를 빠르게 이해할 수 있다.   
```
src
├── api
├── components
├── hooks
├── model
├── pages
│   ├── contract
│   └── docs
└── utils
```
Components 디렉터리라면 디렉터리 구조가 컴포넌트 Hierarchy를 드러낼 수 있고 Page 디렉터리라면 Route path를 드러낼 수 있다. 코드가 어느 곳에 
위치하든 예상할 수 있도록 디렉터리 구조를 구성하면 코드를 파악하는 데 도움이 된다.   

```
src
├── @shared
│   ├── components
│   ├── hooks
│   ├── models
│   └── utils
├── contract
│   ├── components
│   ├── hooks
│   ├── models
│   ├── utils
│   └── index.ts
├── docs
│   ├── components
│   ├── hooks
│   ├── models
│   ├── utils
│   └── index.ts
└── App.tsx
```
첫 번째 디렉터리 구조는 코드가 하는 역할에 따라 분리하였고 두 번째 디렉터리 구조는 페이지(도메인 영역)에 따라 디렉터리를 분리했다. 앱이 커지고 복잡해지면 
첫 번째 디렉터리 구조의 경우에는 코드가 정의된 곳과 코드 사용되는 곳이 멀어지는 문제점이 발생한다.   

두 번째 디렉터리 구조는 Featured Based라고도 할 수 있으며 위의 문제를 해결할 수 있다. 앱 전반에서 공통으로 사용되는 것들만 <b>Top Level</b>의 @shared 디렉터리에서 
관리하고 나머지는 응집도를 높게 각 디렉터리에서 관리하는 것이다.

### ◆ 확장성 있는 코드
확장이 어려운 코드는 내부에서 많은 변경이 발생하여 코드를 읽기 어렵게 만든다. 그리고 생산성도 떨어진다.   

```
const Input = styled.input`
  // styling
`;
const Input = ({
  type,
  value,
  onChange,
}) => {
  return (
    <Input type={type} value={value} onChange={onChange}>
  )
}
```
위 코드의 컴포넌트는 확장에 닫혀 있다. (type은 props로 받았다.) 확장에 닫혀있다는 것은 Input 컴포넌트에 새로운 이벤트 핸들러나 값을 전달하기 어려운 구조라는 뜻이다.   
Ref를 전달할 수도 있고 focus, blur 이벤트에 핸들러를 추가할 수도 있다. 이러한 변경이 발생할 때마다 props를 추가해줘야 하기 때문이다.   

Input 컴포넌트 목적에 따라 달라지며 굳이 스타일링만 추가된 Input 컴포넌트를 별도로 만든다면   

```
const Input = styled.input`
  // styling
`;

const Input = (props: HTMLAttributes<HTMLInputElement>) => {
  return (
    <Input {...props}>
  )
}
```
위 처럼 코드를 작성해야 한다.    

기존 Input HTML Element가 받을 수 있는 Attribute들을 그대로 받을 수 있어야 한다. 이 컴포넌트가 의미있는 컴포넌트가 되기 위해서는 validator에 대한 
처리가 추가되면 더 의미있는 코드가 된다.   

```
const Input = styled.input<{ isValid?: boolean }>`
  // styling
  // error styling
`;
interface Props extends HTMLAttributes<HTMLInputElement> {
  isValid?: boolean;
}
const Input = ({ isValid, ...props }: Props) => {
  return (
    <Input {...props} isValid={isValid}>
  )
}
```
위의 예시로 컴포넌트는 validate를 외부에 위임하고 있으며 상황에 따라 validator에 대한 부분을 함께 추상화한다면 더 응집도 높은 컴포넌트를 만들 수 있다.   

확장에 너무 열려있으면 내부 API를 수정하기 어려워지는 문제가 발생할 수 있다. 라이브러리의 경우 확장성이 높으면 많은 use-case를 대응할 수 있지만 
내부적으로 큰 변화가 있을 때, Breaking Change가 생길 가능성이 높아진다. 그래서 적정선을 찾는 것이 중요하다.   

### ◆ 결론
* 코드 간의 <b>의존성</b>을 고민하는 것!
* 합의된 규칙으로 <b>일관성있게</b> 작성하는 것!
* 적절하게 <b>확장</b> 가능하도록 설계하는 것!
* 어쩔 수 없는 코드는 주석과 함께 <b>격리</b>하는 것!