# Focus 처리

> React Native에서는, 일반적인 React와는 달리 컴포넌트가 다시 부착되는 형태로 적용되는 것이 아니라, 한 번 부착되면 유지된다. 즉, useEffect를 사용하여 컴포넌트가 렌더링될 때 특정 함수를 실행하려 하면 한 번만 실행된다.
> 
> 이러한 문제를 해결하기 위해서 여러 가지 방식이 있는데, 그중에서도 Focus 방식으로 처리하는 방법을 알아보자.

## 1. navigation에 Focus 달기

-

## 2. Hook 사용

### 1. useIsFocused

- 특정 컴포넌트가 Focus됐을 때 true로 변경되는 훅이다.

- 즉, 포커스 된 상태를 나타내는 훅이라고 할 수 있다.

- useEffect의 의존성에 넣어 사용할 수도 있지만, 그런 용도로는 useFocusEffect도 존재한다.

- 사용 예시
1. 조건부 렌더링에 사용하기

```js
import { useIsFocused } from "@react-navigation/native"

const App = () => {
  const isFocused = useIsFocused()

  return <Text>{isFocused ? "focused" : "unfocused"}</Text>
}
```

2. useEffect 의존성에 넣어 사용하기

```js
import { useIsFocused } from '@react-navigation/native';

const App = () => {
const isFocused = useIsFocused()
    return (
    <RenderingCodes><RenderingCodes />)
}

useEffect(()=>{
    console.log('포커스')
}, [isFocused])
```

### 3. useFocusEffect

- 특정 스크린이 Focus 될 때마다 SideEffect를 실행하고 싶을 때 사용한다.

- 아직 사용해 보지 않고, 위의 useIsFocused와 useEffect를 합쳐 사용했다.

- useCallback을 같이 사용하는 것이 필수라 한다.

```js
import { useFocusEffect } from '@react-navigation/native';

function Profile({ userId }) {
  const [user, setUser] = React.useState(null);

  useFocusEffect(
    React.useCallback(() => {
      const unsubscribe = API.subscribe(userId, user => setUser(user));

      return () => unsubscribe();
    }, [userId])
  );

  return <ProfileContent user={user} />;
}
```
