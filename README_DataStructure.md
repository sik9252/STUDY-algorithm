# STUDY-algorithm

**자료구조와 알고리즘에 대한 공부 기록**

---

<a href="https://fastcampus.co.kr/dev_online_algo">공부할때 수강한 인강</a>

---

## 배열

### 배열이 필요한 이유

- 같은 종류의 데이터를 효율적으로 관리하기 위해 사용
- 같은 종류의 데이터를 순차적으로 저장하기 위해 사용

### 배열의 장/단점

- [장점] 빠른 접근이 가능
- [단점] 추가/삭제가 쉽지 않음, 최대 길이를 미리 지정해야 함

### 파이썬에서 배열 사용법

<1차원 배열>

```python
  data = [1, 2, 3, 4]

  >> data

  [1, 2, 3, 4]

  <2차원 배열>

  data = [[1,2,3], [4,5,6], [7,8,9]]

  >> data

  [[1,2,3], [4,5,6], [7,8,9]]

  >> print(data[0])

  [1,2,3]

  >> print(data[0][0])

  1
```

그럼 print(data[0][2])는? ⇒ 3

### 프로그래밍 연습

1. 2차원 배열 data = [[1,2,3], [4,5,6], [7,8,9]]에서 9, 8, 7 순서로 출력해보기

```python
data = [[1,2,3], [4,5,6], [7,8,9]]
print(data[2][2]) # 9
print(data[2][1]) # 8
print(data[2][0]) # 7
```

1. 다음 dataset 에서 전체 이름 안에 M이 몇번 나왔는지 빈도수 체크하기

```python
dataset = ['Braund, Mr. Owen Harris',
'Cumings, Mrs. John Bradley (Florence Briggs Thayer)',
'Heikkinen, Miss. Laina',
'Futrelle, Mrs. Jacques Heath (Lily May Peel)',
'Allen, Mr. William Henry',
'Moran, Mr. James',
'McCarthy, Mr. Timothy J',
'Palsson, Master. Gosta Leonard',
'Johnson, Mrs. Oscar W (Elisabeth Vilhelmina Berg)',
'Nasser, Mrs. Nicholas (Adele Achem)',
'Sandstrom, Miss. Marguerite Rut',
'Bonnell, Miss. Elizabeth',
'Saundercock, Mr. William Henry',
'Andersson, Mr. Anders Johan',
'Vestrom, Miss. Hulda Amanda Adolfina',
'Hewlett, Mrs. (Mary D Kingcome) ',
'Rice, Master. Eugene',
'Williams, Mr. Charles Eugene',
'Vander Planke, Mrs. Julius (Emelia Maria Vandemoortele)',
'Masselmani, Mrs. Fatima',
'Fynney, Mr. Joseph J',
'Beesley, Mr. Lawrence',
'McGowan, Miss. Anna "Annie"',
'Sloper, Mr. William Thompson',
'Palsson, Miss. Torborg Danira',
'Asplund, Mrs. Carl Oscar (Selma Augusta Emilia Johansson)',
'Emir, Mr. Farred Chehab',
'Fortune, Mr. Charles Alexander',
'Dwyer, Miss. Ellen "Nellie"',
'Todoroff, Mr. Lalio']

count_M = 0
for data in dataset:
    for i in range(len(data)):
        if data[i] == 'M':
            count_M += 1

print(count_M) # 38
```

for data in dataset을 왜 하는건지 궁금해서 바로 아래에 print(data)를 적어서 실행해 보았다.

```python
count_M = 0
for data in dataset:
    print(data)
    for i in range(len(data)):
        if data[i] == 'M':
            count_M += 1
print(count_M)
```

```
  Braund, Mr. Owen Harris
  Cumings, Mrs. John Bradley (Florence Briggs Thayer)
  Heikkinen, Miss. Laina
  Futrelle, Mrs. Jacques Heath (Lily May Peel)
  Allen, Mr. William Henry
  Moran, Mr. James
  McCarthy, Mr. Timothy J
  ...
```

그랬더니 위와 같이 출력되는걸 보아 data는 dataset[]을 돌며 ''안의 문장 하나하나를 훑어가는 역할을 하고 있었다.

그러면 for i in range(len(data))에서 각각의 data[i]는 뭘 나타내는 걸까?

```python
count_M = 0
for data in dataset:
    for i in range(len(data)):
        print(data[i])
        if data[i] == 'M':
            count_M += 1
print(count_M)
```

```
B
r
a
u
n
d
,

M
r
.

O
w
e
n

H
a
r
r
i
s
...
```

이런식으로 ''안의 문자열 한개 한개가 출력된다. 따라서 이렇게 한글자 한글자 훑어가며 M을 발견하면 count를 세는 것이다.

---

## Queue - 큐

### 큐 구조

- 가장 먼저 넣은 데이터를 가장 먼저 꺼낼 수 있는 구조(FIFO)

### 알아둘 용어

- Enqueue: 큐에 데이터를 삽입(가장 뒤에 삽입됨)
- Dequeue: 큐에서 데이터를 꺼냄(가장 앞에 있는게 꺼내짐)

파이썬 queue 라이브러리에서 아래와 같은 큐 라이브러리를 제공하지만 한번쯤은 직접 코드를 작성해보자.

- Queue(): 가장 일반적인 큐 자료 구조
- LifoQueue(): 나중에 입력된 데이터가 먼저 출력되는 구조(스택 구조)
- PriorityQueue(): 데이터마다 우선순위를 넣어, 우선순위가 높은 순으로 데이터가 출력되는 구조

### Queue()로 큐 만들기 → FIFO

```python
import queue

data_queue = queue.Queue() # data_queue라는 queue 생성

data_queue.put('hello') # 삽입
data_queue.put(1) # 삽입
data_queue.qsize() # 큐 사이즈 확인, 2
data_queue.get() # 'hello', 맨 앞에 있는(가장 먼저 넣은) 데이터가 출력됨
data_queue.qsize() # 1, get으로 인해 hello가 빠져 나왔기 때문에 2->1이 됨
data_queue.get() # 1
data_queue.qsize() # 0
```

### LifoQueue()로 큐 만들기 → LIFO

```python
import queue

data_queue = queue.LifoQueue()

data_queue.put('hello')
data_queue.put(1)
data_queue.qsize() # 2
data_queue.get() # 1, LIFO 정책이니까 맨 뒤에 있는(가장 나중에 넣은) 데이터가 출력됨
```

### PriorityQueue()로 큐 만들기

데이터가 넣어질때 매겨진 우선순위 중 가장 우선순위가 높은 데이터를 추출하게 됨(1이 우선순위 높음)

자료구조나 알고리즘에서 많이 쓰일 수 있는 큐임

```python
import queue

data_queue = queue.PriorityQueue()

data_queue.put((10, 'korea')) # put((우선순위, '데이터')) -> 데이터는 하나인데 튜플 형식으로 들어감
data_queue.put((5, 1)) # 우선순위는 5, 실제 데이터는 1
data_queue.put((15, 'japan'))
data_queue.qsize() # 3
data_queue.get() # (5, 1)
```

### 큐는 어디에 많이 쓰일까?

- 멀티 태스킹을 위한 프로세스 스케쥴링 방식을 구현하기 위해 많이 사용함(운영체제)

따라서 큐의 활용 예로 픞로세스 스케쥴링 방식을 함께 이해해두는 것이 좋다. 질문에 나올 수도 있음

### 프로그래밍 연습

1. 리스트 변수로 큐를 다루는 enqueue, dequeue를 구현해보자.

```python
queue_list = list()

def enqueue(data)
	queue_list.append(data)

def dequeue()
	data = queue_list[0]
	del queue_list[0] # 주의해야할 부분, 꼭 삭제를 해줘야 반복되지 않음
	return data
```

```python
for index in range(10):
	enqueue(index)

len(queue_list) # 10

dequeue()
# 0 -> 1 -> ... 순으로 출력(왜냐면 큐에 0이 제일 먼저 들어갔으므로 제일 먼저 나옴)
```

---
