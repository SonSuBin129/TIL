## issue

파이썬은 동등 비교 연산자로 그냥 비교가 가능할까?
<br/><br/>

## content

**💡 요약** <br/>
**list**는 ==(동등 비교 연산자)를 통해서 리스트의 길이가 같고 and 요소들이 같을 경우 True, 아닌 경우 False를 반환한다.

```python
# 동등 비교
list1 = [1,2,3]
list2 = [1,2,3]
list3 = [1,2,3,4]

print(list1==list2) # True 출력
print(list1==list3) # False 출력

## 차이점 찾기: set 함수 활용
list1 = [1,2,3]
list2 = [2,3,4]

print(set(list1)-set(list2)) # {1} 출력
print(set(list2)-set(list1)) # {4} 출력
```

<br/>

> **NOTE** <br/>
> C에서는 배열 이름이 포인터로 취급되기 때문에, 동등 비교 연산자로 비교가 불가능하다.

<br/>

## 🧷 참조

- [파이썬에서 리스트 비교하기](https://datasciencebeehive.tistory.com/42)
