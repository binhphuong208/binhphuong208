<!DOCTYPE html>
<html lang="vi">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Intro Pro - Nguyễn Bình Phương</title>

<style>
*{margin:0;padding:0;box-sizing:border-box;font-family:Arial;}

body{
    height:100vh;
    overflow:hidden;
    background:#000;
    color:white;
}

/* INTRO */
#intro{
    position:fixed;
    width:100%;
    height:100%;
    background:#000;
    display:flex;
    flex-direction:column;
    justify-content:center;
    align-items:center;
    z-index:999;
}

.bar{
    width:200px;
    height:5px;
    background:#333;
    margin-top:15px;
}

.progress{
    height:100%;
    width:0%;
    background:#00e5ff;
    animation:load 3s linear forwards;
}

@keyframes load{
    to{width:100%;}
}

.tap{
    margin-top:20px;
    opacity:0;
    animation:show 1s 3s forwards;
}

@keyframes show{
    to{opacity:1;}
}

/* MAIN */
#main{
    display:none;
    height:100vh;
    justify-content:center;
    align-items:center;
    background:#0f2027;
}

/* CARD */
.card{
    text-align:center;
    padding:30px;
    border-radius:20px;
    background:rgba(255,255,255,0.05);
    backdrop-filter:blur(12px);
}

/* AVATAR */
.avatar{
    width:120px;
    height:120px;
    border-radius:50%;
    border:3px solid #00e5ff;
    margin-bottom:10px;
}

/* NAME */
h1{
    background:linear-gradient(90deg,#00e5ff,#00ffcc);
    -webkit-background-clip:text;
    color:transparent;
}

/* INTRO TEXT */
#typing{
    font-size:14px;
    margin:15px 0;
    min-height:40px;
}

/* SOCIAL */
.social{
    display:flex;
    justify-content:center;
    gap:15px;
}

.social img{
    width:25px;
}

.social a{
    background:rgba(255,255,255,0.1);
    padding:10px;
    border-radius:50%;
}
</style>
</head>

<body>

<!-- INTRO -->
<div id="intro">
    <h2>Loading...</h2>
    <div class="bar">
        <div class="progress"></div>
    </div>
    <div class="tap">Tap để vào 🔥</div>
</div>

<!-- MAIN -->
<div id="main">
    <div class="card">

        <img src="YOUR_IMAGE_HERE.jpg" class="avatar">

        <h1>Nguyễn Bình Phương</h1>

        <!-- 🔥 GIỚI THIỆU -->
        <div id="typing"></div>

        <div class="social">
            <a href="https://www.facebook.com/share/1HqZaA7EuE/?mibextid=wwXIfr">
                <img src="https://cdn-icons-png.flaticon.com/512/733/733547.png">
            </a>

            <a href="https://www.tiktok.com/@bphuong_dan_em_anh_hieu">
                <img src="https://cdn-icons-png.flaticon.com/512/3046/3046121.png">
            </a>

            <a href="https://zalo.me/0759220508">
                <img src="https://cdn-icons-png.flaticon.com/512/906/906361.png">
            </a>
        </div>

    </div>
</div>

<!-- YOUTUBE NHẠC -->
<div style="position:fixed; width:0; height:0; overflow:hidden;">
<iframe 
id="yt"
src="https://www.youtube.com/embed/7kHklWkuR60?loop=1&playlist=7kHklWkuR60"
allow="autoplay">
</iframe>
</div>

<script>

/* INTRO CLICK */
document.getElementById("intro").addEventListener("click", function(){
    document.getElementById("main").style.display="flex";
    this.style.display="none";

    const yt = document.getElementById("yt");
    yt.src = yt.src + "&autoplay=1";
});

/* 🔥 TEXT GIỚI THIỆU */
const text="Xin chào, mình là Bình Phương 👋 Một người trẻ đam mê công nghệ, thích khám phá và luôn cố gắng phát triển bản thân mỗi ngày.";
let i=0;

function typing(){
    if(i<text.length){
        document.getElementById("typing").innerHTML+=text.charAt(i);
        i++;
        setTimeout(typing,25);
    }
}

typing();

</script>

</body>
</html>
