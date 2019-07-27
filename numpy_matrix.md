## shape
```python
a = np.arange(10)
```
- python의 range와 같다
- 특정 범위만큼 array로 값을 만들어준다
<br>

```python
a.reshape(2,5)
```
>Out: array([[0, 1, 2, 3, 4],
[5, 6, 7, 8, 9]])
- 모양을 바꿀 수 있다
<br>

```python
a
```
>Out: array([0, 1, 2, 3, 4, 5, 6, 7, 8, 9])
- mutable이라면 값이 바뀌어야하는데..?
- mutable함수의 결과 세가지 중 2번에 해당  
   1. 자기 자신은 바뀌지만 리턴값 none
   2. 자기 자신이 바뀌지 않지만 리턴값 있음
   3. 자기 자신이 바뀌면서 리턴값 있음 (pop)  
<br>

```python
a = a.reshape(2,5) 
a
```
>Out: array([[0, 1, 2, 3, 4],
       [5, 6, 7, 8, 9]])
- reshape은 copy개념이라 재할당 해줘야 한다
<br>

```python
a.sum(0)
```
>Out: array([ 5,  7,  9, 11, 13])
- shift+tab -> 파라메터에 axis 들어감  

***axis**  
axis = 0 : 행끼리 계산
axis = 1 : 열끼리 계산
<br>

***stride**
```python
a.strides
```
>out: (40, 8)
- 최대공약수로 나눈다
- 5개가 한 행을 가진다
- a.size -> 10개 이므로 2행 5열
- 실제로는 한 행이지만, stride를 이용해서 자유롭게 바꿀 수 있다
- -> 계산을 매우 빠르게 만들어 준다
<br>

```python
%time sum(range(1000000000))
%time np.sum(np.arange(1000000000))   #이게 훨씬 빠르다!
```
<br>

## 배열 만들기

```python
a = np.zeros((3,4))  #(3,4)matrix 0으로 만들기
b = np.ones((3,3))  #(3,3)matrix 1로 만들기
c = np.full((3,2),6)  #(3,2)matrix 5으로 만들기

d = np.ones_like(a)  #_like : shape만 똑같은 애를 1로 만들어줌. 아주 자주쓴다!
d = np.zeros_like(a) #   "  0으로
```
<br>

```python
#단위행렬 만들기
b = np.eye(3)
c = np.identity(3)
```
<br>

```python
#전치행렬 만들기
b.T
```
- 상삼각 행렬, 하상각 행렬 등 이름 있는 행렬들 다 만들 수 있다
<br>

```python
#선형 구간, 혹은 로그 구간을 지정한 구간 수 만큼 분할
#e = np.logspace(1,100,5)
d = np.linspace(0,100,5)
```
>Out: array([  0.,  25.,  50.,  75., 100.])
<br>


```python
#초깃값 
e = np.empty((4,2))
```
<br>

## 특정 값 뽑아내기
- indexing, slicing
