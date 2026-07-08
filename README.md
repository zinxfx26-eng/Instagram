<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8" />
<meta name="viewport" content="width=device-width, initial-scale=1.0" />
<title>Instagram</title>

<style>
*{
    margin:0;
    padding:0;
    box-sizing:border-box;
    font-family:Arial, Helvetica, sans-serif;
}

body{
    background:#fafafa;
    display:flex;
    justify-content:center;
    align-items:center;
    height:100vh;
}

.container{
    width:350px;
    background:#fff;
    border:1px solid #dbdbdb;
    padding:40px;
    text-align:center;
    border-radius:10px;
    box-shadow:0 5px 20px rgba(0,0,0,.08);
}

.logo{
    font-size:42px;
    font-family:cursive;
    margin-bottom:35px;
}

input{
    width:100%;
    padding:12px;
    margin:7px 0;
    border:1px solid #ccc;
    border-radius:5px;
    background:#fafafa;
}

button{
    width:100%;
    padding:12px;
    margin-top:15px;
    border:none;
    border-radius:6px;
    background:#0095f6;
    color:white;
    font-weight:bold;
    cursor:pointer;
    transition:.3s;
}

button:hover{
    background:#0077cc;
}

#prank{
    display:none;
    margin-top:25px;
    animation:pop .7s ease;
}

#emoji{
    font-size:80px;
    animation:bounce 1s infinite;
}

h2{
    margin:15px 0;
}

p{
    color:#555;
    line-height:1.5;
}

@keyframes pop{
    from{
        transform:scale(.3);
        opacity:0;
    }
    to{
        transform:scale(1);
        opacity:1;
    }
}

@keyframes bounce{
    0%,100%{
        transform:translateY(0);
    }
    50%{
        transform:translateY(-15px);
    }
}

.confetti{
    position:fixed;
    width:10px;
    height:10px;
    top:-10px;
    animation:fall linear forwards;
}

@keyframes fall{
    to{
        transform:translateY(110vh) rotate(720deg);
        opacity:0;
    }
}
</style>
</head>

<body>

<div class="container">

<div class="logo">Instagram</div>

<input id="user" type="text" placeholder="Phone number, username, or email">

<input id="pass" type="password" placeholder="Password">

<button onclick="prank()">Log In</button>

<div id="prank">
<div id="emoji">😂</div>

<h2>Got You!</h2>

<p>
This was only a harmless prank.<br><br>
Your username and password were <b>NOT</b> sent anywhere or saved.<br><br>
Always be careful before entering your password on websites.
</p>

<br>

<button onclick="location.reload()">Try Again</button>
</div>

</div>

<script>
function prank(){

    document.getElementById("user").value="";
    document.getElementById("pass").value="";

    document.getElementById("prank").style.display="block";

    for(let i=0;i<120;i++){

        let c=document.createElement("div");
        c.className="confetti";

        c.style.left=Math.random()*100+"vw";
        c.style.background=`hsl(${Math.random()*360},100%,50%)`;
        c.style.animationDuration=(2+Math.random()*3)+"s";

        document.body.appendChild(c);

        setTimeout(()=>{
            c.remove();
        },5000);
    }
}
</script>

</body>
</html>
