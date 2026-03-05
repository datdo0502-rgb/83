<!DOCTYPE html>
<html lang="vi">
<head>
<meta charset="UTF-8">
<title>Mini Game Bí Mật</title>

<style>

body{
margin:0;
padding:0;
font-family:Arial;
height:100vh;
display:flex;
justify-content:center;
align-items:center;
overflow:hidden;
}

/* background */
body::before{
content:"";
position:fixed;
top:0;
left:0;
width:100%;
height:100%;
background:url("background.jpg") center/cover no-repeat;
filter:blur(8px) brightness(0.7);
z-index:-2;
}

/* tim bay */
.heart{
position:fixed;
bottom:-20px;
font-size:20px;
animation:fly 6s linear infinite;
opacity:0.8;
}

@keyframes fly{
0%{
transform:translateY(0) scale(1);
opacity:1;
}
100%{
transform:translateY(-110vh) scale(1.5);
opacity:0;
}
}

/* box câu hỏi */
.box{
background:rgba(0,0,0,0.65);
padding:40px;
border-radius:16px;
text-align:center;
color:white;
width:420px;
backdrop-filter:blur(6px);
}

input{
padding:10px;
width:80%;
border-radius:8px;
border:none;
margin-top:15px;
}

button{
margin-top:15px;
padding:10px 20px;
border:none;
border-radius:8px;
background:#ff5fa2;
color:white;
font-size:16px;
cursor:pointer;
}

button:hover{
background:#ff3d8c;
}

#message{
margin-top:15px;
color:#ffb6d5;
}

</style>
</head>

<body>

<div class="box">

<h2 id="question"></h2>

<input id="answer" placeholder="Nhập câu trả lời">

<br>

<button onclick="check()">Trả lời</button>

<p id="message"></p>

</div>

<script>

/* danh sách câu hỏi */

let questions=[

{
q:"Câu 1: Ngày đầu tiên mình gặp nhau là ngày nào?",
a:"15/08"
},

{
q:"Câu 2: Món ăn mà em thích khi đi với anh?",
a:"lẩu"
},

{
q:"Câu 3: Biệt danh anh hay gọi em là gì?",
a:"bé"
},

{
q:"Câu 4: Ai là người tỏ tình trước?",
a:"anh"
},

{
q:"Câu 5: Màu em thích nhất?",
a:"hồng"
}

];

let current=0;

/* load câu hỏi */

function loadQuestion(){
document.getElementById("question").innerText=questions[current].q;
}

/* kiểm tra */

function check(){

let user=document.getElementById("answer").value.toLowerCase();
let correct=questions[current].a.toLowerCase();

if(user===correct){

current++;

if(current<questions.length){

document.getElementById("answer").value="";
document.getElementById("message").innerText="Đúng rồi ❤️";
loadQuestion();

}else{

document.querySelector(".box").innerHTML=`
<h2>Chúc mừng em ❤️</h2>
<p>Em đã vượt qua hết câu hỏi rồi.</p>
<p>Điều đó chứng tỏ tụi mình hiểu nhau khá rõ đó nha.</p>
<p>Chúc em một ngày 8/3 thật vui vẻ.</p>
<p>Anh thương em ❤️</p>
`;

}

}else{

document.getElementById("message").innerText="Sai rồi nha 😜 thử lại đi";

}

}

loadQuestion();

/* tạo tim bay */

function createHeart(){

let heart=document.createElement("div");

heart.className="heart";
heart.innerHTML="❤️";

heart.style.left=Math.random()*100+"vw";
heart.style.animationDuration=(Math.random()*3+3)+"s";

document.body.appendChild(heart);

setTimeout(()=>{
heart.remove();
},6000);

}

setInterval(createHeart,500);

</script>

</body>
</html>

</body>
</html>
