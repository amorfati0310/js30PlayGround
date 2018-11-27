## 배운 것 들 

1. async await 사용 
2. gist에서 raw로 해서 json mock data 요청 받을 수 있구나 

3. Question 의문

```js

const cities2 = []

const load = async(path)=>{
    const response = await fetch(path)
    console.log(response)
    const json = await response.json();
    cities2.push(...json);
    console.dir(cities2)
    return [...json];
    여기서 받은 걸로 쓰려고 하니까 프로미스 값으로 리턴 됨 
    결국 ... return 값을 promise로 씌워서 그런건가?
}

const cities = load(endpoint);
console.log(cities)

```


4. 정규표현식 

3번째마다 ,로 대체한다는 것이 /\B(?=(\d{3})+(?!\d))/g 왜 이게 되는지 !! 공부하기 ! 
```js
const numberWithCommas = (x)=> {
  return x.toString().replace(/\B(?=(\d{3})+(?!\d))/g, ',');
}

const numberWidthCommas = x=> x.toString().replace(/\B(?=(\d{3})+(?!\d))/g, ',')


```


4. findMatches함수 

regex+ match조합 

includes로 판별해도 좋을듯 ! 

state,includes(wordToMatch)
city, includes(wordTomacth)


5. displayMatches함수 

 value추출 -> findMatches로 가지고 옴 
 matchArray.map().join(')
 reduce 대신에 map.join()으로도 이렇게 할 수 있구나 


6. json이 뭐야?

javascript object noation ...
js객체와 유사한 타입인데 정보를 주고 받을 떄 제일 대표적인 type;;; 이거 말고 알아야 될 거 있으려나 ? 
 

