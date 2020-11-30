# bmil-web-creater

> A Vue.js project for bmilWeb

## Build Setup

1. git clone
2. npm install


``` bash
# install dependencies
npm install
```

1. 구글 스프레드 시트를 .xlsx(microsoft exel) 로 다운받는다

2. 엑셀 파일을 json 파일로 변경하는 프로그램을 실행시킨다.

```bash
node app.js 

```

3. http://localhost:4000/ 에 들어간다. 
4. 다운받은 엑셀파일을 선택해서 변환한다.
5. 변환된 json 형식 데이터를 복사해서  /src/assets/data/lab-data-fixed.json 로 저장한다. 
6. npm run dev로 실행한다. 

```bash
# serve with hot reload at localhost:8080
npm run dev
```



# 사용방법

<img src="/src/assets/web_sample_page.png">

1. paper, patents 를 보고 싶으면 기본 상태인 show main 버튼이 true 이면 된다. 
2. Weighted publication 이 보고 싶으면 show main이 true인 상태에서 weighted 버튼을 누르면된다.
3. 각 과제별 모아보기 기능을 누르면 show main이 false 인 상태에서 nrf, itrc, iitp 각 버튼을 누르면 된다. 



# 추가방법

> 만약 과제를 추가하고 싶으면 App.vue 파일을 수정해야됩니다.

1. 스프레드시트에 과제탭을 하나더 만든다. (ex SSUABC)

2. script 안 data에 SSUABCVisible를 추가한다. (ex. SSUABCVisible : false,) 

3. 버튼을 추가합니다. 아래 코드를 사진위치에 추가하면됩니다. template 태그 바로 아래쪽에 있음

   <img src="/src/assets/add_button.png">

4. ```
   <b-button :pressed.sync="SSUABCVisible" variant="outline-primary">SSUABC</b-button>
   ```

5. template 태그 안 내용 가장 아래쪽에 미리 추가해둔 샘플이 있습니다. 수정해서 사용하면됩니다.

   5.1 과제를 1개 이상 추가할시 그대로 복사해서 수정해서 사용하시면됩니다.

6. 추가해둔 샘플에서 item.SSUNRF -> item.SSUABC로 전부 수정합니다.

7. 추가해둔 샘플에서 NRFVisible => SSUABCVisible 로 전부 수정합니다.







