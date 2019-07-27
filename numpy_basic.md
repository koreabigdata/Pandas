## numpy를 쓰는 이유
1. 속도가 빠르다
    - c로 만들어짐
    - 효율적인 데이터 구조(homogeneous, vectorization)  
2. 사용하기 편하다  
<br>

***vectorization 이란?**
- =array programming
- 여러개의 데이터를 하나의 묶음으로 처리한다
- for문을 쓰지 않는다
- 계산이 빨라진다
<br>

***차원**
- 1차원 : vector = 방향이 없다
- 2차원 : matrix 
- n차원 : n차원 tensor  
<br>

## 인스턴스화 방법 세가지
1. 클래스 이용
2. literal
3. factory method 이용
<br>

```python
import numpy as np
a = np.array((1,2))
```
- Factory method pattern : 인스턴스화하지 않고 다른 함수의 힘을 빌려 인스턴스화하는 것 
- homogenious하다 -> 다음 데이터타입이 뭐가 올 지 체크할 필요 없음
- = 속도가 빠르다
- mutable하다
<br>

```python
a = np.array([[1,2],[3,4]]) #2차원
a = np.array([[[1,2],[3,4]],[[1,2],[3,4]]]) #3차원
type(a)
```
>Out : numpy.ndarray
- 클래스다 = 인스턴스화할 수 있다
<br>

```python
n = np.ndarray([0,'1'])
```
>Out: TypeError
<br>

```python
a = np.array(['1',2,3])
a
```
>Out:array(['1', '2', '3'], dtype='<U1')
- homogeneous하기 때문에 string으로 다 바꿔준다
- 즉, factory method를 쓰면 에러도 안나고 편하다!   
<br>

## 배열 속성
```python
a = np.array([[1,2],[3,4]])
a.ndim #몇차원인지
a.shape #몇행 몇열인지
a.size #원소의 갯수
a.itemsize #각 원소가 몇비트인지
a.dtype #데이터타입
```
<br>

## numpy가 쉬운 이유
```python
x = [1,2,3,4]
y = [2,3,4,5]
x+y
```
>Out: [1, 2, 3, 4, 2, 3, 4, 5]
<br>

```python
a = np.array([[1,2],[3,4]])
b = np.array([[1,2],[3,4]])
```
>Out: array([[2, 4],
       [6, 8]])
- 파이썬은 옆에 붙여주지만 넘파이는 각 원소끼리 연산해준다 = element wise
<br>

```python
a = np.array([[1,2],[3,4]], dtype='u1')
a
```
>Out: array([[1, 2],
       [3, 4]], dtype=uint8)
- 데이터 타입을 만들어 줄 수 있다. (작은 범위까지 다 지원해 줌)
- np.sctypeDict (지원해주는 타입들)
<br>

## python 언더바 용법
1. 앞에 _하나 : 갈래상 private
2. 앞에 _하나 : from *할 때 import되지 않음
3. 앞에 _두개 : 맹글링
4. 앞뒤 _두개 : 매직메소드 or 스페셜메소드
5. 갈래상 필요 없는 변수 이름
6. 맨 마지막 결과를 담고 있음
7. _(a) : 다국어 처리할 때
8. 이름뒤에 _붙을 때 : 갈래상 파이썬 이름과 똑같을 경우 구분하기 위함
