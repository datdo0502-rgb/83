<!DOCTYPE html>
<html>
<head>
<meta charset="UTF-8">
<title>Mini Game 8/3</title>

<style>
body{
font-family: Arial;
background:#ffe6f0;
text-align:center;
padding-top:80px;
}

.box{
display:none;
}

.card{
display:none;
background:white;
border-radius:12px;
padding:20px;
width:320px;
margin:auto;
box-shadow:0 4px 10px rgba(0,0,0,0.2);
}

button{
padding:8px 15px;
border:none;
background:#ff4da6;
color:white;
border-radius:6px;
cursor:pointer;
}

input{
padding:6px;
margin-top:10px;
}
</style>

</head>

<body>

<h2>Mini game dành riêng cho em 💗</h2>
<p>Nhân dịp 8/3 hãy xem anh hiểu em tới đâu nhé</p>

<div id="start">
<button onclick="start()">Bắt đầu</button>
</div>

<div id="q1" class="box">
<p>Câu 1: Chúng ta quen nhau vào tháng mấy?</p>
<input id="a1">
<br><br>
<button onclick="c1()">Trả lời</button>
</div>

<div id="q2" class="box">
<p>Câu 2: Món em thích ăn nhất khi đi với anh?</p>
<input id="a2">
<br><br>
<button onclick="c2()">Trả lời</button>
</div>

<div id="q3" class="box">
<p>Câu 3: Khi em giận anh thường làm gì để em hết giận?</p>
<input id="a3">
<br><br>
<button onclick="c3()">Trả lời</button>
</div>

<div id="q4" class="box">
<p>Câu 4: Ai là người dễ thương nhất?</p>
<input id="a4">
<br><br>
<button onclick="c4()">Trả lời</button>
</div>

<div id="card" class="card">
<h3>🎉 Mở khóa thành công</h3>

<p>
Có vẻ anh hiểu em khá rõ rồi nhỉ.  
Cảm ơn em vì đã luôn ở bên anh.
</p>

<p>
Chúc em một ngày <b>8/3</b> thật vui vẻ 🌸  
Luôn đáng yêu như hiện tại và hy vọng
chúng ta sẽ có thêm thật nhiều kỷ niệm cùng nhau.
</p>

<p>❤️</p>

</div>

<script>

function start(){
document.getElementById("start").style.display="none";
document.getElementById("q1").style.display="block";
}

function c1(){
if(document.getElementById("a1").value=="6"){
document.getElementById("q1").style.display="none";
document.getElementById("q2").style.display="block";
}else{
alert("Sai rồi 😜 thử lại xem");
}
}

function c2(){
if(document.getElementById("a2").value=="lẩu"){
document.getElementById("q2").style.display="none";
document.getElementById("q3").style.display="block";
}else{
alert("Sai rồi 😜");
}
}

function c3(){
if(document.getElementById("a3").value=="xin lỗi"){
document.getElementById("q3").style.display="none";
document.getElementById("q4").style.display="block";
}else{
alert("Sai rồi 😜");
}
}

function c4(){
if(document.getElementById("a4").value=="em"){
document.getElementById("q4").style.display="none";
document.getElementById("card").style.display="block";
}else{
alert("Sai rồi 😜");
}
}

</script>

</body>
</html>
