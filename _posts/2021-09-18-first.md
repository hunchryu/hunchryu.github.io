# __[Python] 프로그래머스 LV.1: 숫자 문자열과 영단어__


> ## __문제 링크: https://programmers.co.kr/learn/courses/30/lessons/81301__


### __문제의 목표!__

___영어와 숫자가 무작위로 섞인 번호의 조합을 숫자로 바꾸어 출력하라!___

### __코드 전문__


```python
def solution(s):
    dict_num = {"zero": 0, "one": 1, "two": 2, "three": 3,
               "four": 4, "five": 5, "six": 6, "seven": 7,
               "eight": 8, "nine": 9}
    answer = ''; tmp = ''
    for x in s:
        # 숫자인 경우
        if x.isdigit():
            answer += str(x)
            continue
        # 알파벳인 경우
        tmp += x
        if tmp in dict_num.keys():
            answer += str(dict_num[tmp])
            tmp = ''
    return int(answer)
```

### __풀이 별 단계__

#### 1. 번호 사전 만들기

if문으로 숫자마다 바꾸는 코드를 쓰기에는 가독성도 떨어지고 불필요하게 길어지기 때문에, 사전을 이용한다.


```python
dict_num = {"zero": 0, "one": 1, "two": 2, "three": 3,
               "four": 4, "five": 5, "six": 6, "seven": 7,
               "eight": 8, "nine": 9}
```

#### 2. 한 글자 한 글자 읽어가며, 숫자인지 문자인지 판단한다.

푸는 방법이 여러 가지가 있지만, 가장 먼저 떠오른 방법으로 접근했다.

1. 읽은 것이 숫자일 경우, 바로 answer에 추가한다.

2. 문자일 경우, 단어가 완성될 때까지 계속 영어가 나올 것이다.

3. 고로 따로 tmp에 저장하여 단어가 완성될 때까지 철자를 모은다.

4. 단어가 완성되면, 그에 해당하는 숫자를 사전에서 찾아 answer에 추가하고, tmp는 초기화한다.


제시되는 순서대로 숫자를 추가하기 편하도록 문자열 type에서 풀이를 진행했다.

따라서 사전에서 숫자를 찾아 answer에 넘겨줄 때는 str() 함수를 이용하여 넘겨줬다.

* 여기서 애초에 사전에서 value들을 문자열로 만들었으면 더 깔끔한 코드가 완성됐을 것 같다.


```python
# example
s = "one4seveneight"; tmp = ''; answer = ''
for x in s:
        # 숫자인 경우
        if x.isdigit():
            answer += str(x)
            continue
        # 알파벳인 경우
        tmp += x
        if tmp in dict_num.keys():
            answer += str(dict_num[tmp])
            tmp = ''
```

#### 3. 완성된 answer를 출력한다.

* 여기서 주의할 점은 answer가 현재 __문자열__이라는 것이다.

* 따라서 __int()__를 통해 정수형으로 변경해 출력해야지 문제 조건에 부합하는 답을 제출할 수 있다.


```python
print(int(answer))
```

    1478
    


```python

```
