<!DOCTYPE html>
<html lang="ko">
<head>
<meta charset="UTF-8">
<title>이스텔리아 아카데미 수강신청</title>
<style>
body { font-family: "Noto Sans KR", sans-serif; background: #f5f7fa; padding: 20px; }
.container { background: #fff; max-width: 800px; margin: auto; padding: 25px 35px; border-radius: 12px; box-shadow: 0 4px 12px rgba(0,0,0,0.1); }
h2 { border-left: 6px solid #4a6cf7; padding-left: 10px; }
label { display: block; margin-top: 12px; font-weight: bold; }
input[type="text"], input[type="number"], select { width: 100%; padding: 8px; margin-top: 4px; border: 1px solid #ccc; border-radius: 6px; }
.courses label { font-weight: normal; display: flex; align-items: center; gap: 8px; margin-top: 5px; }
.submit-btn { margin-top: 20px; width: 100%; padding: 12px; background: #4a6cf7; border: none; border-radius: 8px; font-size: 16px; color: white; cursor: pointer; }
#resetBtn { margin-top: 15px; width: 100%; padding: 10px; background: #f74a4a; border: none; border-radius: 8px; color: white; cursor: pointer; font-size: 14px; }
table { width: 100%; border-collapse: collapse; margin-top: 25px; }
table, th, td { border: 1px solid #ccc; }
th, td { padding: 6px 8px; text-align: left; }
#welcome { margin-top: 20px; font-size: 16px; font-weight: bold; color: #4a6cf7; }
.remaining { font-size: 12px; color: #555; margin-left: auto; }
</style>
</head>
<body>

<div class="container">
<h2>이스텔리아 아카데미 수강신청 폼</h2>

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
<label><input type="checkbox" value="드래곤 알 키우기" class="course" data-max="6" data-element="공통"> 드래곤 알 키우기 <span class="remaining"></span></label>
<label><input type="checkbox" value="초능력의 역사" class="course" data-max="6" data-element="공통"> 초능력의 역사 <span class="remaining"></span></label>
<label><input type="checkbox" value="능력이 파생되는 조건 이론" class="course" data-max="6" data-element="공통"> 능력이 파생되는 조건 이론 <span class="remaining"></span></label>
<label><input type="checkbox" value="약초 학개론" class="course" data-max="6" data-element="공통"> 약초 학개론 <span class="remaining"></span></label>
<label><input type="checkbox" value="기숙사별 역사" class="course" data-max="6" data-element="공통"> 기숙사별 역사 <span class="remaining"></span></label>
<label><input type="checkbox" value="마나 및 체력 조절 강의" class="course" data-max="6" data-element="공통"> 마나 및 체력 조절 강의 <span class="remaining"></span></label>

<h4>불</h4>
<label><input type="checkbox" value="기초 염화학" class="course" data-max="6" data-element="불"> 기초 염화학 <span class="remaining"></span></label>
<label><input type="checkbox" value="화염 제어술식" class="course" data-max="6" data-element="불"> 화염 제어술식 <span class="remaining"></span></label>
<label><input type="checkbox" value="방화장벽과 투사술" class="course" data-max="6" data-element="불"> 방화장벽과 투사술 <span class="remaining"></span></label>
<label><input type="checkbox" value="전투화염술" class="course" data-max="6" data-element="불"> 전투화염술 <span class="remaining"></span></label>

<h4>물</h4>
<label><input type="checkbox" value="기초 수계 조작학" class="course" data-max="6" data-element="물"> 기초 수계 조작학 <span class="remaining"></span></label>
<label><input type="checkbox" value="상태 변화 이해" class="course" data-max="6" data-element="물"> 상태 변화 이해 <span class="remaining"></span></label>
<label><input type="checkbox" value="심화조작" class="course" data-max="6" data-element="물"> 심화조작 <span class="remaining"></span></label>

<h4>풀</h4>
<label><input type="checkbox" value="풀정령학" class="course" data-max="6" data-element="풀"> 풀정령학 <span class="remaining"></span></label>
<label><input type="checkbox" value="허브학" class="course" data-max="6" data-element="풀"> 허브학 <span class="remaining"></span></label>
<label><input type="checkbox" value="독초·맹독학" class="course" data-max="6" data-element="풀"> 독초·맹독학 <span class="remaining"></span></label>

<h4>바람</h4>
<label><input type="checkbox" value="마나 상관이론" class="course" data-max="6" data-element="바람"> 마나 상관이론 <span class="remaining"></span></label>
<label><input type="checkbox" value="바람 조작론" class="course" data-max="6" data-element="바람"> 바람 조작론 <span class="remaining"></span></label>
<label><input type="checkbox" value="바람깃 기동술" class="course" data-max="6" data-element="바람"> 바람깃 기동술 <span class="remaining"></span></label>

<h4>전기</h4>
<label><input type="checkbox" value="마나 전도학" class="course" data-max="6" data-element="전기"> 마나 전도학 <span class="remaining"></span></label>
<label><input type="checkbox" value="낙뢰 유도법" class="course" data-max="6" data-element="전기"> 낙뢰 유도법 <span class="remaining"></span></label>
<label><input type="checkbox" value="섬광 사격화" class="course" data-max="6" data-element="전기"> 섬광 사격화 <span class="remaining"></span></label>

</div>

<button class="submit-btn" type="submit">수강신청 제출</button>
<button id="resetBtn">기록 초기화 (관리자용)</button>
</form>

<div id="welcome"></div>

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

<script>
const courseCounts = {};
document.querySelectorAll(".course").forEach(c => { courseCounts[c.value]=0; });

// 남은 인원 표시
function updateRemaining(){
    document.querySelectorAll(".course").forEach(c=>{
        const remaining = c.dataset.max - courseCounts[c.value];
        c.parentElement.querySelector(".remaining").innerText = `(잔여: ${remaining}명)`;
        c.disabled = remaining <= 0;
    });
}

const form = document.getElementById("courseForm");
const tableBody = document.getElementById("responsesTable").querySelector("tbody");
const elementSelect = document.getElementById("element");
const welcomeDiv = document.getElementById("welcome");

// 페이지 로드 시 localStorage 복원
window.addEventListener("load", function(){
    const storedData = JSON.parse(localStorage.getItem("courseResponses") || "[]");
    storedData.forEach(entry=>{
        const row = tableBody.insertRow();
        row.insertCell().innerText = entry.name;
        row.insertCell().innerText = entry.grade;
        row.insertCell().innerText = entry.element;
        row.insertCell().innerText = entry.courses.join(", ");
        entry.courses.forEach(c=>courseCounts[c]++);
    });
    updateRemaining();
});

// 속성별 선택 제한
document.querySelectorAll(".course").forEach(c=>{
    c.addEventListener("click", function(){
        const selectedElement = elementSelect.value;
        if(c.dataset.element !== "공통" && c.dataset.element !== selectedElement){
            alert("선택한 과목은 본인의 속성과 맞지 않습니다!");
            c.checked=false;
        }
    });
});

// 제출 이벤트
form.addEventListener("submit", function(e){
    e.preventDefault();
    const name = document.getElementById("name").value;
    const grade = document.getElementById("grade").value;
    const element = document.getElementById("element").value;

    const selectedCourses=[];
    document.querySelectorAll(".course").forEach(c=>{
        if(c.checked){
            const courseName=c.value;
            if(courseCounts[courseName]<6){
                courseCounts[courseName]++;
                selectedCourses.push(courseName);
            } else {
                alert(courseName+" 정원이 꽉 찼습니다!");
                c.checked=false;
            }
        }
    });

    if(selectedCourses.length===0){ alert("적어도 한 과목은 선택해야 합니다!"); return; }

    const row=tableBody.insertRow();
    row.insertCell().innerText=name;
    row.insertCell().innerText=grade;
    row.insertCell().innerText=element;
    row.insertCell().innerText=selectedCourses.join(", ");

    const storedData = JSON.parse(localStorage.getItem("courseResponses")||"[]");
    storedData.push({name, grade, element, courses:selectedCourses});
    localStorage.setItem("courseResponses", JSON.stringify(storedData));

    updateRemaining();
    form.reset();
    welcomeDiv.innerText="이스텔리아 아카데미에서 뵙겠습니다.";
});

// 관리자용 초기화 버튼
const resetBtn = document.getElementById("resetBtn");
const adminPassword = "이스텔리아123"; // 관리자 비번

resetBtn.addEventListener("click", function(){
    const pw = prompt("삭제 권한 비밀번호를 입력하세요:");
    if(pw===adminPassword){
        localStorage.removeItem("courseResponses");
        alert("기록이 초기화되었습니다!");
        location.reload();
    } else {
        alert("비밀번호가 틀렸습니다. 삭제 불가!");
    }
});
</script>

</body>
</html>
