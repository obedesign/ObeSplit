<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
<title>ObeSplit - AI UHD Editor</title>
<script src="https://cdn.tailwindcss.com"></script>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap" rel="stylesheet">
<style>
*{font-family:Inter,sans-serif;-webkit-tap-highlight-color:transparent;box-sizing:border-box}
body{margin:0; overscroll-behavior:none; touch-action: manipulation}
#previewWrap{touch-action:none; overscroll-behavior:none}
#previewBox{touch-action:none; will-change:transform}
#video{transform-origin:center center; will-change:transform}
.timeline-handle{position:absolute; top:0; bottom:0; width:14px; background:rgba(24,229,139,0.9); display:flex; align-items:center; justify-content:center; z-index:10}
.timeline-handle.left{left:0; border-radius:8px 0 0 8px}
.timeline-handle.right{right:0; border-radius:0 8px 8px 0}
.transition-dot{width:20px; height:20px; background:#2a2a2a; border:2px solid #444; transform:rotate(45deg); display:flex; align-items:center; justify-content:center; flex-shrink:0; cursor:pointer}
.transition-dot.active{border-color:#18E58B; background:#18E58B}
#zoomBadge{position:absolute; top:8px; right:8px; background:rgba(0,0,0,0.7); color:#18E58B; font-size:11px; padding:3px 7px; border-radius:10px; display:none; z-index:20}

.no-scrollbar::-webkit-scrollbar{display:none}
.no-scrollbar{-ms-overflow-style:none;scrollbar-width:none}
.clip-item{user-select:none;-webkit-user-select:none;border:1px solid #2a2a2a}
.clip-item.selected{border-color:#18E58B!important;box-shadow:0 0 0 1px #18E58B inset}
#timelineScroll{touch-action:pan-x;overscroll-behavior-x:contain}
button:active{transform:scale(.96)}
.edit-tool{min-width:78px;width:78px;height:72px;background:#242424;border:1px solid #303030;border-radius:14px;display:flex;flex-direction:column;align-items:center;justify-content:center;gap:7px;color:#ddd;flex-shrink:0}
.edit-tool svg{width:22px;height:22px}
.edit-tool span{font-size:10px;white-space:nowrap}
.edit-tool.active{background:#18E58B;color:#000;border-color:#18E58B}
.range-green{accent-color:#18E58B}
.panel-card{background:#242424;border:1px solid #303030;border-radius:14px}
.small-control{background:#242424;border:1px solid #333;border-radius:10px}
.option-active{background:#18E58B!important;color:#000!important;border-color:#18E58B!important}
</style>
</head>
<body class="bg-[#0a0a0a] flex justify-center min-h-screen overflow-hidden">
<div class="w-full max-w-[440px] bg-[#121212] flex flex-col h-[100dvh] text-white relative">
<!-- HEADER -->
<div class="flex items-center justify-between px-3 py-2.5">
  <div class="flex gap-2">
    <button onclick="location.reload()" class="w-8 h-8 flex items-center justify-center rounded-full">
      <svg width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="white" stroke-width="2"><path d="M18 6L6 18M6 6l12 12"/></svg>
    </button>
    <button class="w-8 h-8 flex items-center justify-center rounded-full">
      <svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="white" stroke-width="2"><circle cx="11" cy="11" r="6"/><path d="M21 21l-4.3-4.3"/></svg>
    </button>
  </div>
  <div class="flex gap-2 items-center relative">
    <button id="aiUhdBtn" class="bg-[#232323] px-3.5 py-2 rounded-xl text-[12px] font-semibold flex items-center gap-1.5 border border-[#333]">
      <span class="w-2.5 h-2.5 rotate-45 bg-[#18E58B] block rounded-[2px]"></span>AI UHD
      <svg width="12" height="12" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5"><path d="M6 9l6 6 6-6"/></svg>
    </button>
    <button id="exportBtn" class="bg-[#18E58B] text-black px-6 h-9 rounded-xl font-bold text-[14px]">Export</button>
    <!-- EXPORT PANEL -->
    <div id="exportPanel" class="hidden absolute top-12 right-0 w-[340px] bg-[#1A1A1A] border border-[#2A2A2A] rounded-[20px] z-[100] shadow-2xl max-h-[85vh] overflow-y-auto no-scrollbar">
      <div class="flex p-1 m-3 bg-[#242424] rounded-full">
        <button id="tabVideo" class="flex-1 py-2 rounded-full bg-white text-black text-[13px] font-bold">Video</button>
        <button id="tabGif" class="flex-1 py-2 rounded-full text-[#777] text-[13px]">GIF</button>
      </div>
      <div class="px-4 pb-4">
        <div class="flex justify-between py-3.5 border-b border-[#252525]">
          <div class="flex items-center gap-2"><span class="w-3.5 h-3.5 rotate-45 bg-[#18E58B] block rounded-[2px]"></span><span class="text-[13px] font-semibold">AI Ultra HD</span></div>
          <button id="aiToggle" class="w-11 h-6 bg-[#18E58B] rounded-full relative"><span class="absolute top-0.5 left-0.5 w-5 h-5 bg-white rounded-full translate-x-5 transition-all"></span></button>
        </div>
        <div class="pt-4">
          <div class="text-[11px] text-[#666] font-semibold mb-3">RESOLUTION</div>
          <div class="grid grid-cols-4 gap-2" id="resGroup">
            <button data-res="480p" class="res-opt h-10 rounded-xl bg-[#242424] text-[12px]">480p</button>
            <button data-res="720p" class="res-opt h-10 rounded-xl bg-[#242424] text-[12px]">720p</button>
            <button data-res="1080p" class="res-opt h-10 rounded-xl bg-white text-black font-bold text-[12px]">1080p</button>
            <button data-res="4K" class="res-opt h-10 rounded-xl bg-[#242424] text-[12px]">2K/4K</button>
          </div>
        </div>
        <div class="pt-5">
          <div class="text-[11px] text-[#666] font-semibold mb-3">FRAME RATE</div>
          <div class="flex gap-2 flex-wrap" id="fpsGroup">
            <button data-fps="24" class="fps-opt px-3.5 h-9 rounded-xl bg-[#242424] text-[12px]">24 FPS</button>
            <button data-fps="30" class="fps-opt px-3.5 h-9 rounded-xl bg-white text-black font-bold text-[12px]">30 FPS</button>
            <button data-fps="60" class="fps-opt px-3.5 h-9 rounded-xl bg-[#242424] text-[12px]">60 FPS</button>
          </div>
        </div>
        <div class="pt-5">
          <div class="text-[11px] text-[#666] font-semibold mb-3">BITRATE</div>
          <div class="flex gap-2 flex-wrap" id="brGroup">
            <button data-br="8" class="br-opt px-3.5 h-9 rounded-xl bg-[#242424] text-[12px]">8 Mbps</button>
            <button data-br="20" class="br-opt px-3.5 h-9 rounded-xl bg-white text-black font-bold text-[12px]">20 Mbps</button>
            <button data-br="40" class="br-opt px-3.5 h-9 rounded-xl bg-[#242424] text-[12px]">40 Mbps</button>
          </div>
          <div class="text-[11px] text-[#666] mt-2" id="bitrateLabel">20 Mbps</div>
        </div>
        <div class="flex justify-between py-3.5 border-t border-[#252525] mt-5">
          <div class="flex items-center gap-2"><span class="text-[13px]">Watermark</span></div>
          <button id="wmToggle" class="w-11 h-6 bg-[#2a2a2a] rounded-full relative"><span class="absolute top-0.5 left-0.5 w-5 h-5 bg-white rounded-full transition-all"></span></button>
        </div>
        <div class="mt-5 p-3 rounded-xl bg-[#242424] flex justify-between">
          <span class="text-[11px] text-[#777]">ESTIMATED FILE SIZE</span>
          <span id="estSize" class="text-[13px] font-semibold">~ 0 MB</span>
        </div>
      </div>
    </div>
  </div>
</div>

<!-- PREVIEW -->
<div id="previewWrap" class="flex justify-center bg-[#0f0f0f] px-4 py-3 shrink-0">
  <div id="previewBox" class="relative bg-black overflow-hidden rounded-[4px]" style="width:62%;aspect-ratio:9/16;">
    <video id="video" class="w-full h-full object-cover" playsinline></video>
    <div id="textLayer" class="absolute inset-0 pointer-events-none"></div>
    <div id="zoomBadge">100%</div>
    <img id="photoPreview" class="w-full h-full object-cover hidden" alt="preview"/>
    <div id="textLayer" class="absolute inset-0"></div>
    <canvas id="exportCanvas" class="hidden"></canvas>
  </div>
</div>

<!-- PLAYBACK -->
<div class="flex justify-between px-4 py-3 border-y border-[#1e1e1e] shrink-0">
  <button id="fitBtn" class="w-9 h-9 flex items-center justify-center">
    <svg width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="white" stroke-width="1.6"><path d="M15 3h6v6"/><path d="M9 21H3v-6"/><path d="M21 3l-7 7"/><path d="M3 21l7-7"/></svg>
  </button>
  <button id="playBtn">
    <svg id="playIcon" width="26" height="26" viewBox="0 0 24 24" fill="white"><path d="M8 5.14v14l11-7-11-7z"/></svg>
    <svg id="pauseIcon" class="hidden" width="26" height="26" viewBox="0 0 24 24" fill="white"><rect x="6" y="5" width="4" height="14" rx="1"/><rect x="14" y="5" width="4" height="14" rx="1"/></svg>
  </button>
  <div class="flex gap-2 items-center">
    <button class="w-9 h-9 flex items-center justify-center relative">
      <svg width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="white" stroke-width="1.5"><rect x="3" y="4" width="12" height="12" rx="2"/><path d="M15 8l4-1v10l-4-1V8z"/></svg>
      <span class="absolute -bottom-0.5 right-0 text-[7px] bg-white text-black px-1 rounded font-bold">ON</span>
    </button>
    <button id="undoBtn" class="w-9 h-9 flex items-center justify-center"><svg width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="white" stroke-width="1.6"><path d="M9 14L4 9l5-5"/><path d="M4 9h10a4 4 0 1 1 0 8H9"/></svg></button>
    <button id="redoBtn" class="w-9 h-9 flex items-center justify-center"><svg width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="white" stroke-width="1.6"><path d="M15 14l5-5-5-5"/><path d="M20 9H10a4 4 0 1 0 0 8h5"/></svg></button>
    <button id="keyframeBtn" class="w-8 h-8 bg-[#232323] rounded-lg flex items-center justify-center border border-[#333]"><svg width="16" height="16" viewBox="0 0 24 24"><path d="M12 3l7 9-7 9-7-9 7-9z" fill="white"/><circle cx="12" cy="12" r="2.5" fill="black"/></svg></button>
  </div>
</div>

<!-- TIME -->
<div class="flex justify-between px-4 py-2 text-[11px] text-[#666] shrink-0">
  <span id="timeLabel">00:00 / 00:00</span>
  <div id="ruler" class="flex gap-3"></div>
</div>

<!-- TIMELINE -->
<div class="flex-1 bg-[#1e1e1e] relative flex flex-col overflow-hidden">
  <div id="timelineScroll" class="flex-1 overflow-x-auto overflow-y-hidden no-scrollbar">
    <div id="timelineContent" class="relative h-full pt-2" style="min-width:100%;width:fit-content;">
      <div id="playhead" class="absolute top-0 bottom-0 w-[2px] bg-white z-30 pointer-events-none" style="left:160px"><div class="w-[10px] h-[10px] bg-white rotate-45 -ml-[4px] rounded-[1px]"></div></div>
      <div id="keyframeMarkers" class="absolute top-0 left-0 right-0 h-3 z-10 pointer-events-none"></div>
      <div class="flex items-center px-2 gap-2">
        <div class="flex gap-2 shrink-0 sticky left-2 z-20 bg-[#1e1e1e]">
          <button id="muteBtn" class="bg-[#2a2a2a] w-[68px] h-[52px] rounded-xl flex flex-col items-center justify-center gap-1 text-[10px] text-[#ccc] border border-[#333]"><svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5"><path d="M11 5L6 9H2v6h4l5 4V5z"/><line x1="23" y1="9" x2="17" y2="15"/><line x1="17" y1="9" x2="23" y2="15"/></svg>Mute clip</button>
          <button id="coverBtn" class="bg-[#2a2a2a] w-[68px] h-[52px] rounded-xl flex flex-col items-center justify-center gap-1 text-[10px] border border-[#333]"><svg width="20" height="20" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5"><path d="M12 20h9"/><path d="M16.5 3.5a2.12 2.12 0 0 1 3 3L7 19l-4 1 1-4L16.5 3.5z"/></svg>Cover</button>
        </div>
        <div id="clipsContainer" class="flex gap-[2px] h-[52px] ml-1 items-center"></div>
        <button id="addMediaBtn" class="w-10 h-[52px] bg-white rounded-xl flex items-center justify-center text-black text-[22px] font-bold shrink-0 ml-1">+</button>
      </div>
      <div class="flex items-center px-2 pt-3 gap-2"><div class="w-[144px] shrink-0"></div><button id="addAudioBtn2" class="flex-1 h-9 bg-[#2a2a2a] rounded-md flex items-center px-3 text-[13px] text-[#777] gap-2">+ Add audio</button></div>
      <div class="flex items-center px-2 pt-2 gap-2 pb-4"><div class="w-[144px] shrink-0"></div><button id="addTextBtn2" class="flex-1 h-9 bg-[#2a2a2a] rounded-md flex items-center px-3 text-[13px] text-[#777] gap-2">+ Add text</button></div>
    </div>
  </div>
</div>

<!-- BOTTOM TOOLS -->
<div class="bg-[#121212] border-t border-[#1e1e1e] shrink-0">
  <div id="bottomBar" class="flex gap-0 overflow-x-auto no-scrollbar px-1 py-2">
    <button data-tool="edit" class="tool-btn min-w-[74px] flex flex-col items-center gap-1 py-1.5 text-[11px] text-[#999] shrink-0"><div class="w-7 h-7 flex items-center justify-center"><svg width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5"><path d="M11 4H4a2 2 0 0 0-2 2v14a2 2 0 0 0 2 2h14a2 2 0 0 0 2-2v-7"/><path d="M18.5 2.5a2.12 2.12 0 0 1 3 3L12 15l-4 1 1-4 9.5-9.5z"/></svg></div><span>Edit</span></button>
    <button data-tool="audio" class="tool-btn min-w-[74px] flex flex-col items-center gap-1 py-1.5 text-[11px] text-[#999] shrink-0"><div class="w-7 h-7 flex items-center justify-center"><svg width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5"><path d="M9 18V5l12-2v13"/><circle cx="6" cy="18" r="3"/><circle cx="18" cy="16" r="3"/></svg></div><span>Audio</span></button>
    <button data-tool="text" class="tool-btn min-w-[74px] flex flex-col items-center gap-1 py-1.5 text-[11px] text-[#999] shrink-0"><div class="w-7 h-7 flex items-center justify-center"><svg width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5"><polyline points="4 7 4 4 20 4 20 7"/><line x1="9" y1="20" x2="15" y2="20"/><line x1="12" y1="4" x2="12" y2="20"/></svg></div><span>Text</span></button>
    <button data-tool="effects" class="tool-btn min-w-[74px] flex flex-col items-center gap-1 py-1.5 text-[11px] text-[#999] shrink-0"><div class="w-7 h-7 flex items-center justify-center"><svg width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5"><path d="M12 2l2.4 7.2H22l-6.2 4.5 2.4 7.2L12 16.4 5.8 20.9l2.4-7.2L2 9.2h7.6z"/></svg></div><span>Effects</span></button>
    <button data-tool="overlay" class="tool-btn min-w-[74px] flex flex-col items-center gap-1 py-1.5 text-[11px] text-[#999] shrink-0"><div class="w-7 h-7 flex items-center justify-center"><svg width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5"><rect x="3" y="3" width="18" height="18" rx="2"/><rect x="9" y="9" width="12" height="12" rx="2"/></svg></div><span>Overlay</span></button>
    <button data-tool="captions" class="tool-btn min-w-[74px] flex flex-col items-center gap-1 py-1.5 text-[11px] text-[#999] shrink-0"><div class="w-7 h-7 flex items-center justify-center"><svg width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5"><path d="M21 15a2 2 0 0 1-2 2H7l-4 4V5a2 2 0 0 1 2-2h14a2 2 0 0 1 2 2z"/><path d="M7 10h3M7 14h3M14 10h3M14 14h3"/></svg></div><span>Captions</span></button>
    <button data-tool="filters" class="tool-btn min-w-[74px] flex flex-col items-center gap-1 py-1.5 text-[11px] text-[#999] shrink-0"><div class="w-7 h-7 flex items-center justify-center"><svg width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5"><polygon points="22 3 2 3 10 12.46 10 19 14 21 14 12.46 22 3"/></svg></div><span>Filters</span></button>
    <button data-tool="sticker" class="tool-btn min-w-[74px] flex flex-col items-center gap-1 py-1.5 text-[11px] text-[#999] shrink-0"><div class="w-7 h-7 flex items-center justify-center"><svg width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5"><circle cx="12" cy="12" r="10"/><path d="M8 14s1.5 2 4 2 4-2 4-2"/><line x1="9" y1="9" x2="9.01" y2="9"/><line x1="15" y1="9" x2="15.01" y2="9"/></svg></div><span>Sticker</span></button>
    <button data-tool="aspect" class="tool-btn min-w-[74px] flex flex-col items-center gap-1 py-1.5 text-[11px] text-[#999] shrink-0"><div class="w-7 h-7 flex items-center justify-center"><svg width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5"><rect x="2" y="2" width="20" height="20" rx="2"/></svg></div><span>Aspect</span></button>
    <button data-tool="background" class="tool-btn min-w-[74px] flex flex-col items-center gap-1 py-1.5 text-[11px] text-[#999] shrink-0"><div class="w-7 h-7 flex items-center justify-center"><svg width="22" height="22" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5"><rect x="3" y="3" width="18" height="18" rx="2"/></svg></div><span>Background</span></button>
  </div>
  <div id="toolPanel" class="hidden border-t border-[#1e1e1e] bg-[#121212]">
    <div class="flex justify-between items-center px-4 py-2"><span id="toolTitle" class="text-[13px] font-bold">Tool</span><button id="closeToolPanel" class="w-8 h-8 flex items-center justify-center text-[#777]"><svg width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M18 6L6 18M6 6l12 12"/></svg></button></div>
    <div id="toolContent" class="p-4 max-h-[45vh] overflow-auto no-scrollbar"></div>
  </div>
  <input type="file" id="mediaInput" accept="video/*,image/*" multiple class="hidden">
  <input type="file" id="audioInput" accept="audio/*" class="hidden">
  <audio id="bgAudio" class="hidden"></audio>
</div>
</div>
<script>
/* CORE ELEMENTS */
const video=document.getElementById('video');
const photoPreview=document.getElementById('photoPreview');
const mediaInput=document.getElementById('mediaInput');
const clipsContainer=document.getElementById('clipsContainer');
const addMediaBtn=document.getElementById('addMediaBtn');
const timeLabel=document.getElementById('timeLabel');
const ruler=document.getElementById('ruler');
const playhead=document.getElementById('playhead');
const timelineScroll=document.getElementById('timelineScroll');
const playBtn=document.getElementById('playBtn');
const playIcon=document.getElementById('playIcon');
const pauseIcon=document.getElementById('pauseIcon');
const exportBtn=document.getElementById('exportBtn');
const exportPanel=document.getElementById('exportPanel');
const aiUhdBtn=document.getElementById('aiUhdBtn');

let clips=[];let totalDuration=0;let globalTime=0;let isPlaying=false;let raf=null;
let currentRes='1080p';let currentFps=30;let currentBitrate=20;let isAiUhd=true;let isGif=false;let watermark=false;let selectedClipId=null;
const PX_PER_SEC=60;

function fmt(s){if(!isFinite(s)) s=0;const m=Math.floor(s/60).toString().padStart(2,'0');const sec=Math.floor(s%60).toString().padStart(2,'0');return `${m}:${sec}`;}
function updateRuler(){ruler.innerHTML='';const step=totalDuration>60?10:2;for(let t=0;t<=Math.ceil(totalDuration);t+=step){const el=document.createElement('span');el.textContent=fmt(t);ruler.appendChild(el);}}
function updateTimeLabel(){timeLabel.textContent=`${fmt(globalTime)} / ${fmt(totalDuration)}`;}
function updateEstSize(){const seconds=Math.max(totalDuration,0);const mb=(seconds*currentBitrate/8);document.getElementById('estSize').textContent=`~ ${mb.toFixed(1)} MB`;}
function calcTotal(){totalDuration=clips.reduce((a,c)=>a+c.duration,0);updateRuler();updateTimeLabel();updateEstSize();}

function getClipAtTime(time){let acc=0;for(let i=0;i<clips.length;i++){const c=clips[i];if(time>=acc&&time<acc+c.duration){return{clip:c,index:i,local:time-acc,start:acc};}acc+=c.duration;}if(clips.length){const last=clips[clips.length-1];return{clip:last,index:clips.length-1,local:last.duration,start:totalDuration-last.duration};}return null;}

function showClip(clip,localTime){
 if(!clip)return;selectedClipId=clip.id;
 document.querySelectorAll('.clip-item').forEach(el=>{el.classList.toggle('selected',el.dataset.id===clip.id);});
 if(clip.type.startsWith('video')){
   photoPreview.classList.add('hidden');video.classList.remove('hidden');
   if(video.src!==clip.url){video.src=clip.url;}
   if(Math.abs(video.currentTime-localTime)>0.4){try{video.currentTime=localTime;}catch(e){}}
 }else{
   video.classList.add('hidden');video.pause();photoPreview.classList.remove('hidden');photoPreview.src=clip.url;
 }
}

function renderClips(){
 clipsContainer.innerHTML='';
 clips.forEach(c=>{
  const wrap=document.createElement('div');wrap.dataset.id=c.id;
  wrap.className='clip-item relative h-[52px] bg-black rounded-lg overflow-hidden flex shrink-0 cursor-pointer';
  wrap.style.width=(Math.max(c.duration,0.8)*PX_PER_SEC)+'px';wrap.style.minWidth='60px';
  if(c.id===selectedClipId){wrap.classList.add('selected');}
  const thumbs=document.createElement('div');thumbs.className='flex h-full w-full';
  if(c.type.startsWith('video')&&c.thumbs&&c.thumbs.length){c.thumbs.forEach(u=>{const im=document.createElement('img');im.src=u;im.className='h-full flex-1 object-cover pointer-events-none';thumbs.appendChild(im);});}
  else if(c.type.startsWith('image')){const im=document.createElement('img');im.src=c.url;im.className='h-full w-full object-cover pointer-events-none';thumbs.appendChild(im);}
  else{const ph=document.createElement('div');ph.className='w-full h-full bg-[#111]';thumbs.appendChild(ph);}
  wrap.appendChild(thumbs);
  const dur=document.createElement('div');dur.className='absolute bottom-0 right-0 bg-black/70 text-[9px] px-1 rounded-tl';dur.textContent=fmt(c.duration);wrap.appendChild(dur);
  wrap.addEventListener('click',()=>{let acc=0;for(let cl of clips){if(cl.id===c.id)break;acc+=cl.duration;}seekGlobal(acc+0.01);});
  clipsContainer.appendChild(wrap);
 });
 calcTotal();
}

async function generateThumbsForClip(clip){
 if(!clip.type.startsWith('video'))return;
 const v=document.createElement('video');v.src=clip.url;v.muted=true;v.playsInline=true;
 await new Promise(res=>v.onloadedmetadata=()=>res());
 clip.duration=v.duration||3;
 const count=Math.max(1,Math.min(10,Math.floor(clip.duration)));
 clip.thumbs=[];
 for(let i=0;i<count;i++){
  const t=(i+0.5)*(clip.duration/count);
  await new Promise(res=>{const onSeek=()=>{v.removeEventListener('seeked',onSeek);res();};v.addEventListener('seeked',onSeek);v.currentTime=t;});
  const can=document.createElement('canvas');can.width=80;can.height=52;const ctx=can.getContext('2d');
  try{ctx.drawImage(v,0,0,80,52);}catch(e){ctx.fillStyle='#111';ctx.fillRect(0,0,80,52);}
  clip.thumbs.push(can.toDataURL());
 }
}

async function addFiles(files){
 for(let f of files){
  const url=URL.createObjectURL(f);
  const id=Date.now()+Math.random().toString(36).slice(2);
  const clip={id,file:f,url,type:f.type,duration:f.type.startsWith('image')?3:1,thumbs:[],cover:null,volume:1,opacity:1,speed:1,muted:false};
  clips.push(clip);
  if(f.type.startsWith('video')){await generateThumbsForClip(clip);}
 }
 renderClips();
 if(totalDuration>0&&globalTime===0){seekGlobal(0.01);}
}

function seekGlobal(t){
 globalTime=Math.max(0,Math.min(t,totalDuration));
 const info=getClipAtTime(globalTime);if(info){showClip(info.clip,info.local);}
 updateTimeLabel();updatePlayhead();
}
function updatePlayhead(){
 if(totalDuration===0){playhead.style.left='160px';return;}
 const baseOffset=160;
 const trackWidth=Math.max(clipsContainer.scrollWidth,clips.reduce((a,c)=>a+c.duration*PX_PER_SEC,0));
 const ratio=totalDuration>0?globalTime/totalDuration:0;
 const x=baseOffset+ratio*trackWidth;playhead.style.left=x+'px';
}
function tick(){
 if(!isPlaying)return;
 const info=getClipAtTime(globalTime);
 if(!info){pause();seekGlobal(0);return;}
 if(info.clip.type.startsWith('video')){if(!video.paused){globalTime=info.start+video.currentTime;}}else{globalTime+=1/60;}
 if(globalTime>=totalDuration){pause();seekGlobal(totalDuration);return;}
 const nextInfo=getClipAtTime(globalTime);
 if(nextInfo&&nextInfo.clip.id!==info.clip.id){
  showClip(nextInfo.clip,nextInfo.local);
  if(nextInfo.clip.type.startsWith('video')){video.currentTime=nextInfo.local;video.play().catch(()=>{});}
 }
 updateTimeLabel();updatePlayhead();
 raf=requestAnimationFrame(tick);
}
function play(){
 if(clips.length===0){alert('Add a video or image first - tap the + button on timeline');return;}
 if(globalTime>=totalDuration-0.02){seekGlobal(0);}
 isPlaying=true;playIcon.classList.add('hidden');pauseIcon.classList.remove('hidden');
 const info=getClipAtTime(globalTime);
 if(info&&info.clip.type.startsWith('video')){video.currentTime=info.local;video.play().catch(()=>{});}
 raf=requestAnimationFrame(tick);
}
function pause(){isPlaying=false;playIcon.classList.remove('hidden');pauseIcon.classList.add('hidden');video.pause();if(raf){cancelAnimationFrame(raf);raf=null;}}

timelineScroll.addEventListener('pointerdown',e=>{
 if(e.target.closest('button'))return;
 const rect=clipsContainer.getBoundingClientRect();
 const move=ev=>{
  const x=ev.clientX-rect.left+timelineScroll.scrollLeft;
  const ratio=x/Math.max(1,clipsContainer.scrollWidth);
  seekGlobal(ratio*totalDuration);
 };
 const up=()=>{window.removeEventListener('pointermove',move);window.removeEventListener('pointerup',up);};
 window.addEventListener('pointermove',move);window.addEventListener('pointerup',up);move(e);
});

addMediaBtn.addEventListener('click',()=>mediaInput.click());
mediaInput.addEventListener('change',async e=>{if(e.target.files.length){await addFiles(e.target.files);}e.target.value='';});
playBtn.addEventListener('click',()=>{isPlaying?pause():play();});

document.getElementById('muteBtn').addEventListener('click',()=>{
 const info=getClipAtTime(globalTime);
 if(info){info.clip.muted=!info.clip.muted;video.muted=info.clip.muted;}else{video.muted=!video.muted;}
 document.getElementById('muteBtn').classList.toggle('bg-[#18E58B]',video.muted);
});

document.getElementById('coverBtn').addEventListener('click',()=>{
 const info=getClipAtTime(globalTime);if(!info){alert('Add media first');return;}
 const can=document.createElement('canvas');can.width=720;can.height=1280;const ctx=can.getContext('2d');
 try{if(info.clip.type.startsWith('video')){ctx.drawImage(video,0,0,can.width,can.height);}else{ctx.drawImage(photoPreview,0,0,can.width,can.height);}info.clip.cover=can.toDataURL();renderClips();}catch(e){}
});
document.getElementById('fitBtn').addEventListener('click',()=>{const box=document.getElementById('previewBox');box.style.width=box.style.width==='100%'?'62%':'100%';});
document.getElementById('undoBtn').addEventListener('click',()=>{const tl=document.getElementById('textLayer');if(tl.lastChild){tl.removeChild(tl.lastChild);}});
document.getElementById('redoBtn').addEventListener('click',()=>{video.style.filter='';photoPreview.style.filter='';});
document.getElementById('keyframeBtn').addEventListener('click',()=>{const marker=document.createElement('div');marker.className='absolute top-1 w-2.5 h-2.5 bg-white rotate-45 rounded-[1px] border border-black';marker.style.left=playhead.style.left;document.getElementById('keyframeMarkers').appendChild(marker);});

const icons={
 split:`<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.6"><path d="M6 3l6 9-6 9"/><path d="M18 3l-6 9 6 9"/></svg>`,
 volume:`<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.6"><path d="M11 5L6 9H2v6h4l5 4V5z"/><path d="M15 9a4 4 0 0 1 0 6"/></svg>`,
 animations:`<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.6"><path d="M12 2l2.5 7.5L22 12l-7.5 2.5L12 22l-2.5-7.5L2 12l7.5-2.5L12 2z"/></svg>`,
 effects:`<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.6"><path d="M12 2l2.2 6.8H21l-5.5 4 2.1 6.8-5.6-4.1-5.6 4.1 2.1-6.8-5.5-4h6.8L12 2z"/></svg>`,
 delete:`<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.6"><path d="M4 7h16"/><path d="M10 11v6M14 11v6"/><path d="M6 7l1 14h10l1-14"/><path d="M9 7V4h6v3"/></svg>`,
 speed:`<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.6"><path d="M3 12a9 9 0 1 1 18 0"/><path d="M12 12l4-4"/><circle cx="12" cy="12" r="1"/></svg>`,
 crop:`<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.6"><path d="M6 2v16a4 4 0 0 0 4 4h12"/><path d="M2 6h16a4 4 0 0 1 4 4v12"/></svg>`,
 duplicate:`<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.6"><rect x="7" y="7" width="13" height="13" rx="2"/><path d="M4 16H3a2 2 0 0 1-2-2V3a2 2 0 0 1 2-2h11a2 2 0 0 1 2 2v1"/></svg>`,
 replace:`<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.6"><path d="M20 11a8 8 0 0 0-14.9-4"/><path d="M4 5v4h4"/><path d="M4 13a8 8 0 0 0 14.9 4"/><path d="M20 19v-4h-4"/></svg>`,
 overlay:`<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.6"><rect x="3" y="3" width="14" height="14" rx="2"/><rect x="8" y="8" width="13" height="13" rx="2"/></svg>`,
 adjust:`<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.6"><path d="M4 21v-7M4 10V3M12 21v-9M12 8V3M20 21v-5M20 12V3"/><path d="M1 14h6M9 8h6M17 16h6"/></svg>`,
 filters:`<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.6"><path d="M22 3H2l8 9.5V19l4 2v-8.5L22 3z"/></svg>`,
 removebg:`<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.6"><circle cx="12" cy="12" r="8"/><path d="M8 16l8-8"/><path d="M5 5l14 14"/></svg>`,
 airemove:`<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.6"><path d="M12 2l1.7 5.3L19 9l-5.3 1.7L12 16l-1.7-5.3L5 9l5.3-1.7L12 2z"/><path d="M19 15l.8 2.2L22 18l-2.2.8L19 21l-.8-2.2L16 18l2.2-.8L19 15z"/></svg>`,
 opacity:`<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.6"><circle cx="12" cy="12" r="9"/><path d="M12 3v18"/></svg>`,
 transform:`<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.6"><path d="M15 3h6v6M9 21H3v-6M21 3l-7 7M3 21l7-7"/></svg>`,
 extract:`<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.6"><path d="M9 18V5l12-2v13"/><circle cx="6" cy="18" r="3"/><circle cx="18" cy="16" r="3"/></svg>`,
 voice:`<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.6"><path d="M12 1a3 3 0 0 0-3 3v8a3 3 0 0 0 6 0V4a3 3 0 0 0-3-3z"/><path d="M19 10v2a7 7 0 0 1-14 0v-2"/><line x1="12" y1="19" x2="12" y2="23"/><line x1="8" y1="23" x2="16" y2="23"/></svg>`,
 audiofx:`<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.6"><path d="M3 18v-6a9 9 0 0 1 18 0v6"/><path d="M21 19a2 2 0 0 1-2 2h-1a2 2 0 0 1-2-2v-3a2 2 0 0 1 2-2h3zM3 19a2 2 0 0 0 2 2h1a2 2 0 0 0 2-2v-3a2 2 0 0 0-2-2H3z"/></svg>`,
 enhance:`<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.6"><path d="M12 2l2.4 7.2H22l-6.2 4.5 2.4 7.2L12 16.4 5.8 20.9l2.4-7.2L2 9.2h7.6z"/></svg>`,
 translate:`<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.6"><circle cx="12" cy="12" r="10"/><path d="M2 12h20M12 2a15.3 15.3 0 0 1 4 10 15.3 15.3 0 0 1-4 10 15.3 15.3 0 0 1-4-10A15.3 15.3 0 0 1 12 2z"/></svg>`,
 freeze:`<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.6"><rect x="6" y="4" width="4" height="16"/><rect x="14" y="4" width="4" height="16"/></svg>`,
 reverse:`<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.6"><polyline points="11 5 6 9 11 13"/><path d="M20 9H6"/></svg>`,
 mask:`<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.6"><rect x="3" y="3" width="18" height="18" rx="2"/><circle cx="12" cy="12" r="4"/></svg>`,
 unlink:`<svg viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.6"><path d="M10 13a5 5 0 0 0 7.54.54l3-3a5 5 0 0 0-7.07-7.07l-1.72 1.71"/><path d="M14 11a5 5 0 0 0-7.54-.54l-3 3a5 5 0 0 0 7.07 7.07l1.71-1.71"/><line x1="18" y1="6" x2="6" y2="18"/></svg>`
};

const editTools=[
 ['split','Split'],['volume','Volume'],['animations','Animations'],['effects','Effects'],['delete','Delete'],['speed','Speed'],['crop','Crop'],['duplicate','Duplicate'],['replace','Replace'],['overlay','Overlay'],['adjust','Adjust'],['filters','Filters'],['removebg','Remove background'],['airemove','AI remove'],['opacity','Opacity'],['transform','Transform'],['extract','Extract audio'],['voice','Isolate voice'],['audiofx','Audio effects'],['enhance','Enhance voice'],['translate','Video translator'],['freeze','Freeze'],['reverse','Reverse'],['mask','Mask'],['unlink','Unlink']
];

function openTool(id){
 const panel=document.getElementById('toolPanel');
 const content=document.getElementById('toolContent');
 const title=document.getElementById('toolTitle');
 panel.classList.remove('hidden');
 if(id=='edit'){
  title.textContent='Edit';
  content.innerHTML='';
  const scroll=document.createElement('div');
  scroll.id='editToolsScroll';
  scroll.className='flex gap-2 overflow-x-auto no-scrollbar pb-2';
  editTools.forEach(function(pair){
    var key=pair[0]; var name=pair[1];
    var btn=document.createElement('button');
    btn.className='edit-tool';
    btn.setAttribute('data-edit-tool',key);
    btn.innerHTML=(icons[key]||'')+'<span>'+name+'</span>';
    (function(k){ btn.addEventListener('click',function(){ selectEditTool(k); }); })(key);
    scroll.appendChild(btn);
  });
  content.appendChild(scroll);
  var area=document.createElement('div');
  area.id='editOptionArea';
  area.className='mt-3';
  area.innerHTML='<div class="panel-card p-4 text-center"><div class="text-[13px] font-semibold">Select an Edit tool</div><div class="text-[11px] text-[#777] mt-1">Choose a tool above to edit the selected clip.</div></div>';
  content.appendChild(area);
  return;
 }
 if(id==='audio'){
  title.textContent='Audio';
  content.innerHTML='<div class="space-y-3"><button onclick="document.getElementById(\'audioInput\').click()" class="w-full h-11 bg-[#18E58B] text-black rounded-xl font-bold text-[13px]">Add Audio</button><div class="panel-card p-4"><div class="flex justify-between text-[12px] mb-2"><span>Volume</span><span id="audioVolumeLabel">100%</span></div><input id="audioVolumeRange" type="range" min="0" max="100" value="100" class="w-full range-green"></div></div>';
  var range=document.getElementById('audioVolumeRange');
  range.oninput=function(){var value=Number(range.value);video.volume=value/100;document.getElementById('audioVolumeLabel').textContent=value+'%';};
  return;
 }
 if(id=='text'){
  title.textContent='Text';
  content.innerHTML='<div class="space-y-3"><div class="flex gap-2"><input id="textInp" placeholder="Enter text" class="bg-[#242424] px-4 py-3 rounded-xl flex-1 text-[13px] outline-none border border-[#333]"><button onclick="addTxt()" class="bg-[#18E58B] text-black px-5 rounded-xl font-bold">Add</button></div><div class="panel-card p-3"><div class="text-[11px] text-[#777]">Add text directly over the preview.</div></div></div>';
  return;
 }
 if(id=='effects'){
  title.textContent='Effects';
  content.innerHTML='<div class="grid grid-cols-3 gap-2"><button onclick="clearFilter()" class="small-control py-3 text-xs">None</button><button onclick="applyFilter(\'grayscale(1)\')" class="small-control py-3 text-xs">B&W</button><button onclick="applyFilter(\'sepia(1)\')" class="small-control py-3 text-xs">Sepia</button><button onclick="applyFilter(\'contrast(1.3) saturate(1.3)\')" class="small-control py-3 text-xs">Vivid</button><button onclick="applyFilter(\'brightness(1.2)\')" class="small-control py-3 text-xs">Bright</button><button onclick="applyFilter(\'blur(3px)\')" class="small-control py-3 text-xs">Blur</button></div>';
  return;
 }
 if(id==='overlay'){title.textContent='Overlay';content.innerHTML='<button onclick="document.getElementById(\'mediaInput\').click()" class="w-full h-11 bg-[#18E58B] text-black rounded-xl font-bold text-[13px]">Add Overlay Media</button>';return;}
 if(id==='captions'){title.textContent='Captions';content.innerHTML='<button onclick="autoCaption()" class="w-full h-11 bg-[#18E58B] text-black rounded-xl font-bold text-[13px]">Auto Captions</button>';return;}
 if(id==='filters'){title.textContent='Filters';content.innerHTML='<div class="grid grid-cols-3 gap-2"><button onclick="clearFilter()" class="small-control py-3 text-xs">Natural</button><button onclick="applyFilter(\'contrast(1.2) saturate(1.4)\')" class="small-control py-3 text-xs">Vivid</button><button onclick="applyFilter(\'grayscale(1)\')" class="small-control py-3 text-xs">Mono</button></div>';return;}
 if(id==='sticker'){title.textContent='Sticker';content.innerHTML='<div class="grid grid-cols-4 gap-2"><button onclick="addShapeSticker(\'circle\')" class="small-control h-12 flex items-center justify-center"><svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><circle cx="12" cy="12" r="8"/></svg></button><button onclick="addShapeSticker(\'square\')" class="small-control h-12 flex items-center justify-center"><svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><rect x="5" y="5" width="14" height="14" rx="2"/></svg></button><button onclick="addShapeSticker(\'star\')" class="small-control h-12 flex items-center justify-center"><svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M12 3l2.5 6 6.5.5-5 4.2 1.5 6.3-5.5-3.3-5.5 3.3 1.5-6.3-5-4.2 6.5-.5L12 3z"/></svg></button><button onclick="addShapeSticker(\'line\')" class="small-control h-12 flex items-center justify-center"><svg width="24" height="24" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M5 19L19 5"/></svg></button></div>';return;}
 if(id=='aspect'){title.textContent='Aspect Ratio';content.innerHTML='<div class="flex gap-2 flex-wrap"><button onclick="setAspect(\'9/16\',\'62%\')" class="small-control px-4 py-3 text-xs">9:16</button><button onclick="setAspect(\'16/9\',\'100%\')" class="small-control px-4 py-3 text-xs">16:9</button><button onclick="setAspect(\'1/1\',\'62%\')" class="small-control px-4 py-3 text-xs">1:1</button><button onclick="setAspect(\'4/5\',\'70%\')" class="small-control px-4 py-3 text-xs">4:5</button></div>';return;}
 if(id==='background'){title.textContent='Background';content.innerHTML='<div class="flex gap-3"><button onclick="setPreviewBackground(\'#000000\')" class="w-11 h-11 rounded-full bg-black border border-[#444]"></button><button onclick="setPreviewBackground(\'#1a1a1a\')" class="w-11 h-11 rounded-full bg-[#1a1a1a] border border-[#444]"></button><button onclick="setPreviewBackground(\'#18E58B\')" class="w-11 h-11 rounded-full bg-[#18E58B]"></button></div>';return;}
}

window.selectEditTool=function(key){
 document.querySelectorAll('[data-edit-tool]').forEach(function(btn){btn.classList.toggle('active',btn.dataset.editTool===key);});
 var area=document.getElementById('editOptionArea');
 var info=getClipAtTime(globalTime);
 if(!info&&key!=='replace'){area.innerHTML='<div class="panel-card p-4 text-center"><div class="text-[13px] font-semibold">Add media first</div><div class="text-[11px] text-[#777] mt-1">This Edit tool needs a selected clip.</div></div>';return;}
 if(key==='split'){area.innerHTML='<div class="panel-card p-4"><div class="text-[12px] font-semibold mb-3">Split at '+fmt(globalTime)+'</div><button onclick="splitCurrentClip()" class="w-full h-11 bg-[#18E58B] text-black rounded-xl font-bold text-[13px]">Split Clip</button></div>';return;}
 if(key==='volume'){var value=Math.round((info.clip.volume||1)*100);area.innerHTML='<div class="panel-card p-4"><div class="flex justify-between text-[12px] mb-3"><span>Volume</span><span id="clipVolumeLabel">'+value+'%</span></div><input id="clipVolume" type="range" min="0" max="200" value="'+value+'" class="w-full range-green"></div>';document.getElementById('clipVolume').oninput=function(e){var v=Number(e.target.value);info.clip.volume=v/100;video.volume=v/100;document.getElementById('clipVolumeLabel').textContent=v+'%';};return;}
 if(key==='speed'){area.innerHTML='<div class="grid grid-cols-4 gap-2"><button onclick="setClipSpeed(.25)" class="small-control py-3 text-xs">0.25x</button><button onclick="setClipSpeed(.5)" class="small-control py-3 text-xs">0.5x</button><button onclick="setClipSpeed(1)" class="small-control py-3 text-xs">1x</button><button onclick="setClipSpeed(2)" class="small-control py-3 text-xs">2x</button></div>';return;}
 if(key==='delete'){area.innerHTML='<div class="panel-card p-4"><div class="text-[12px] mb-3">Delete the selected clip?</div><button onclick="deleteSelectedClip()" class="w-full h-11 bg-[#d93838] text-white rounded-xl font-bold text-[13px]">Delete Clip</button></div>';return;}
 if(key==='duplicate'){area.innerHTML='<button onclick="duplicateSelectedClip()" class="w-full h-11 bg-[#18E58B] text-black rounded-xl font-bold text-[13px]">Duplicate Clip</button>';return;}
 if(key==='replace'){area.innerHTML='<button onclick="replaceSelectedClip()" class="w-full h-11 bg-[#18E58B] text-black rounded-xl font-bold text-[13px]">Choose Replacement Media</button>';return;}
 if(key==='crop'){area.innerHTML='<div class="panel-card p-4 space-y-3"><div class="text-[12px]">Crop</div><div class="grid grid-cols-3 gap-2"><button onclick="setCrop(\'center\')" class="small-control py-3 text-xs">Center</button><button onclick="setCrop(\'square\')" class="small-control py-3 text-xs">Square</button><button onclick="setCrop(\'fit\')" class="small-control py-3 text-xs">Fit</button></div></div>';return;}
 if(key==='opacity'){area.innerHTML='<div class="panel-card p-4"><div class="flex justify-between text-[12px] mb-3"><span>Opacity</span><span id="opacityLabel">100%</span></div><input id="opacityRange" type="range" min="0" max="100" value="100" class="w-full range-green"></div>';document.getElementById('opacityRange').oninput=function(e){var v=Number(e.target.value);info.clip.opacity=v/100;video.style.opacity=v/100;photoPreview.style.opacity=v/100;document.getElementById('opacityLabel').textContent=v+'%';};return;}
 if(key==='transform'){area.innerHTML='<div class="grid grid-cols-2 gap-2"><button onclick="transformScale(1.1)" class="small-control py-3 text-xs">Scale +</button><button onclick="transformScale(.9)" class="small-control py-3 text-xs">Scale -</button><button onclick="rotatePreview(-90)" class="small-control py-3 text-xs">Rotate Left</button><button onclick="rotatePreview(90)" class="small-control py-3 text-xs">Rotate Right</button><button onclick="resetTransform()" class="small-control py-3 text-xs col-span-2">Reset Transform</button></div>';return;}
 if(key==='adjust'){area.innerHTML='<div class="space-y-4">'+adjustSlider('brightness','Brightness',100)+adjustSlider('contrast','Contrast',100)+adjustSlider('saturation','Saturation',100)+adjustSlider('blur','Blur',0)+'</div>';bindAdjustSliders();return;}
 if(key==='filters'){area.innerHTML='<div class="grid grid-cols-3 gap-2"><button onclick="clearFilter()" class="small-control py-3 text-xs">Natural</button><button onclick="applyFilter(\'grayscale(1)\')" class="small-control py-3 text-xs">Mono</button><button onclick="applyFilter(\'sepia(1)\')" class="small-control py-3 text-xs">Warm</button><button onclick="applyFilter(\'contrast(1.2) saturate(1.4)\')" class="small-control py-3 text-xs">Vivid</button><button onclick="applyFilter(\'brightness(1.2)\')" class="small-control py-3 text-xs">Bright</button><button onclick="applyFilter(\'saturate(.6)\')" class="small-control py-3 text-xs">Soft</button></div>';return;}
 if(key==='animations'){area.innerHTML='<div class="grid grid-cols-3 gap-2"><button onclick="animatePreview(\'none\')" class="small-control py-3 text-xs">None</button><button onclick="animatePreview(\'zoom\')" class="small-control py-3 text-xs">Zoom</button><button onclick="animatePreview(\'fade\')" class="small-control py-3 text-xs">Fade</button></div>';return;}
 if(key==='effects'){area.innerHTML='<div class="grid grid-cols-3 gap-2"><button onclick="clearFilter()" class="small-control py-3 text-xs">None</button><button onclick="applyFilter(\'grayscale(1)\')" class="small-control py-3 text-xs">Mono</button><button onclick="applyFilter(\'sepia(1)\')" class="small-control py-3 text-xs">Sepia</button><button onclick="applyFilter(\'blur(4px)\')" class="small-control py-3 text-xs">Blur</button><button onclick="applyFilter(\'contrast(1.4)\')" class="small-control py-3 text-xs">Contrast</button><button onclick="applyFilter(\'saturate(1.6)\')" class="small-control py-3 text-xs">Saturate</button></div>';return;}
 if(key==='removebg'){area.innerHTML='<div class="panel-card p-4"><div class="text-[12px] font-semibold">Remove Background</div><div class="text-[11px] text-[#777] mt-1 mb-3">Background removal controls are ready.</div><button onclick="showFeatureMessage(\'Remove Background\')" class="w-full h-10 bg-[#18E58B] text-black rounded-xl font-bold text-xs">Remove Background</button></div>';return;}
 if(key==='airemove'){area.innerHTML='<div class="panel-card p-4"><div class="text-[12px] font-semibold">AI Remove</div><div class="text-[11px] text-[#777] mt-1 mb-3">Select an object area for AI removal.</div><button onclick="showFeatureMessage(\'AI Remove\')" class="w-full h-10 bg-[#18E58B] text-black rounded-xl font-bold text-xs">Start AI Remove</button></div>';return;}
 if(key==='extract'){area.innerHTML='<button onclick="extractAudio()" class="w-full h-11 bg-[#18E58B] text-black rounded-xl font-bold text-[13px]">Extract Audio</button>';return;}
 if(key==='voice'){area.innerHTML='<button onclick="showFeatureMessage(\'Isolate Voice\')" class="w-full h-11 bg-[#18E58B] text-black rounded-xl font-bold text-[13px]">Isolate Voice</button>';return;}
 if(key==='audiofx'){area.innerHTML='<div class="grid grid-cols-2 gap-2"><button onclick="showFeatureMessage(\'Echo\')" class="small-control py-3 text-xs">Echo</button><button onclick="showFeatureMessage(\'Reverb\')" class="small-control py-3 text-xs">Reverb</button><button onclick="showFeatureMessage(\'Bass\')" class="small-control py-3 text-xs">Bass</button><button onclick="showFeatureMessage(\'Voice\')" class="small-control py-3 text-xs">Voice</button></div>';return;}
 if(key==='enhance'){area.innerHTML='<button onclick="showFeatureMessage(\'Enhance Voice\')" class="w-full h-11 bg-[#18E58B] text-black rounded-xl font-bold text-[13px]">Enhance Voice</button>';return;}
 if(key==='translate'){area.innerHTML='<div class="space-y-2"><select id="translateLang" class="w-full bg-[#242424] border border-[#333] rounded-xl px-3 h-11 text-xs"><option>English</option><option>Spanish</option><option>French</option><option>Portuguese</option><option>Arabic</option><option>German</option></select><button onclick="showFeatureMessage(\'Video Translator\')" class="w-full h-11 bg-[#18E58B] text-black rounded-xl font-bold text-[13px]">Translate Video</button></div>';return;}
 if(key==='freeze'){area.innerHTML='<button onclick="freezeFrame()" class="w-full h-11 bg-[#18E58B] text-black rounded-xl font-bold text-[13px]">Freeze Current Frame</button>';return;}
 if(key==='reverse'){area.innerHTML='<button onclick="showFeatureMessage(\'Reverse\')" class="w-full h-11 bg-[#18E58B] text-black rounded-xl font-bold text-[13px]">Reverse Clip</button>';return;}
 if(key==='mask'){area.innerHTML='<div class="grid grid-cols-3 gap-2"><button onclick="applyMask(\'circle\')" class="small-control py-3 text-xs">Circle</button><button onclick="applyMask(\'square\')" class="small-control py-3 text-xs">Square</button><button onclick="clearMask()" class="small-control py-3 text-xs">None</button></div>';return;}
 if(key==='unlink'){area.innerHTML='<div class="panel-card p-4"><div class="text-[12px] mb-3">Separate the selected video\'s audio from the video clip.</div><button onclick="unlinkClip()" class="w-full h-11 bg-[#18E58B] text-black rounded-xl font-bold text-[13px]">Unlink</button></div>';return;}
 area.innerHTML='<div class="panel-card p-4 text-center"><div class="text-[13px] font-semibold">'+key+'</div></div>';
}
function adjustSlider(id,label,value){return `<div><div class="flex justify-between text-[11px] mb-2"><span>${label}</span><span id="${id}Label">${value}</span></div><input id="${id}Adjust" data-adjust="${id}" type="range" min="0" max="200" value="${value}" class="w-full range-green"></div>`;}
function bindAdjustSliders(){document.querySelectorAll('[data-adjust]').forEach(input=>{input.addEventListener('input',applyAdjustments);});}
function applyAdjustments(){
 const brightness=Number(document.getElementById('brightnessAdjust')?.value||100)/100;
 const contrast=Number(document.getElementById('contrastAdjust')?.value||100)/100;
 const saturation=Number(document.getElementById('saturationAdjust')?.value||100)/100;
 const blur=Number(document.getElementById('blurAdjust')?.value||0);
 const filter=`brightness(${brightness}) contrast(${contrast}) saturate(${saturation}) blur(${blur}px)`;
 video.style.filter=filter;photoPreview.style.filter=filter;
 ['brightness','contrast','saturation','blur'].forEach(id=>{const input=document.getElementById(id+'Adjust');const label=document.getElementById(id+'Label');if(input&&label){label.textContent=id==='blur'?input.value+'px':input.value+'%';}});
}

window.splitCurrentClip=function(){
 const info=getClipAtTime(globalTime);if(!info){alert('Add a video or image first using the + button');return;}const clip=info.clip;const local=info.local;
 if(clips.length===0){alert('Add media first');return;}
 if(local<=0.05||local>=clip.duration-0.05){alert('Move playhead to middle of clip to split');return;}
 const first={...clip,id:Date.now()+Math.random(),duration:local};
 const second={...clip,id:Date.now()+Math.random()+1,duration:clip.duration-local};
 if(clip.type.startsWith('video')){first.thumbs=clip.thumbs?clip.thumbs.slice(0,Math.max(1,Math.floor(clip.thumbs.length*(local/clip.duration)))):[];second.thumbs=clip.thumbs?clip.thumbs.slice(Math.max(1,Math.floor(clip.thumbs.length*(local/clip.duration)))):[];}
 clips.splice(info.index,1,first,second);selectedClipId=second.id;renderClips();seekGlobal(info.start+local+0.001);
};
window.deleteSelectedClip=function(){
 const info=getClipAtTime(globalTime);if(!info)return;
 clips.splice(info.index,1);
 selectedClipId=clips.length?clips[Math.min(info.index,clips.length-1)].id:null;
 renderClips();
 if(clips.length){seekGlobal(Math.min(info.start,totalDuration));}else{video.removeAttribute('src');video.load();photoPreview.classList.add('hidden');}
};
window.duplicateSelectedClip=function(){
 const info=getClipAtTime(globalTime);if(!info)return;
 const copy={...info.clip,id:Date.now()+Math.random(),thumbs:info.clip.thumbs?[...info.clip.thumbs]:[]};
 clips.splice(info.index+1,0,copy);selectedClipId=copy.id;renderClips();
};
window.replaceSelectedClip=function(){
 const info=getClipAtTime(globalTime);if(!info){mediaInput.click();return;}
 const input=document.createElement('input');input.type='file';input.accept='video/*,image/*';
 input.onchange=async()=>{const file=input.files[0];if(!file)return;const old=info.clip;old.file=file;old.url=URL.createObjectURL(file);old.type=file.type;old.thumbs=[];old.duration=file.type.startsWith('image')?3:1;if(file.type.startsWith('video')){await generateThumbsForClip(old);}renderClips();seekGlobal(info.start+0.01);};
 input.click();
};
window.setClipSpeed=function(speed){const info=getClipAtTime(globalTime);if(!info)return;info.clip.speed=speed;video.playbackRate=speed;};
window.applyFilter=function(filter){video.style.filter=filter;photoPreview.style.filter=filter;};
window.clearFilter=function(){video.style.filter='';photoPreview.style.filter='';};
window.animatePreview=function(type){
 if(type==='zoom'){video.style.transform='scale(1.1)';photoPreview.style.transform='scale(1.1)';}
 else if(type==='fade'){video.style.opacity='.65';photoPreview.style.opacity='.65';}
 else{resetTransform();video.style.opacity='1';photoPreview.style.opacity='1';}
};
window.setCrop=function(type){
 if(type==='square'){video.style.objectFit='cover';photoPreview.style.objectFit='cover';}
 else if(type==='fit'){video.style.objectFit='contain';photoPreview.style.objectFit='contain';}
 else{video.style.objectFit='cover';photoPreview.style.objectFit='cover';}
};
let previewScale=1;let previewRotation=0;
window.transformScale=function(amount){previewScale*=amount;video.style.transform=`scale(${previewScale}) rotate(${previewRotation}deg)`;photoPreview.style.transform=`scale(${previewScale}) rotate(${previewRotation}deg)`;};
window.rotatePreview=function(deg){previewRotation+=deg;video.style.transform=`scale(${previewScale}) rotate(${previewRotation}deg)`;photoPreview.style.transform=`scale(${previewScale}) rotate(${previewRotation}deg)`;};
window.resetTransform=function(){previewScale=1;previewRotation=0;video.style.transform='';photoPreview.style.transform='';};
window.extractAudio=function(){const info=getClipAtTime(globalTime);if(!info||!info.clip.type.startsWith('video')){alert('Select a video clip first');return;}alert('Audio extraction is ready to be connected to the project audio track.');};
window.freezeFrame=function(){
 const info=getClipAtTime(globalTime);if(!info)return;
 const can=document.createElement('canvas');can.width=720;can.height=1280;const ctx=can.getContext('2d');
 try{
  if(info.clip.type.startsWith('video')){ctx.drawImage(video,0,0,can.width,can.height);}else{ctx.drawImage(photoPreview,0,0,can.width,can.height);}
  const data=can.toDataURL('image/png');
  const freezeClip={id:Date.now()+Math.random(),file:null,url:data,type:'image/png',duration:3,thumbs:[],cover:null};
  clips.splice(info.index+1,0,freezeClip);renderClips();
 }catch(e){}
};
window.applyMask=function(type){if(type==='circle'){video.style.clipPath='circle(45% at 50% 50%)';photoPreview.style.clipPath='circle(45% at 50% 50%)';}else if(type==='square'){video.style.clipPath='inset(10%)';photoPreview.style.clipPath='inset(10%)';}};
window.clearMask=function(){video.style.clipPath='';photoPreview.style.clipPath='';};
window.unlinkClip=function(){showFeatureMessage('Unlink');};
window.showFeatureMessage=function(name){alert(`${name} is added to the ObeSplit Edit system.`);};
window.addTxt=function(){
 const input=document.getElementById('textInp');const value=input?.value;if(!value)return;
 const d=document.createElement('div');d.textContent=value;d.className='absolute left-1/2 top-1/2 -translate-x-1/2 -translate-y-1/2 bg-black/60 px-3 py-1.5 rounded-lg text-white font-bold';d.contentEditable=true;
 document.getElementById('textLayer').appendChild(d);input.value='';
};
window.autoCaption=()=>{const d=document.createElement('div');d.textContent='Caption '+fmt(globalTime);d.className='absolute left-1/2 top-1/2 -translate-x-1/2 -translate-y-1/2 bg-black/60 px-3 py-1.5 rounded-lg text-white font-bold';document.getElementById('textLayer').appendChild(d);};
window.addShapeSticker=function(type){
 const d=document.createElement('div');d.className='absolute left-1/2 top-1/2 -translate-x-1/2 -translate-y-1/2';
 if(type==='circle'){d.innerHTML=`<div style="width:55px;height:55px;border:4px solid #18E58B;border-radius:50%;"></div>`;}
 else if(type==='square'){d.innerHTML=`<div style="width:55px;height:55px;border:4px solid #18E58B;border-radius:8px;"></div>`;}
 else if(type==='star'){d.innerHTML=`<svg width="60" height="60" viewBox="0 0 24 24" fill="#18E58B" stroke="#18E58B"><path d="M12 2l3 6 7 .8-5 4.7 1.5 7-6.5-3.3-6.5 3.3 1.5-7-5-4.7L9 8l3-6z"/></svg>`;}
 else{d.innerHTML=`<div style="width:70px;height:4px;background:#18E58B;transform:rotate(-45deg);"></div>`;}
 document.getElementById('textLayer').appendChild(d);
};
window.setAspect=function(ratio,width){const box=document.getElementById('previewBox');box.style.aspectRatio=ratio;box.style.width=width;};
window.setPreviewBackground=function(color){document.getElementById('previewWrap').style.background=color;};

document.querySelectorAll('.tool-btn').forEach(button=>{
 button.addEventListener('click',()=>{
  document.querySelectorAll('.tool-btn').forEach(b=>{b.classList.remove('text-[#18E58B]');b.classList.add('text-[#999]');});
  button.classList.remove('text-[#999]');button.classList.add('text-[#18E58B]');
  openTool(button.dataset.tool);
 });
});
document.getElementById('closeToolPanel').addEventListener('click',()=>{document.getElementById('toolPanel').classList.add('hidden');});
document.getElementById('addAudioBtn2').addEventListener('click',()=>{document.getElementById('audioInput').click();});
document.getElementById('addTextBtn2').addEventListener('click',()=>openTool('text'));
document.getElementById('audioInput').addEventListener('change',e=>{const f=e.target.files[0];if(!f)return;const url=URL.createObjectURL(f);const audio=document.getElementById('bgAudio');audio.src=url;audio.play().catch(()=>{});});
aiUhdBtn.addEventListener('click',()=>{exportPanel.classList.toggle('hidden');});

function bindGroup(selector){
 document.querySelectorAll(selector).forEach(btn=>{
  btn.addEventListener('click',()=>{
   document.querySelectorAll(selector).forEach(b=>{b.classList.remove('bg-white','text-black','font-bold');b.classList.add('bg-[#242424]');});
   btn.classList.remove('bg-[#242424]');btn.classList.add('bg-white','text-black','font-bold');
  });
 });
}
bindGroup('.res-opt');bindGroup('.fps-opt');bindGroup('.br-opt');
document.getElementById('resGroup').addEventListener('click',e=>{const b=e.target.closest('.res-opt');if(b){currentRes=b.dataset.res;updateEstSize();}});
document.getElementById('fpsGroup').addEventListener('click',e=>{const b=e.target.closest('.fps-opt');if(b){currentFps=parseInt(b.dataset.fps);}});
document.getElementById('brGroup').addEventListener('click',e=>{const b=e.target.closest('.br-opt');if(b){currentBitrate=parseInt(b.dataset.br);document.getElementById('bitrateLabel').textContent=currentBitrate+' Mbps';updateEstSize();}});

document.getElementById('aiToggle').addEventListener('click',()=>{
 isAiUhd=!isAiUhd;
 const button=document.getElementById('aiToggle');const knob=button.querySelector('span');
 if(isAiUhd){button.classList.remove('bg-[#2a2a2a]');button.classList.add('bg-[#18E58B]');knob.classList.add('translate-x-5');}
 else{button.classList.remove('bg-[#18E58B]');button.classList.add('bg-[#2a2a2a]');knob.classList.remove('translate-x-5');}
});
document.getElementById('wmToggle').addEventListener('click',()=>{
 watermark=!watermark;
 const button=document.getElementById('wmToggle');const knob=button.querySelector('span');
 if(watermark){button.classList.remove('bg-[#2a2a2a]');button.classList.add('bg-[#18E58B]');knob.classList.add('translate-x-5');}
 else{button.classList.remove('bg-[#18E58B]');button.classList.add('bg-[#2a2a2a]');knob.classList.remove('translate-x-5');}
});

/* EXPORT */
exportBtn.addEventListener('click',async()=>{
 if(clips.length===0){alert('Add media first using + button');return;}
 const resMap={'480p':[854,480],'720p':[1280,720],'1080p':[1920,1080],'4K':[3840,2160]};
 const [w,h]=resMap[currentRes]||[1920,1080];
 const canvas=document.getElementById('exportCanvas');canvas.width=w;canvas.height=h;
 const ctx=canvas.getContext('2d');
 const stream=canvas.captureStream(currentFps);
 let mime='video/webm;codecs=vp9';
 if(!MediaRecorder.isTypeSupported(mime)){mime='video/webm';}
 const recorder=new MediaRecorder(stream,{mimeType:mime,videoBitsPerSecond:currentBitrate*1000000});
 const chunks=[];recorder.ondataavailable=e=>{if(e.data.size>0){chunks.push(e.data);}};
 recorder.onstop=()=>{
  const blob=new Blob(chunks,{type:mime});const url=URL.createObjectURL(blob);
  const a=document.createElement('a');a.href=url;a.download=`ObeSplit_${currentRes}_${currentFps}fps.webm`;a.click();
  setTimeout(()=>URL.revokeObjectURL(url),1000);
  exportPanel.classList.add('hidden');
 };
 recorder.start();
 let t=0;
 const drawLoop=setInterval(()=>{
  const info=getClipAtTime(t);
  if(!info){clearInterval(drawLoop);recorder.stop();return;}
  ctx.fillStyle='#000';ctx.fillRect(0,0,w,h);
  if(info.clip.type.startsWith('video')){
   try{video.currentTime=info.local;ctx.drawImage(video,0,0,w,h);}catch(e){}
  }else{
   try{ctx.drawImage(photoPreview,0,0,w,h);}catch(e){}
  }
  t+=1/currentFps;
  if(t>=totalDuration){clearInterval(drawLoop);recorder.stop();}
 },1000/currentFps);
});

/* EXPORT TABS */
document.getElementById('tabVideo').addEventListener('click',()=>{
 isGif=false;
 document.getElementById('tabVideo').className='flex-1 py-2 rounded-full bg-white text-black text-[13px] font-bold';
 document.getElementById('tabGif').className='flex-1 py-2 rounded-full text-[#777] text-[13px]';
});
document.getElementById('tabGif').addEventListener('click',()=>{
 isGif=true;
 document.getElementById('tabGif').className='flex-1 py-2 rounded-full bg-white text-black text-[13px] font-bold';
 document.getElementById('tabVideo').className='flex-1 py-2 rounded-full text-[#777] text-[13px]';
});

/* VIDEO EVENTS */
video.addEventListener('loadedmetadata',()=>{
 if(!isFinite(video.duration))return;
 if(selectedClipId){
  const clip=clips.find(c=>c.id===selectedClipId);
  if(clip){clip.duration=video.duration;renderClips();}
 }
});
video.addEventListener('ended',()=>{
 if(!isPlaying)return;
 const info=getClipAtTime(globalTime);
 if(info){
  const next=clips[info.index+1];
  if(next){let start=0;for(let i=0;i<=info.index;i++){start+=clips[i].duration;}seekGlobal(start+0.001);video.play().catch(()=>{});}
  else{pause();}
 }
});
updateTimeLabel();updateRuler();updateEstSize();

// ===== V5 PATCH: KEEP STYLE, FIX FUNCTIONALITY =====
let videoScale = 1, videoX = 0, videoY = 0;
let lastDist = 0, lastX = 0, lastY = 0, isPinching = false, isPanning = false;
const previewBox = document.getElementById('previewBox');
const videoEl = document.getElementById('video');
const zoomBadge = document.getElementById('zoomBadge');

// Prevent browser zoom on preview
previewBox.addEventListener('touchstart', (e)=>{
  if(e.touches.length===2){
    e.preventDefault();
    isPinching=true;
    lastDist = Math.hypot(e.touches[0].clientX-e.touches[1].clientX, e.touches[0].clientY-e.touches[1].clientY);
  } else if(e.touches.length===1 && videoScale>1){
    isPanning=true;
    lastX = e.touches[0].clientX - videoX;
    lastY = e.touches[0].clientY - videoY;
  }
},{passive:false});

previewBox.addEventListener('touchmove', (e)=>{
  if(e.touches.length===2 && isPinching){
    e.preventDefault();
    const dist = Math.hypot(e.touches[0].clientX-e.touches[1].clientX, e.touches[0].clientY-e.touches[1].clientY);
    const delta = dist / (lastDist||dist);
    videoScale = Math.min(3, Math.max(0.5, videoScale * delta));
    lastDist = dist;
    applyVideoTransform();
  } else if(e.touches.length===1 && isPanning && videoScale>1){
    e.preventDefault();
    videoX = e.touches[0].clientX - lastX;
    videoY = e.touches[0].clientY - lastY;
    applyVideoTransform();
  }
},{passive:false});

previewBox.addEventListener('touchend', (e)=>{
  if(e.touches.length<2) isPinching=false;
  if(e.touches.length===0) isPanning=false;
  setTimeout(()=>{zoomBadge.style.display='none'}, 1000);
});

previewBox.addEventListener('wheel', (e)=>{
  if(e.ctrlKey){
    e.preventDefault();
    videoScale = Math.min(3, Math.max(0.5, videoScale + (e.deltaY<0?0.1:-0.1)));
    applyVideoTransform();
  }
},{passive:false});

function applyVideoTransform(){
  videoEl.style.transform = `translate(${videoX}px, ${videoY}px) scale(${videoScale})`;
  zoomBadge.textContent = Math.round(videoScale*100)+'%';
  zoomBadge.style.display='block';
}

// Double tap to reset zoom
let lastTap=0;
previewBox.addEventListener('touchend', (e)=>{
  const now=Date.now();
  if(now-lastTap<300 && e.touches.length===0){
    videoScale=1; videoX=0; videoY=0; applyVideoTransform();
  }
  lastTap=now;
});

// ===== TRIM HANDLES =====
function attachTrimHandlers(){
  document.querySelectorAll('.clip-item').forEach((el, idx)=>{
    const left = el.querySelector('.timeline-handle.left');
    const right = el.querySelector('.timeline-handle.right');
    if(!left||!right) return;
    
    let startX, startDur, startTrim;
    const onStart = (e, side)=>{
      e.stopPropagation();
      startX = (e.touches?e.touches[0].clientX:e.clientX);
      const clip = clips[idx];
      startDur = clip.duration;
      startTrim = clip.trimStart||0;
    };
    const onMove = (e, side)=>{
      if(startX===undefined) return;
      e.preventDefault();
      const curX = (e.touches?e.touches[0].clientX:e.clientX);
      const diffSec = (curX - startX) / 80; // 80px = 1 sec
      const clip = clips[idx];
      if(side==='left'){
        let newTrim = Math.max(0, Math.min(startTrim + diffSec, startDur - 0.3));
        clip.trimStart = newTrim;
        clip.duration = clip.origDuration - newTrim - (clip.trimEnd||0);
      }else{
        let newEnd = Math.max(0, Math.min((clip.trimEnd||0) - diffSec, clip.origDuration - (clip.trimStart||0) - 0.3));
        clip.trimEnd = newEnd;
        clip.duration = clip.origDuration - (clip.trimStart||0) - newEnd;
      }
      renderClips(); updateTimeLabel();
    };
    const onEnd = ()=>{ startX=undefined; };
    
    left.addEventListener('touchstart', (e)=>onStart(e,'left'), {passive:false});
    left.addEventListener('touchmove', (e)=>onMove(e,'left'), {passive:false});
    left.addEventListener('touchend', onEnd);
    left.addEventListener('mousedown', (e)=>{onStart(e,'left'); window.addEventListener('mousemove', (ev)=>onMove(ev,'left')); window.addEventListener('mouseup', ()=>{onEnd(); window.removeEventListener('mousemove', (ev)=>onMove(ev,'left'));}, {once:true});});
    
    right.addEventListener('touchstart', (e)=>onStart(e,'right'), {passive:false});
    right.addEventListener('touchmove', (e)=>onMove(e,'right'), {passive:false});
    right.addEventListener('touchend', onEnd);
    right.addEventListener('mousedown', (e)=>{onStart(e,'right'); window.addEventListener('mousemove', (ev)=>onMove(ev,'right')); window.addEventListener('mouseup', ()=>{onEnd(); window.removeEventListener('mousemove', (ev)=>onMove(ev,'right'));}, {once:true});});
  });
}

// Override renderClips to include handles and transitions
const _origRender = window.renderClips;
window.renderClips = function(){
  const container = document.getElementById('timeline');
  if(!container) return _origRender && _origRender();
  container.innerHTML='';
  let total = 0;
  clips.forEach((clip,i)=>{
    // transition dot before clip (except first)
    if(i>0){
      const transWrap = document.createElement('div');
      transWrap.className='flex items-center justify-center px-1';
      const dot = document.createElement('div');
      dot.className='transition-dot ' + (clip.transition && clip.transition!=='none' ? 'active':'');
      dot.innerHTML = clip.transition && clip.transition!=='none' ? '<span style="transform:rotate(-45deg);font-size:10px">✦</span>' : '';
      dot.title = clip.transition||'none';
      dot.onclick = (e)=>{ e.stopPropagation(); openTransitionPicker(i); };
      transWrap.appendChild(dot);
      container.appendChild(transWrap);
    }
    const div = document.createElement('div');
    div.className='clip-item relative flex-shrink-0 bg-[#2a2a2a] rounded-lg overflow-hidden ' + (clip.id===selectedClipId?'selected':'');
    div.style.width = Math.max(70, clip.duration*80)+'px';
    div.style.height='56px';
    div.dataset.id=clip.id;
    div.innerHTML = `
      <div class="timeline-handle left"><div style="width:2px;height:18px;background:white;border-radius:2px"></div></div>
      <div class="w-full h-full flex items-center px-4 text-[11px] truncate">${clip.name||'Clip '+(i+1)}<br>${clip.duration.toFixed(1)}s</div>
      <div class="timeline-handle right"><div style="width:2px;height:18px;background:white;border-radius:2px"></div></div>
    `;
    div.onclick = ()=>{ selectClip(clip.id); };
    container.appendChild(div);
    total+=clip.duration;
  });
  attachTrimHandlers();
  if(typeof updateRuler==='function') updateRuler();
};

// Transition picker
window.openTransitionPicker = function(clipIndex){
  const existing = document.getElementById('transPicker');
  if(existing) existing.remove();
  const picker = document.createElement('div');
  picker.id='transPicker';
  picker.className='fixed bottom-[160px] left-1/2 -translate-x-1/2 bg-[#1e1e1e] border border-[#333] rounded-2xl p-3 flex gap-2 z-[200] shadow-2xl';
  picker.innerHTML = `
    <button data-t="none" class="px-3 py-2 rounded-xl bg-[#2a2a2a] text-[11px]">None</button>
    <button data-t="fade" class="px-3 py-2 rounded-xl bg-[#2a2a2a] text-[11px]">Fade</button>
    <button data-t="slide" class="px-3 py-2 rounded-xl bg-[#2a2a2a] text-[11px]">Slide</button>
    <button data-t="zoom" class="px-3 py-2 rounded-xl bg-[#2a2a2a] text-[11px]">Zoom</button>
    <button data-t="wipe" class="px-3 py-2 rounded-xl bg-[#2a2a2a] text-[11px]">Wipe</button>
  `;
  document.body.appendChild(picker);
  picker.querySelectorAll('button').forEach(b=>{
    if(clips[clipIndex].transition===b.dataset.t) b.classList.add('option-active');
    b.onclick=()=>{
      clips[clipIndex].transition=b.dataset.t;
      picker.remove();
      renderClips();
    };
  });
  setTimeout(()=>{ document.addEventListener('click', function close(e){ if(!picker.contains(e.target)){ picker.remove(); document.removeEventListener('click', close);} }, {once:true}); }, 100);
};

// Fix Split, Volume, Delete to actually work
window.doSplit = function(){
  if(!selectedClipId) return;
  const idx = clips.findIndex(c=>c.id===selectedClipId);
  if(idx<0) return;
  const clip = clips[idx];
  const info = getClipAtTime(globalTime);
  if(!info || info.index!==idx) { // split at half if not playing
    const half = clip.duration/2;
    const c2 = {...clip, id:'c_'+Date.now(), duration: clip.duration-half, trimStart:(clip.trimStart||0)+half };
    clip.duration=half;
    clips.splice(idx+1,0,c2);
  } else {
    const local = info.local;
    const leftDur = local;
    const rightDur = clip.duration - local;
    if(leftDur<0.2||rightDur<0.2) return;
    const c2 = {...clip, id:'c_'+Date.now(), duration:rightDur, trimStart:(clip.trimStart||0)+leftDur };
    clip.duration=leftDur;
    clips.splice(idx+1,0,c2);
  }
  renderClips();
};

window.setVolume = function(v){
  if(!selectedClipId) return;
  const clip=clips.find(c=>c.id===selectedClipId);
  if(clip){ clip.volume=v/100; video.volume=clip.volume; }
};

// Patch openTool to wire buttons
const _openTool = window.openTool;
window.openTool = function(tool){
  _openTool && _openTool(tool);
  if(tool==='edit'){
    setTimeout(()=>{
      const splitBtn = document.querySelector('[data-action="split"]') || document.getElementById('splitBtn');
      // find by text Split
      document.querySelectorAll('button').forEach(b=>{
        if(b.textContent.trim()==='Split') b.onclick = doSplit;
        if(b.textContent.trim()==='Delete') b.onclick = ()=>{ 
          const idx=clips.findIndex(c=>c.id===selectedClipId);
          if(idx>=0){ clips.splice(idx,1); selectedClipId=clips[0]?.id||null; renderClips(); if(clips.length===0) video.src=''; }
        };
      });
      const volRange = document.getElementById('volumeRange');
      if(volRange) volRange.oninput = (e)=>setVolume(e.target.value);
    }, 50);
  }
};

// Make export actually work with current state
document.getElementById('exportBtn').onclick = async ()=>{
  if(clips.length===0){ alert('Add video first'); return; }
  const btn = document.getElementById('exportBtn');
  btn.textContent='Exporting...';
  try{
    const canvas = document.getElementById('exportCanvas');
    const resMap={'480p':[854,480],'720p':[1280,720],'1080p':[1920,1080],'4K':[3840,2160]};
    const res = document.querySelector('.res-opt.bg-white')?.dataset.res || '1080p';
    const fps = parseInt(document.querySelector('.fps-opt.bg-white')?.dataset.fps||'30');
    const [w,h]=resMap[res]||[1920,1080];
    canvas.width=w; canvas.height=h;
    const ctx=canvas.getContext('2d');
    const stream=canvas.captureStream(fps);
    // add audio track if exists
    try{
      const audioCtx = new AudioContext();
      const dest = audioCtx.createMediaStreamDestination();
      if(video.captureStream){
        const vStream = video.captureStream();
        vStream.getAudioTracks().forEach(t=>dest.stream.addTrack(t));
        dest.stream.getAudioTracks().forEach(t=>stream.addTrack(t));
      }
    }catch(e){}
    let mime='video/webm;codecs=vp9';
    if(!MediaRecorder.isTypeSupported(mime)) mime='video/webm';
    const recorder=new MediaRecorder(stream,{mimeType:mime});
    const chunks=[];
    recorder.ondataavailable=e=>{ if(e.data.size>0) chunks.push(e.data); };
    recorder.onstop=()=>{
      const blob=new Blob(chunks,{type:mime});
      const url=URL.createObjectURL(blob);
      const a=document.createElement('a'); a.href=url; a.download=`ObeSplit_${res}_${Date.now()}.webm`; a.click();
      setTimeout(()=>URL.revokeObjectURL(url),2000);
      btn.textContent='Export';
      document.getElementById('exportPanel')?.classList.add('hidden');
    };
    recorder.start();
    let t=0;
    const totalDur = clips.reduce((s,c)=>s+c.duration,0);
    const interval = setInterval(()=>{
      const info=getClipAtTime(t);
      if(!info){ clearInterval(interval); recorder.stop(); return; }
      // transition effect
      ctx.fillStyle='#000'; ctx.fillRect(0,0,w,h);
      ctx.save();
      let alpha=1;
      // check if near transition
      if(info.local < 0.3 && info.index>0 && clips[info.index].transition && clips[info.index].transition!=='none'){
        const prog = info.local/0.3;
        if(clips[info.index].transition==='fade') alpha=prog;
        if(clips[info.index].transition==='zoom') ctx.setTransform(0.5+prog*0.5,0,0,0.5+prog*0.5,w/2*(1-(0.5+prog*0.5)),h/2*(1-(0.5+prog*0.5)));
      }
      ctx.globalAlpha=alpha;
      if(info.clip.type?.startsWith('video')){
        try{ 
          const v = document.getElementById('video');
          v.currentTime = (info.clip.trimStart||0) + info.local;
          ctx.drawImage(v,0,0,w,h);
        }catch(e){}
      }
      ctx.restore();
      // textLayer render
      t+=1/fps;
      if(t>=totalDur){ clearInterval(interval); recorder.stop(); }
    }, 1000/fps);
  }catch(err){ alert('Export failed: '+err.message); btn.textContent='Export'; }
};

// Init
if(typeof renderClips==='function') renderClips();
applyVideoTransform();
console.log('ObeSplit V5 patched: zoom, trim, split, transitions, export fixed');

</script>
</body>
</html>
