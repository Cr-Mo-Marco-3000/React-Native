# Initiating React Native

> React Native 프로젝트를 빌드할 때 여러 가지 방법이 있다.
> 
> 세팅이 필요하다
> 
> [세팅 Doc](https://reactnative.dev/docs/environment-setup)

- `npx react-native init AwesomeProject`
  
  - 기본 뼈대만 제공하므로 쓰지 않는다.
  
  - 세팅이 정상적으로 됐는지 확인하기 위해서만 사용한다.
  
  - 만약 설치 과정에서 문제가 생겼다면
    
    - `npm uninstall -g react-native-cli @react-native-community/cli`
    
    - `npm uninstall react-native-cli @react-native-community/cli`
    
    - 로컬 & 글로벌 두 번 날리고 시작하자 => 로컬이 표시가 되지 않아도 날려보자

## 실행

- Metro Server만 실행
  
  - `npm start`

- `npx react-native run-android`
  
  - npx react-native run-ios`

- `npm run android`
  
  - `npm run ios`

## 어떤 빌드 툴을 사용할 것인가?

## 1. Ignite

- React Native 앱을 생성해주는 CLI
  
  - Boilerplate, Build tool

- 사용하는 것도 좋지만, 직접 설정하고픈 파일들까지 설치되기 때문에, 주의!
  
  - expo등도 설치된다.

- Ignite 코드를 참고하면, 좋은 코드를 짤 때 도움이 될 수 있다.

## 2. Create React Native App

- 페이스북과 Expo의 합작
  
  - Expo의 문제는, 안드로이드랑 iOS파일에 접근을 못한다는 것

- 우리가 접근해야 하는 Native 파일에 접근 권한을 가진 어플을 만들어준다.
  
  - 안드로이드나 IOS 파일에 접근 가능하다!
  
  - 동시에 Expo로도 작업이 가능하다!
    
    - Expo SDK에도 접근이 가능
    
    - `expo install ~~~`

- 
