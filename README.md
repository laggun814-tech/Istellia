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
#resetBtn { margin-top: 15px; width: 100%; padding: 12px; background: #f74a4a; border: none; border-radius: 8px; color: white; cursor: pointer; font-size: 16px; }
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
