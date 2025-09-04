# TwitterCheatCode
트위터/X의 콘솔창에서 실행할 수 있는 유용한 명령어들

# 경고/Warning
이 레포지토리 내 코드를 디버깅 콘솔창에서 실행함으로써 생기는 모든 문제에 대해 저(harunadev)는 책임지지 않습니다. 한국어 트위터/X에서만 사용 가능합니다.

모든 코드는 직접 작성되었으며, 100% 로컬에서 실행되며, 온라인으로 개인정보나 기타 데이터를 전송하지 않습니다. 코드를 실행하는것이 확실치 않다면 실행하지 마세요.

코드는 소리소문없이 작동 불가가 될 수 있습니다 _(예: 트위터가 조용히 웹 레이아웃을 변경하는 등)_. 이 경우가 발생하면 Issues에서 문제를 제보해주세요.

코드 분석이 필요하다면, ChatGPT나 Copilot등에게 코드 분석을 의뢰하세요.

I (harunadev) do not take any reponsibility of any problems occured by running the code on your browser. All codes in this are built to run on Korean Twitter/X page. Sorry English Users TT

## 팔로잉 창에서 맞팔 필터링하기
1. 본인 계정의 팔로잉 탭으로 이동 (`https://twitter.com/*계정*/following`)
2. F12를 눌러 디버그 창을 열고, Console창으로 이동, 아래 코드를 붙여넣고 엔터를 눌러 실행합니다.
```js
var temp1 = document.querySelector('[aria-label="타임라인: 팔로잉"]').firstChild; window.onscroll = function() {for (var i of temp1.children) {if (i.innerHTML.includes('userFollowIndicator')) {i.style.opacity = '0';}}}
```
3. 스크롤할때 마다 팔로잉 리스트가 업데이트가 되어, 맞팔된 유저는 투명처리, 맞팔이 되지 않은 유저는 표시됩니다.

## 팔로워 창에서 맞팔 필터링하기
1. 본인 계정의 팔로워 탭으로 이동 (`https://twitter.com/*계정*/followers`)
2. F12를 눌러 디버그 창을 열고, Console창으로 이동, 아래 코드를 붙여넣고 엔터를 눌러 실행합니다.
```js
var temp1 = document.querySelector('[aria-label="타임라인: 팔로워"]').firstChild; window.onscroll = function() {for (var i of temp1.children) {if (i.innerHTML.includes('언팔로우')) {i.style.opacity = '0';}}}
```
3. 스크롤할때 마다 팔로워 리스트가 업데이트가 되어, 맞팔된 유저는 투명처리, 맞팔이 되지 않은 유저만 표시됩니다.
