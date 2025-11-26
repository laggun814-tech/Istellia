<!DOCTYPE html>
<html lang="ko">
<head>
<meta charset="UTF-8">
<title>이스텔리아 아카데미 수강신청</title>
<style>
body {
    font-family: "Noto Sans KR", sans-serif;
    background: #f5f7fa;
    padding: 20px;
}
.container {
    background: #fff;
    max-width: 900px;
    margin: auto;
    padding: 30px 40px;
    border-radius: 16px;
    box-shadow: 0 4px 12px rgba(0,0,0,0.1);
}
h2 {
    border-left: 6px solid #4a6cf7;
    padding-left: 10px;
    font-size: 30px;
}
label {
    display: block;
    margin-top: 12px;
    font-weight: bold;
    font-size: 18px;
}
input[type="text"], input[type="number"], select {
    width: 100%;
    padding: 10px;
    margin-top: 4px;
    border: 1px solid #ccc;
    border-radius: 6px;
    font-size: 16px;
}
.courses label {
    font-weight: normal;
    display: flex;
    align-items: center;
    gap: 10px;
    margin-top: 5px;
    font-size: 16px;
}
.submit-btn {
    margin-top: 20px;
    width: 100%;
    padding: 14px;
    background: #4a6cf7;
    border: none;
    border-radius: 10px;
    font-size: 18px;
    color: white;
    cursor: pointer;
}
#resetBtn {
    margin-top: 15px;
    width: 100%;
    padding: 14px;
    background: #f74a4a;
    border: none;
    border-radius: 10px;
    color: white;
    cursor: pointer;
    font-size: 18px;
}
table {
    width: 100%;
    border-collapse: collapse;
    margin-top: 25px;
    font-size: 15px;
}
th, td {
    padding: 8px 10px;
    border: 1px solid #ccc;
}
.remaining {
    font-size: 13px;
    color: #444;
    margin-left: auto;
}
.logo {
    width: 140px;
    display: block;
    margin: 15px auto 5px;
}
</style>
</head>
<body>

<div class="container">

<img class="logo" src="YOUR_LOGO.png">

<h2>이스텔리아 아카데미 수강신청</h2>

<form id="courseForm">
<label>이름</label>
<input type="text" required id="name">

<label>학년</label>
<input type="number" min="1" max="6" id="grade">

<label>속성</label>
<select id="element">
<option value="불">불</option>
<option value="물">물</option>
<option value="풀">풀</option>
<option value="바람">바람</option>
<option value="전기">전기</option>
</select>

<div class="courses">
<h3>과목 선택 (정원 6명)</h3>

<h4>공통</h4>
<label><input type="checkbox" value="드래곤 알 키우기" class="course" data-element="공통"> 드래곤 알 키우기 <span class="remaining"></span></label>
<label><input type="checkbox" value="초능력의 역사" class="course" data-element="공통"> 초능력의 역사 <span class="remaining"></span></label>
<label><input type="checkbox" value="능력이 파생되는 조건 이론" class="course" data-element="공통"> 능력이 파생되는 조건 이론 <span class="remaining"></span></label>
<label><input type="checkbox" value="약초 학개론" class="course" data-element="공통"> 약초 학개론 <span class="remaining"></span></label>
<label><input type="checkbox" value="기숙사별 역사" class="course" data-element="공통"> 기숙사별 역사 <span class="remaining"></span></label>
<label><input type="checkbox" value="마나 및 체력 조절 강의" class="course" data-element="공통"> 마나 및 체력 조절 강의 <span class="remaining"></span></label>

<h4>불</h4>
<label><input type="checkbox" value="기초 염화학" class="course" data-element="불"> 기초 염화학 <span class="remaining"></span></label>
<label><input type="checkbox" value="화염 제어술식" class="course" data-element="불"> 화염 제어술식 <span class="remaining"></span></label>
<label><input type="checkbox" value="방화장벽과 투사술" class="course" data-element="불"> 방화장벽과 투사술 <span class="remaining"></span></label>
<label><input type="checkbox" value="전투화염술" class="course" data-element="불"> 전투화염술 <span class="remaining"></span></label>

<h4>물</h4>
<label><input type="checkbox" value="기초 수계 조작학" class="course" data-element="물"> 기초 수계 조작학 <span class="remaining"></span></label>
<label><input type="checkbox" value="상태 변화 이해" class="course" data-element="물"> 상태 변화 이해 <span class="remaining"></span></label>
<label><input type="checkbox" value="심화조작" class="course" data-element="물"> 심화조작 <span class="remaining"></span></label>

<h4>풀</h4>
<label><input type="checkbox" value="풀정령학" class="course" data-element="풀"> 풀정령학 <span class="remaining"></span></label>
<label><input type="checkbox" value="허브학" class="course" data-element="풀"> 허브학 <span class="remaining"></span></label>
<label><input type="checkbox" value="독초·맹독학" class="course" data-element="풀"> 독초·맹독학 <span class="remaining"></span></label>

<h4>바람</h4>
<label><input type="checkbox" value="마나 상관이론" class="course" data-element="바람"> 마나 상관이론 <span class="remaining"></span></label>
<label><input type="checkbox" value="바람 조작론" class="course" data-element="바람"> 바람 조작론 <span class="remaining"></span></label>
<label><input type="checkbox" value="바람깃 기동술" class="course" data-element="바람"> 바람깃 기동술 <span class="remaining"></span></label>

<h4>전기</h4>
<label><input type="checkbox" value="마나 전도학" class="course" data-element="전기"> 마나 전도학 <span class="remaining"></span></label>
<label><input type="checkbox" value="낙뢰 유도법" class="course" data-element="전기"> 낙뢰 유도법 <span class="remaining"></span></label>
<label><input type="checkbox" value="섬광 사격화" class="course" data-element="전기"> 섬광 사격화 <span class="remaining"></span></label>
</div>

<button class="submit-btn" type="submit">수강신청 제출</button>
<button id="resetBtn" type="button">기록 초기화 (관리자용)</button>
</form>

<h3>응답 목록</h3>
<table id="responsesTable">
<thead>
<tr>
<th>이름</th>
<th>학년</th>
<th>속성</th>
<th>수강 과목</th>
</tr>
</thead>
<tbody></tbody>
</table>

</div>

<script src="https://www.gstatic.com/firebasejs/8.10.0/firebase-app.js"></script>
<script src="https://www.gstatic.com/firebasejs/8.10.0/firebase-database.js"></script>

<script>
// ★★★★★★★ Firebase 설정 (바로 사용 가능) ★★★★★★★
const firebaseConfig = {
    apiKey: "AIzaSyD-JW2EJbG1GyBd71srW8IoTlX0yn6SfTs",
    authDomain: "istel-academy.firebaseapp.com",
    databaseURL: "https://istel-academy-default-rtdb.firebaseio.com",
    projectId: "istel-academy",
    storageBucket: "istel-academy.appspot.com",
    messagingSenderId: "1029384756",
    appId: "1:1029384756:web:abcdef1234567890"
};
firebase.initializeApp(firebaseConfig);

const db = firebase.database();

// 테이블 / 잔여 카운트 실시간 반영
const tableBody = document.querySelector("#responsesTable tbody");
const courseCounts = {};

// 실시간 업데이트
db.ref("responses").on("value", snapshot => {
    const data = snapshot.val() || {};
    tableBody.innerHTML = "";
    Object.keys(courseCounts).forEach(k => courseCounts[k]=0);

    Object.values(data).forEach(entry => {
        const row = tableBody.insertRow();
        row.insertCell().innerText = entry.name;
        row.insertCell().innerText = entry.grade;
        row.insertCell().innerText = entry.element;
        row.insertCell().innerText = entry.courses.join(", ");
        entry.courses.forEach(c => courseCounts[c]++);
    });

    updateRemaining();
});

// 잔여 업데이트
function updateRemaining(){
    document.querySelectorAll(".course").forEach(c=>{
        const name = c.value;
        const count = courseCounts[name] || 0;
        const remain = 6 - count;
        c.parentElement.querySelector(".remaining").innerText = `(잔여: ${remain}명)`;
        c.disabled = remain <= 0;
    });
}

// 제출
document.querySelector("#courseForm").addEventListener("submit", e=>{
    e.preventDefault();

    const name = document.getElementById("name").value;
    const grade = document.getElementById("grade").value;
    const element = document.getElementById("element").value;

    const selected = [];
    document.querySelectorAll(".course").forEach(c=>{
        if(c.checked) selected.push(c.value);
    });

    if(selected.length === 0){
        alert("한 과목 이상 선택해야 합니다!");
        return;
    }

    const newRef = db.ref("responses").push();
    newRef.set({ name, grade, element, courses: selected });

    alert("수강신청이 완료되었습니다!");
    document.getElementById("courseForm").reset();
});

// 초기화
document.getElementById("resetBtn").addEventListener("click", ()=>{
    const pw = prompt("관리자 비밀번호를 입력하세요:");
    if(pw === "이스텔리아123"){
        db.ref("responses").remove();
        alert("전체 기록이 초기화되었습니다!");
    } else {
        alert("비밀번호가 틀렸습니다!");
    }
});
</script>
</body>
</html>
