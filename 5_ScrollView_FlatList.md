# ScrollView and FlatList

> ScrollView와 FlatList는 둘 다, 특정한 페이지 내에서 다수의 리스트들을 렌더링한 후, 스크롤하여 이를 보여주는 컴포넌트들을 말한다.
> 
> React Native 내부적으로는 FlatList가 조금 더 효율적으로 동작하지만, 작성이 조금 더 복잡하다.

- ScrollView와 FlatList에 flex 등으로 height를 지정하거나, 혹은 이 컴포넌트들을 포함하는 parent에 높이를 지정하는 것을 잊지 말자.

- ScrollView에도 적용되는 사항인지 모르지만, FlatList 내부에서 렌더링되는 리스트들의 높이를 지정할 때는
  
  1. height를 주어 일정하게 고정시키거나
  
  2. 만약 내부 요소에 따라 높이가 변동될경우, 모든 요소에 flex:1를 적용시켜야 한다.
  - 다른 방법으로 높이를 주려 할 경우, 의도한 대로 렌더링이 되지 않는다.

- 이외의 컴포넌트 중 조금 더 효율적인 방식으로 VirtualizedList가 있는데, 이는 아직 다루어보지 않았다.



## 1. ScrollView

- 스크롤뷰는 일반적으로, 리스트들을 한 번에 렌더링할 때 쓴다.

- 따라서 리스트의 수가 매우 많고, 한 번에 모든 리스트를 보여줄 필요가 없을 때는 FlatList를 쓰는 것이 바람직하다.



---



## 2. FlatList

- 리스트들의 모든 요소를 렌더링하는 것이 아니라, 일부만 렌더링하고, 스크롤함에 따라 추가로 렌더링하는 무한 스크롤등을 사용할 때 적합하다.

### props

1. data
   
   - FlatList 내부에서 렌더링될 리스트에 들어갈 데이터들의 배열이다.

2. renderItem
   
   - FlatList 내부에 렌더링할 요소 컴포넌트들이다.

3. keyExtractor
   
   - 리스트 렌더링시 사용될 key로 사용될 변수를 넣는다.
   
   - 여기서 특이한 점은 `keyExtractor={(item)=> item.id}` 이렇게 함수로 넣는다는 것이다.

4. extraData
   
   - 데이터를 추가로 넣고 싶을 때, 사용하는 것 같은데 아직 모르겠다.
   
   - 초기 렌더링 이슈 등이 생겼는데, 이를 통해 해결하는 것 같다.

5. onReached
   
   - 함수를 value로 넣어, 스크롤하여 FlatList의 끝에 스크롤이 닿았을 때, 그 함수를 실행한다.
   
   - 무한스크롤을 구현할 때 쓰인다.
   
   - onEndReachedThreshold prop을 같이 사용하여, 스크롤 끝에 완충 높이를 정할 수도 있다.

### Methods

- useRef를 통해 사용한다.

- scrollToEnd(), scrollToIndex()등이 있다.
  
  - 어떤 용도인지는 감이 올 것이다.
