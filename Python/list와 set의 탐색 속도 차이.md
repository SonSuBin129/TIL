## issue

[백준 1920번](https://www.acmicpc.net/problem/1920) 문제를 풀다가 list로는 시간초과가 나던 문제가 set로 변경 후 풀렸다.
<br/><br/>

## content

**💡 요약** <br/>
**set, dictionary**는 해시함수를 이용하여 해시값을 저장하고 있는 **해시테이블 자료구조**를 사용하기 때문에, 빠른 탐색이 가능하다.

list처럼 배열의 순서를 돌면서 탐색하는 것이 아니라, <br/>
해당 값의 해시 값을 알고 있으면 바로 접근할 수 있는 것이다!<br/>
따라서 list와 비교했을 때 set과 dictionary는 빠른 탐색이 가능하다.

<br/>

> **NOTE** <br/>
> list는 삭제할때 O(N)이지만, set과 dictionary는 O(1)이다.
> list의 인덱싱 a[i] 같은 경우는 O(1)이다.

<br/>

## 🧷 참조

- [왜 Dict는 List보다 빠를까](https://eumgill98.tistory.com/101)
