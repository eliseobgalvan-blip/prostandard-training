# sinpausa-training
The Training App

<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
<meta name="apple-mobile-web-app-capable" content="yes">
<meta name="apple-mobile-web-app-status-bar-style" content="black-translucent">
<meta name="apple-mobile-web-app-title" content="Sin Pausa">
<meta name="theme-color" content="#0a0a0a">
<title>Sin Pausa Training</title>
<link rel="manifest" href="data:application/manifest+json,{%22name%22:%22Sin%20Pausa%22,%22short_name%22:%22Sin%20Pausa%22,%22start_url%22:%22.%22,%22display%22:%22standalone%22,%22background_color%22:%22%230a0a0a%22,%22theme_color%22:%22%230a0a0a%22,%22orientation%22:%22portrait%22,%22icons%22:[{%22src%22:%22data:image/svg+xml,%3Csvg%20xmlns='http://www.w3.org/2000/svg'%20viewBox='0%200%20512%20512'%3E%3Crect%20width='512'%20height='512'%20fill='%230a0a0a'/%3E%3Ctext%20x='256'%20y='340'%20font-size='280'%20text-anchor='middle'%20fill='%23C9A92C'%3E%F0%9F%92%AA%3C/text%3E%3C/svg%3E%22,%22sizes%22:%22512x512%22,%22type%22:%22image/svg+xml%22}]}">
<link rel="apple-touch-icon" href="data:image/svg+xml,<svg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 512 512'><rect width='512' height='512' rx='100' fill='%230a0a0a'/><text x='256' y='340' font-size='280' text-anchor='middle' fill='%23C9A92C'>💪</text></svg>">
<style>
*{margin:0;padding:0;box-sizing:border-box;-webkit-tap-highlight-color:transparent}
html,body{height:100%;background:#0a0a0a;color:#f0f0f0;font-family:-apple-system,'Helvetica Neue',sans-serif;overscroll-behavior:none}
input[type=number]{-webkit-appearance:none;-moz-appearance:textfield}
input[type=number]::-webkit-inner-spin-button,input[type=number]::-webkit-outer-spin-button{-webkit-appearance:none}
::-webkit-scrollbar{display:none}
button{-webkit-appearance:none;cursor:pointer;touch-action:manipulation}
textarea,input[type=text]{font-family:-apple-system,'Helvetica Neue',sans-serif}
#app{max-width:480px;margin:0 auto;min-height:100vh;padding-bottom:60px}
.hdr{background:#111;border-bottom:1px solid #1e1e1e;padding:16px 20px 12px;padding-top:max(env(safe-area-inset-top),16px);position:sticky;top:0;z-index:100}
.hdr-top{display:flex;justify-content:space-between;align-items:flex-start;margin-bottom:12px}
.brand{font-size:9px;letter-spacing:3px;color:#888;text-transform:uppercase;margin-bottom:2px}
.appname{font-size:20px;font-weight:800;color:#fff;letter-spacing:-.5px}
.appsub{font-size:11px;color:#444;margin-top:1px}
.wkbox{display:flex;align-items:center;gap:10px;background:#131313;border-radius:10px;padding:8px 14px;border:1px solid #1e1e1e}
.wkbtn{background:none;border:none;color:#444;font-size:22px;padding:0;line-height:1;width:24px}
.wknum{font-size:22px;font-weight:800;color:#C9A92C;line-height:1}
.wktxt{font-size:9px;color:#555;letter-spacing:2px;text-transform:uppercase}
.tabs{display:flex;gap:4px}
.tab{flex:1;padding:8px 0;border-radius:8px;border:none;font-size:9px;font-weight:700;letter-spacing:.3px;text-transform:uppercase;background:#131313;color:#555}
.tab.active{background:#C9A92C;color:#000}
.dtabs{display:flex;gap:6px;padding:12px 16px 0;overflow-x:auto}
.dtab{flex:0 0 auto;padding:8px 12px;border-radius:10px;border:2px solid #1e1e1e;background:#111;min-width:58px;text-align:center}
.dtab.active{border-color:#C9A92C;background:#1e1e1e}
.dtab .dd{font-size:12px;font-weight:800;color:#555}
.dtab.active .dd{color:#C9A92C}
.dtab .df{font-size:8px;color:#444;margin-top:2px;text-transform:uppercase}
.dtab.active .df{color:#aaa}
.dtab .dp{font-size:9px;margin-top:2px;color:#333}
.dtab.active .dp{color:#C9A92C}
.card{background:#131313;border:1px solid #1e1e1e;border-radius:12px;margin-bottom:10px;overflow:hidden}
.card.gb{border-color:#C9A92C55}
.card.prcard{border-color:#C9A92C;background:#C9A92C0a}
.ch{padding:10px 14px 8px;border-bottom:1px solid #1e1e1e;display:flex;justify-content:space-between;align-items:flex-start}
.cb{padding:10px 14px 12px}
.exn{font-size:12px;font-weight:700;color:#fff;line-height:1.35}
.exm{font-size:10px;color:#555;margin-top:2px}
.vbadge{font-size:10px;color:#C9A92C;font-weight:700;text-align:right;white-space:nowrap;line-height:1.4}
.pr-badge{display:inline-block;background:#C9A92C;color:#000;font-size:8px;font-weight:800;letter-spacing:1px;padding:2px 6px;border-radius:4px;margin-left:6px;vertical-align:middle}
.sg{display:grid;grid-template-columns:24px 1fr 1fr 50px;gap:6px;align-items:center;margin-bottom:6px}
.cl{font-size:9px;color:#444;text-transform:uppercase;letter-spacing:1px}
.sn{width:22px;height:22px;border-radius:5px;display:flex;align-items:center;justify-content:center;font-size:10px;font-weight:800;border:1px solid #252525;background:#1a1a1a;color:#444}
.sn.filled{background:#C9A92C22;border-color:#C9A92C;color:#C9A92C}
.si{background:#1a1a1a;border:1px solid #252525;border-radius:7px;padding:8px 10px;color:#fff;font-size:14px;font-weight:600;width:100%;outline:none;-webkit-appearance:none}
.pv{font-size:10px;color:#444;text-align:center}
.pv.up{color:#4ade80;font-weight:700}
/* Rest Timer */
.rtimer{position:fixed;bottom:28px;left:50%;transform:translateX(-50%);z-index:999;display:flex;flex-direction:column;align-items:center;gap:5px;pointer-events:none;opacity:0;transition:opacity .3s}
.rtimer.vis{opacity:1;pointer-events:all}
.tring{position:relative;width:76px;height:76px}
.tring svg{transform:rotate(-90deg)}
.tring circle{fill:none;stroke:#1e1e1e;stroke-width:5}
.tring .prog{stroke:#C9A92C;stroke-width:5;stroke-linecap:round;stroke-dasharray:207;stroke-dashoffset:0;transition:stroke-dashoffset .1s linear}
.tring.done .prog{stroke:#4ade80}
.tnum{position:absolute;top:50%;left:50%;transform:translate(-50%,-50%);font-size:20px;font-weight:800;color:#fff}
.tlbl{font-size:9px;color:#888;letter-spacing:2px;text-transform:uppercase}
.tskip{background:#1a1a1a;border:1px solid #2a2a2a;border-radius:20px;padding:4px 12px;font-size:11px;font-weight:700;color:#666}
/* Workout Timer */
.wtimer-bar{background:#131313;border:1px solid #1e1e1e;border-radius:10px;padding:10px 14px;margin:10px 16px;display:flex;align-items:center;gap:10px}
.wtimer-display{font-size:22px;font-weight:800;color:#C9A92C;font-variant-numeric:tabular-nums;letter-spacing:-1px}
.wtimer-label{font-size:10px;color:#555;text-transform:uppercase;letter-spacing:1px}
.wtimer-btn{padding:6px 14px;border-radius:8px;border:none;font-size:11px;font-weight:800;cursor:pointer}
.wtimer-btn.start{background:#C9A92C;color:#000}
.wtimer-btn.stop{background:#f87171;color:#000}
/* Meals */
.mc{border-radius:12px;padding:12px 14px;margin-bottom:10px;border:1px solid #1e1e1e;background:#131313;display:flex;align-items:flex-start;gap:10px}
.mc.ck{background:#C9A92C18;border-color:#C9A92C}
.mch{width:24px;height:24px;border-radius:6px;border:2px solid #444;background:transparent;display:flex;align-items:center;justify-content:center;font-size:13px;font-weight:800;color:#000;flex-shrink:0;margin-top:1px}
.mch.ck{background:#C9A92C;border-color:#C9A92C}
.mn{font-size:12px;font-weight:700;color:#ccc}
.mn.ck{color:#C9A92C}
.mi{font-size:10px;color:#555;margin-top:3px;line-height:1.5}
/* Supplements */
.suprow{display:flex;align-items:center;gap:10px;padding:8px 0;border-bottom:1px solid #1e1e1e}
.suprow:last-child{border-bottom:none}
.supcheck{width:22px;height:22px;border-radius:6px;border:2px solid #444;background:transparent;display:flex;align-items:center;justify-content:center;font-size:11px;font-weight:800;color:#000;flex-shrink:0;cursor:pointer}
.supcheck.ck{background:#C9A92C;border-color:#C9A92C}
.supname{font-size:12px;color:#ccc;flex:1}
.suptime{font-size:10px;color:#555}
.sl{font-size:10px;font-weight:700;color:#888;letter-spacing:2px;text-transform:uppercase;margin-bottom:10px}
.sgrid{display:grid;grid-template-columns:1fr 1fr 1fr;gap:8px;margin-bottom:14px}
.scard{background:#131313;border:1px solid #1e1e1e;border-radius:10px;padding:12px 8px;text-align:center}
.sv{font-size:20px;font-weight:800;color:#C9A92C}
.slbl{font-size:9px;color:#888;margin-top:3px;text-transform:uppercase;letter-spacing:1px;white-space:pre-line}
.bcwrap{overflow-x:auto;padding-bottom:4px}
.bc{display:flex;align-items:flex-end;gap:6px;height:90px;padding:0 4px}
.bcol{display:flex;flex-direction:column;align-items:center;gap:4px;flex:1;min-width:26px}
.bar{background:#C9A92C;border-radius:3px 3px 0 0;width:100%;min-height:4px}
.blbl{font-size:9px;color:#555}
.gr{margin-bottom:12px}
.gt{display:flex;justify-content:space-between;margin-bottom:4px}
.gn{font-size:11px;color:#ccc;flex:1;margin-right:8px}
.gp{font-size:12px;font-weight:800;white-space:nowrap}
.gtr{display:flex;align-items:center;gap:8px}
.gbg{flex:1;height:4px;background:#1e1e1e;border-radius:2px;overflow:hidden}
.gfill{height:100%;border-radius:2px}
.grng{font-size:10px;color:#888;white-space:nowrap}
.crow{display:flex;align-items:center;gap:10px;margin-bottom:8px}
.cday{width:32px;font-size:11px;font-weight:700;color:#888}
.cbg{flex:1;height:6px;background:#1e1e1e;border-radius:3px;overflow:hidden}
.cfill{height:100%;border-radius:3px}
.ccnt{font-size:11px;color:#888;width:36px;text-align:right}
.aic{background:#131313;border:1px solid #C9A92C55;border-radius:12px;padding:14px;margin-bottom:14px}
.aih{display:flex;justify-content:space-between;align-items:center;margin-bottom:8px}
.ail{font-size:11px;font-weight:700;color:#C9A92C;letter-spacing:2px;text-transform:uppercase}
.aib{background:#C9A92C;border:none;border-radius:6px;padding:6px 14px;font-size:10px;font-weight:800;color:#000;letter-spacing:1px}
.ait{font-size:12px;color:#444;line-height:1.7}
.ait.ld{color:#ccc}
textarea,input[type=text]{width:100%;background:#1a1a1a;border:1px solid #252525;border-radius:8px;padding:8px 10px;color:#ccc;font-size:12px;outline:none;box-sizing:border-box}
textarea{resize:none}
.cinrow{display:flex;gap:6px}
.cinbtn{flex:1;padding:10px 0;border-radius:8px;border:1px solid #252525;background:#1a1a1a;color:#555;font-size:11px;font-weight:700;text-align:center}
.cinbtn.sel{border-color:#C9A92C;background:#C9A92C22;color:#C9A92C}
.missedday{display:flex;align-items:center;justify-content:space-between;padding:8px 0;border-bottom:1px solid #1e1e1e;font-size:11px;color:#888}
.missedday:last-child{border-bottom:none}
.prrow{display:flex;justify-content:space-between;align-items:center;padding:8px 0;border-bottom:1px solid #1e1e1e}
.prrow:last-child{border-bottom:none}
.prname{font-size:11px;color:#ccc;flex:1;margin-right:8px}
.prval{font-size:13px;font-weight:800;color:#C9A92C;white-space:nowrap}
.prdate{font-size:9px;color:#555;margin-top:2px}
.watercups{display:flex;gap:4px;flex-wrap:wrap}
.wcup{width:30px;height:30px;border-radius:7px;border:1px solid #252525;background:#1a1a1a;font-size:14px;display:flex;align-items:center;justify-content:center;cursor:pointer}
.wcup.filled{background:#1e3a5f;border-color:#3b82f6}
.btng{width:100%;padding:14px;border-radius:10px;border:none;background:#C9A92C;color:#000;font-size:13px;font-weight:800;letter-spacing:1px;margin-bottom:12px}
.btno{width:100%;padding:14px;border-radius:10px;border:1px solid #C9A92C;background:transparent;color:#C9A92C;font-size:13px;font-weight:800;letter-spacing:1px}
.btng:disabled{opacity:.5}
.rpt-prev{background:#131313;border:1px solid #1e1e1e;border-radius:12px;padding:14px;margin-bottom:12px}
.rpt-txt{font-size:12px;color:#ccc;line-height:1.8;white-space:pre-wrap}
.pad{padding:0 16px}
.padt{padding:12px 16px 4px}
.secpad{padding:14px 16px 0}
.empty{font-size:12px;color:#444;text-align:center;padding:20px 0}
svg.lc{width:100%;overflow:visible}
.edb{width:100%;background:none;border:none;padding:12px 14px;display:flex;justify-content:space-between;align-items:center;text-align:left}
.edn{font-size:12px;font-weight:700;color:#fff}
.edm{font-size:10px;color:#888;margin-top:3px}
.edg{font-size:14px;font-weight:800;white-space:nowrap;margin-left:8px}
.edd{padding:0 14px 14px;border-top:1px solid #1e1e1e}
.dfl{font-size:16px;font-weight:800;color:#fff}
.dfs{font-size:12px;color:#C9A92C;font-weight:600;margin-top:1px}
.plan-ta{width:100%;background:#1a1a1a;border:1px solid #252525;border-radius:8px;padding:10px 12px;color:#ccc;font-size:12px;resize:none;outline:none;box-sizing:border-box;line-height:1.6;min-height:140px}
.ps{font-size:11px;padding:10px 12px;border-radius:8px;margin-top:8px;line-height:1.5}
.ps.ok{background:#0f2e1a;border:1px solid #16a34a;color:#4ade80}
.ps.err{background:#2e0f0f;border:1px solid #dc2626;color:#f87171}
.ps.loading{background:#1e1a0f;border:1px solid #C9A92C55;color:#C9A92C}
.pp{background:#1a1a1a;border-radius:8px;padding:10px 12px;margin-top:8px}
.ppd{font-size:10px;font-weight:700;color:#C9A92C;letter-spacing:1px;text-transform:uppercase;margin-bottom:4px;margin-top:10px}
.ppd:first-child{margin-top:0}
.ppe{font-size:11px;color:#888;padding:2px 0}
.ss-title{font-size:11px;font-weight:700;color:#C9A92C;letter-spacing:2px;text-transform:uppercase;margin-bottom:10px;padding-bottom:6px;border-bottom:1px solid #1e1e1e}
.ss{margin-bottom:20px}
/* Exercise notes */
.ex-note{background:#1a1a1a;border:1px solid #1e1e1e;border-radius:6px;padding:6px 10px;color:#888;font-size:11px;resize:none;outline:none;width:100%;box-sizing:border-box;margin-top:6px}
/* Step counter */
.step-row{display:flex;align-items:center;gap:10px;padding:8px 0;border-bottom:1px solid #1e1e1e}
.step-row:last-child{border-bottom:none}
.step-day{width:32px;font-size:11px;font-weight:700;color:#888}
.step-bar-bg{flex:1;height:8px;background:#1e1e1e;border-radius:4px;overflow:hidden}
.step-bar-fill{height:100%;border-radius:4px;background:#4ade80}
.step-bar-fill.warn{background:#C9A92C}
.step-bar-fill.low{background:#f87171}
.step-val{font-size:11px;font-weight:700;width:52px;text-align:right}
/* Whatsapp share */
.wa-btn{width:100%;padding:14px;border-radius:10px;border:none;background:#25D366;color:#fff;font-size:13px;font-weight:800;letter-spacing:1px;margin-bottom:10px;cursor:pointer}
</style>
</head>
<body>
<div id="app"></div>
<div class="rtimer" id="rtimer">
  <div class="tring" id="tring">
    <svg width="76" height="76" viewBox="0 0 76 76">
      <circle cx="38" cy="38" r="33"/>
      <circle class="prog" id="tcirc" cx="38" cy="38" r="33"/>
    </svg>
    <div class="tnum" id="tnum">60</div>
  </div>
  <div class="tlbl">Rest</div>
  <button class="tskip" onclick="skipTimer()">Skip ✕</button>
</div>

<script>
const PROG={
  Mon:{label:"Monday",focus:"Back / Biceps",exercises:[
    {name:"Lat Pull Down with Rope",sets:4,reps:"20,15,10,10"},
    {name:"Bent Over Barbell Row",sets:4,reps:"15,10,10,8"},
    {name:"T-Bar Row from Ground",sets:4,reps:"10,10,10,10"},
    {name:"Underhand Lat Pull Down",sets:4,reps:"10,10,10,10"},
    {name:"Seated Row with Triangle",sets:4,reps:"15,15,10,–"},
    {name:"EZ Bar Bicep Curl",sets:4,reps:"15,15,10,8"},
    {name:"DB Hammer Curl",sets:3,reps:"15,15,15"},
  ]},
  Tue:{label:"Tuesday",focus:"Chest / Triceps",exercises:[
    {name:"Pec Dec Fly",sets:4,reps:"20,15,15,10"},
    {name:"Incline Barbell Press",sets:4,reps:"15,10,10,8"},
    {name:"Incline DB Press",sets:4,reps:"15,15,10,8"},
    {name:"Flat Hammer Press",sets:3,reps:"20,15,10"},
    {name:"Cable Fly + Rope Tricep Press Down",sets:4,reps:"15,15,15,15"},
  ]},
  Wed:{label:"Wednesday",focus:"Legs",exercises:[
    {name:"Leg Extensions (hold 5s)",sets:4,reps:"15,15,15,15"},
    {name:"Leg Press",sets:4,reps:"20,20,20,20"},
    {name:"Smith / Barbell Squats",sets:4,reps:"15,15,10,8"},
    {name:"Hack Squat",sets:3,reps:"15,12,8"},
    {name:"Leg Curls (laying down)",sets:4,reps:"15,15,15,15"},
  ]},
  Thu:{label:"Thursday",focus:"Shoulders",exercises:[
    {name:"DB Shoulder Press",sets:5,reps:"20,15,15,10,8"},
    {name:"DB Side Laterals",sets:4,reps:"15,15,15,15"},
    {name:"DB Front Raises + Plate Raises",sets:4,reps:"10,10,10,10"},
    {name:"Shoulder Press on Smith Machine",sets:4,reps:"15,15,10,8"},
    {name:"Machine Side Lateral",sets:4,reps:"20,20,20,20"},
    {name:"EZ Curl Bar Upright Row",sets:4,reps:"15,15,15,15"},
    {name:"Pec Dec Rear Fly",sets:4,reps:"15,15,15,15"},
  ]},
  Fri:{label:"Friday",focus:"Biceps / Triceps",exercises:[
    {name:"Rope Tricep Press Down",sets:4,reps:"20,20,20,20"},
    {name:"EZ Curl Bar Cable Press Down",sets:4,reps:"10,10,10,10"},
    {name:"DB OH Tricep + Straight Bar Curls",sets:4,reps:"15,15,10,10"},
    {name:"Single Arm Press + Rope Bicep Curl",sets:3,reps:"15,15,15"},
    {name:"Skull Crushers + DB Hammer Curl",sets:4,reps:"15,15,15,15"},
    {name:"Preacher Curl (hold 5s)",sets:2,reps:"20,20"},
  ]},
};
const MEALS=[
  {name:"Meal 1 — Pre Workout A.M.",items:["Egg White (raw) — 160g","Whole Egg — 2","Sourdough Bread — 3 slices","Blueberry (raw) — 60g"]},
  {name:"Meal 2",items:["Rice Cakes — 1","Peanut Butter (smooth) — 16g"]},
  {name:"Meal 3",items:["Ground Beef 95/5 (cooked) — 170g","Sweet Potato (cooked) — 150g","Avocado (raw) — 30g","Asparagus (raw) — 60g"]},
  {name:"Meal 4 — Pre Workout",items:["Chicken Breast (cooked) — 170g","White Rice (cooked) — 180g","Banana (raw) — 100g"]},
  {name:"Meal 5 — Post Workout",items:["Chicken Breast (cooked) — 170g","White Rice (cooked) — 180g","Pineapple (raw) — 60g"]},
  {name:"Meal 6 — Before Bed",items:["Greek Yogurt (non-fat) — 170g","Pineapple (raw) — 60g","Whey Protein Powder — 15g"]},
];
const SUPPS=[
  {name:"Multivitamin",time:"Morning"},
  {name:"Fish Oil",time:"Morning"},
  {name:"Vitamin D3",time:"Morning"},
  {name:"Creatine",time:"Pre/Post Workout"},
  {name:"Whey Protein",time:"Post Workout"},
  {name:"Magnesium",time:"Before Bed"},
];
const DAYS=["Mon","Tue","Wed","Thu","Fri"];
const G="#C9A92C";
const WATER_GOAL=16;
const STEP_GOAL=7000;

const KEY="eli-training-v4";
function def(){return{week:3,logs:{},meals:{},bodyweight:{},checkins:{},water:{},missed:{},supps:{},steps:{},exnotes:{},wtimes:{}};}
function loadS(){try{const d=JSON.parse(localStorage.getItem(KEY));return d?{...def(),...d}:def();}catch{return def();}}
function saveS(s){try{localStorage.setItem(KEY,JSON.stringify(s));}catch{}}
let S=loadS();
const wk=w=>"w"+w;

// ── Workout Timer ─────────────────────────────────────────────────────────────
let wtInt=null,wtStart=null,wtElapsed=0,wtRunning=false;
function startWorkoutTimer(){
  if(wtRunning)return;
  wtRunning=true;wtStart=Date.now()-wtElapsed*1000;
  const W=wk(S.week);
  if(!S.wtimes[W])S.wtimes[W]={};
  S.wtimes[W][activeDay]={start:wtStart,elapsed:0};
  saveS(S);
  wtInt=setInterval(()=>{
    wtElapsed=Math.floor((Date.now()-wtStart)/1000);
    const el=document.getElementById("wt-display");
    if(el)el.textContent=fmtTime(wtElapsed);
  },1000);
  re();
}
function stopWorkoutTimer(){
  if(!wtRunning)return;
  clearInterval(wtInt);wtRunning=false;
  const W=wk(S.week);
  if(!S.wtimes[W])S.wtimes[W]={};
  S.wtimes[W][activeDay]={elapsed:wtElapsed};
  saveS(S);re();
}
function fmtTime(sec){
  const h=Math.floor(sec/3600),m=Math.floor((sec%3600)/60),s=sec%60;
  if(h>0)return`${h}:${String(m).padStart(2,"0")}:${String(s).padStart(2,"0")}`;
  return`${String(m).padStart(2,"0")}:${String(s).padStart(2,"0")}`;
}

// ── Rest Timer ────────────────────────────────────────────────────────────────
const TDUR=60,CIRC=2*Math.PI*33;
let tInt=null,tRem=0;
function startTimer(){
  clearInterval(tInt);tRem=TDUR;
  const el=document.getElementById("rtimer"),num=document.getElementById("tnum"),c=document.getElementById("tcirc"),ring=document.getElementById("tring");
  if(!el)return;
  el.classList.add("vis");ring.classList.remove("done");
  c.style.strokeDasharray=CIRC;c.style.strokeDashoffset=0;
  if(navigator.vibrate)navigator.vibrate(40);
  tInt=setInterval(()=>{
    tRem--;
    if(c)c.style.strokeDashoffset=CIRC*(1-tRem/TDUR);
    if(num)num.textContent=tRem>0?tRem:"✓";
    if(tRem<=0){clearInterval(tInt);ring.classList.add("done");if(navigator.vibrate)navigator.vibrate([80,40,80]);setTimeout(()=>{if(el)el.classList.remove("vis");},1800);}
  },1000);
}
function skipTimer(){clearInterval(tInt);const el=document.getElementById("rtimer");if(el)el.classList.remove("vis");}

// ── Helpers ───────────────────────────────────────────────────────────────────
function bestSet(el){if(!el)return null;let b=0;Object.values(el).forEach(s=>{if(parseFloat(s.w)>b)b=parseFloat(s.w);});return b||null;}
function totalVol(el){if(!el)return 0;let v=0;Object.values(el).forEach(s=>{v+=(parseFloat(s.w)||0)*(parseFloat(s.r)||0);});return Math.round(v);}
function exTrend(d,ei){
  return Object.keys(S.logs).sort((a,b)=>+a.slice(1)-+b.slice(1))
    .map(w=>({week:+w.slice(1),weight:bestSet(S.logs[w]?.[d]?.[ei]),vol:totalVol(S.logs[w]?.[d]?.[ei])}))
    .filter(p=>p.weight);
}
function weeklyVols(){
  return Object.keys(S.logs).sort((a,b)=>+a.slice(1)-+b.slice(1))
    .map(w=>{let t=0;DAYS.forEach(d=>Object.values(S.logs[w]?.[d]||{}).forEach(e=>{t+=totalVol(e);}));return{week:+w.slice(1),vol:t};})
    .filter(p=>p.vol>0);
}
function allGains(){
  const g=[];
  DAYS.forEach(d=>PROG[d].exercises.forEach((ex,ei)=>{
    const t=exTrend(d,ei);
    if(t.length>=2){const f=t[0].weight,l=t[t.length-1].weight;g.push({name:ex.name,first:f,last:l,pct:Math.round(((l-f)/f)*100),day:d,ei});}
  }));
  return g.sort((a,b)=>b.pct-a.pct);
}
function getPRs(){
  const prs=[];
  DAYS.forEach(d=>PROG[d].exercises.forEach((ex,ei)=>{
    let best=0,bestWk=null;
    Object.keys(S.logs).forEach(w=>{const b=bestSet(S.logs[w]?.[d]?.[ei]);if(b&&b>best){best=b;bestWk=+w.slice(1);}});
    if(best>0)prs.push({name:ex.name,weight:best,week:bestWk,day:d});
  }));
  return prs.sort((a,b)=>b.weight-a.weight);
}
function isPR(d,ei,weight){
  if(!weight)return false;
  let best=0;
  Object.keys(S.logs).forEach(w=>{if(w===wk(S.week))return;const b=bestSet(S.logs[w]?.[d]?.[ei]);if(b&&b>best)best=b;});
  return parseFloat(weight)>best&&best>0;
}

// ── AI ────────────────────────────────────────────────────────────────────────
let insightTxt="",reportTxt="";
async function callAI(prompt,pdfBase64=null){
  try{
    const content=pdfBase64?[{type:"document",source:{type:"base64",media_type:"application/pdf",data:pdfBase64}},{type:"text",text:prompt}]:[{type:"text",text:prompt}];
    const r=await fetch("https://api.anthropic.com/v1/messages",{method:"POST",headers:{"Content-Type":"application/json"},body:JSON.stringify({model:"claude-sonnet-4-6",max_tokens:2000,messages:[{role:"user",content}]})});
    const d=await r.json();return d.content?.[0]?.text||"No response.";
  }catch{return"AI unavailable — check connection.";}
}
async function doInsight(){
  const vols=weeklyVols(),gains=allGains();
  const bwE=Object.entries(S.bodyweight||{}).sort((a,b)=>+a[0].slice(1)-+b[0].slice(1));
  const latestBW=bwE.length?bwE[bwE.length-1][1]:null;
  if(!vols.length){insightTxt="Log workouts first and I'll analyze your progress.";re();return;}
  insightTxt="...";re();
  insightTxt=await callAI(`Physique coach for Eli Galvan (6'2", starting 340lbs${latestBW?`, current ${latestBW}lbs`:""}, 4am training, Week ${S.week}, Sin Pausa). Weeks logged:${vols.length}. Volumes:${JSON.stringify(vols)}. Top gains:${JSON.stringify(gains.slice(0,5))}. Write 3-4 sentences direct coaching with specific numbers. Flag plateaus. One tip for next week. No bullets.`);
  re();
}
async function doReport(){
  const gains=allGains(),w=wk(S.week);
  let workout="";
  DAYS.forEach(d=>{
    const dl=S.logs[w]?.[d];if(!dl)return;
    workout+=`\n${PROG[d].label}:\n`;
    const wtime=S.wtimes[w]?.[d];
    if(wtime?.elapsed)workout+=`  Duration: ${fmtTime(wtime.elapsed)}\n`;
    PROG[d].exercises.forEach((ex,ei)=>{
      const el=dl[ei];if(!el)return;
      workout+=`  ${ex.name}: ${Object.values(el).map(s=>`${s.w||"?"}lbs x${s.r||"?"}`).join(", ")} Vol:${totalVol(el)}lbs`;
      const note=S.exnotes[w]?.[d]?.[ei];
      if(note)workout+=` [Note: ${note}]`;
      workout+="\n";
    });
  });
  const md=S.meals[w]||{};
  const mealStr=DAYS.map(d=>{const dm=md[d]||{};return`${d}:${MEALS.filter((_,i)=>dm[i]).length}/${MEALS.length}`;}).join(" | ");
  const suppStr=DAYS.map(d=>{const sd=S.supps[w]?.[d]||{};return`${d}:${SUPPS.filter((_,i)=>sd[i]).length}/${SUPPS.length}supps`;}).join(" ");
  const ci=S.checkins[w]||{};
  const ciStr=DAYS.map(d=>`${d}:E${ci[d]?.energy||"–"}/5,S${ci[d]?.soreness||"–"}/5,${ci[d]?.sleep||"–"}hrs`).join(" ");
  const stepStr=DAYS.map(d=>`${d}:${S.steps[w]?.[d]||0}`).join(" ");
  const bw=S.bodyweight[w]||null;
  reportTxt="Generating...";re();
  reportTxt=await callAI(`Write a weekly training report for Eli Galvan to send his coach at Sin Pausa. Eli: 6'2", Week ${S.week}${bw?`, bodyweight: ${bw}lbs`:""}.

WORKOUT DATA:\n${workout}
STRENGTH GAINS (all time):\n${gains.slice(0,8).map(g=>`${g.name}: ${g.first}→${g.last}lbs (${g.pct>0?"+":""}${g.pct}%)`).join("\n")}
MEAL COMPLIANCE:\n${mealStr}
SUPPLEMENT COMPLIANCE:\n${suppStr}
RECOVERY:\n${ciStr}
DAILY STEPS:\n${stepStr}
Notes:${md.notes||"None"}

Sections: 1.WEEK ${S.week} SUMMARY 2.TRAINING HIGHLIGHTS (PRs, duration) 3.AREAS TO IMPROVE 4.NUTRITION & SUPPLEMENT COMPLIANCE 5.RECOVERY & STEPS 6.GOALS FOR WEEK ${S.week+1}. Concise, factual, coach-ready.`);
  re();
}
function exportPDF(){
  const gains=allGains(),w=wk(S.week),bw=S.bodyweight[w]||null;
  const html=`<!DOCTYPE html><html><head><meta charset="utf-8"><style>*{margin:0;padding:0;box-sizing:border-box}body{font-family:'Helvetica Neue',Arial,sans-serif;padding:40px;max-width:780px;margin:0 auto;color:#111}.hdr{border-bottom:3px solid #C9A92C;padding-bottom:16px;margin-bottom:20px;display:flex;justify-content:space-between;align-items:flex-end}.brand{font-size:10px;letter-spacing:3px;text-transform:uppercase;color:#888;margin-bottom:4px}.name{font-size:26px;font-weight:800}.sub{font-size:12px;color:#666;margin-top:2px}.badge{background:#C9A92C;color:#000;font-weight:800;padding:8px 16px;border-radius:8px;text-align:center}.bl{font-size:9px;letter-spacing:2px;display:block}.bn{font-size:22px;line-height:1.1}.sec{margin-bottom:22px}.st{font-size:9px;letter-spacing:3px;text-transform:uppercase;color:#C9A92C;font-weight:700;margin-bottom:10px;padding-bottom:5px;border-bottom:1px solid #f0f0f0}.rpt{font-size:12px;line-height:1.8;color:#333;white-space:pre-wrap}.gg{display:grid;grid-template-columns:1fr 1fr;gap:8px}.gi{background:#f9f9f9;border-radius:7px;padding:9px;display:flex;justify-content:space-between;align-items:center}.gn{font-size:10px;color:#555}.gv{font-size:12px;font-weight:800;color:#16a34a;text-align:right}.gv.dn{color:#dc2626}table{width:100%;border-collapse:collapse;font-size:10px}th{background:#f5f5f5;padding:5px 8px;text-align:left;font-size:8px;letter-spacing:1px;text-transform:uppercase;color:#888}td{padding:5px 8px;border-bottom:1px solid #f0f0f0;color:#333}.dh{background:#111;color:#C9A92C;font-size:9px;font-weight:800;letter-spacing:2px;text-transform:uppercase;padding:5px 8px}.ft{margin-top:30px;padding-top:12px;border-top:1px solid #eee;display:flex;justify-content:space-between;font-size:9px;color:#bbb}@media print{body{padding:20px}}</style></head><body>
<div class="hdr"><div><div class="brand">Sin Pausa · Structured Physique Building</div><div class="name">Eli Galvan</div><div class="sub">Weekly Training Report · 6'2"${bw?` · ${bw} lbs`:""}</div></div><div class="badge"><span class="bl">WEEK</span><span class="bn">${S.week}</span></div></div>
<div class="sec"><div class="st">Coach Report</div><div class="rpt">${reportTxt.replace(/</g,"&lt;").replace(/>/g,"&gt;")}</div></div>
<div class="sec"><div class="st">Strength Gains (All Time)</div><div class="gg">${gains.slice(0,8).map(g=>`<div class="gi"><div class="gn">${g.name}</div><div class="gv ${g.pct<0?"dn":""}">${g.pct>0?"+":""}${g.pct}%<br><span style="font-size:9px;font-weight:400;color:#888">${g.first}→${g.last}lbs</span></div></div>`).join("")}${!gains.length?'<div style="color:#999;font-size:11px;grid-column:span 2">No multi-week data yet</div>':""}</div></div>
<div class="sec"><div class="st">Workouts — Week ${S.week}</div><table>${DAYS.map(d=>{const dl=S.logs[w]?.[d];const wt=S.wtimes[w]?.[d];if(!dl)return`<tr><td class="dh" colspan="3">${PROG[d].label} — ${PROG[d].focus}</td></tr><tr><td colspan="3" style="color:#bbb;font-style:italic;padding:6px 8px">Not logged</td></tr>`;const rows=PROG[d].exercises.map((ex,ei)=>{const el=dl[ei];if(!el)return"";const note=S.exnotes[w]?.[d]?.[ei];return`<tr><td>${ex.name}${note?` <span style="color:#888;font-size:9px">[${note}]</span>`:""}</td><td>${Object.values(el).map((s,i)=>`S${i+1}:${s.w||"?"}×${s.r||"?"}`).join(" · ")}</td><td style="color:#C9A92C;font-weight:700">${totalVol(el).toLocaleString()}lbs</td></tr>`;}).join("");return`<tr><td class="dh" colspan="3">${PROG[d].label} — ${PROG[d].focus}${wt?.elapsed?` · ${fmtTime(wt.elapsed)}`:""}</td></tr><tr><th>Exercise</th><th>Sets</th><th>Volume</th></tr>${rows}`;}).join("")}</table></div>
<div class="ft"><span>Eli Galvan · Sin Pausa</span><span>Week ${S.week} Report · ${new Date().toLocaleDateString()}</span></div></body></html>`;
  const blob=new Blob([html],{type:"text/html"});
  const url=URL.createObjectURL(blob);
  const a=document.createElement("a");a.href=url;a.download=`EliGalvan_Week${S.week}_Report.html`;a.click();
  setTimeout(()=>URL.revokeObjectURL(url),1000);
}
function shareWhatsApp(){
  if(!reportTxt||reportTxt==="Generating...")return;
  const text=encodeURIComponent(`*Eli Galvan — Week ${S.week} Training Report*\n\n${reportTxt}`);
  window.open(`https://wa.me/?text=${text}`,"_blank");
}

// ── Charts ────────────────────────────────────────────────────────────────────
function barChart(data,vk){
  if(!data.length)return`<div class="empty">Log 2+ weeks to see trend</div>`;
  const max=Math.max(...data.map(d=>d[vk]),1);
  return`<div class="bcwrap"><div class="bc">${data.map(d=>{const h=Math.max(4,Math.round((d[vk]/max)*80));return`<div class="bcol"><div class="bar" style="height:${h}px"></div><div class="blbl">Wk${d.week}</div></div>`;}).join("")}</div></div>`;
}
function lineChart(data,key="weight"){
  if(data.length<2)return`<div class="empty">Log one more week to see trend</div>`;
  const W=300,H=70,pad=8,vals=data.map(d=>d[key]),mn=Math.min(...vals),mx=Math.max(...vals),rng=mx-mn||1;
  const pts=data.map((d,i)=>({x:pad+i*(W-pad*2)/(data.length-1),y:H-pad-(d[key]-mn)/rng*(H-pad*2),v:d[key],wk:d.week}));
  return`<svg viewBox="0 0 ${W} ${H}" class="lc" style="height:80px"><polyline points="${pts.map(p=>`${p.x},${p.y}`).join(" ")}" fill="none" stroke="${G}" stroke-width="2" stroke-linejoin="round"/>${pts.map(p=>`<circle cx="${p.x}" cy="${p.y}" r="3" fill="${G}"/><text x="${p.x}" y="${H}" text-anchor="middle" font-size="8" fill="#555">Wk${p.wk}</text>`).join("")}</svg>`;
}

// ── PDF Upload ────────────────────────────────────────────────────────────────
async function readPDFB64(file){return new Promise((res,rej)=>{const r=new FileReader();r.onload=e=>res(e.target.result.split(",")[1]);r.onerror=rej;r.readAsDataURL(file);});}
let parseStatus="",parsedPlan=null,parsedMeals=null,workoutPasteText="",mealPasteText="";

async function handlePDFUpload(input,type){
  const file=input.files[0];if(!file)return;
  parseStatus=type==="workout"?"loading-workout":"loading-meal";parsedPlan=null;parsedMeals=null;re();
  try{
    const b64=await readPDFB64(file);
    const prompt=type==="workout"?
      `Extract the complete workout plan from this PDF. Return ONLY valid JSON:\n{"Mon":{"label":"Monday","focus":"Back / Biceps","exercises":[{"name":"Exercise Name","sets":4,"reps":"20,15,10,10"}]},"Tue":{...},"Wed":{...},"Thu":{...},"Fri":{...}}\nRules: Mon/Tue/Wed/Thu/Fri keys. reps comma-separated per set. Supersets join names with " superset ".`:
      `Extract the complete meal plan from this PDF. Return ONLY valid JSON array:\n[{"name":"Meal 1 — Pre Workout A.M.","items":["Egg White (raw) — 160g","Whole Egg — 2"]},...]\nPreserve meal timing labels and quantities exactly.`;
    const result=await callAI(prompt,b64);
    const parsed=JSON.parse(result.replace(/```json|```/g,"").trim());
    if(type==="workout"){
      if(!["Mon","Tue","Wed","Thu","Fri"].some(d=>parsed[d]?.exercises?.length>0))throw new Error();
      parsedPlan=parsed;parseStatus="ok-workout";
    }else{
      if(!Array.isArray(parsed)||!parsed.length)throw new Error();
      parsedMeals=parsed;parseStatus="ok-meal";
    }
  }catch{parseStatus=type==="workout"?"err-workout":"err-meal";}
  re();
}
async function parseWorkoutPlan(text){
  if(!text?.trim()){alert("Please paste your workout plan first.");return;}
  parseStatus="loading-workout";parsedPlan=null;re();
  try{
    const result=await callAI(`Parse this workout plan into JSON. Return ONLY valid JSON:\n{"Mon":{"label":"Monday","focus":"Back / Biceps","exercises":[{"name":"Exercise Name","sets":4,"reps":"20,15,10,10"}]},"Tue":{...},"Wed":{...},"Thu":{...},"Fri":{...}}\nRules: Mon/Tue/Wed/Thu/Fri keys. reps comma-separated string. sets integer. Supersets join with " superset ".\n\nPlan:\n${text}`);
    const parsed=JSON.parse(result.replace(/```json|```/g,"").trim());
    if(!["Mon","Tue","Wed","Thu","Fri"].some(d=>parsed[d]?.exercises?.length>0))throw new Error();
    parsedPlan=parsed;parseStatus="ok-workout";
  }catch{parseStatus="err-workout";parsedPlan=null;}
  re();
}
async function parseMealPlan(text){
  if(!text?.trim()){alert("Please paste your meal plan first.");return;}
  parseStatus="loading-meal";parsedMeals=null;re();
  try{
    const result=await callAI(`Parse this meal plan into JSON array. Return ONLY valid JSON:\n[{"name":"Meal 1 — Pre Workout A.M.","items":["Egg White (raw) — 160g"]},{"name":"Meal 2","items":["Rice Cakes — 1"]}]\nPreserve meal timing labels and quantities.\n\nMeal plan:\n${text}`);
    const parsed=JSON.parse(result.replace(/```json|```/g,"").trim());
    if(!Array.isArray(parsed)||!parsed.length)throw new Error();
    parsedMeals=parsed;parseStatus="ok-meal";
  }catch{parseStatus="err-meal";parsedMeals=null;}
  re();
}
function applyWorkoutPlan(){
  if(!parsedPlan)return;
  Object.assign(PROG,parsedPlan);S.customProgram=parsedPlan;saveS(S);
  parsedPlan=null;parseStatus="";workoutPasteText="";
  alert("✅ Workout plan updated! All logged data preserved.");re();
}
function applyMealPlan(){
  if(!parsedMeals)return;
  S.customMeals=parsedMeals;saveS(S);
  MEALS.length=0;parsedMeals.forEach(m=>MEALS.push(m));
  parsedMeals=null;parseStatus="";mealPasteText="";
  alert("✅ Meal plan updated!");re();
}
(function loadCustomPlans(){
  if(S.customProgram)Object.assign(PROG,S.customProgram);
  if(S.customMeals){MEALS.length=0;S.customMeals.forEach(m=>MEALS.push(m));}
})();

// ── State ─────────────────────────────────────────────────────────────────────
let activeTab="log",activeDay="Mon",aView="overview",selEx=null;
function re(){document.getElementById("app").innerHTML="";render();}

// ── Render ────────────────────────────────────────────────────────────────────
function render(){
  const app=document.getElementById("app");
  const W=wk(S.week),PW=wk(S.week-1);
  const dayLog=S.logs[W]?.[activeDay]||{};
  const prevLog=S.logs[PW]?.[activeDay]||{};
  const mealData=S.meals[W]||{};
  const ci=S.checkins[W]?.[activeDay]||{};
  const vols=weeklyVols(),gains=allGains(),day=PROG[activeDay];
  const wtime=S.wtimes[W]?.[activeDay];

  let html=`<div class="hdr">
    <div class="hdr-top">
      <div style="flex:1;text-align:center">
        <div style="font-size:26px;font-weight:900;color:#C9A92C;letter-spacing:-0.5px;line-height:1.1">SIN PAUSA</div>
        <div style="font-size:11px;font-weight:700;color:#fff;letter-spacing:2px;text-transform:uppercase;margin-top:2px">Training App</div>
        <div style="font-size:10px;color:#C9A92C;font-style:italic;margin-top:4px">"Mientras ellos duermen, tú te forjas."</div>
        <div style="font-size:9px;color:#555;margin-top:2px">"While they sleep, you are being forged."</div>
      </div>
      <div class="wkbox">
        <button class="wkbtn" onclick="chWeek(-1)">‹</button>
        <div style="text-align:center"><div class="wktxt">Week</div><div class="wknum">${S.week}</div></div>
        <button class="wkbtn" onclick="chWeek(1)">›</button>
      </div>
    </div>
    <div class="tabs">
      ${[["log","📝 Log"],["meals","🍗 Meals"],["body","💪 Body"],["analytics","📊 Stats"],["report","📤 Report"],["settings","⚙️"]].map(([v,l])=>`<button class="tab${activeTab===v?" active":""}" onclick="setTab('${v}')">${l}</button>`).join("")}
    </div>
  </div>`;

  // ── LOG ──
  if(activeTab==="log"){
    html+=`<div class="dtabs">`;
    DAYS.forEach(d=>{
      const exs=PROG[d].exercises,dl=S.logs[W]?.[d]||{};
      const done=exs.filter((_,ei)=>Object.keys(dl[ei]||{}).some(si=>dl[ei][si]?.w)).length;
      html+=`<button class="dtab${d===activeDay?" active":""}" onclick="setDay('${d}')">
        <div class="dd">${d}</div><div class="df">${PROG[d].focus.split(" / ")[0]}</div>
        <div class="dp">${done===exs.length?"✓":`${done}/${exs.length}`}</div>
      </button>`;
    });
    html+=`</div>`;

    // Workout timer bar
    const savedElapsed=wtime?.elapsed||0;
    const displayTime=wtRunning?fmtTime(wtElapsed):(savedElapsed?fmtTime(savedElapsed):"00:00");
    html+=`<div class="wtimer-bar">
      <div style="flex:1">
        <div class="wtimer-label">Workout Duration</div>
        <div class="wtimer-display" id="wt-display">${displayTime}</div>
      </div>
      ${!wtRunning?`<button class="wtimer-btn start" onclick="startWorkoutTimer()">▶ Start</button>`:`<button class="wtimer-btn stop" onclick="stopWorkoutTimer()">■ Stop</button>`}
    </div>`;

    html+=`<div class="padt"><div class="dfl">${day.label}</div><div class="dfs">${day.focus}</div></div>
    <div class="pad" style="margin-top:10px">
    <div class="card" style="padding:12px 14px;margin-bottom:10px">
      <div class="sl" style="margin-bottom:8px">Today's Check-In</div>
      <div style="display:grid;grid-template-columns:1fr 1fr 1fr;gap:10px">
        <div><div style="font-size:9px;color:#555;text-transform:uppercase;letter-spacing:1px;margin-bottom:5px">Energy 1–5</div>
          <div class="cinrow">${[1,2,3,4,5].map(n=>`<button class="cinbtn${ci.energy===n?" sel":""}" onclick="setCheckin('energy',${n})">${n}</button>`).join("")}</div>
        </div>
        <div><div style="font-size:9px;color:#555;text-transform:uppercase;letter-spacing:1px;margin-bottom:5px">Soreness 1–5</div>
          <div class="cinrow">${[1,2,3,4,5].map(n=>`<button class="cinbtn${ci.soreness===n?" sel":""}" onclick="setCheckin('soreness',${n})">${n}</button>`).join("")}</div>
        </div>
        <div><div style="font-size:9px;color:#555;text-transform:uppercase;letter-spacing:1px;margin-bottom:5px">Sleep hrs</div>
          <div class="cinrow">${[5,6,7,8].map(n=>`<button class="cinbtn${ci.sleep===n?" sel":""}" onclick="setCheckin('sleep',${n})">${n}</button>`).join("")}</div>
        </div>
      </div>
    </div>`;

    day.exercises.forEach((ex,ei)=>{
      const vol=totalVol(dayLog[ei]),reps=ex.reps.split(",");
      const curBest=bestSet(dayLog[ei]);
      const isNewPR=curBest&&isPR(activeDay,ei,curBest);
      const note=S.exnotes[W]?.[activeDay]?.[ei]||"";
      html+=`<div class="card${isNewPR?" prcard":""}"><div class="ch">
        <div style="flex:1;margin-right:8px">
          <div class="exn">${ex.name}${isNewPR?`<span class="pr-badge">🏆 PR</span>`:""}</div>
          <div class="exm">${ex.sets} sets · ${ex.reps}</div>
        </div>
        ${vol>0?`<div class="vbadge">${vol.toLocaleString()}<br><span style="color:#555;font-weight:400">lbs vol</span></div>`:""}
      </div><div class="cb">
        <div class="sg" style="margin-bottom:6px"><div></div><div class="cl">Weight</div><div class="cl">Reps</div><div class="cl">Prev</div></div>`;
      for(let si=0;si<ex.sets;si++){
        const e=dayLog[ei]?.[si]||{},p=prevLog[ei]?.[si]||{};
        const isUp=e.w&&p.w&&parseFloat(e.w)>parseFloat(p.w);
        html+=`<div class="sg">
          <div class="sn${e.w?" filled":""}">${si+1}</div>
          <input class="si" type="number" inputmode="decimal" placeholder="lbs" value="${e.w||""}" onchange="setSet('${activeDay}',${ei},${si},'w',this.value)">
          <input class="si" type="number" inputmode="decimal" placeholder="${reps[si]||"–"}" value="${e.r||""}" onchange="setSet('${activeDay}',${ei},${si},'r',this.value)">
          <div class="pv${isUp?" up":""}">${p.w||"–"}${isUp?"↑":""}</div>
        </div>`;
      }
      html+=`<textarea class="ex-note" rows="1" placeholder="Notes for this exercise..." onchange="setExNote('${activeDay}',${ei},this.value)">${note}</textarea>`;
      html+=`</div></div>`;
    });

    const isMissed=S.missed[W]?.[activeDay];
    html+=`<div class="card" style="padding:12px 14px">
      <div style="display:flex;justify-content:space-between;align-items:center">
        <div style="font-size:12px;color:#888">Mark day as missed?</div>
        <button onclick="toggleMissed('${activeDay}')" style="padding:6px 14px;border-radius:8px;border:1px solid ${isMissed?"#f87171":"#252525"};background:${isMissed?"#f8717122":"#1a1a1a"};color:${isMissed?"#f87171":"#555"};font-size:11px;font-weight:700">${isMissed?"✓ Missed":"Mark Missed"}</button>
      </div>
      ${isMissed?`<div style="margin-top:8px"><input type="text" placeholder="Reason (optional)..." value="${S.missed[W][activeDay].reason||""}" onchange="setMissedReason('${activeDay}',this.value)" style="font-size:11px;padding:6px 10px"></div>`:""}
    </div></div>`;
  }

  // ── MEALS ──
  if(activeTab==="meals"){
    const water=S.water[W]?.[activeDay]||0;
    const suppData=S.supps[W]?.[activeDay]||{};
    html+=`<div class="dtabs">`;
    DAYS.forEach(d=>{
      const dm=mealData[d]||{},checked=MEALS.filter((_,i)=>dm[i]).length;
      html+=`<button class="dtab${d===activeDay?" active":""}" onclick="setDay('${d}')">
        <div class="dd">${d}</div>
        <div class="dp" style="color:${checked===MEALS.length?"#4ade80":checked>0?G:"#333"}">${checked}/${MEALS.length}</div>
      </button>`;
    });
    html+=`</div><div class="secpad">
      <div style="font-size:13px;font-weight:700;color:#fff;margin-bottom:3px">${day.label} — Nutrition</div>
      <div style="font-size:11px;color:#888;margin-bottom:12px">Tap each meal and supplement as you complete them</div>`;

    MEALS.forEach((meal,mi)=>{
      const checked=!!(mealData[activeDay]?.[mi]);
      html+=`<div class="mc${checked?" ck":""}" onclick="toggleMeal('${activeDay}',${mi})">
        <div class="mch${checked?" ck":""}">${checked?"✓":""}</div>
        <div><div class="mn${checked?" ck":""}">${meal.name}</div><div class="mi">${meal.items.join(" · ")}</div></div>
      </div>`;
    });

    // Supplements
    html+=`<div class="card" style="padding:12px 14px;margin-bottom:10px">
      <div class="sl" style="margin-bottom:4px">💊 Supplements</div>
      ${SUPPS.map((sup,si)=>{
        const checked=!!(suppData[si]);
        return`<div class="suprow" onclick="toggleSupp('${activeDay}',${si})" style="cursor:pointer">
          <div class="supcheck${checked?" ck":""}">${checked?"✓":""}</div>
          <div class="supname">${sup.name}</div>
          <div class="suptime">${sup.time}</div>
        </div>`;
      }).join("")}
    </div>`;

    // Water
    html+=`<div class="card" style="padding:12px 14px;margin-bottom:10px">
      <div class="sl" style="margin-bottom:8px">💧 Water — ${water}/${WATER_GOAL} cups · ${Math.round(water*8)} oz</div>
      <div class="watercups">${Array.from({length:WATER_GOAL}).map((_,i)=>`<button class="wcup${i<water?" filled":""}" onclick="setWater('${activeDay}',${i<water?i:i+1})">${i<water?"💧":"○"}</button>`).join("")}</div>
      <div style="font-size:10px;color:#555;margin-top:8px">Goal: 1 gallon · Tap to fill</div>
    </div>
    <div class="card" style="padding:12px 14px">
      <div class="sl" style="margin-bottom:8px">Notes / Substitutions</div>
      <textarea rows="3" placeholder="Any swaps, skipped meals, or notes..." onchange="setNote(this.value)">${mealData.notes||""}</textarea>
    </div></div>`;
  }

  // ── BODY ──
  if(activeTab==="body"){
    const bwEntries=Object.entries(S.bodyweight||{}).sort((a,b)=>+a[0].slice(1)-+b[0].slice(1));
    const latestBW=bwEntries.length?bwEntries[bwEntries.length-1][1]:null;
    const prs=getPRs();
    const missedEntries=[];
    Object.entries(S.missed||{}).forEach(([w,days])=>Object.entries(days).forEach(([d,v])=>{if(v)missedEntries.push({week:+w.slice(1),day:d,reason:v.reason||""});}));

    html+=`<div class="secpad">
      <div class="card" style="padding:14px;margin-bottom:14px">
        <div class="sl">⚖️ Body Weight — Week ${S.week}</div>
        <div style="display:flex;align-items:center;gap:10px;margin-bottom:14px">
          <input type="number" inputmode="decimal" placeholder="lbs" value="${S.bodyweight[W]||""}" onchange="setBW(this.value)"
            style="flex:1;background:#1a1a1a;border:1px solid #252525;border-radius:8px;padding:10px 12px;color:#fff;font-size:18px;font-weight:800;outline:none;-webkit-appearance:none">
          <div style="font-size:11px;color:#555">this week</div>
        </div>
        ${bwEntries.length>=2?`
          <div style="margin-bottom:10px">${lineChart(bwEntries.map(([w,v])=>({week:+w.slice(1),weight:v})))}</div>
          <div style="display:grid;grid-template-columns:1fr 1fr 1fr;gap:8px">
            <div style="text-align:center;background:#1a1a1a;border-radius:8px;padding:8px"><div style="font-size:16px;font-weight:800;color:#C9A92C">${bwEntries[0][1]}</div><div style="font-size:9px;color:#555;text-transform:uppercase">Start</div></div>
            <div style="text-align:center;background:#1a1a1a;border-radius:8px;padding:8px"><div style="font-size:16px;font-weight:800;color:#fff">${latestBW}</div><div style="font-size:9px;color:#555;text-transform:uppercase">Current</div></div>
            <div style="text-align:center;background:#1a1a1a;border-radius:8px;padding:8px"><div style="font-size:16px;font-weight:800;color:${latestBW-bwEntries[0][1]<=0?"#4ade80":"#f87171"}">${latestBW-bwEntries[0][1]>0?"+":""}${(latestBW-bwEntries[0][1]).toFixed(1)}</div><div style="font-size:9px;color:#555;text-transform:uppercase">Change</div></div>
          </div>`:`<div class="empty" style="padding:8px 0">Log weight each week to track trend</div>`}
      </div>

      <!-- Step Counter -->
      <div class="card" style="padding:14px;margin-bottom:14px">
        <div class="sl">🚶 Daily Steps — Goal: ${STEP_GOAL.toLocaleString()}</div>
        ${DAYS.map(d=>{
          const steps=S.steps[W]?.[d]||0;
          const pct=Math.min(100,Math.round(steps/STEP_GOAL*100));
          const color=pct>=100?"#4ade80":pct>=70?G:"#f87171";
          return`<div class="step-row">
            <div class="step-day">${d}</div>
            <input type="number" inputmode="numeric" placeholder="steps" value="${steps||""}" onchange="setSteps('${d}',this.value)"
              style="width:80px;background:#1a1a1a;border:1px solid #252525;border-radius:6px;padding:5px 8px;color:#fff;font-size:12px;font-weight:600;outline:none;-webkit-appearance:none">
            <div class="step-bar-bg" style="flex:1"><div class="step-bar-fill ${pct<70?"low":pct<100?"warn":""}" style="width:${pct}%"></div></div>
            <div class="step-val" style="color:${color}">${steps?steps.toLocaleString():"–"}</div>
          </div>`;
        }).join("")}
      </div>

      <!-- PR Board -->
      <div class="card" style="padding:14px;margin-bottom:14px">
        <div class="sl">🏆 Personal Records</div>
        ${!prs.length?`<div class="empty">Start logging to build your PR board</div>`:
          prs.slice(0,10).map(pr=>`<div class="prrow"><div><div class="prname">${pr.name}</div><div class="prdate">Week ${pr.week} · ${pr.day}</div></div><div class="prval">${pr.weight} lbs</div></div>`).join("")}
      </div>

      <!-- Missed -->
      <div class="card" style="padding:14px;margin-bottom:14px">
        <div class="sl">📋 Missed Workouts</div>
        ${!missedEntries.length?`<div class="empty">No missed days — keep it up!</div>`:
          missedEntries.slice(-8).reverse().map(m=>`<div class="missedday"><div>Week ${m.week} · ${m.day}${m.reason?`<div style="font-size:10px;color:#555">${m.reason}</div>`:""}</div><div style="font-size:10px;color:#f87171">Missed</div></div>`).join("")}
      </div>
    </div>`;
  }

  // ── ANALYTICS ──
  if(activeTab==="analytics"){
    html+=`<div class="secpad">
      <div class="tabs" style="margin-bottom:14px">
        <button class="tab${aView==="overview"?" active":""}" onclick="setAView('overview')">Overview</button>
        <button class="tab${aView==="exercise"?" active":""}" onclick="setAView('exercise')">By Exercise</button>
      </div>
      <div class="aic">
        <div class="aih"><div class="ail">⚡ AI Coach</div><button class="aib" onclick="doInsight()">Analyze</button></div>
        <div class="ait${insightTxt?" ld":""}">${insightTxt||"Tap Analyze to get coaching feedback on your data."}</div>
      </div>`;

    if(aView==="overview"){
      const totalV=vols.reduce((s,v)=>s+v.vol,0);
      const allCI=Object.values(S.checkins||{}).flatMap(w=>Object.values(w));
      const avgSleep=allCI.filter(c=>c.sleep).length?(allCI.filter(c=>c.sleep).reduce((s,c)=>s+c.sleep,0)/allCI.filter(c=>c.sleep).length).toFixed(1):null;
      const avgEnergy=allCI.filter(c=>c.energy).length?(allCI.filter(c=>c.energy).reduce((s,c)=>s+c.energy,0)/allCI.filter(c=>c.energy).length).toFixed(1):null;
      const allSteps=Object.values(S.steps||{}).flatMap(w=>Object.values(w).map(v=>+v)).filter(Boolean);
      const avgSteps=allSteps.length?Math.round(allSteps.reduce((a,b)=>a+b,0)/allSteps.length):null;
      html+=`<div class="sgrid">
        <div class="scard"><div class="sv">${vols.length||"–"}</div><div class="slbl">Weeks\nLogged</div></div>
        <div class="scard"><div class="sv">${gains.filter(g=>g.pct>0).length||"–"}</div><div class="slbl">Lifts\nUp</div></div>
        <div class="scard"><div class="sv">${totalV>0?(totalV/1000).toFixed(0)+"k":"–"}</div><div class="slbl">Total\nVolume</div></div>
      </div>
      <div class="sgrid">
        <div class="scard"><div class="sv">${avgSleep||"–"}</div><div class="slbl">Avg\nSleep hrs</div></div>
        <div class="scard"><div class="sv">${avgEnergy||"–"}</div><div class="slbl">Avg\nEnergy /5</div></div>
        <div class="scard"><div class="sv">${avgSteps?avgSteps.toLocaleString():"–"}</div><div class="slbl">Avg\nSteps/Day</div></div>
      </div>
      <div class="card" style="padding:14px;margin-bottom:14px">
        <div class="sl">Weekly Volume (lbs)</div>${barChart(vols,"vol")}
      </div>
      <div class="card" style="padding:14px;margin-bottom:14px">
        <div class="sl">Strength Gains</div>
        ${!gains.length?`<div class="empty">Log 2+ weeks to see gains</div>`:gains.slice(0,6).map(g=>`
          <div class="gr"><div class="gt"><div class="gn">${g.name}</div><div class="gp" style="color:${g.pct>0?"#4ade80":"#f87171"}">${g.pct>0?"+":""}${g.pct}%</div></div>
          <div class="gtr"><div class="gbg"><div class="gfill" style="width:${Math.min(100,Math.abs(g.pct)*3)}%;background:${g.pct>0?"#4ade80":"#f87171"}"></div></div>
          <div class="grng">${g.first}→${g.last}lbs</div></div></div>`).join("")}
      </div>`;
    }
    if(aView==="exercise"){
      html+=`<div class="dtabs" style="margin-bottom:12px">${DAYS.map(d=>`<button class="dtab${d===activeDay?" active":""}" onclick="setDay('${d}');setAView('exercise')" style="min-width:50px"><div class="dd">${d}</div></button>`).join("")}</div>`;
      PROG[activeDay].exercises.forEach((ex,ei)=>{
        const trend=exTrend(activeDay,ei),isSel=selEx===ei;
        const latest=trend[trend.length-1],first=trend[0];
        const gained=trend.length>=2?latest.weight-first.weight:null;
        html+=`<div class="card${isSel?" gb":""}">
          <button class="edb" onclick="selEx=${isSel?null:ei};re()">
            <div><div class="edn">${ex.name}</div><div class="edm">${trend.length?`${trend.length} wk${trend.length>1?"s":""} · Best: ${latest.weight}lbs`:"No data yet"}</div></div>
            ${gained!==null?`<div class="edg" style="color:${gained>=0?"#4ade80":"#f87171"}">${gained>=0?"+":""}${gained}lbs</div>`:""}
          </button>
          ${isSel?`<div class="edd"><div class="sl" style="margin-top:8px">Best Weight / Week</div>${lineChart(trend)}</div>`:""}
        </div>`;
      });
    }
    html+=`</div>`;
  }

  // ── REPORT ──
  if(activeTab==="report"){
    const W2=wk(S.week);
    html+=`<div class="secpad">
      <div style="font-size:14px;font-weight:800;color:#fff;margin-bottom:3px">Weekly Trainer Report</div>
      <div style="font-size:11px;color:#888;margin-bottom:14px">AI builds your full report from workouts, meals, supplements, steps, and recovery data.</div>
      <div class="card" style="padding:14px;margin-bottom:14px">
        <div class="sl">Meal Compliance — Week ${S.week}</div>
        ${DAYS.map(d=>{const dm=(S.meals[W2]||{})[d]||{},checked=MEALS.filter((_,i)=>dm[i]).length,pct=Math.round(checked/MEALS.length*100);
          return`<div class="crow"><div class="cday">${d}</div><div class="cbg"><div class="cfill" style="width:${pct}%;background:${pct===100?"#4ade80":pct>=66?G:"#f87171"}"></div></div><div class="ccnt">${checked}/${MEALS.length}</div></div>`;
        }).join("")}
        <div class="sl" style="margin-top:12px;margin-bottom:6px">Supplement Compliance</div>
        ${DAYS.map(d=>{const sd=(S.supps[W2]||{})[d]||{},checked=SUPPS.filter((_,i)=>sd[i]).length,pct=Math.round(checked/SUPPS.length*100);
          return`<div class="crow"><div class="cday">${d}</div><div class="cbg"><div class="cfill" style="width:${pct}%;background:${pct===100?"#4ade80":pct>=66?G:"#f87171"}"></div></div><div class="ccnt">${checked}/${SUPPS.length}</div></div>`;
        }).join("")}
      </div>
      <button class="btng" onclick="doReport()" ${reportTxt==="Generating..."?"disabled":""}>⚡ Generate Week ${S.week} Report</button>
      ${reportTxt&&reportTxt!=="Generating..."?`
        <div class="rpt-prev"><div class="sl">Report Preview</div><div class="rpt-txt">${reportTxt}</div></div>
        <button class="wa-btn" onclick="shareWhatsApp()">💬 Share via WhatsApp</button>
        <button class="btno" onclick="exportPDF()">📄 Download PDF Report</button>`:""}
      ${reportTxt==="Generating..."?`<div style="text-align:center;padding:20px;color:#888;font-size:12px">Generating your report...</div>`:""}
    </div>`;
  }

  // ── SETTINGS ──
  if(activeTab==="settings"){
    html+=`<div class="secpad">
      <div style="font-size:14px;font-weight:800;color:#fff;margin-bottom:4px">Update Your Plan</div>
      <div style="font-size:11px;color:#888;margin-bottom:18px">When your trainer sends a new plan via PDF or WhatsApp, update it here. Your logged data is never lost.</div>

      <div class="ss"><div class="ss-title">📋 Workout Plan</div>
      <div class="card" style="padding:14px">
        <div style="font-size:11px;color:#888;margin-bottom:10px;line-height:1.5">Upload a PDF from your trainer or paste the plan as text.</div>
        <label style="display:block;padding:11px;border-radius:8px;border:1px dashed #333;background:#1a1a1a;color:#888;font-size:11px;font-weight:700;text-align:center;cursor:pointer;margin-bottom:8px">
          📄 Upload Workout PDF
          <input type="file" accept=".pdf,application/pdf" style="display:none" onchange="handlePDFUpload(this,'workout')">
        </label>
        <div style="text-align:center;font-size:10px;color:#444;margin-bottom:8px">— or paste text below —</div>
        <textarea class="plan-ta" id="workoutTA" placeholder="Mon Back / Biceps&#10;1. Lat Pull Down 4x20,15,10,10&#10;2. Bent Over Row 4x15,10,10,8&#10;..." onchange="workoutPasteText=this.value">${workoutPasteText}</textarea>
        ${parseStatus==="loading-workout"?`<div class="ps loading">⏳ Reading your plan...</div>`:""}
        ${parseStatus==="err-workout"?`<div class="ps err">❌ Couldn't parse. Make sure it includes day labels and exercises with sets/reps.</div>`:""}
        ${parsedPlan&&parseStatus==="ok-workout"?`
          <div class="ps ok">✅ ${Object.keys(parsedPlan).length} days detected — review below then Apply.</div>
          <div class="pp">${Object.entries(parsedPlan).map(([d,v])=>`<div class="ppd">${d} — ${v.focus}</div>${v.exercises.map(ex=>`<div class="ppe">· ${ex.name} ${ex.sets}×${ex.reps}</div>`).join("")}`).join("")}</div>
          <button class="btng" style="margin-top:12px" onclick="applyWorkoutPlan()">✅ Apply Workout Plan</button>`:""}
        ${!parsedPlan&&parseStatus!=="loading-workout"?`<button class="btng" style="margin-top:10px" onclick="parseWorkoutPlan(document.getElementById('workoutTA')?.value||workoutPasteText)">⚡ Parse Workout Plan</button>`:""}
      </div></div>

      <div class="ss"><div class="ss-title">🍗 Meal Plan</div>
      <div class="card" style="padding:14px">
        <div style="font-size:11px;color:#888;margin-bottom:10px;line-height:1.5">Upload a PDF or paste your updated meal plan.</div>
        <label style="display:block;padding:11px;border-radius:8px;border:1px dashed #333;background:#1a1a1a;color:#888;font-size:11px;font-weight:700;text-align:center;cursor:pointer;margin-bottom:8px">
          📄 Upload Meal Plan PDF
          <input type="file" accept=".pdf,application/pdf" style="display:none" onchange="handlePDFUpload(this,'meal')">
        </label>
        <div style="text-align:center;font-size:10px;color:#444;margin-bottom:8px">— or paste text below —</div>
        <textarea class="plan-ta" id="mealTA" placeholder="Meal One (Pre Workout A.M.)&#10;- Egg White 160g&#10;- Whole Egg 2&#10;..." onchange="mealPasteText=this.value">${mealPasteText}</textarea>
        ${parseStatus==="loading-meal"?`<div class="ps loading">⏳ Reading your meal plan...</div>`:""}
        ${parseStatus==="err-meal"?`<div class="ps err">❌ Couldn't parse. Make sure it lists meals with food items and quantities.</div>`:""}
        ${parsedMeals&&parseStatus==="ok-meal"?`
          <div class="ps ok">✅ ${parsedMeals.length} meals detected — review below then Apply.</div>
          <div class="pp">${parsedMeals.map(m=>`<div class="ppd">${m.name}</div>${m.items.map(i=>`<div class="ppe">· ${i}</div>`).join("")}`).join("")}</div>
          <button class="btng" style="margin-top:12px" onclick="applyMealPlan()">✅ Apply Meal Plan</button>`:""}
        ${!parsedMeals&&parseStatus!=="loading-meal"?`<button class="btng" style="margin-top:10px" onclick="parseMealPlan(document.getElementById('mealTA')?.value||mealPasteText)">⚡ Parse Meal Plan</button>`:""}
      </div></div>

      <div class="ss"><div class="ss-title">📌 Current Active Plan</div>
      <div class="card" style="padding:14px">
        ${Object.entries(PROG).map(([d,v])=>`<div class="ppd">${d} — ${v.focus}</div>${v.exercises.map(ex=>`<div class="ppe">· ${ex.name} (${ex.sets} sets)</div>`).join("")}`).join("")}
        <div style="margin-top:12px;padding-top:12px;border-top:1px solid #1e1e1e">
          <div style="font-size:10px;color:#555;margin-bottom:4px;text-transform:uppercase;letter-spacing:1px">Meal Plan (${MEALS.length} meals)</div>
          ${MEALS.map(m=>`<div class="ppe">· ${m.name}</div>`).join("")}
        </div>
      </div></div>

      <div class="ss"><div class="ss-title" style="color:#f87171">⚠️ Data</div>
      <div class="card" style="padding:14px">
        <div style="font-size:11px;color:#888;margin-bottom:10px">Reset removes ALL logged data. Plan is kept. Cannot be undone.</div>
        <button onclick="if(confirm('Delete all logged data?')){S.logs={};S.meals={};S.bodyweight={};S.checkins={};S.water={};S.missed={};S.supps={};S.steps={};S.exnotes={};S.wtimes={};saveS(S);re();}" style="width:100%;padding:12px;border-radius:8px;border:1px solid #f87171;background:transparent;color:#f87171;font-size:12px;font-weight:700">Reset All Logged Data</button>
      </div></div>
    </div>`;
  }

  html+=`<div style="padding:14px 16px 0;font-size:10px;color:#222;text-align:center">+2.5–5 lbs/week · 60s rest · Mind-to-muscle every rep</div>`;
  app.innerHTML=html;
}

// ── Actions ───────────────────────────────────────────────────────────────────
function chWeek(d){S.week=Math.max(1,S.week+d);saveS(S);re();}
function setTab(t){activeTab=t;re();}
function setDay(d){activeDay=d;re();}
function setAView(v){aView=v;re();}
function setSet(day,ei,si,field,val){
  const w=wk(S.week);
  if(!S.logs[w])S.logs[w]={};if(!S.logs[w][day])S.logs[w][day]={};
  if(!S.logs[w][day][ei])S.logs[w][day][ei]={};if(!S.logs[w][day][ei][si])S.logs[w][day][ei][si]={};
  S.logs[w][day][ei][si][field]=val;saveS(S);
  if(field==="w"&&val)startTimer();
  re();
}
function setExNote(day,ei,val){
  const w=wk(S.week);
  if(!S.exnotes[w])S.exnotes[w]={};if(!S.exnotes[w][day])S.exnotes[w][day]={};
  S.exnotes[w][day][ei]=val;saveS(S);
}
function toggleMeal(day,mi){
  const w=wk(S.week);if(!S.meals[w])S.meals[w]={};if(!S.meals[w][day])S.meals[w][day]={};
  S.meals[w][day][mi]=!S.meals[w][day][mi];saveS(S);re();
}
function toggleSupp(day,si){
  const w=wk(S.week);if(!S.supps[w])S.supps[w]={};if(!S.supps[w][day])S.supps[w][day]={};
  S.supps[w][day][si]=!S.supps[w][day][si];saveS(S);re();
}
function setNote(val){const w=wk(S.week);if(!S.meals[w])S.meals[w]={};S.meals[w].notes=val;saveS(S);}
function setWater(day,cups){const w=wk(S.week);if(!S.water[w])S.water[w]={};S.water[w][day]=cups;saveS(S);re();}
function setSteps(day,val){const w=wk(S.week);if(!S.steps[w])S.steps[w]={};S.steps[w][day]=parseInt(val)||0;saveS(S);}
function setCheckin(field,val){
  const w=wk(S.week);if(!S.checkins[w])S.checkins[w]={};if(!S.checkins[w][activeDay])S.checkins[w][activeDay]={};
  S.checkins[w][activeDay][field]=val;saveS(S);re();
}
function setBW(val){const w=wk(S.week);S.bodyweight[w]=parseFloat(val)||null;saveS(S);}
function toggleMissed(day){
  const w=wk(S.week);if(!S.missed[w])S.missed[w]={};
  if(S.missed[w][day])delete S.missed[w][day];else S.missed[w][day]={reason:""};
  saveS(S);re();
}
function setMissedReason(day,val){const w=wk(S.week);if(S.missed[w]?.[day])S.missed[w][day].reason=val;saveS(S);}

render();
</script>
</body>
</html>

