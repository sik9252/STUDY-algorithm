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
