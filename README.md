f5c0db234dceada1adea1dc9025e8e28

## Firestore 빌드 속도 빠르게 하기!

### 원인
- could_firestore 패키지를 설치 후 실행하면 ios 네이티브 패키지가 설치됨
- ios 네이티브 패키지는 C++이란 언어로 500,000줄 이상으로 작성됨
- 이 코드를 기계어로 번역하는 과정이 매우 오래 걸렸었음!

### 해결방법
- https://github.com/invertase/firestore-ios-sdk-frameworks
- 위 레포지토리에서 이미 번역된 네이티브 패키지를 제공함
- 아래의 내용을 `Podfile`에 'target 'RunnerTests' do` 위에 붙이기
`pod 'FirebaseFirestore', :git => 'https://github.com/invertase/firestore-ios-sdk-frameworks.git', :tag => '10.19.0'`
- 실행하면 에러가 나는데 Firebase Core와 버전 맞추기
- 터미널에서 iod 폴더로 이동 후 `pod install -repo-update` 실행해서 패키지 업데이트해서 받아오기!