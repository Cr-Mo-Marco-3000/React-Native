# Focus 처리

> React Native에서는, 일반적인 React와는 달리 컴포넌트가 다시 부착되는 형태로 적용되는 것이 아니라, 한 번 부착되면 유지된다. 즉, useEffect를 사용하여 컴포넌트가 렌더링될 때 특정 함수를 실행하려 하면 한 번만 실행된다.
> 
> 이러한 문제를 해결하기 위해서 여러 가지 방식이 있는데, 그중에서도 Focus 방식으로 처리하는 방법을 알아보자.



## 1. navigation에 Focus 달기

- ### `onEndReachedThreshold`



## 2. useIsFocused

- 특정 컴포넌트가 Focus됐을 때 true로 변경되는 훅이다.

- useEffect의 의존성에 넣어 사용하는 등, 여러 가지 방법으로 사용하자.

- 사용 예시

```js
import { useIsFocused } from '@react-navigation/native';

const App = () => {
const isFocused = useIsFocused()
    return(...)
}

useEffect(()=>{
    console.log('포커스')
}, [isFocused])
```
