<!DOCTYPE html>
<html lang="ko">
<head>
<meta charset="UTF-8">
<title>이스텔리아 아카데미 수강신청</title>
<style>
body { font-family: "Noto Sans KR", sans-serif; background: #f5f7fa; padding: 20px; }
.container { background: #fff; max-width: 850px; margin: auto; padding: 30px 40px; border-radius: 12px; box-shadow: 0 6px 18px rgba(0,0,0,0.12); text-align: center;}
h2 { border-left: 6px solid #4a6cf7; padding-left: 12px; font-size: 28px; margin-bottom: 10px;}
label { display: block; margin-top: 14px; font-weight: bold; font-size: 16px;}
input[type="text"], input[type="number"], select { width: 100%; padding: 10px; margin-top: 6px; border: 1px solid #ccc; border-radius: 6px; font-size: 15px;}
.courses label { font-weight: normal; display: flex; align-items: center; gap: 10px; margin-top: 6px; font-size: 15px;}
.submit-btn { margin-top: 25px; width: 100%; padding: 14px; background: #4a6cf7; border: none; border-radius: 8px; font-size: 18px; color: white; cursor: pointer; font-weight: bold; }
table { width: 100%; border-collapse: collapse; margin-top: 30px; }
table, th, td { border: 1px solid #ccc; }
th, td { padding: 8px 10px; text-align: left; font-size: 15px;}
#welcome { margin-top: 22px; font-size: 18px; font-weight: bold; color: #4a6cf7; }
.logo { max-width: 120px; margin-bottom: 15px; }
.remaining { font-size: 12px; color: #555; margin-left: auto; }
</style>
</head>
<body>

<div class="container">
<img src="https://i.imgur.com/RKbPtQd.png" alt="이스텔리아 로고" class="logo">
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

<h4>불</h4>
<label><input type="checkbox" value="기초 염화학" class="course" data-max="6" data-element="불"> 기초 염화학 <span class="remaining"></span></label>
<label><input type="checkbox" value="화염 제어술식" class="course" data-max="6" data-element="불"> 화염 제어술식 <span class="remaining"></span></label>

<h4>물</h4>
<label><input type="checkbox" value="기초 수계 조작학" class="course" data-max="6" data-element="물"> 기초 수계 조작학 <span class="remaining"></span></label>
<label><input type="checkbox" value="상태 변화 이해" class="course" data-max="6" data-element="물"> 상태 변화 이해 <span class="remaining"></span></label>

<h4>풀</h4>
<label><input type="checkbox" value="풀정령학" class="course" data-max="6" data-element="풀"> 풀정령학 <span class="remaining"></span></label>
<label><input type="checkbox" value="허브학" class="course" data-max="6" data-element="풀"> 허브학 <span class="remaining"></span></label>

<h4>바람</h4>
<label><input type="checkbox" value="바람 조작론" class="course" data-max="6" data-element="바람"> 바람 조작론 <span class="remaining"></span></label>

<h4>전기</h4>
<label><input type="checkbox" value="낙뢰 유도법" class="course" data-max="6" data-element="전기"> 낙뢰 유도법 <span class="remaining"></span></label>

</div>

<button class="submit-btn" type="submit">수강신청 제출</button>
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

<script>
const form = document.getElementById("courseForm");
const tableBody = document.getElementById("responsesTable").querySelector("tbody");
const elementSelect = document.getElementById("element");
const welcomeDiv = document.getElementById("welcome");

const githubUser = "username";   // GitHub 계정
const githubRepo = "repo";       // 저장소 이름
const filePath = "responses.json";
const githubToken = "ghp_XXXXXXXXXXXXXXXXXXXX"; // Personal Access Token
const apiUrl = `https://api.github.com/repos/${githubUser}/${githubRepo}/contents/${filePath}`;

let courseCounts = {};
document.querySelectorAll(".course").forEach(c => { courseCounts[c.value]=0; });

// GitHub에서 데이터 불러오기
async function loadResponses(){
    try{
        const res = await fetch(`https://raw.githubusercontent.com/${githubUser}/${githubRepo}/main/${filePath}`);
        const data = await res.json();
        tableBody.innerHTML="";
        courseCounts = {};
        document.querySelectorAll(".course").forEach(c=>courseCounts[c.value]=0);
        data.forEach(entry=>{
            const row = tableBody.insertRow();
            row.insertCell().innerText = entry.name;
            row.insertCell().innerText = entry.grade;
            row.insertCell().innerText = entry.element;
            row.insertCell().innerText = entry.courses.join(", ");
            entry.courses.forEach(c=>courseCounts[c]++);
        });
        updateRemaining();
        return data;
    } catch(err){
        console.error(err);
        tableBody.innerHTML="<tr><td colspan='4'>데이터 로드 실패</td></tr>";
        return [];
    }
}

function updateRemaining(){
    document.querySelectorAll(".course").forEach(c=>{
        const remaining = c.dataset.max - (courseCounts[c.value] || 0);
        c.parentElement.querySelector(".remaining").innerText = `(잔여: ${remaining}명)`;
        c.disabled = remaining <= 0;
    });
}

// 속성 체크
document.querySelectorAll(".course").forEach(c=>{
    c.addEventListener("click", function(){
        const selectedElement = elementSelect.value;
        if(c.dataset.element !== "공통" && c.dataset.element !== selectedElement){
            alert("선택한 과목은 본인의 속성과 맞지 않습니다!");
            c.checked=false;
        }
    });
});

// GitHub 저장
async function saveResponses(newData){
    try{
        const fileRes = await fetch(apiUrl, { headers: { Authorization:`token ${githubToken}` } });
        const fileData = await fileRes.json();
        const sha = fileData.sha;
        await fetch(apiUrl, {
            method: "PUT",
            headers: {
                Authorization:`token ${githubToken}`,
                "Content-Type":"application/json"
            },
            body: JSON.stringify({
                message:"수강신청 업데이트",
                content:btoa(unescape(encodeURIComponent(JSON.stringify(newData,null,2)))),
                sha:sha
            })
        });
    } catch(err){ console.error(err); alert("GitHub 저장 실패"); }
}

// 제출
form.addEventListener("submit", async function(e){
    e.preventDefault();
    const name = document.getElementById("name").value;
    const grade = document.getElementById("grade").value;
    const element = elementSelect.value;

    const selectedCourses=[];
    document.querySelectorAll(".course").forEach(c=>{ if(c.checked) selectedCourses.push(c.value); });
    if(selectedCourses.length===0){ alert("적어도 한 과목은 선택해야 합니다!"); return; }

    const data = await loadResponses();
    data.push({name, grade, element, courses:selectedCourses});
    await saveResponses(data);
    await loadResponses();
    form.reset();
    welcomeDiv.innerText="이스텔리아 아카데미에서 뵙겠습니다.";
});

// 초기 로드
window.addEventListener("load", loadResponses);
</script>

</body>
</html>
