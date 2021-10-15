# STUDY-algorithm

**자료구조와 알고리즘에 대한 공부 기록
with JavaScript**

---

[규칙] 먼저 내가 스스로 작성한 코드를 html 파일의 윗부분에 작성하고

또 다른 답안 예시를 아래에 작성한다.

---

<a href="https://www.inflearn.com/course/%EC%9E%90%EB%B0%94%EC%8A%A4%ED%81%AC%EB%A6%BD%ED%8A%B8-%EC%95%8C%EA%B3%A0%EB%A6%AC%EC%A6%98-%EB%AC%B8%EC%A0%9C%ED%92%80%EC%9D%B4">공부할때 수강한 인강</a>

---

## 세 수 중 최소값 구하기

푼 날짜: 2021.10.10

걸린 시간: 9m

나는 a, b, c를 모두 각각 비교해 주었는데 if/else문 한개로 먼저 a와 b를 비교해 그 중 작은 수를 answer에 넣고 마지막에 if문 하나로 answer에 들어있는 값(a 혹은 b겠지)과 c를 비교해주면 더욱 짧은 코드로 작성이 가능했다. 즉, 하나씩 모두 비교할 필요 없이 <u>두 수를 먼저 비교해서 answer 변수에 저장해두고 남은 수와 answer를 비교하면 된다.</u>

---

## 삼각형 판별하기

푼 날짜: 2021.10.11

걸린 시간: 3m

정석은 3개의 변의 길이 중에 첫번째로 짧은 변의 길이와 두번째로 짧은 변의 길이의 합이 가장 긴 변의 길이보다 길어야 한다는 것을 전제로 문제를 풀이하는 것이다. 나는 삼각형의 두 변의 길이의 합은 나머지 한 변의 길이보다 크다라는 것을 전제로 if 문을 이용해 모든 경우를 검사해서 풀이하였다. 첫번째 문제에서 세 수를 비교하는 방법을 이용해 가장 긴 변의 길이를 max에 넣어주고 total(세 변 길이의합)에서 max를 빼준 값과 max에 들어있는 값을 비교해서 판별하면 된다.

---

## 연필 개수

푼 날짜: 2021.10.12

걸린 시간: 1m

자바스크립트의 함수중 입력받은 값을 올림해주는 함수를 사용했다.<br/>

- Math.round(): 반올림<br/>
- Math.ceil(): 올림<br/>
- Math.floor(): 내림

자바스크립트에서는 부동소수점을 표현하는 방법에 한계가 있어 실수의 경우 정밀한 숫자를 표현하는데 한계(오차)가 있다. 이러한 오차는 **Number.EPSILON**이란 상수를 사용해 기존 값에 이 상수를 더해 오차를 많이 줄어들게끔 보정해줄수는 있지만, 이는 충분하다고는 할 수 없으므로 정밀한 숫자 계산은 front-end보다는 server에서 계산해주는 것이 더 좋을것 같다!

---

## 1부터 N까지의 합

푼 날짜: 2021.10.12

걸린 시간: 1m

딱히 중요한건 없고 반복문을 이용해 sum 변수에 누적합을 넣는다.

---

## 최소값 구하기

푼 날짜: 2021.10.13

걸린 시간: 2m

Number.MAX_SAFE_INTEGER
JavaScript에서 안전한 최대 정수값을 나타낸다. (253 - 1)

보통 알고리즘 문제를 풀 때 변수값을 매개변수로 들어오는 값으로 초기화해놓고 비교를 했었는데 Number.MAX_SAFE_INTEGER를 이용해 들어올 수 있는 가장 큰 값을 넣어놓고, 최솟값 비교를 할 수 있도록 한다.

Number.MAX_SAFE_INTEGER를 사용하는 이유는 정수를 정확하고 올바르게 비교할 수 있는 안전함을 가지고 있기 때문이라고 한다.

---

## 홀수

푼 날짜: 2021.10.14

걸린 시간: 8m

일단 내가 짠 코드는 아직 자바스크립트 문법을 잘 모르는 상태에서 짜서 그런가 선언한 변수도 많고 반복문도 정석으로 돌렸다. 하지만 답안의 반복문을 보면

```javascript
for (let x of arr) {
  if (x % 2 === 1) {
    sum += x;
    if (x < min) min = x;
  }
}
```

let i = 0; i < arr.length; i++ 가 아닌 let x of arr라고 되어있다. (이걸 보고 약간 파이썬의 for i in range() 문법이 생각났다.) 여튼 이번 문제를 통해 알게 된 **첫번째로 알게 된 부분**이다.

그리고 **두번째로 알게 된 부분**은 한 함수 안에서 어떻게 여러 값을 return 하는가? 였는데 일단 자바스크립트에서는 answer라는 배열을 만들어 그 안에

```javascript
answer.push(sum);
answer.push(min);
return answer;
```

와 같은 형태로 return할 값을 push 해준후 return answer를 실행하면 된다.

즉, return명령은 함수에서 값을 반환하지만 복수의 값을 반환할 수는 없다. 따라서 배열과 객체를 이용해 복수의 값을 반환하게 할 수 있다. 쉽게 말하면 위에 설명한 방법처럼 여러값들을 배열 혹은 객체로 묶어서 하나의 값으로 만든다음에 반환시키는 방법이다.

그런데 위와 같이 코드를 짠 후 실행시켜보면 아래와 같은 배열의 형태로 결과가 출력된다.

**(2) [256, 41]**

해당 문제에서 원하는 것은 첫번째 줄에 홀수들의 합을 출력하고 두번째 줄에 홀수중에 가장 작은 값을 출력하는 것이므로 배열 형태가 아닌 두 줄의 형태로 출력해줘야 한다.
따라서 **구조 분해 할당**을 이용해 결과값을 두 줄로 출력할 수 있다.

```javascript
<script>
  function solution(arr) {
    let sum = 0;
    let min = Number.MAX_SAFE_INTEGER;
    for (let x of arr) {
      if (x % 2 === 1) {
        sum += x;
        if (x < min) min = x;
      }
    }
    return [sum, min]; // 1
  }
  arr = [12, 77, 38, 41, 53, 92, 85];
  let [resultSum, resultMin] = solution(arr); // 2
  console.log(resultSum); // 3
  console.log(resultMin); // 4
  </script>
```

1. 배열 형식으로 return 한다.
2. resultNum에는 solution() 함수를 실행하고 반환한 배열의 첫번째 값인 sum을 resultMin에는 두번째 값인 mind을 할당한다.
3. 2에서 수행한 resultNum 값 출력한다.
4. 2에서 수행한 resultMin 값 출력한다.

이렇게 코드를 작성한 후 결과값을 보면

**256**<br/>
**41**

이처럼 결과값이 두 줄로 출력된다.

※ 배운것: 새로운 for문 형식, 복수 값 return, 구조분해할당

---

## 10부제

푼 날짜: 2021.10.15

걸린 시간: 3m

'n의 자리만 필요하다'라는 뉘앙스가 있으면 나머지 연산을 생각해보자.
