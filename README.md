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

정석은 3개의 변의 길이 중에 첫번째로 짧은 변의 길이와 두번째로 짧은 변의 길이의 합이 가장 긴 변의 길이보다 길어야 한다는 것을 전제로 문제를 풀이하는 것이다. 나는 삼각형의 두 변의 길이의 합은 나머지 한 변의 길이보다 크다라는 것을 전제로 if 문을 이용해 모든 경우를 검사해서 풀이하였다. 첫번째 문제에서 세 수를 비교하는 방법을 이용해 가장 긴 변의 길이를 max에 넣어주고 total(세 변 길이의합)에서 max를 빼준 값과 max에 들어있는 값을 비교해서 판별하면 된다.
