# 인덱스.html 
<!DOCTYPE html><html lang="ko">
<머리>
 <meta charset=>UTF-8" />
 <meta 이름="viewport" 콘텐츠="width=장치 너비, 초기 규모=1.0" />
 <title>·✿☆ 말랑노트 ☆✿·</title>
 <스타일>
 본문 {
 폰트 패밀리: '아리알', 산세리프;
 배경색: #ff0f5;
 색상: #333;
 텍스트 align: 중심;
 패딩: 2rem;
 }
 h1 {
 color: #ff69b4;
 }
 #메시지 {
 여백 상단: 1rem;
 패딩: 1rem;
 배경: 흰색;
 국경 radius: 1rem;
 최대 너비: 400 px;
 여백 왼쪽: 자동;
 여백 오른쪽: 자동;
 }
 .message {
 테두리 하단: px 점선 #ccc;
 패딩: 0.5렘 0;
 }
 입력, 버튼 {
 패딩: 0.5렘;
 여백: 0.5rem;
 국경 radius: 10 px;
 경계: 1 px 고체 #cc;
 }
 버튼 {
 배경색: #ffb6c1;
 색상: 흰색;
 커서: 포인터;
 }
 버튼: hover {
 배경색: #ff69b4;
 }
 </스타일>
</머리>
<바디>
 <h1>❤️ 말랑노트 익명 게시판 ❤️</h1>
 <div>
 <입력 유형="text" id="newMessage" 플레이스홀더="드림을 입력하세요!" />
 <버튼 클릭="메시지 보내기()">보내기</버튼>
 </div>
 <div id="messages"></div><!-- Firebase SDK --> <script src="https://www.gstatic.com/firebasejs/9.6.10/firebase-app-compat.js "></script><script src="https://www.gstatic.com/firebasejs/9.6.10/firebase-database-compat.js "></script></script><script><script>
 const firebaseConfig = {
 apiKey: "—————————————",
 authDomain: "———————————",
 데이터베이스URL: "———————————",
 projectId: "———————————",
 스토리지버킷: "——————————————",
 messagingSenderId: "————————————",
 appId: "——————————"
 };
 화력 기지.initializeApp(firebaseConfig);
 const db = firebase.database();

 함수 sendMessage() {
 const text = document.getElementById('newMessage').가치;
 만약 (텍스트. trim()) {
 db.ref ('messages').push({ 텍스트});
 document.getElementById('newMessage').값 = '';
 }
 }

 db.ref ('messages').on('child_added', (snapshot) => {
 const message = snapstash.val ();
 const div = document.createElement('div');
 div.classList.add('메시지');
 div.textContent = 메시지.텍스트;
 document.getElementById('메시지').appendChild(div);
 });
 </script></body>
</html>

