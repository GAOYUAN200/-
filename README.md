<!DOCTYPE html>
<html lang="zh-CN">

<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>我们</title>

<meta property="og:title" content="我们">
<meta property="og:description" content="陆韦彬 ❤ 高原">
<meta name="apple-mobile-web-app-title" content="我们">
<meta name="theme-color" content="#1d1b3a">

<style>

*{
    margin:0;
    padding:0;
    box-sizing:border-box;
}

html,body{
    width:100%;
    height:100%;
}

body{
    font-family:"PingFang SC","Microsoft YaHei",sans-serif;
    background:linear-gradient(
        135deg,
        #14172f 0%,
        #211d46 50%,
        #3b1f66 100%
    );
    overflow:hidden;
    color:#fff;
}

/* 背景光效 */

body::before{
    content:"";
    position:fixed;
    width:200%;
    height:200%;
    left:-50%;
    top:-50%;
    background:
    radial-gradient(circle,rgba(255,105,180,.15) 0%,transparent 40%),
    radial-gradient(circle at 80% 70%,rgba(138,43,226,.18) 0%,transparent 45%);
    animation:floatbg 15s infinite ease-in-out;
}

@keyframes floatbg{
    0%,100%{
        transform:translate(0,0);
    }
    50%{
        transform:translate(-40px,-40px);
    }
}

.container{
    position:relative;
    z-index:1;
    max-width:520px;
    width:100%;
    margin:auto;
    height:100%;
    display:flex;
    flex-direction:column;
    justify-content:center;
    align-items:center;
    padding:20px;
    text-align:center;
}

/* 爱心 */

.heart-wrap{
    position:relative;
    margin-bottom:25px;
}

.heart{
    font-size:64px;
    animation:heartBeat 1.3s infinite;
}

@keyframes heartBeat{
    0%,100%{
        transform:scale(1);
    }
    50%{
        transform:scale(1.15);
    }
}

.ring{
    position:absolute;
    width:110px;
    height:110px;
    border-radius:50%;
    border:2px solid rgba(255,105,180,.2);
    left:50%;
    top:50%;
    transform:translate(-50%,-50%);
    animation:ring 2s infinite;
}

@keyframes ring{
    0%,100%{
        transform:translate(-50%,-50%) scale(1);
        opacity:.3;
    }
    50%{
        transform:translate(-50%,-50%) scale(1.25);
        opacity:.05;
    }
}

/* 图片 */

.photo{
    width:220px;
    height:220px;
    object-fit:cover;
    border-radius:28px;
    box-shadow:
    0 0 25px rgba(255,105,180,.25),
    0 20px 60px rgba(0,0,0,.35);
    margin-bottom:35px;
}

/* 标题 */

.title{
    font-size:48px;
    font-weight:700;
    background:linear-gradient(
        135deg,
        #ff67c8,
        #bb8cff
    );
    -webkit-background-clip:text;
    -webkit-text-fill-color:transparent;
    margin-bottom:15px;
}

.line{
    width:200px;
    height:2px;
    background:linear-gradient(
        90deg,
        transparent,
        #ff67c8,
        transparent
    );
    margin-bottom:30px;
}

/* 计时卡片 */

.card{
    width:100%;
    background:rgba(30,35,72,.75);
    border-radius:28px;
    padding:28px;
    border:1px solid rgba(255,255,255,.08);
}

.card-title{
    font-size:20px;
    margin-bottom:20px;
}

.timer{
    display:grid;
    grid-template-columns:repeat(4,1fr);
    gap:12px;
}

.item{
    background:rgba(255,255,255,.04);
    border:1px solid rgba(255,255,255,.08);
    border-radius:16px;
    padding:15px 5px;
}

.value{
    font-size:22px;
    font-weight:700;
    color:#ff7fd2;
}

.label{
    margin-top:8px;
    color:#bfc4da;
    font-size:14px;
}

.date{
    margin-top:22px;
    color:#d7d9ea;
    font-size:14px;
}

.highlight{
    color:#ff7fd2;
}

@media(max-width:480px){

    .photo{
        width:180px;
        height:180px;
    }

    .title{
        font-size:38px;
    }

    .value{
        font-size:18px;
    }

    .item{
        padding:12px 4px;
    }

    .card{
        padding:20px;
    }

}

</style>
</head>

<body>

<div class="container">

    <div class="heart-wrap">
        <div class="ring"></div>
        <div class="heart">❤️</div>
    </div>

    <img
        class="photo"
        src="https://raw.githubusercontent.com/GAOYUAN200/our-story/main/1ee8ea1eedae471666d7a9b6961ce1b7.jpg"
        alt="我们"
        onerror="this.src='https://via.placeholder.com/300x300'"
    >

    <div class="title">我们</div>

    <div class="line"></div>

    <div class="card">

        <div class="card-title">已经在一起</div>

        <div class="timer">

            <div class="item">
                <div class="value" id="days">0</div>
                <div class="label">天</div>
            </div>

            <div class="item">
                <div class="value" id="hours">00</div>
                <div class="label">小时</div>
            </div>

            <div class="item">
                <div class="value" id="minutes">00</div>
                <div class="label">分钟</div>
            </div>

            <div class="item">
                <div class="value" id="seconds">00</div>
                <div class="label">秒</div>
            </div>

        </div>

        <div class="date">
            始于
            <span class="highlight">
                2025年10月5日 22:23
            </span>
        </div>

    </div>

</div>

<script>

const startTime =
new Date(2025,9,5,22,23,0).getTime();

function update(){

    const now=Date.now();

    const diff=now-startTime;

    const days=Math.floor(
        diff/(1000*60*60*24)
    );

    const hours=Math.floor(
        (diff%(1000*60*60*24))
        /(1000*60*60)
    );

    const minutes=Math.floor(
        (diff%(1000*60*60))
        /(1000*60)
    );

    const seconds=Math.floor(
        (diff%(1000*60))
        /1000
    );

    document.getElementById("days").innerText=days;
    document.getElementById("hours").innerText=String(hours).padStart(2,"0");
    document.getElementById("minutes").innerText=String(minutes).padStart(2,"0");
    document.getElementById("seconds").innerText=String(seconds).padStart(2,"0");

}

update();

setInterval(update,1000);

</script>

</body>
</html>
