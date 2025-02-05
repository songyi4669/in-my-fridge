# What-is-in-my-fridge 🧊🧅🥦
https://song-fridge.netlify.app

![ezgif com-gif-maker (1)](https://user-images.githubusercontent.com/81962246/129341557-e2e6ffdb-918c-4f51-aac9-9e0f5c71ed56.gif)


## 소개
-냉장고에 있는 식자재를 등록하여 앱으로 관리할 수 있는 프로젝트 입니다.

## 주요기능
1. 기존 소셜 계정으로 로그인 가능
2. 냉장고 아이템을 직접 등록할 수 있는 입력창
3. 아이템을 Add하면 실시간으로 냉장고 속 카드가 보여지고 실시간 수정 가능
4. Delete하면 아이템 카드 삭제 가능
5. 재접속 시 데이터 보존 가능
6. 파일 이미지 미 등록 시 기본 이미지 제공
7. 반응형으로 보다 보기 편한 UI


## 기술스택
이 프로젝트에 사용된 기술은 다음과 같습니다.
- React.js
- React.Hooks
- React.Router
- PostCSS
- Firebase
- Cloudinary


## 기능 상세
### 1. 기존 소셜 계정으로 로그인 가능
- Firebase로 기존 소셜 계정으로 로그인이 가능합니다.
- 로그인에 성공하면 React.Router을 사용하여 냉장고 메모 화면으로 전환됩니다.

### 2. 냉장고 아이템을 직접 등록할 수 있는 입력창
- 아이템 정보를 직접 입력할 수 있습니다.
- 아이템의 저장소(냉장/냉동)에 따라 카드의 배경 색이 달라집니다.
- Cloudinary를 이용하여 이미지 업로드가 가능합니다.

### 3. 아이템을 Add하면 실시간으로 냉장고 속 카드가 보여지고 실시간 수정 가능
- 아이템을 Add하면 냉장고 속 화면에 카드가 등록됩니다.
- 아이템을 등록하고 수정하면 실시간으로 냉장고 속 화면에 적용됩니다.

### 4. Delete하면 아이템 카드 삭제 가능
- 등록한 아이템을 Delete하면 삭제됩니다.

### 5. 재접속 시 데이터 보존 가능
- 앱을 나가거나 로그아웃 후, 재 로그인해도 firebase로 기존 데이터가 저장되어 보여집니다.

### 6. 파일 이미지 미 등록 시 기본 이미지 제공
- 아이템을 등록할 때 이미지 파일을 등록하지 않으면 지정된 기본 이미지로 업로드됩니다.

### 7. 반응형으로 보다 보기 편한 UI
- 반응형 CSS로 브라우저 크기에 따라 냉장고 채우기/냉장고 속 위치가 변경됩니다.



## 성능 개선
### 1. memo를 사용하여 불필요한 업데이트 제거
- 아이템 수정 시 업데이트 되는   
 header, footer, image_file_input, item, add_form, button을   
 memo로 업데이트가 발생하지 않도록 합니다. 
 
 ### 2. onLogout에 useCallback사용
- onLogout부분의 리랜더를 막기 위해 useCallback을 사용합니다.
```javascript
    const onLogout = useCallback(() => {
        authService.logout();
    }, [authService]);
```
([authService]을 통해 authService변경 시에는 새로운 콜백이 되도록 해줍니다.)
 
