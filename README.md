<!DOCTYPE html>
<html lang="ckb" dir="rtl">
<head>
<meta name="google-site-verification" content="l94UFbpbyxBMfIn_CJQY8uTaT9tmIFewPVbfFoqwM9s" />
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>زانکۆلاین — عبداللە یاسین نظام‌الدین</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Noto+Kufi+Arabic:wght@400;600;700;900&family=IBM+Plex+Sans+Arabic:wght@400;500;600;700&display=swap" rel="stylesheet">
<style>
  :root{
    --bg:#f8f2e9;
    --indigo:#c1631e;
    --indigo-2:#e2953f;
    --indigo-deep:#241a10;
    --ink:#2a1f15;
    --muted:#8c7c68;
    --card:#ffffff;
    --line:#ece0cf;
    --green:#1fab6f;
    --green-bg:#e7f9f1;
    --amber:#b8860f;
    --amber-bg:#fdf3e0;
  }
  *{box-sizing:border-box; margin:0; padding:0;}
  body{
    background:var(--bg);
    color:var(--ink);
    font-family:'IBM Plex Sans Arabic', sans-serif;
    min-height:100vh;
    padding-bottom:92px;
    -webkit-font-smoothing:antialiased;
  }
  .wrap{max-width:720px; margin:0 auto; padding:20px 16px 8px;}

  /* ---------- topbar ---------- */
  .topbar{
    display:flex; align-items:center; justify-content:space-between;
    margin-bottom:18px;
  }
  .topbar .icons{display:flex; gap:10px;}
  .icon-btn{
    position:relative;
    width:42px; height:42px; border-radius:50%;
    background:#fff; border:1px solid var(--line);
    display:flex; align-items:center; justify-content:center;
    color:var(--muted); cursor:pointer;
  }
  .icon-btn svg{width:19px; height:19px;}
  .bell-dot{
    position:absolute; top:-3px; left:-3px;
    min-width:17px; height:17px; padding:0 4px;
    border-radius:100px; background:#e6403c; color:#fff;
    font-size:10px; font-weight:800;
    display:flex; align-items:center; justify-content:center;
    border:2px solid var(--bg);
    animation:bellPulse 1.6s ease-in-out infinite;
  }
  .bell-dot.hide{display:none;}
  @keyframes bellPulse{0%,100%{transform:scale(1);} 50%{transform:scale(1.15);}}

  /* ---------- notif / register modals ---------- */
  .mini-overlay{
    position:fixed; inset:0; z-index:110;
    background:rgba(36,26,16,.45);
    display:none; align-items:center; justify-content:center;
    padding:20px;
  }
  .mini-overlay.open{display:flex;}
  .mini-panel{
    width:100%; max-width:400px;
    background:var(--card);
    border-radius:22px;
    box-shadow:0 20px 60px rgba(36,26,16,.35);
    overflow:hidden;
    animation:miniIn .28s cubic-bezier(.34,1.56,.64,1);
  }
  @keyframes miniIn{from{opacity:0; transform:translateY(14px) scale(.97);} to{opacity:1; transform:translateY(0) scale(1);}}
  .notif-hero{
    background:linear-gradient(135deg, var(--indigo), var(--indigo-2));
    color:#fff; padding:30px 22px 24px; text-align:center;
  }
  .notif-hero .emoji{font-size:40px; margin-bottom:8px;}
  .notif-hero h3{font-family:'Noto Kufi Arabic',sans-serif; font-size:18px; font-weight:900;}
  .notif-hero p{font-size:12.5px; color:#ffe9d3; margin-top:6px; line-height:1.8;}
  .mini-body{padding:18px 20px 22px;}
  .mini-body p{font-size:13px; color:var(--muted); line-height:1.9; text-align:center;}
  .mini-close-btn{
    display:block; width:100%; margin-top:16px;
    background:linear-gradient(135deg, var(--indigo), var(--indigo-2));
    color:#fff; border:none; border-radius:100px;
    padding:12px; font-size:13.5px; font-weight:700;
    font-family:inherit; cursor:pointer;
  }
  .mini-head{
    display:flex; align-items:center; justify-content:space-between;
    padding:16px 18px; border-bottom:1px solid var(--line);
  }
  .mini-head h3{font-family:'Noto Kufi Arabic',sans-serif; font-size:15.5px; font-weight:800; color:var(--indigo-deep);}
  .mini-x{
    width:30px; height:30px; border-radius:50%;
    background:var(--bg); border:none; color:var(--muted);
    font-size:15px; cursor:pointer;
  }
  .reg-form{padding:18px 20px 20px; display:flex; flex-direction:column; gap:11px;}
  .reg-form label{font-size:12px; font-weight:700; color:var(--ink); margin-bottom:-4px;}
  .reg-form input, .reg-form select{
    border:1px solid var(--line); border-radius:12px; padding:11px 14px;
    font-size:13.5px; font-family:inherit; background:var(--bg); color:var(--ink); outline:none;
    width:100%;
  }
  .reg-form input:focus, .reg-form select:focus{border-color:var(--indigo);}
  .reg-submit{
    margin-top:6px; background:linear-gradient(135deg, var(--indigo), var(--indigo-2));
    color:#fff; border:none; border-radius:100px;
    padding:13px; font-size:13.5px; font-weight:800;
    font-family:inherit; cursor:pointer;
  }
  .reg-ok{
    display:none; text-align:center; padding:26px 20px 30px;
  }
  .reg-ok .emoji{font-size:42px; margin-bottom:10px;}
  .reg-ok h3{font-family:'Noto Kufi Arabic',sans-serif; font-size:16px; font-weight:900; color:var(--indigo-deep);}
  .reg-ok p{font-size:12.5px; color:var(--muted); margin-top:6px; line-height:1.8;}
  .brand{
    display:flex; align-items:center; gap:8px;
    font-family:'Noto Kufi Arabic', sans-serif;
    font-weight:700; font-size:16.5px; color:var(--indigo-deep);
  }
  .brand .dot{width:8px; height:8px; border-radius:50%; background:#22c55e;}
  .online-pill{
    display:flex; align-items:center; gap:6px;
    background:var(--green-bg); color:var(--green);
    font-size:12px; font-weight:600;
    padding:6px 12px; border-radius:100px;
  }

  /* ---------- sections ---------- */
  .section{display:none;}
  .section.active{display:block;}
  .page-title{
    font-family:'Noto Kufi Arabic', sans-serif;
    font-weight:900; font-size:21px;
    margin:4px 0 16px;
  }
  .page-head{display:flex; align-items:center; gap:10px; margin:4px 0 16px;}
  .page-head .page-title{margin:0;}
  .back-btn{
    width:36px; height:36px; border-radius:50%; flex-shrink:0;
    background:#fff; border:1px solid var(--line); color:var(--indigo-deep);
    display:flex; align-items:center; justify-content:center; cursor:pointer;
  }
  .back-btn svg{width:18px; height:18px;}

  /* ---------- profile card ---------- */
  .profile-card{
    background:linear-gradient(160deg, #1c1712, #150f08);
    border-radius:24px;
    overflow:hidden;
    box-shadow:0 24px 50px -28px rgba(76,60,20,0.45);
    margin-bottom:22px;
  }
  .profile-inner{display:grid; grid-template-columns:150px 1fr; gap:0;}
  .profile-photo{position:relative; min-height:220px; background:#0d0a06;}
  .profile-photo img{width:100%; height:100%; object-fit:cover; display:block;}
  .profile-photo::after{content:""; position:absolute; inset:0; background:linear-gradient(180deg, transparent 60%, rgba(13,10,6,0.6)); }
  .profile-data{padding:20px 20px 18px; color:#f4ead6;}
  .profile-data h2{font-family:'Noto Kufi Arabic', sans-serif; font-size:19px; font-weight:900; line-height:1.3;}
  .profile-status{margin-top:5px; font-size:12.5px; color:#e6b13c; font-weight:600; display:flex; align-items:center; gap:6px;}
  .profile-status .d{width:6px; height:6px; border-radius:50%; background:#7fc97f;}
  .profile-fields{margin-top:14px; display:flex; flex-direction:column; gap:8px;}
  .profile-fields .row{display:flex; justify-content:space-between; font-size:13px;}
  .profile-fields .row .k{color:#a89a7c;}
  .profile-fields .row .v{color:#f4ead6; font-weight:600;}
  .profile-fields .row .v.pending{color:#e6b13c; font-weight:500; font-size:12px;}

  .pills{display:flex; flex-wrap:wrap; gap:8px; margin:16px 0 4px;}
  .pill{
    padding:8px 14px; border-radius:100px; font-size:12.5px; font-weight:600;
    background:#fff; border:1px solid var(--line); color:var(--indigo-deep);
  }

  /* ---------- skills box ---------- */
  .skills-box{
    background:var(--card); border:1px solid var(--line); border-radius:18px;
    padding:18px 20px; margin:18px 0 4px;
  }
  .skills-box .skills-head{
    display:flex; align-items:center; justify-content:space-between;
    font-family:'Noto Kufi Arabic', sans-serif; font-size:16px; font-weight:800;
    color:var(--ink); padding-bottom:12px; margin-bottom:4px;
    border-bottom:1px solid var(--line);
  }
  .skills-box .skills-head svg{width:19px; height:19px; color:#f0b429;}
  .skill-item{
    display:flex; align-items:center; justify-content:space-between;
    padding:11px 0; font-size:14px; font-weight:600; color:var(--ink);
  }
  .skill-item + .skill-item{border-top:1px dashed var(--line);}
  .skill-check{
    width:24px; height:24px; border-radius:50%; flex-shrink:0;
    background:var(--indigo); color:#fff;
    display:flex; align-items:center; justify-content:center;
  }
  .skill-check svg{width:13px; height:13px;}

  /* ---------- nav cards (home) ---------- */
  .nav-card{
    background:var(--card); border-radius:18px; padding:18px;
    display:flex; align-items:center; justify-content:space-between;
    margin-bottom:14px; border:1px solid var(--line);
    cursor:pointer;
  }
  .nav-card .left{display:flex; align-items:center; gap:12px;}
  .nav-card .chev{color:var(--muted); font-size:18px;}
  .nav-card .txt h3{font-family:'Noto Kufi Arabic', sans-serif; font-size:16px; font-weight:700;}
  .nav-card .txt p{font-size:12.5px; color:var(--muted); margin-top:4px; max-width:220px;}
  .nav-ic{
    width:52px; height:52px; border-radius:14px;
    display:flex; align-items:center; justify-content:center;
    flex-shrink:0;
  }
  .nav-ic svg{width:24px; height:24px;}
  .ic-a{background:#fdf3e0; color:#c68a1f;}
  .ic-b{background:#efe4d6; color:#5c4326;}
  .ic-c{background:#e7f9f1; color:#1fab6f;}
  .ic-d{background:#f7e9d6; color:#a2611e;}

  /* ---------- rankings ---------- */
  .stat-strip{
    background:#f5e7d3; color:var(--indigo-deep);
    border-radius:14px; padding:12px 16px;
    font-size:13px; font-weight:700; text-align:center;
    margin-bottom:16px;
  }
  .uni-card{border-radius:18px; overflow:hidden; margin-bottom:18px; border:1px solid var(--line); background:#fff;}

  /* ---------- stats summary ---------- */
  .stats-summary{
    background:#fff; border:1px solid var(--line);
    border-radius:20px; padding:20px 18px; margin-bottom:20px;
    box-shadow:0 1px 2px rgba(36,26,16,.04), 0 6px 20px rgba(36,26,16,.05);
  }
  .stats-summary-head{
    display:flex; align-items:center; justify-content:space-between;
    margin-bottom:18px; padding-bottom:14px; border-bottom:1px solid var(--line);
  }
  .stats-summary-head h3{
    font-family:'Noto Kufi Arabic', sans-serif; font-size:15.5px; font-weight:900;
    color:var(--indigo-deep); display:flex; align-items:center; gap:8px; letter-spacing:.2px;
  }
  .stats-refresh{
    display:flex; align-items:center; gap:6px;
    background:var(--indigo-deep); color:#fff; border:none;
    font-size:11.5px; font-weight:700; padding:8px 14px;
    border-radius:100px; cursor:pointer; font-family:inherit;
    box-shadow:0 2px 6px rgba(36,26,16,.18);
    transition:opacity .15s ease;
  }
  .stats-refresh:active{opacity:.75;}
  .stats-refresh svg{width:13px; height:13px;}
  .stats-refresh.spin svg{animation:statSpin .6s linear;}
  @keyframes statSpin{to{transform:rotate(360deg);}}

  .stats-grid{display:grid; grid-template-columns:1fr 1fr; gap:12px; margin-bottom:18px;}
  .stat-card{
    background:#fbf9f6; border:1px solid var(--line); border-radius:16px;
    padding:18px 14px; text-align:center; position:relative;
  }
  .stat-card.full{grid-column:1 / -1;}
  .stat-card .stat-emoji{
    width:40px; height:40px; margin:0 auto 10px; font-size:19px;
    display:flex; align-items:center; justify-content:center;
    background:#fff; border:1px solid var(--line); border-radius:12px;
    box-shadow:0 1px 2px rgba(36,26,16,.05);
  }
  .stat-card .stat-num{
    font-family:'Noto Kufi Arabic', sans-serif; font-weight:900; font-size:26px;
    color:var(--indigo-deep); font-variant-numeric:tabular-nums; letter-spacing:.3px;
  }
  .stat-card .stat-label{font-size:11.5px; color:var(--muted); margin-top:6px; font-weight:700;}

  .dist-box{background:#fff; border:1px solid var(--line); border-radius:18px; padding:18px 16px; margin-bottom:16px; box-shadow:0 1px 2px rgba(36,26,16,.04);}
  .dist-box-title{
    font-family:'Noto Kufi Arabic', sans-serif; font-weight:800; font-size:13.5px;
    color:var(--indigo-deep); margin-bottom:16px; display:flex; align-items:center; gap:6px;
  }
  .dist-row{display:flex; align-items:center; gap:10px; margin-bottom:13px;}
  .dist-row:last-child{margin-bottom:0;}
  .dist-label{font-weight:800; font-size:12.5px; color:var(--ink); white-space:nowrap; min-width:52px;}
  .dist-track{flex:1; height:9px; border-radius:100px; background:#f1ece2; position:relative; overflow:hidden;}
  .dist-fill{
    position:absolute; top:0; right:0; height:100%; border-radius:100px;
    background:linear-gradient(90deg, var(--indigo-2), var(--indigo));
  }
  .dist-count{font-weight:800; font-size:12.5px; color:var(--indigo); white-space:nowrap; min-width:38px; text-align:left; font-variant-numeric:tabular-nums;}

  .top10-box{background:#fff; border:1px solid var(--line); border-radius:18px; padding:16px 16px; margin-bottom:14px; box-shadow:0 1px 2px rgba(36,26,16,.04);}
  .top10-title{
    font-family:'Noto Kufi Arabic', sans-serif; font-weight:800; font-size:13.5px;
    color:var(--indigo-deep); margin-bottom:10px; display:flex; align-items:center; gap:6px; line-height:1.6;
  }
  .top10-row{
    display:flex; align-items:center; gap:12px;
    padding:11px 2px; border-bottom:1px solid var(--line);
  }
  .top10-row:last-child{border-bottom:none;}
  .top10-rank{
    background:#f1ece2; color:var(--muted); font-weight:800; font-size:11.5px;
    width:26px; height:26px; flex-shrink:0; border-radius:9px;
    display:flex; align-items:center; justify-content:center;
  }
  .top10-row:nth-child(2) .top10-rank{background:linear-gradient(135deg,#f6e2b8,#d9a441); color:#5c4008;}
  .top10-row:nth-child(3) .top10-rank{background:linear-gradient(135deg,#e6e6ea,#b7bcc4); color:#3a3d44;}
  .top10-row:nth-child(4) .top10-rank{background:linear-gradient(135deg,#e9c7a6,#c98a52); color:#4a2c10;}
  .top10-name{font-weight:700; font-size:13px; color:var(--ink); flex:1; text-align:right;}
  .top10-count{
    background:var(--amber-bg); color:var(--amber); font-weight:800; font-size:12.5px;
    padding:6px 12px; border-radius:100px; white-space:nowrap; flex-shrink:0;
  }
  .stats-note{
    display:flex; gap:10px; align-items:flex-start;
    background:#fbf9f6; border:1px solid var(--line); border-radius:16px;
    padding:14px 14px; font-size:12px; line-height:1.85; color:var(--ink);
  }
  .stats-note .n-emoji{font-size:17px; flex-shrink:0;}

  .uni-head{
    background:linear-gradient(135deg, var(--indigo), var(--indigo-2));
    color:#fff; padding:16px 18px;
    display:flex; align-items:center; justify-content:space-between;
  }
  .uni-head h3{font-family:'Noto Kufi Arabic', sans-serif; font-size:16px; font-weight:800;}
  .uni-head .badge{background:rgba(255,255,255,0.18); font-size:11.5px; padding:4px 10px; border-radius:100px;}
  table{width:100%; border-collapse:collapse; font-size:12px;}
  thead th{
    background:#f7f0e5; color:var(--muted); font-weight:700;
    padding:9px 6px; text-align:center; font-size:11px; border-bottom:1px solid var(--line);
  }
  tbody td{padding:9px 6px; text-align:center; border-bottom:1px solid var(--line); font-weight:600;}
  tbody tr:nth-child(even){background:#fbf6ee;}
  td.dept{text-align:right; font-weight:600; font-size:12px; line-height:1.4;}
  td.lq{font-size:10.5px; color:var(--indigo-deep); font-weight:700;}
  td.zank{color:var(--indigo-deep);}
  td.par{color:#c68a1f;}
  .note-box{
    background:var(--amber-bg); color:#8a6208; border-radius:14px;
    padding:14px 16px; font-size:12.5px; line-height:1.7; margin:10px 0 20px;
  }

  .tg-live-card{
    display:flex; align-items:center; justify-content:space-between;
    background:#fff; border:1px solid var(--line); border-radius:16px;
    padding:14px 16px; margin:0 0 16px; text-decoration:none; color:inherit;
  }
  .tg-live-card .left{display:flex; align-items:center; gap:12px;}
  .tg-live-ic{
    width:44px; height:44px; border-radius:12px; flex-shrink:0;
    background:#e6f4fb; color:#229ED9;
    display:flex; align-items:center; justify-content:center;
  }
  .tg-live-ic svg{width:22px; height:22px;}
  .tg-live-card .txt h3{font-family:'Noto Kufi Arabic',sans-serif; font-size:13.5px; font-weight:800; color:var(--ink);}
  .tg-live-card .txt p{font-size:11.5px; color:var(--muted); margin-top:4px; display:flex; align-items:center; gap:5px;}
  .tg-live-dot{width:7px; height:7px; border-radius:50%; background:#22c55e; flex-shrink:0; animation:tgLivePulse 1.4s ease-in-out infinite;}
  @keyframes tgLivePulse{0%,100%{opacity:1;} 50%{opacity:.35;}}
  #tg-live-count{color:#1fab6f; font-weight:800;}


  /* ---------- price list ---------- */
  .price-group{margin-bottom:22px;}
  .price-group h3{
    font-family:'Noto Kufi Arabic', sans-serif; font-size:15px; font-weight:800;
    color:var(--indigo-deep); margin-bottom:10px; display:flex; align-items:center; gap:8px;
  }
  .price-row{
    display:flex; align-items:center; justify-content:space-between;
    background:#fff; border:1px solid var(--line); border-radius:14px;
    padding:12px 16px; margin-bottom:8px;
  }
  .price-row .name{font-size:13px; font-weight:600;}
  .price-row .amount{font-size:14px; font-weight:800; color:var(--indigo-deep); white-space:nowrap;}
  .price-row .amount span{font-size:10.5px; font-weight:500; color:var(--muted);}

  /* ---------- calculator ---------- */
  .calc-card{background:#fff; border:1px solid var(--line); border-radius:18px; padding:18px; margin-bottom:16px;}
  .calc-card h3{font-family:'Noto Kufi Arabic', sans-serif; font-size:15px; font-weight:800; margin-bottom:12px;}
  .subj-row{display:flex; gap:8px; margin-bottom:8px; min-width:0;}
  .subj-row input{
    flex:1; min-width:0; border:1px solid var(--line); border-radius:10px; padding:10px 12px;
    font-family:inherit; font-size:13px; background:#fbf6ee;
  }
  .subj-row input.score{flex:0 0 72px; min-width:0; text-align:center; padding:10px 6px;}
  .subj-row .rm{
    width:30px; flex-shrink:0; border:none; background:#fbeaea; color:#c0392b;
    border-radius:10px; font-size:16px; cursor:pointer; padding:0;
  }
  @media (max-width:380px){
    .subj-row{gap:5px;}
    .subj-row input{padding:9px 8px; font-size:12px;}
    .subj-row input.score{flex-basis:56px;}
  }
  .add-btn{
    width:100%; padding:11px; border-radius:12px; border:1px dashed #e8cca4;
    background:#f8ecdc; color:var(--indigo-deep); font-weight:700; font-size:13px;
    margin:6px 0 14px; cursor:pointer;
  }
  .subj-btn-row{display:flex; gap:8px; margin:6px 0 14px;}
  .subj-btn-row .add-btn{margin:0; flex:1;}
  .subj-btn-row .remove-btn{
    flex:0 0 44px; border-radius:12px; border:1px dashed #e6b3ac;
    background:#fbeaea; color:#c0392b; font-weight:800; font-size:16px; cursor:pointer;
  }
  .subj-btn-row .remove-btn:disabled{opacity:.4; cursor:not-allowed;}
  .calc-btn{
    width:100%; padding:13px; border-radius:12px; border:none;
    background:linear-gradient(135deg, var(--indigo), var(--indigo-2));
    color:#fff; font-weight:800; font-size:14.5px; cursor:pointer;
  }
  .result-box{
    margin-top:14px; padding:16px; border-radius:14px;
    background:var(--green-bg); color:var(--green);
    text-align:center; font-weight:800; font-size:15px; display:none;
  }
  .result-box .sub{display:block; font-size:11.5px; font-weight:500; color:#4a9c76; margin-top:4px;}

  /* ---------- province tabs ---------- */
  .prov-tabs{display:flex; gap:8px; margin-bottom:16px;}
  .prov-tab-btn{
    flex:1; padding:10px 6px; border-radius:12px; border:1px solid var(--line);
    background:#fff; color:var(--indigo-deep); font-family:inherit; font-weight:700;
    font-size:13px; cursor:pointer;
  }
  .prov-tab-btn.active{
    background:linear-gradient(135deg, var(--indigo), var(--indigo-2));
    color:#fff; border-color:transparent;
  }
  .prov-block.prov-hidden{display:none;}

  /* ---------- زانکۆکان: category menu ---------- */
  .rank-menu{display:flex; flex-direction:column; gap:12px;}
  .rank-menu-btn{
    display:flex; align-items:center; gap:14px;
    width:100%; text-align:right;
    background:var(--card); border:1px solid var(--line); border-radius:18px;
    padding:16px 16px; cursor:pointer; font-family:inherit;
  }
  .rank-menu-icon{
    width:48px; height:48px; border-radius:14px; flex-shrink:0;
    display:flex; align-items:center; justify-content:center;
    font-size:22px;
    background:linear-gradient(135deg, var(--indigo), var(--indigo-2));
  }
  .rank-menu-txt{flex:1; min-width:0;}
  .rank-menu-txt h3{font-family:'Noto Kufi Arabic', sans-serif; font-size:15px; font-weight:800; color:var(--indigo-deep);}
  .rank-menu-txt p{font-size:12px; color:var(--muted); margin-top:3px; line-height:1.6;}
  .rank-menu-chevron{color:var(--muted); flex-shrink:0;}
  .rank-menu-chevron svg{width:18px; height:18px;}

  .rank-view{display:none;}
  .rank-view.active-view{display:block;}
  .rank-view-back{
    display:flex; align-items:center; gap:6px;
    background:#fff; border:1px solid var(--line); border-radius:100px;
    padding:9px 16px; font-family:inherit; font-weight:700; font-size:12.5px;
    color:var(--indigo-deep); cursor:pointer; margin-bottom:14px;
  }
  .rank-view-back svg{width:14px; height:14px;}
  .rank-view-title{
    font-family:'Noto Kufi Arabic', sans-serif; font-weight:900; font-size:18px;
    margin-bottom:14px;
  }

  /* ---------- score search ---------- */
  .search-card{background:#fff; border:1px solid var(--line); border-radius:18px; padding:18px; margin-bottom:16px;}
  .search-row{display:flex; gap:8px; margin-bottom:12px;}
  .search-row input[type="number"]{
    flex:1; border:1px solid var(--line); border-radius:10px; padding:12px 14px;
    font-family:inherit; font-size:15px; font-weight:700; background:#fbf6ee; text-align:center;
  }
  .search-btn{
    padding:0 22px; border-radius:10px; border:none;
    background:linear-gradient(135deg, var(--indigo), var(--indigo-2));
    color:#fff; font-weight:800; font-size:14px; cursor:pointer;
  }
  .track-filters{display:flex; gap:8px; margin-bottom:4px;}
  .track-btn{
    flex:1; padding:9px 6px; border-radius:10px; border:1px solid var(--line);
    background:#fbf6ee; color:var(--muted); font-family:inherit; font-weight:700;
    font-size:12.5px; cursor:pointer;
  }
  .track-btn.active{background:var(--indigo); color:#fff; border-color:transparent;}
  .fav-toggle-btn{
    width:100%; margin-top:10px; padding:11px; border-radius:12px; border:1px dashed #e8cca4;
    background:#f8ecdc; color:var(--indigo-deep); font-weight:700; font-size:13px; cursor:pointer;
  }
  .result-item{
    background:#fff; border:1px solid var(--line); border-radius:16px; padding:14px 16px;
    margin-bottom:10px; display:flex; justify-content:space-between; align-items:center; gap:10px;
  }
  .result-item .info{flex:1;}
  .result-item .dept-name{font-size:13.5px; font-weight:700; line-height:1.4;}
  .result-item .meta{font-size:11.5px; color:var(--muted); margin-top:5px;}
  .result-item .score-badge{font-size:13px; font-weight:800; color:var(--indigo-deep); white-space:nowrap;}
  .result-item.reach .score-badge{color:#c68a1f;}
  .chance-pill{
    display:inline-block; margin-top:6px; font-size:10.5px; font-weight:700;
    padding:3px 9px; border-radius:100px;
  }
  .chance-safe{background:var(--green-bg); color:var(--green);}
  .chance-mid{background:var(--amber-bg); color:var(--amber);}
  .chance-low{background:#fdeceb; color:#c0392b;}
  .fav-star{
    width:36px; height:36px; border-radius:50%; border:1px solid var(--line);
    background:#fbf6ee; font-size:16px; cursor:pointer; flex-shrink:0;
    display:flex; align-items:center; justify-content:center;
  }
  .fav-star.active{background:#fdf3e0; border-color:#e6c88a; color:#c68a1f;}
  .no-results{text-align:center; color:var(--muted); font-size:13px; padding:24px 0;}

  /* ---------- bottom nav ---------- */
  .bottom-nav{
    position:fixed; bottom:0; left:0; right:0;
    background:#fff; border-top:1px solid var(--line);
    display:flex; justify-content:space-around; align-items:center;
    padding:10px 6px 14px; z-index:50;
  }
  .nav-item{
    display:flex; flex-direction:column; align-items:center; gap:4px;
    font-size:11px; color:var(--muted); font-weight:600;
    background:none; border:none; font-family:inherit; cursor:pointer;
    padding:6px 10px; border-radius:14px;
  }
  .nav-item svg{width:20px; height:20px;}
  .nav-item.active{
    background:linear-gradient(135deg, var(--indigo), var(--indigo-2));
    color:#fff;
  }

  /* ---------- زیرەک assistant ---------- */
  .zirak-fab{
    position:fixed; z-index:60;
    left:18px; bottom:96px;
    width:56px; height:56px; border-radius:50%;
    background:linear-gradient(135deg, var(--indigo), var(--indigo-2));
    color:#fff; border:none; cursor:pointer;
    box-shadow:0 14px 30px -10px rgba(193,99,30,.55);
    display:flex; align-items:center; justify-content:center;
    font-size:22px;
  }
  .zirak-overlay{
    position:fixed; inset:0; z-index:100;
    background:rgba(36,26,16,.45);
    display:none; align-items:flex-end; justify-content:center;
  }
  .zirak-overlay.open{display:flex;}
  .zirak-panel{
    width:100%; max-width:460px; height:min(640px, 88vh);
    background:var(--card);
    border-radius:24px 24px 0 0;
    display:flex; flex-direction:column; overflow:hidden;
    box-shadow:0 -20px 60px rgba(36,26,16,.35);
  }
  .zirak-head{
    background:linear-gradient(135deg, var(--indigo), var(--indigo-2));
    color:#fff; padding:16px 18px;
    display:flex; align-items:center; gap:12px;
  }
  .zirak-avatar{
    width:40px; height:40px; border-radius:50%;
    background:rgba(255,255,255,.18);
    display:flex; align-items:center; justify-content:center;
    font-size:18px; flex-shrink:0;
    border:1px solid rgba(255,255,255,.35);
  }
  .zirak-head-txt{flex:1; line-height:1.4;}
  .zirak-head-txt .name{font-family:'Noto Kufi Arabic',sans-serif; font-weight:800; font-size:15.5px;}
  .zirak-head-txt .status{font-size:11.5px; color:#ffe9d3; display:flex; align-items:center; gap:5px;}
  .zirak-head-txt .status .d{width:6px; height:6px; border-radius:50%; background:#7fe0a3;}
  .zirak-close{
    width:32px; height:32px; border-radius:50%;
    background:rgba(255,255,255,.18); border:none; color:#fff;
    font-size:16px; cursor:pointer; flex-shrink:0;
  }
  .zirak-thread{
    flex:1; overflow-y:auto; padding:16px 14px;
    display:flex; flex-direction:column; gap:10px;
    background:var(--bg);
  }
  .zirak-row{display:flex; width:100%;}
  .zirak-row.bot{justify-content:flex-start;}
  .zirak-row.user{justify-content:flex-end;}
  .zirak-bubble{
    max-width:78%; padding:10px 14px; border-radius:16px;
    font-size:13.5px; line-height:1.85;
  }
  .zirak-row.bot .zirak-bubble{
    background:#fff; border:1px solid var(--line); color:var(--ink);
    border-bottom-right-radius:4px;
  }
  .zirak-row.user .zirak-bubble{
    background:linear-gradient(135deg, var(--indigo), var(--indigo-2));
    color:#fff; border-bottom-left-radius:4px;
  }
  .zirak-tg{
    margin-top:8px; display:inline-flex; align-items:center; gap:6px;
    background:var(--indigo-deep); color:#fff; text-decoration:none;
    font-size:12.5px; font-weight:700; padding:8px 14px; border-radius:100px;
  }
  .zirak-typing{
    display:flex; align-items:center; gap:4px;
    background:#fff; border:1px solid var(--line);
    padding:12px 16px; border-radius:16px; border-bottom-right-radius:4px;
    width:fit-content;
  }
  .zirak-typing span{width:6px; height:6px; border-radius:50%; background:var(--muted); animation:zirakBlink 1.1s infinite;}
  .zirak-typing span:nth-child(2){animation-delay:.18s;}
  .zirak-typing span:nth-child(3){animation-delay:.36s;}
  @keyframes zirakBlink{0%,60%,100%{opacity:.25; transform:translateY(0);} 30%{opacity:1; transform:translateY(-2px);}}
  .zirak-form{display:flex; gap:8px; padding:12px; border-top:1px solid var(--line); background:#fff;}
  .zirak-form input{
    flex:1; border:1px solid var(--line); border-radius:100px; padding:11px 16px;
    font-size:13.5px; font-family:inherit; background:var(--bg); color:var(--ink); outline:none;
  }
  .zirak-form input:focus{border-color:var(--indigo);}
  .zirak-send{
    background:linear-gradient(135deg, var(--indigo), var(--indigo-2));
    color:#fff; border:none; border-radius:50%; width:40px; height:40px;
    flex-shrink:0; font-size:16px; cursor:pointer;
  }
  .zirak-send:disabled{opacity:.5;}

  /* ---------- loading screen ---------- */
  #zank-loader{
    position:fixed; inset:0; z-index:9999;
    background:radial-gradient(circle at 50% 30%, #fdf3e0, var(--bg) 70%);
    display:flex; flex-direction:column; align-items:center; justify-content:center;
    transition:opacity .6s ease, visibility .6s ease;
  }
  #zank-loader.hide{opacity:0; visibility:hidden; pointer-events:none;}
  .loader-build{width:180px; height:150px; overflow:visible;}
  .loader-title{
    font-family:'Noto Kufi Arabic', sans-serif; font-weight:900; font-size:20px;
    color:var(--indigo-deep); margin-top:16px; letter-spacing:.3px;
  }
  .loader-sub{font-size:12.5px; color:var(--muted); margin-top:6px;}
  .loader-bar-wrap{
    width:190px; height:6px; border-radius:100px; background:var(--line);
    margin-top:24px; overflow:hidden;
  }
  .loader-bar-fill{
    height:100%; width:0%; border-radius:100px;
    background:linear-gradient(135deg, var(--indigo), var(--indigo-2));
  }
  .lb-base, .lb-base2{opacity:0; animation:lbBaseIn .45s ease forwards;}
  .lb-base2{animation-delay:.08s;}
  .lb-col{
    transform-box:fill-box; transform-origin:50% 100%;
    transform:scaleY(0);
    animation:lbColRise .5s cubic-bezier(.34,1.56,.64,1) forwards;
  }
  .lb-roofbar, .lb-roof{opacity:0; animation:lbRoofDrop .45s ease forwards; animation-delay:.85s;}
  .lb-roof{fill:var(--indigo-deep);}
  @keyframes lbBaseIn{from{opacity:0; transform:translateY(8px);} to{opacity:1; transform:translateY(0);}}
  @keyframes lbColRise{to{transform:scaleY(1);}}
  @keyframes lbRoofDrop{from{opacity:0; transform:translateY(-12px);} to{opacity:1; transform:translateY(0);}}

  footer.foot{text-align:center; font-size:11.5px; color:var(--muted); margin:30px 0 10px;}

  @media (max-width:520px){
    .profile-inner{grid-template-columns:120px 1fr;}
    .profile-photo{min-height:190px;}
    table{font-size:10.5px;}
    td.dept{font-size:11px;}
  }
</style>
</head>
<body>

<div id="zank-loader">
  <svg class="loader-build" viewBox="0 0 200 160" xmlns="http://www.w3.org/2000/svg">
    <rect class="lb-base" x="18" y="140" width="164" height="9" rx="2" fill="#241a10"/>
    <rect class="lb-base2" x="28" y="130" width="144" height="8" rx="2" fill="#c1631e"/>
    <rect class="lb-col" x="36" y="60" width="11" height="70" fill="#e2953f" style="animation-delay:.05s"/>
    <rect class="lb-col" x="64" y="60" width="11" height="70" fill="#e2953f" style="animation-delay:.18s"/>
    <rect class="lb-col" x="92" y="60" width="11" height="70" fill="#e2953f" style="animation-delay:.31s"/>
    <rect class="lb-col" x="120" y="60" width="11" height="70" fill="#e2953f" style="animation-delay:.44s"/>
    <rect class="lb-col" x="148" y="60" width="11" height="70" fill="#e2953f" style="animation-delay:.57s"/>
    <rect class="lb-roofbar" x="23" y="54" width="154" height="8" rx="1" fill="#c1631e"/>
    <polygon class="lb-roof" points="28,54 100,16 172,54"/>
  </svg>
  <div class="loader-title">زانکۆلاین</div>
  <div class="loader-sub">خەریکی ئامادەکردنە…</div>
  <div class="loader-bar-wrap"><div class="loader-bar-fill" id="zank-loader-fill"></div></div>
</div>

<div class="wrap">

  <div class="topbar">
    <div class="icons">
      <div class="icon-btn" id="reg-btn" onclick="openRegister()"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><circle cx="12" cy="8" r="4"/><path d="M4 20c0-4.4 3.6-8 8-8s8 3.6 8 8"/></svg></div>
      <div class="icon-btn" id="bell-btn" onclick="openNotif()"><svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M18 8a6 6 0 0 0-12 0c0 7-3 9-3 9h18s-3-2-3-9"/><path d="M13.73 21a2 2 0 0 1-3.46 0"/></svg><span class="bell-dot" id="bell-dot">1</span></div>
    </div>
    <div class="brand">زانکۆلاین <span class="dot"></span></div>
  </div>

  <!-- ===================== HOME / PROFILE ===================== -->
  <section id="home" class="section active">
    <div class="profile-card">
      <div class="profile-inner">
        <div class="profile-photo"><img src="data:image/jpeg;base64,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# Zankolain