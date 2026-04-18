<!DOCTYPE html>
<html lang="ko">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
<title>인터넷 요금 진단</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Pretendard:wght@400;500;600;700;800;900&display=swap" rel="stylesheet">
<style>
*{margin:0;padding:0;box-sizing:border-box;-webkit-tap-highlight-color:transparent}
:root{
  --bg:#F2F4F6;
  --white:#FFFFFF;
  --text:#191F28;
  --text2:#6B7280;
  --text3:#B0B8C1;
  --blue:#3182F6;
  --blue-l:#EBF3FF;
  --green:#00C471;
  --green-l:#E9FAF2;
  --red:#F04452;
  --red-l:#FFF0F1;
  --yellow:#FFD600;
  --border:#E8ECF0;
  --shadow:0 2px 20px rgba(0,0,0,0.08);
}
html{scroll-behavior:smooth}
body{font-family:'Pretendard','Apple SD Gothic Neo',sans-serif;background:var(--white);color:var(--text);-webkit-font-smoothing:antialiased;overflow-x:hidden}

/* ─────────────────────────────
   SECTION 공통
───────────────────────────── */
section{padding:64px 24px}
.inner{max-width:480px;margin:0 auto}
.eyebrow{display:inline-block;font-size:11px;font-weight:700;letter-spacing:.1em;color:var(--blue);background:var(--blue-l);padding:5px 12px;border-radius:100px;margin-bottom:16px}
.sec-h{font-size:26px;font-weight:900;letter-spacing:-.03em;line-height:1.3;margin-bottom:12px}
.sec-sub{font-size:15px;color:var(--text2);line-height:1.75}

/* ─────────────────────────────
   HERO
───────────────────────────── */
#hero{
  background:#0A0F1E;
  padding:0;
  min-height:100svh;
  display:flex;flex-direction:column;
}
.hero-grid{
  position:absolute;inset:0;
  background-image:
    linear-gradient(rgba(49,130,246,0.07) 1px,transparent 1px),
    linear-gradient(90deg,rgba(49,130,246,0.07) 1px,transparent 1px);
  background-size:28px 28px;
  pointer-events:none;
}
.hero-glow{
  position:absolute;
  width:320px;height:320px;border-radius:50%;
  background:radial-gradient(circle,rgba(49,130,246,0.15) 0%,transparent 70%);
  top:-80px;right:-80px;pointer-events:none;
}
.hero-body{
  flex:1;display:flex;flex-direction:column;justify-content:center;
  padding:80px 28px 48px;max-width:480px;margin:0 auto;width:100%;
  position:relative;z-index:1;
}
.hero-live{
  display:inline-flex;align-items:center;gap:7px;
  background:rgba(240,68,82,0.15);border:1px solid rgba(240,68,82,0.35);
  border-radius:8px;padding:6px 13px;margin-bottom:28px;width:fit-content;
}
.live-dot{width:7px;height:7px;border-radius:50%;background:var(--red);animation:blink .9s infinite}
@keyframes blink{0%,100%{opacity:1}50%{opacity:.15}}
.live-text{font-size:11px;font-weight:700;color:var(--red);letter-spacing:.06em}
.hero-h{font-size:34px;font-weight:900;color:#fff;line-height:1.2;letter-spacing:-.04em;margin-bottom:16px}
.hero-h em{font-style:normal;color:#93C5FD}
.hero-desc{font-size:15px;color:rgba(255,255,255,0.55);line-height:1.75;margin-bottom:36px}
.hero-counter-wrap{
  background:rgba(255,255,255,0.04);border:1px solid rgba(255,255,255,0.1);
  border-radius:20px;padding:24px;margin-bottom:32px;
}
.hc-label{font-size:12px;color:rgba(255,255,255,0.4);letter-spacing:.06em;margin-bottom:8px}
.hc-num{font-size:52px;font-weight:900;color:var(--red);letter-spacing:-.04em;line-height:1;font-variant-numeric:tabular-nums}
.hc-sub{font-size:12px;color:rgba(255,255,255,0.3);margin-top:8px;line-height:1.6}
.hero-cta{
  width:100%;padding:18px;border-radius:16px;border:none;cursor:pointer;
  background:var(--blue);color:#fff;
  font-size:16px;font-weight:800;font-family:'Pretendard',sans-serif;
  box-shadow:0 8px 32px rgba(49,130,246,0.4);
  transition:transform .14s,box-shadow .14s;
}
.hero-cta:active{transform:scale(.97)}
.hero-hint{text-align:center;font-size:12px;color:rgba(255,255,255,0.25);margin-top:12px}
.hero-scroll{
  display:flex;justify-content:center;align-items:center;gap:8px;
  padding:20px 0 32px;color:rgba(255,255,255,0.25);font-size:12px;
  animation:bob 2s ease-in-out infinite;
  position:relative;z-index:1;
}
@keyframes bob{0%,100%{transform:translateY(0)}50%{transform:translateY(6px)}}

/* ─────────────────────────────
   STORY 1 · 아깝지 않았던 이유
───────────────────────────── */
#story1{background:var(--white);padding:72px 24px}
.story-block{margin-bottom:48px}
.sb-num{font-size:11px;font-weight:700;color:var(--text3);letter-spacing:.12em;margin-bottom:14px}
.sb-h{font-size:22px;font-weight:900;letter-spacing:-.03em;line-height:1.35;margin-bottom:12px}
.sb-p{font-size:15px;color:var(--text2);line-height:1.8}
.sb-p strong{color:var(--text);font-weight:700}
.highlight-box{
  background:var(--bg);border-left:3px solid var(--blue);
  border-radius:0 12px 12px 0;padding:16px 18px;margin:20px 0;
}
.hb-text{font-size:14px;color:var(--text);line-height:1.7;font-weight:500}
.hb-text em{font-style:normal;color:var(--blue);font-weight:700}

/* ─────────────────────────────
   STORY 2 · 왜 이런 일이?
───────────────────────────── */
#story2{background:var(--bg);padding:72px 24px}
.reason-cards{display:flex;flex-direction:column;gap:12px;margin-top:28px}
.rc{
  background:var(--white);border-radius:16px;padding:20px;
  display:flex;gap:16px;align-items:flex-start;
  box-shadow:0 1px 8px rgba(0,0,0,0.06);
}
.rc-icon{
  width:44px;height:44px;border-radius:12px;flex-shrink:0;
  display:flex;align-items:center;justify-content:center;font-size:20px;
}
.rc-body{}
.rc-title{font-size:15px;font-weight:800;color:var(--text);margin-bottom:5px;letter-spacing:-.01em}
.rc-desc{font-size:13px;color:var(--text2);line-height:1.65}
.rc-desc strong{color:var(--text);font-weight:700}

/* ─────────────────────────────
   계산기
───────────────────────────── */
#calc{background:var(--white);padding:72px 24px}
.calc-card{
  background:var(--bg);border-radius:20px;padding:28px 22px;
}
.calc-row{margin-bottom:22px}
.calc-label{font-size:13px;font-weight:700;color:var(--text2);margin-bottom:10px}
.slider-wrap{display:flex;align-items:center;gap:14px}
input[type=range]{
  flex:1;-webkit-appearance:none;height:5px;
  background:var(--border);border-radius:3px;outline:none;cursor:pointer;
}
input[type=range]::-webkit-slider-thumb{
  -webkit-appearance:none;width:22px;height:22px;
  border-radius:50%;background:var(--blue);border:3px solid #fff;
  box-shadow:0 2px 8px rgba(49,130,246,0.4);cursor:pointer;
}
.sl-val{
  font-size:16px;font-weight:800;color:var(--blue);
  min-width:64px;text-align:right;
}
.divider{height:1px;background:var(--border);margin:24px 0}
.result-grid{display:grid;grid-template-columns:1fr 1fr;gap:10px;margin-bottom:20px}
.rg-card{border-radius:14px;padding:16px 14px}
.rg-card.red{background:var(--red-l)}
.rg-card.blue{background:var(--blue-l)}
.rg-card.dark{background:var(--text);grid-column:span 2}
.rg-label{font-size:11px;font-weight:700;letter-spacing:.06em;margin-bottom:6px}
.rg-card.red .rg-label{color:var(--red)}
.rg-card.blue .rg-label{color:var(--blue)}
.rg-card.dark .rg-label{color:rgba(255,255,255,0.45)}
.rg-num{font-size:22px;font-weight:900;letter-spacing:-.03em}
.rg-card.red .rg-num{color:var(--red)}
.rg-card.blue .rg-num{color:var(--blue)}
.rg-card.dark .rg-num{color:var(--yellow);font-size:30px}
.rg-card.dark .rg-label{text-align:center}
.rg-card.dark .rg-num{text-align:center;display:block}
.rg-sub{font-size:11px;color:rgba(255,255,255,0.4);text-align:center;margin-top:4px}
.calc-insight{
  background:var(--white);border-radius:14px;padding:16px 18px;
  display:flex;gap:12px;align-items:flex-start;
}
.ci-icon{
  width:28px;height:28px;border-radius:8px;background:var(--blue);
  color:#fff;font-size:13px;font-weight:900;flex-shrink:0;
  display:flex;align-items:center;justify-content:center;
}
.ci-text{font-size:13px;color:var(--text2);line-height:1.65}
.ci-text strong{color:var(--blue);font-weight:700}

/* ─────────────────────────────
   STORY 3 · 지금까지 얼마?
───────────────────────────── */
#story3{
  background:var(--text);padding:72px 24px;text-align:center;
}
.s3-pre{font-size:13px;color:rgba(255,255,255,0.45);letter-spacing:.06em;margin-bottom:12px}
.s3-h{font-size:26px;font-weight:900;color:#fff;line-height:1.35;letter-spacing:-.03em;margin-bottom:28px}
.loss-counter{
  font-size:58px;font-weight:900;color:var(--red);
  letter-spacing:-.04em;line-height:1;margin-bottom:8px;
  font-variant-numeric:tabular-nums;
}
.s3-unit{font-size:20px;color:rgba(240,68,82,0.65);font-weight:700}
.s3-sub{font-size:13px;color:rgba(255,255,255,0.35);margin-bottom:32px;line-height:1.7}
.s3-comparison{
  display:grid;grid-template-columns:1fr 1fr;gap:10px;margin-bottom:32px;
}
.sc-card{border-radius:14px;padding:16px 14px;text-align:left}
.sc-card.gray{background:rgba(255,255,255,0.06)}
.sc-card.green{background:rgba(0,196,113,0.12);border:1px solid rgba(0,196,113,0.25)}
.sc-label{font-size:10px;font-weight:700;letter-spacing:.08em;margin-bottom:6px}
.sc-card.gray .sc-label{color:rgba(255,255,255,0.35)}
.sc-card.green .sc-label{color:var(--green)}
.sc-item{font-size:13px;color:rgba(255,255,255,0.55);padding:4px 0;line-height:1.5}
.sc-item.highlight{color:#fff;font-weight:700}
.sc-item.g{color:var(--green);font-weight:700}
.s3-arrow{font-size:24px;margin-bottom:24px}

/* ─────────────────────────────
   SOCIAL PROOF
───────────────────────────── */
#proof{background:var(--bg);padding:72px 24px}
.review-list{display:flex;flex-direction:column;gap:12px;margin-top:28px}
.review{
  background:var(--white);border-radius:16px;padding:20px;
  box-shadow:0 1px 8px rgba(0,0,0,0.05);
}
.rv-top{display:flex;align-items:center;gap:10px;margin-bottom:12px}
.rv-avatar{
  width:38px;height:38px;border-radius:50%;
  display:flex;align-items:center;justify-content:center;
  font-size:14px;font-weight:800;color:#fff;flex-shrink:0;
}
.rv-name{font-size:14px;font-weight:700;color:var(--text)}
.rv-info{font-size:11px;color:var(--text3)}
.stars{color:#FFD600;font-size:12px;letter-spacing:1px}
.rv-title{font-size:15px;font-weight:800;color:var(--text);margin-bottom:6px;letter-spacing:-.01em}
.rv-body{font-size:13px;color:var(--text2);line-height:1.7}
.rv-benefit{
  display:inline-flex;align-items:center;gap:6px;
  background:var(--green-l);border-radius:8px;padding:6px 11px;
  margin-top:12px;
}
.rb-text{font-size:12px;font-weight:700;color:#007947}
.stat-row{
  display:grid;grid-template-columns:1fr 1fr 1fr;gap:10px;
  margin-top:28px;
}
.stat{text-align:center;padding:18px 8px;background:var(--white);border-radius:14px}
.stat-num{font-size:22px;font-weight:900;color:var(--blue);margin-bottom:4px;letter-spacing:-.02em}
.stat-label{font-size:11px;color:var(--text2);line-height:1.4}

/* ─────────────────────────────
   CTA
───────────────────────────── */
#cta{background:var(--white);padding:72px 24px 40px}
.cta-card{
  background:var(--text);border-radius:24px;padding:32px 24px;
}
.cta-eyebrow{
  display:inline-block;background:rgba(255,214,0,0.15);
  border:1px solid rgba(255,214,0,0.3);
  color:var(--yellow);font-size:11px;font-weight:700;letter-spacing:.08em;
  padding:5px 12px;border-radius:100px;margin-bottom:20px;
}
.cta-h{font-size:24px;font-weight:900;color:#fff;line-height:1.3;letter-spacing:-.03em;margin-bottom:8px}
.cta-sub{font-size:14px;color:rgba(255,255,255,0.5);line-height:1.7;margin-bottom:28px}
.form-group{margin-bottom:12px}
.form-input{
  width:100%;background:rgba(255,255,255,0.07);
  border:1.5px solid rgba(255,255,255,0.12);
  border-radius:12px;padding:15px 16px;
  color:#fff;font-size:15px;font-family:'Pretendard',sans-serif;
  outline:none;transition:border-color .18s;
}
.form-input::placeholder{color:rgba(255,255,255,0.25)}
.form-input:focus{border-color:var(--blue)}
.agree-wrap{
  display:flex;align-items:flex-start;gap:10px;
  padding:14px 15px;
  background:rgba(255,255,255,0.05);
  border:1px solid rgba(255,255,255,0.1);
  border-radius:12px;margin-bottom:20px;cursor:pointer;
}
.chk{
  width:20px;height:20px;border-radius:6px;border:1.5px solid rgba(255,255,255,0.2);
  background:transparent;flex-shrink:0;margin-top:1px;cursor:pointer;
  transition:all .18s;display:flex;align-items:center;justify-content:center;
  font-size:11px;font-weight:800;color:transparent;
}
.chk.on{background:var(--blue);border-color:var(--blue);color:#fff}
.agree-text{font-size:13px;color:rgba(255,255,255,0.45);line-height:1.6;cursor:pointer}
.agree-text strong{color:rgba(255,255,255,0.75)}
.btn-submit{
  width:100%;padding:17px;border-radius:14px;border:none;cursor:pointer;
  background:var(--blue);color:#fff;
  font-size:16px;font-weight:800;font-family:'Pretendard',sans-serif;
  box-shadow:0 6px 24px rgba(49,130,246,0.4);
  transition:transform .14s;margin-bottom:12px;
}
.btn-submit:active{transform:scale(.97)}
.btn-kakao{
  width:100%;padding:14px;border-radius:14px;border:none;cursor:pointer;
  background:#FEE500;color:#191919;
  font-size:14px;font-weight:700;font-family:'Pretendard',sans-serif;
  display:flex;align-items:center;justify-content:center;gap:8px;
}
.form-note{font-size:11px;color:rgba(255,255,255,0.2);text-align:center;margin-top:14px;line-height:1.6}

/* ─────────────────────────────
   FLOATING CTA
───────────────────────────── */
#float-cta{
  position:fixed;bottom:0;left:0;right:0;z-index:100;
  padding:12px 20px 24px;
  background:linear-gradient(to top,rgba(255,255,255,1) 60%,rgba(255,255,255,0));
  max-width:480px;margin:0 auto;
  transform:translateY(100%);transition:transform .4s cubic-bezier(.4,0,.2,1);
}
#float-cta.show{transform:translateY(0)}
.float-btn{
  width:100%;padding:17px;border-radius:16px;border:none;cursor:pointer;
  background:var(--blue);color:#fff;
  font-size:15px;font-weight:800;font-family:'Pretendard',sans-serif;
  box-shadow:0 8px 28px rgba(49,130,246,0.45);
}

/* ─────────────────────────────
   SUCCESS
───────────────────────────── */
#success-overlay{
  position:fixed;inset:0;background:rgba(0,0,0,0.6);z-index:200;
  display:none;align-items:center;justify-content:center;padding:24px;
}
#success-overlay.show{display:flex}
.success-card{
  background:var(--white);border-radius:24px;padding:40px 28px;
  text-align:center;width:100%;max-width:380px;
}
.sc-icon{font-size:52px;margin-bottom:20px}
.sc-title{font-size:24px;font-weight:900;letter-spacing:-.03em;margin-bottom:10px}
.sc-desc{font-size:14px;color:var(--text2);line-height:1.7;margin-bottom:24px}
.sc-info{
  background:var(--bg);border-radius:14px;padding:18px;
  display:flex;flex-direction:column;gap:10px;margin-bottom:24px;
}
.sci-row{display:flex;justify-content:space-between;align-items:center}
.sci-l{font-size:13px;color:var(--text2)}
.sci-r{font-size:14px;font-weight:700;color:var(--text)}
.sci-r.green{color:var(--green)}
.sci-r.blue{color:var(--blue)}
.btn-close{
  width:100%;padding:14px;border-radius:14px;border:1.5px solid var(--border);
  background:var(--white);color:var(--text2);
  font-size:14px;font-weight:600;font-family:'Pretendard',sans-serif;cursor:pointer;
}

/* UTIL */
::-webkit-scrollbar{width:0}
</style>
</head>
<body>

<!-- ════════════ HERO ════════════ -->
<section id="hero" style="position:relative">
  <div class="hero-grid"></div>
  <div class="hero-glow"></div>
  <div class="hero-body">
    <div class="hero-live">
      <div class="live-dot"></div>
      <div class="live-text">지금 이 순간도 새고 있어요</div>
    </div>
    <h1 class="hero-h">옆 사람은<br>같은 인터넷을<br><em>더 싸게</em> 씁니다</h1>
    <p class="hero-desc">
      통신비는 쓰면서도 잘 모르는 돈이에요.<br>
      아깝지도 않고, 그냥 나가죠.<br>
      근데 그 차이가 평생 쌓이면?
    </p>
    <div class="hero-counter-wrap">
      <div class="hc-label">이 페이지를 열어둔 이후 버려진 금액</div>
      <div class="hc-num" id="heroCounter">₩0.0</div>
      <div class="hc-sub">초당 ₩7.1 낭비 기준 · 3년 이상 같은 통신사 사용 고객</div>
    </div>
    <button class="hero-cta" onclick="smoothTo('calc')">내가 얼마나 손해봤는지 계산하기 →</button>
    <div class="hero-hint">30초 · 무료 · 개인정보 불필요</div>
  </div>
  <div class="hero-scroll" onclick="smoothTo('story1')">
    아래로 스크롤 ↓
  </div>
</section>

<!-- ════════════ STORY 1 ════════════ -->
<section id="story1">
  <div class="inner">
    <div class="story-block">
      <div class="sb-num">CHAPTER 01</div>
      <h2 class="sb-h">왜 아깝지 않았을까요?</h2>
      <p class="sb-p">
        전기세, 수도세처럼 인터넷 요금도 <strong>그냥 나가는 돈</strong>이었어요.<br><br>
        매달 자동이체로 빠져나가고, 뭘 쓰는지도 잘 모르고, 딱히 불편하지도 않으니까 굳이 바꿀 이유가 없었죠.
      </p>
      <div class="highlight-box">
        <div class="hb-text">문제는, 통신사가 <em>그걸 알고 있다</em>는 거예요.<br>바꾸지 않는 고객에겐 아무 혜택도 안 줍니다.</div>
      </div>
      <p class="sb-p">
        신규 가입 고객에게만 사은품을 주고, 요금을 낮춰줘요.<br>
        기존 고객은? 그냥 두는 거예요.
      </p>
    </div>
    <div class="story-block">
      <div class="sb-num">CHAPTER 02</div>
      <h2 class="sb-h">커피 한 잔 차이가<br>만든 일</h2>
      <p class="sb-p">
        한 달에 <strong>만 원 차이</strong>면 별거 아닌 것 같죠?<br><br>
        근데 10년이면 120만 원이에요.<br>
        20년이면 240만 원.<br><br>
        의학이 발달해서 우리 120살까지 산다고요?<br>
        <strong>30살 기준으로 90년 더 살면 — 1,080만 원.</strong>
      </p>
      <div class="highlight-box">
        <div class="hb-text">아깝지 않았던 그 만 원이,<br>사실 <em>제일 비싼 돈</em>이었어요.</div>
      </div>
    </div>
  </div>
</section>

<!-- ════════════ SLOGAN ════════════ -->
<section id="slogan" style="background:#0A0F1E;padding:72px 24px;text-align:center;position:relative;overflow:hidden">
  <div style="position:absolute;inset:0;background-image:linear-gradient(rgba(49,130,246,0.05) 1px,transparent 1px),linear-gradient(90deg,rgba(49,130,246,0.05) 1px,transparent 1px);background-size:28px 28px;pointer-events:none"></div>
  <div style="position:absolute;width:280px;height:280px;border-radius:50%;background:radial-gradient(circle,rgba(240,68,82,0.12) 0%,transparent 70%);top:50%;left:50%;transform:translate(-50%,-50%);pointer-events:none"></div>
  <div class="inner" style="position:relative;z-index:1">
    <div style="display:inline-block;background:rgba(240,68,82,0.15);border:1px solid rgba(240,68,82,0.3);border-radius:100px;padding:5px 14px;margin-bottom:28px;font-size:11px;font-weight:700;color:var(--red);letter-spacing:.1em">핵심 메시지</div>
    <div style="font-size:13px;color:rgba(255,255,255,0.35);letter-spacing:.08em;margin-bottom:20px;font-weight:500">당신이 몰랐던 진실</div>
    <p style="font-size:26px;font-weight:900;color:#fff;line-height:1.4;letter-spacing:-.03em;margin-bottom:20px;word-break:keep-all">
      아깝지 않게 썼던<br>그 <span style="color:var(--red)">구독료</span>가<br>당신의 노후 자금<br><span style="color:var(--red)">천만 원</span>을<br>갉아먹습니다.
    </p>
    <div style="width:40px;height:2px;background:rgba(255,255,255,0.15);margin:0 auto 24px"></div>
    <p style="font-size:17px;font-weight:700;color:rgba(255,255,255,0.75);line-height:1.65;letter-spacing:-.02em;word-break:keep-all">
      어차피 써야 할 필수 비용이라면,<br><span style="color:var(--yellow);font-weight:900">단 1원도 낭비하지 마세요.</span>
    </p>
  </div>
</section>

<!-- ════════════ STORY 2 · 왜 이런 일? ════════════ -->
<section id="story2">
  <div class="inner">
    <div class="eyebrow">왜 이런 일이 생길까요?</div>
    <h2 class="sec-h">통신사가<br>절대 말해주지 않는 것</h2>
    <div class="reason-cards">
      <div class="rc">
        <div class="rc-icon" style="background:#FFF0F1">🔒</div>
        <div class="rc-body">
          <div class="rc-title">약정이 끝나도 요금은 그대로</div>
          <div class="rc-desc">약정 기간이 지났는데도 <strong>통신사는 먼저 연락 안 해요.</strong> 그냥 같은 요금 계속 받아요.</div>
        </div>
      </div>
      <div class="rc">
        <div class="rc-icon" style="background:#EBF3FF">🎁</div>
        <div class="rc-body">
          <div class="rc-title">신규 고객에게만 혜택을</div>
          <div class="rc-desc">새로 가입하는 고객에겐 <strong>사은품, 요금 할인</strong>을 주면서 기존 고객은 관리 대상이 아니에요.</div>
        </div>
      </div>
      <div class="rc">
        <div class="rc-icon" style="background:#E9FAF2">😶</div>
        <div class="rc-body">
          <div class="rc-title">귀찮아서 그냥 두는 사람들</div>
          <div class="rc-desc">변경 절차가 복잡할 것 같고, 위약금이 걱정되고. 통신사는 <strong>이 심리를 이용해요.</strong></div>
        </div>
      </div>
      <div class="rc">
        <div class="rc-icon" style="background:#FFF8E0">📊</div>
        <div class="rc-body">
          <div class="rc-title">비교가 너무 어려워</div>
          <div class="rc-desc">SKT, KT, LG, 스카이라이프, 헬로비전 — <strong>뭐가 더 싼지 알기 어렵게</strong> 만들어 놨어요.</div>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- ════════════ 계산기 ════════════ -->
<section id="calc">
  <div class="inner">
    <div class="eyebrow">내 손해 계산기</div>
    <h2 class="sec-h">직접 계산해보세요</h2>
    <p class="sec-sub" style="margin-bottom:32px">슬라이더를 움직여보면<br>숫자가 달라지는 걸 볼 수 있어요.</p>
    <div class="calc-card">
      <div class="calc-row">
        <div class="calc-label">현재 나이</div>
        <div class="slider-wrap">
          <input type="range" id="slAge" min="20" max="70" value="35" step="1" oninput="calcUpdate()">
          <div class="sl-val" id="valAge">35세</div>
        </div>
      </div>
      <div class="calc-row">
        <div class="calc-label">지금까지 같은 통신사 사용 기간</div>
        <div class="slider-wrap">
          <input type="range" id="slUsed" min="1" max="20" value="5" step="1" oninput="calcUpdate()">
          <div class="sl-val" id="valUsed">5년</div>
        </div>
      </div>
      <div class="calc-row" style="margin-bottom:0">
        <div class="calc-label">옆 사람과의 월 요금 차이</div>
        <div class="slider-wrap">
          <input type="range" id="slDiff" min="5000" max="40000" value="10000" step="5000" oninput="calcUpdate()">
          <div class="sl-val" id="valDiff">1만원</div>
        </div>
      </div>
      <div class="divider"></div>
      <div class="result-grid">
        <div class="rg-card red">
          <div class="rg-label">이미 손해본 금액</div>
          <div class="rg-num" id="rAlready">60만원</div>
        </div>
        <div class="rg-card blue">
          <div class="rg-label">앞으로 손해볼 금액</div>
          <div class="rg-num" id="rFuture">1,020만원</div>
        </div>
        <div class="rg-card dark">
          <div class="rg-label">120세까지 평생 손해 합계</div>
          <div class="rg-num" id="rTotal">1,080만원</div>
          <div class="rg-sub" id="rSub">기준: 35세 · 5년 사용 · 월 1만원 차이</div>
        </div>
      </div>
      <div class="calc-insight">
        <div class="ci-icon">!</div>
        <div class="ci-text" id="calcInsight">지금 바꾸면 <strong>오늘부터 이 손해가 멈춥니다.</strong> 거기다 사은품·결합할인까지 받을 수 있어요.</div>
      </div>
    </div>
  </div>
</section>

<!-- ════════════ STORY 3 · 각성 ════════════ -->
<section id="story3">
  <div class="inner">
    <div class="s3-pre">진짜 문제는 이거예요</div>
    <h2 class="s3-h">알면서도 안 바꾸면<br>이 숫자는 계속 커져요</h2>
    <div class="loss-counter" id="lossCounter">₩0</div>
    <div class="s3-unit">지금까지 손해본 금액 (평균 기준)</div>
    <div class="s3-sub" style="margin-top:8px">3년 사용 · 월 1만원 차이 기준<br>지금도 초당 ₩0.38씩 늘어나고 있어요</div>

    <div class="s3-comparison">
      <div class="sc-card gray">
        <div class="sc-label">그냥 두면</div>
        <div class="sc-item">매달 손해</div>
        <div class="sc-item highlight">계속 반복</div>
        <div class="sc-item">10년 후</div>
        <div class="sc-item highlight">+120만원 손해</div>
      </div>
      <div class="sc-card green">
        <div class="sc-label">지금 바꾸면</div>
        <div class="sc-item" style="color:rgba(255,255,255,0.5)">손해 즉시 중단</div>
        <div class="sc-item g">사은품 수령</div>
        <div class="sc-item" style="color:rgba(255,255,255,0.5)">절감 시작</div>
        <div class="sc-item g">+최대 94만원 혜택</div>
      </div>
    </div>
  </div>
</section>

<!-- ════════════ SOCIAL PROOF ════════════ -->
<section id="proof">
  <div class="inner">
    <div class="eyebrow">실제 후기</div>
    <h2 class="sec-h">이미 바꾼 사람들의<br>이야기</h2>
    <div class="stat-row">
      <div class="stat">
        <div class="stat-num">94만원</div>
        <div class="stat-label">평균<br>수령 혜택</div>
      </div>
      <div class="stat">
        <div class="stat-num">30초</div>
        <div class="stat-label">진단<br>소요 시간</div>
      </div>
      <div class="stat">
        <div class="stat-num">당일</div>
        <div class="stat-label">혜택<br>지급 보장</div>
      </div>
    </div>
    <div class="review-list">
      <div class="review">
        <div class="rv-top">
          <div class="rv-avatar" style="background:#3182F6">김</div>
          <div>
            <div class="rv-name">김○○님 · 서울 마포구</div>
            <div class="rv-info">3년 사용 후 전환</div>
          </div>
          <div class="stars" style="margin-left:auto">★★★★★</div>
        </div>
        <div class="rv-title">"그냥 쓰던 인터넷 바꿨더니 이게 되네요"</div>
        <div class="rv-body">약정 끝난 지 2년이나 됐는데 그냥 쓰고 있었어요. 바꿀 생각도 없었는데 지인이 알려줘서 해봤더니 요금은 비슷하고 사은품이 나오더라고요.</div>
        <div class="rv-benefit"><div class="rb-text">✓ 사은품 87만원 수령</div></div>
      </div>
      <div class="review">
        <div class="rv-top">
          <div class="rv-avatar" style="background:#00C471">이</div>
          <div>
            <div class="rv-name">이○○님 · 경기 수원시</div>
            <div class="rv-info">5년 사용 후 전환</div>
          </div>
          <div class="stars" style="margin-left:auto">★★★★★</div>
        </div>
        <div class="rv-title">"위약금 걱정했는데 오히려 남았어요"</div>
        <div class="rv-body">위약금 때문에 망설였는데 계산해보니까 위약금 내고도 54만원이 남더라고요. 진작 할 걸 싶었어요.</div>
        <div class="rv-benefit"><div class="rb-text">✓ 위약금 제하고 54만원 수령</div></div>
      </div>
      <div class="review">
        <div class="rv-top">
          <div class="rv-avatar" style="background:#F04452">박</div>
          <div>
            <div class="rv-name">박○○님 · 인천 남동구</div>
            <div class="rv-info">부모님 대신 신청</div>
          </div>
          <div class="stars" style="margin-left:auto">★★★★★</div>
        </div>
        <div class="rv-title">"부모님 인터넷 10년 넘었다고 하셔서"</div>
        <div class="rv-body">부모님이 10년 넘게 같은 회사 쓰고 계셨어요. 대신 알아봐드렸더니 사은품도 받고 월 요금도 조금 낮아졌어요. 이걸 왜 이제 알았나 싶었죠.</div>
        <div class="rv-benefit"><div class="rb-text">✓ 가족결합 포함 총 94만원 수령</div></div>
      </div>
    </div>
  </div>
</section>

<!-- ════════════ CTA FORM ════════════ -->
<section id="cta">
  <div class="inner">
    <div class="cta-card">
      <div class="cta-eyebrow">무료 · 30초 · 지금 바로</div>
      <h2 class="cta-h">손해, 오늘부터<br>멈추세요</h2>
      <p class="cta-sub">전화번호 남기시면 전문 상담사가<br>최적 플랜을 직접 설계해드려요.<br>광고성 전화 없이 채팅으로만 연락합니다.</p>
      <div class="form-group">
        <input type="text" class="form-input" id="inp-name" placeholder="성함을 입력해 주세요">
      </div>
      <div class="form-group">
        <input type="tel" class="form-input" id="inp-phone" placeholder="010-0000-0000" oninput="fmtPhone(this)">
      </div>
      <div class="agree-wrap" onclick="toggleAgree()">
        <div class="chk" id="chk"></div>
        <div class="agree-text"><strong>무료 플랜 설계</strong>에 동의합니다. 위약금 포함 계산 후 실제 이득일 때만 추천드려요.</div>
      </div>
      <button class="btn-submit" onclick="submitForm()">손해 멈추고 혜택 받기</button>
      <button class="btn-kakao" onclick="alert('카카오 공유는 배포 환경에서 활성화됩니다.')">
        <svg width="20" height="20" viewBox="0 0 24 24" fill="none"><path d="M12 3C6.48 3 2 6.48 2 10.8c0 2.72 1.6 5.12 4 6.56l-.96 3.52 4.08-2.72c.92.16 1.88.24 2.88.24 5.52 0 10-3.48 10-7.8C22 6.48 17.52 3 12 3z" fill="#191919"/></svg>
        친구에게 공유하기
      </button>
      <div class="form-note">상담은 채팅으로만 진행됩니다 · 광고 전화 없음<br>위약금 계산 후 이득 없으면 솔직히 말씀드려요</div>
    </div>
  </div>
</section>

<!-- FLOATING CTA -->
<div id="float-cta">
  <button class="float-btn" onclick="smoothTo('cta')">지금 손해 멈추기 →</button>
</div>

<!-- SUCCESS OVERLAY -->
<div id="success-overlay">
  <div class="success-card">
    <div class="sc-icon">✅</div>
    <div class="sc-title">신청 완료!</div>
    <div class="sc-desc">담당 상담사가 <strong>영업일 기준 24시간 이내</strong> 채팅으로 연락드립니다.</div>
    <div class="sc-info">
      <div class="sci-row"><div class="sci-l">예상 혜택 금액</div><div class="sci-r green">최대 940,000원</div></div>
      <div class="sci-row"><div class="sci-l">손해 중단 시점</div><div class="sci-r blue">전환 즉시</div></div>
      <div class="sci-row"><div class="sci-l">광고 전화</div><div class="sci-r">없음</div></div>
    </div>
    <button class="btn-close" onclick="closeSuccess()">확인</button>
  </div>
</div>

<script>
/* ── 히어로 카운터 ── */
var heroStart = Date.now();
setInterval(function(){
  var sec = (Date.now()-heroStart)/1000;
  document.getElementById('heroCounter').textContent = '₩' + (sec*7.1).toFixed(1);
},50);

/* ── 손해 카운터 (story3) ── */
var lossStart = Date.now();
var lossBase = 36 * 12 * 10000; // 3년 * 월1만
setInterval(function(){
  var sec = (Date.now()-lossStart)/1000;
  var v = lossBase + sec*0.38;
  document.getElementById('lossCounter').textContent = '₩' + Math.floor(v).toLocaleString();
},80);

/* ── 계산기 ── */
function calcUpdate(){
  var age = parseInt(document.getElementById('slAge').value);
  var used = parseInt(document.getElementById('slUsed').value);
  var diff = parseInt(document.getElementById('slDiff').value);

  document.getElementById('valAge').textContent = age+'세';
  document.getElementById('valUsed').textContent = used+'년';
  document.getElementById('valDiff').textContent = (diff/10000)+'만원';

  var remain = 120 - age;
  var already = used * 12 * diff;
  var future = remain * 12 * diff;
  var total = already + future;

  animCount('rAlready', already);
  animCount('rFuture', future);
  animCount('rTotal', total);

  document.getElementById('rSub').textContent =
    '기준: '+age+'세 · '+used+'년 사용 · 월 '+(diff/10000)+'만원 차이';
  document.getElementById('calcInsight').innerHTML =
    '지금 바꾸면 앞으로 <strong>'+future.toLocaleString()+'원</strong>의 손해를 막을 수 있어요.';
}

var timers = {};
function animCount(id, target){
  if(timers[id]) clearInterval(timers[id]);
  var el = document.getElementById(id);
  var cur = 0;
  var step = Math.max(1, Math.ceil(target/40));
  timers[id] = setInterval(function(){
    cur = Math.min(cur+step, target);
    el.textContent = formatWon(cur);
    if(cur >= target) clearInterval(timers[id]);
  },20);
}
function formatWon(n){
  if(n >= 10000000) return Math.round(n/10000000*10)/10 + '억원';
  if(n >= 1000000) return Math.round(n/10000) + '만원';
  if(n >= 10000) return Math.round(n/10000*10)/10 + '만원';
  return n.toLocaleString() + '원';
}
calcUpdate();

/* ── 플로팅 CTA ── */
window.addEventListener('scroll', function(){
  var h = document.getElementById('hero').offsetHeight;
  var fc = document.getElementById('float-cta');
  if(window.scrollY > h * 0.7){
    fc.classList.add('show');
  } else {
    fc.classList.remove('show');
  }
});

/* ── 스무스 스크롤 ── */
function smoothTo(id){
  var el = document.getElementById(id);
  if(el) el.scrollIntoView({behavior:'smooth', block:'start'});
}

/* ── 폼 ── */
var agreed = false;
function toggleAgree(){
  agreed = !agreed;
  var c = document.getElementById('chk');
  c.classList.toggle('on', agreed);
  c.textContent = agreed ? '✓' : '';
}
function fmtPhone(inp){
  var v = inp.value.replace(/\D/g,'');
  if(v.length>=7) v = v.slice(0,3)+'-'+v.slice(3,7)+'-'+v.slice(7,11);
  else if(v.length>=4) v = v.slice(0,3)+'-'+v.slice(3);
  inp.value = v;
}
function submitForm(){
  var name = document.getElementById('inp-name').value.trim();
  var phone = document.getElementById('inp-phone').value.trim();
  if(!name){ alert('성함을 입력해 주세요.'); return; }
  if(!phone || phone.length < 12){ alert('전화번호를 정확히 입력해 주세요.'); return; }
  if(!agreed){ alert('동의 체크를 해주세요.'); return; }
  document.getElementById('float-cta').classList.remove('show');
  document.getElementById('success-overlay').classList.add('show');
}
function closeSuccess(){
  document.getElementById('success-overlay').classList.remove('show');
}
</script>
</body>
</html>
