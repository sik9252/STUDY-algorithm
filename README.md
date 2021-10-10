# STUDY-algorithm

**자료구조와 알고리즘에 대한 공부 기록
with JavaScript**

---

[규칙] 먼저 내가 스스로 작성한 코드를 html 파일의 윗부분에 작성하고

모범 답안을 아래에 작성한다.

---

<a href="https://www.inflearn.com/course/%EC%9E%90%EB%B0%94%EC%8A%A4%ED%81%AC%EB%A6%BD%ED%8A%B8-%EC%95%8C%EA%B3%A0%EB%A6%AC%EC%A6%98-%EB%AC%B8%EC%A0%9C%ED%92%80%EC%9D%B4">공부할때 수강한 인강</a>

---

## 세 수 중 최소값 구하기

푼 날짜: 2021.10.10

걸린 시간: 9m

나는 a, b, c를 모두 각각 비교해 주었는데 if/else문 한개로 먼저 a와 b를 비교해 그 중 작은 수를 answer에 넣고 마지막에 if문 하나로 answer에 들어있는 값(a 혹은 b겠지)과 c를 비교해주면 더욱 짧은 코드로 작성이 가능했다. 즉, 하나씩 모두 비교할 필요 없이 <u>두 수를 먼저 비교해서 answer 변수에 저장해두고 남은 수와 answer를 비교하면 된다.</u>
