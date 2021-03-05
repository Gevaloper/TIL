# Dictonary 자료형

중괄호{}를 사용하며 key와 value를 연관시켜서 저장하는 자료형
이 때 key는 중복되면 안 되고 수정되는 자료형이어서는 안 된다. 즉, Tuple은 가능하나 List는 불가능하다.
하지만 value는 어떤 자료형이든 상관 없다.
unordered하므로 index로 접근하는 Tuple, List와는 달리 key값으로 접근한다.

## 연산과 함수
### 추가
#### dict[key] = value
기존에 존재하지 않은 key에 value를 연관시켜서 추가한다.
```python
>>> a = {'name': 'pey', 'phone' : '0119993233', 'birth' : '1118'}
>>> a['age'] = 30
>>> a
{'name': 'pey', 'phone': '0119993233', 'birth': '1118', 'age': 30}
```
기존에 존재하는 key를 사용하면 해당 key의 value가 바뀐다.
```python
>>> a['birth'] = '0115'
>>> a
{'name': 'pey', 'phone': '0119993233', 'birth': '0115', 'age': 30}
```
### 삭제
#### del dict[key]
key에 해당하는 요소를 삭제한다.
```python
>>> del a['age']
>>> a
{'name': 'pey', 'phone': '0119993233', 'birth': '0115'}
```
#### dict.clear()
dictionary의 모든 요소를 삭제하여 dictionary를 비운다.
```python
>>> a.clear()
>>> a
{}
```

### key, value 반환하기
#### dict.get(key)
key에 해당하는 value를 반환한다. 
```python
>>> a = {'name': 'pey', 'phone': '0119993233', 'birth': '1118'}
>>> a.get('name')
'pey'
```
같은 결과를 a[key]를 통해서 얻을 수 있다.
```python
>>> a['name']
'pey'
```
key가 존재하지 않을 경우 None을 반환한다.
```python
>>> print(a.get('address'))
None
```
dict.get(key, default)를 이용하면 key값이 존재하지 않을 경우 default를 반환한다.
```python
>>> print(a.get('address', 'Korea'))
Korea
```
#### dict.keys()
dictionary의 모든 key를 dict_keys 객체로 반환한다.
list()를 이용하여 리스트로 변환할 수 있다.
```python
>>> a.keys()
dict_keys(['name', 'phone', 'birth'])
```
#### dict.values()
dictionary의 모든 value를 dict_values 객체로 반환한다.
list()를 이용하여 리스트로 변환할 수 있다.
```python
>>> a.values()
dict_values(['pey', '0119993233', '1118'])
```
#### dict.itesm()
dictionary의 모든 key와 value를 dict_items 객체로 반환한다.
이 때 연관된 key와 value는 Tuple로 묶인다.
list()를 이용하여 리스트로 변환할 수 있다.
```python
>>> a.items()
dict_items([('name', 'pey'), ('phone', '0119993233'), ('birth', '1118')])
```

### 기타
#### key in dict
key가 dict안에 있는지 확인하여 있다면 True를 없다면 False를 반환한다.
```python
>>> 'name' in a
True
>>> 'address' in a
False

```