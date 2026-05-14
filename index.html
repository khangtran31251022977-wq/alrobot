<!DOCTYPE html>
<html lang="vi">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
<meta name="theme-color" content="#0f1117">
<meta name="apple-mobile-web-app-capable" content="yes">
<meta name="apple-mobile-web-app-status-bar-style" content="black-translucent">
<title>PinMap – Ghi chú địa điểm</title>
<link rel="stylesheet" href="https://unpkg.com/leaflet@1.9.4/dist/leaflet.css"/>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link href="https://fonts.googleapis.com/css2?family=Be+Vietnam+Pro:wght@400;500;600&display=swap" rel="stylesheet">
<style>
  *{box-sizing:border-box;margin:0;padding:0;-webkit-tap-highlight-color:transparent}
  :root{
    --bg:#0f1117;--surface:#1a1d27;--surface2:#22263a;--border:#2e3350;
    --text:#e8eaf0;--text2:#8b90a8;--accent:#4f8ef7;--accent2:#6f6af7;
    --danger:#e05a5a;--success:#3ecf8e;--warn:#f5a623;
    --cat-customer:#4f8ef7;--cat-friend:#3ecf8e;--cat-family:#f5a623;--cat-other:#9b8ef7;
    --radius:14px;--radius-sm:10px;
  }
  html,body{height:100%;width:100%;overflow:hidden;background:var(--bg);font-family:'Be Vietnam Pro',sans-serif;color:var(--text)}
  #app{display:flex;flex-direction:column;height:100%;width:100%;position:relative}

  /* TOP BAR */
  #topbar{
    position:absolute;top:0;left:0;right:0;z-index:1000;
    padding:env(safe-area-inset-top,12px) 12px 0;
    background:linear-gradient(to bottom,rgba(15,17,23,0.95) 70%,transparent);
  }
  #topbar-inner{display:flex;gap:8px;align-items:center;padding-bottom:10px}
  #search-wrap{
    flex:1;display:flex;align-items:center;gap:8px;
    background:var(--surface);border:1px solid var(--border);
    border-radius:var(--radius);padding:0 12px;height:44px
  }
  #search-wrap svg{flex-shrink:0;color:var(--text2)}
  #search-input{
    flex:1;background:none;border:none;outline:none;color:var(--text);
    font-family:inherit;font-size:15px
  }
  #search-input::placeholder{color:var(--text2)}
  #search-clear{background:none;border:none;padding:4px;cursor:pointer;color:var(--text2);line-height:0;display:none}
  #locate-btn{
    width:44px;height:44px;border-radius:var(--radius-sm);flex-shrink:0;
    background:var(--surface);border:1px solid var(--border);
    display:flex;align-items:center;justify-content:center;cursor:pointer;color:var(--text2)
  }
  #locate-btn:active{opacity:.7}

  /* SEARCH RESULTS */
  #search-results{
    position:absolute;top:calc(env(safe-area-inset-top,12px) + 54px);left:12px;right:12px;z-index:1001;
    background:var(--surface);border:1px solid var(--border);border-radius:var(--radius);
    overflow:hidden;display:none;max-height:260px;overflow-y:auto
  }
  .sr-item{
    display:flex;align-items:center;gap:10px;padding:11px 14px;cursor:pointer;
    border-bottom:1px solid var(--border);transition:background .15s
  }
  .sr-item:last-child{border-bottom:none}
  .sr-item:active{background:var(--surface2)}
  .sr-dot{width:10px;height:10px;border-radius:50%;flex-shrink:0}
  .sr-info{flex:1;min-width:0}
  .sr-name{font-size:14px;font-weight:500;white-space:nowrap;overflow:hidden;text-overflow:ellipsis}
  .sr-sub{font-size:12px;color:var(--text2);margin-top:2px}

  /* MAP */
  #map{flex:1;z-index:1}
  .leaflet-container{background:#1a1e2e!important}
  .leaflet-popup-content-wrapper{
    background:var(--surface)!important;border:1px solid var(--border)!important;
    border-radius:var(--radius)!important;box-shadow:0 8px 32px rgba(0,0,0,.5)!important;
    padding:0!important;overflow:hidden!important
  }
  .leaflet-popup-tip-container{display:none}
  .leaflet-popup-content{margin:0!important;width:260px!important}
  .leaflet-control-zoom{border:1px solid var(--border)!important;background:var(--surface)!important;border-radius:var(--radius-sm)!important}
  .leaflet-control-zoom a{background:var(--surface)!important;color:var(--text)!important;border:none!important}
  .leaflet-control-zoom a:hover{background:var(--surface2)!important}
  .leaflet-bar{border:none!important}

  /* POPUP CONTENT */
  .popup-header{padding:14px 14px 10px;border-bottom:1px solid var(--border)}
  .popup-cat{
    display:inline-block;font-size:11px;font-weight:600;letter-spacing:.04em;text-transform:uppercase;
    padding:2px 8px;border-radius:20px;margin-bottom:6px
  }
  .popup-name{font-size:16px;font-weight:600;color:var(--text)}
  .popup-phone{font-size:13px;color:var(--text2);margin-top:3px}
  .popup-body{padding:10px 14px 14px}
  .popup-notes{font-size:13px;color:var(--text2);line-height:1.5;margin-bottom:12px}
  .popup-date{font-size:11px;color:var(--text2);opacity:.6;margin-bottom:12px}
  .popup-actions{display:flex;gap:8px}
  .popup-btn{
    flex:1;height:36px;border-radius:var(--radius-sm);font-family:inherit;
    font-size:13px;font-weight:500;cursor:pointer;border:none;transition:opacity .15s
  }
  .popup-btn:active{opacity:.7}
  .btn-edit{background:var(--surface2);color:var(--text)}
  .btn-delete{background:rgba(224,90,90,.15);color:var(--danger)}

  /* FAB */
  #fab{
    position:absolute;bottom:calc(env(safe-area-inset-bottom,20px) + 80px);right:18px;
    z-index:1000;width:56px;height:56px;border-radius:50%;
    background:var(--accent);border:none;cursor:pointer;
    display:flex;align-items:center;justify-content:center;
    box-shadow:0 4px 20px rgba(79,142,247,.4);transition:transform .15s,box-shadow .15s
  }
  #fab:active{transform:scale(.93);box-shadow:0 2px 10px rgba(79,142,247,.3)}

  /* LIST BTN */
  #list-btn{
    position:absolute;bottom:calc(env(safe-area-inset-bottom,20px) + 80px);left:18px;
    z-index:1000;height:44px;padding:0 16px;border-radius:22px;
    background:var(--surface);border:1px solid var(--border);cursor:pointer;
    display:flex;align-items:center;gap:6px;color:var(--text);font-family:inherit;font-size:13px;font-weight:500
  }
  #list-btn:active{opacity:.7}
  #list-count{
    background:var(--accent);color:#fff;font-size:11px;font-weight:700;
    min-width:18px;height:18px;border-radius:9px;display:flex;align-items:center;justify-content:center;padding:0 4px
  }

  /* BOTTOM SHEET */
  #sheet-overlay{position:fixed;inset:0;z-index:2000;background:rgba(0,0,0,0);pointer-events:none;transition:background .3s}
  #sheet-overlay.open{background:rgba(0,0,0,.55);pointer-events:all}
  #sheet{
    position:fixed;bottom:0;left:0;right:0;z-index:2001;
    background:var(--surface);border-radius:20px 20px 0 0;
    border-top:1px solid var(--border);
    transform:translateY(100%);transition:transform .35s cubic-bezier(.32,1,.5,1);
    max-height:75vh;display:flex;flex-direction:column;
    padding-bottom:env(safe-area-inset-bottom,0)
  }
  #sheet.open{transform:translateY(0)}
  #sheet-handle{width:36px;height:4px;border-radius:2px;background:var(--border);margin:10px auto 0}
  #sheet-head{display:flex;align-items:center;justify-content:space-between;padding:12px 16px 8px}
  #sheet-title{font-size:16px;font-weight:600}
  #sheet-close{background:none;border:none;color:var(--text2);cursor:pointer;line-height:0;padding:4px}
  #sort-row{display:flex;gap:6px;padding:0 16px 10px;border-bottom:1px solid var(--border)}
  .sort-btn{
    height:30px;padding:0 12px;border-radius:15px;font-family:inherit;font-size:12px;font-weight:500;
    cursor:pointer;border:1px solid var(--border);background:none;color:var(--text2);transition:all .15s
  }
  .sort-btn.active{background:var(--accent);color:#fff;border-color:var(--accent)}
  #markers-list{overflow-y:auto;flex:1;padding:8px 12px 12px}
  .marker-card{
    background:var(--surface2);border:1px solid var(--border);border-radius:var(--radius);
    padding:12px 14px;margin-bottom:8px;cursor:pointer;transition:border-color .15s
  }
  .marker-card:active{border-color:var(--accent)}
  .mc-top{display:flex;align-items:flex-start;justify-content:space-between;gap:8px;margin-bottom:6px}
  .mc-name{font-size:14px;font-weight:600;flex:1}
  .mc-cat{font-size:11px;font-weight:600;padding:2px 8px;border-radius:20px}
  .mc-phone{font-size:12px;color:var(--text2);margin-bottom:4px}
  .mc-notes{font-size:12px;color:var(--text2);overflow:hidden;text-overflow:ellipsis;white-space:nowrap}
  .mc-date{font-size:11px;color:var(--text2);opacity:.5;margin-top:6px}
  .empty-state{text-align:center;padding:40px 16px;color:var(--text2)}
  .empty-state svg{margin-bottom:12px;opacity:.4}
  .empty-state p{font-size:14px;line-height:1.5}

  /* MODAL */
  #modal-overlay{
    position:fixed;inset:0;z-index:3000;background:rgba(0,0,0,.7);
    display:none;align-items:flex-end;justify-content:center;
    padding-bottom:env(safe-area-inset-bottom,0)
  }
  #modal-overlay.open{display:flex}
  #modal{
    background:var(--surface);border-radius:20px 20px 0 0;border-top:1px solid var(--border);
    width:100%;max-width:540px;padding:20px 20px calc(20px + env(safe-area-inset-bottom,0));
    max-height:90vh;overflow-y:auto
  }
  #modal h2{font-size:18px;font-weight:600;margin-bottom:20px}
  .field{margin-bottom:14px}
  .field label{display:block;font-size:12px;font-weight:600;color:var(--text2);margin-bottom:6px;text-transform:uppercase;letter-spacing:.05em}
  .field input,.field textarea,.field select{
    width:100%;background:var(--surface2);border:1px solid var(--border);border-radius:var(--radius-sm);
    color:var(--text);font-family:inherit;font-size:15px;padding:11px 13px;outline:none;
    transition:border-color .15s;-webkit-appearance:none
  }
  .field input:focus,.field textarea:focus,.field select:focus{border-color:var(--accent)}
  .field textarea{min-height:80px;resize:none}
  .field select option{background:var(--surface2)}
  .cat-grid{display:grid;grid-template-columns:1fr 1fr;gap:8px}
  .cat-opt{
    display:flex;align-items:center;gap:8px;padding:10px 12px;border-radius:var(--radius-sm);
    border:1.5px solid var(--border);cursor:pointer;transition:all .15s;background:var(--surface2)
  }
  .cat-opt.selected{border-color:var(--accent);background:rgba(79,142,247,.1)}
  .cat-dot{width:10px;height:10px;border-radius:50%;flex-shrink:0}
  .cat-label{font-size:13px;font-weight:500}
  .modal-actions{display:flex;gap:10px;margin-top:20px}
  .btn-cancel{
    flex:1;height:48px;border-radius:var(--radius);background:var(--surface2);
    border:1px solid var(--border);color:var(--text);font-family:inherit;font-size:15px;font-weight:500;cursor:pointer
  }
  .btn-save{
    flex:2;height:48px;border-radius:var(--radius);background:var(--accent);
    border:none;color:#fff;font-family:inherit;font-size:15px;font-weight:600;cursor:pointer
  }
  .btn-cancel:active,.btn-save:active{opacity:.8}

  /* TOAST */
  #toast{
    position:fixed;bottom:calc(env(safe-area-inset-bottom,20px) + 140px);left:50%;transform:translateX(-50%) translateY(20px);
    z-index:4000;background:var(--surface2);border:1px solid var(--border);
    border-radius:var(--radius);padding:10px 16px;font-size:13px;font-weight:500;
    opacity:0;transition:opacity .25s,transform .25s;pointer-events:none;white-space:nowrap
  }
  #toast.show{opacity:1;transform:translateX(-50%) translateY(0)}

  /* GPS MARKER */
  .gps-dot{
    width:16px;height:16px;border-radius:50%;background:var(--accent);
    border:3px solid #fff;box-shadow:0 0 0 4px rgba(79,142,247,.3)
  }
</style>
</head>
<body>
<div id="app">
  <div id="map"></div>

  <div id="topbar">
    <div id="topbar-inner">
      <div id="search-wrap">
        <svg width="16" height="16" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><circle cx="11" cy="11" r="8"/><path d="m21 21-4.35-4.35"/></svg>
        <input id="search-input" type="text" placeholder="Tìm kiếm tên khách hàng…" autocomplete="off">
        <button id="search-clear" onclick="clearSearch()">
          <svg width="16" height="16" fill="none" stroke="currentColor" stroke-width="2.5" viewBox="0 0 24 24"><path d="M18 6 6 18M6 6l12 12"/></svg>
        </button>
      </div>
      <button id="locate-btn" onclick="locateUser()" title="Vị trí hiện tại">
        <svg width="20" height="20" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><path d="M12 2a10 10 0 1 0 0 20A10 10 0 0 0 12 2z"/><circle cx="12" cy="12" r="3"/><path d="M12 2v3M12 19v3M2 12h3M19 12h3"/></svg>
      </button>
    </div>
  </div>
  <div id="search-results"></div>

  <button id="fab" onclick="openAddModal()" title="Thêm địa điểm">
    <svg width="24" height="24" fill="none" stroke="white" stroke-width="2.5" viewBox="0 0 24 24"><path d="M12 5v14M5 12h14"/></svg>
  </button>

  <button id="list-btn" onclick="openSheet()">
    <svg width="16" height="16" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><path d="M9 5H7a2 2 0 0 0-2 2v12a2 2 0 0 0 2 2h10a2 2 0 0 0 2-2V7a2 2 0 0 0-2-2h-2M9 5a2 2 0 0 0 2 2h2a2 2 0 0 0 2-2M9 5a2 2 0 0 1 2-2h2a2 2 0 0 1 2 2"/></svg>
    Danh sách
    <span id="list-count">0</span>
  </button>

  <div id="sheet-overlay" onclick="closeSheet()"></div>
  <div id="sheet">
    <div id="sheet-handle"></div>
    <div id="sheet-head">
      <span id="sheet-title">Tất cả địa điểm</span>
      <button id="sheet-close" onclick="closeSheet()">
        <svg width="20" height="20" fill="none" stroke="currentColor" stroke-width="2" viewBox="0 0 24 24"><path d="M18 6 6 18M6 6l12 12"/></svg>
      </button>
    </div>
    <div id="sort-row">
      <button class="sort-btn active" data-sort="newest" onclick="setSort(this,'newest')">Mới nhất</button>
      <button class="sort-btn" data-sort="oldest" onclick="setSort(this,'oldest')">Cũ nhất</button>
      <button class="sort-btn" data-sort="name" onclick="setSort(this,'name')">Tên A–Z</button>
    </div>
    <div id="markers-list"></div>
  </div>

  <div id="modal-overlay">
    <div id="modal">
      <h2 id="modal-title">Thêm địa điểm</h2>
      <div class="field">
        <label>Tên khách hàng / địa điểm *</label>
        <input id="f-name" type="text" placeholder="VD: Nguyễn Văn A">
      </div>
      <div class="field">
        <label>Số điện thoại</label>
        <input id="f-phone" type="tel" placeholder="VD: 0901 234 567">
      </div>
      <div class="field">
        <label>Ghi chú</label>
        <textarea id="f-notes" placeholder="Thông tin thêm, địa chỉ chi tiết…"></textarea>
      </div>
      <div class="field">
        <label>Phân loại</label>
        <div class="cat-grid" id="cat-grid"></div>
      </div>
      <div class="modal-actions">
        <button class="btn-cancel" onclick="closeModal()">Huỷ</button>
        <button class="btn-save" onclick="saveMarker()">Lưu địa điểm</button>
      </div>
    </div>
  </div>

  <div id="toast"></div>
</div>

<script src="https://unpkg.com/leaflet@1.9.4/dist/leaflet.js"></script>
<script>
const CATS = [
  {id:'customer',label:'Khách hàng',color:'#4f8ef7'},
  {id:'friend',label:'Bạn bè',color:'#3ecf8e'},
  {id:'family',label:'Gia đình',color:'#f5a623'},
  {id:'other',label:'Khác',color:'#9b8ef7'}
];
const STORE_KEY = 'pinmap_markers';
let map, gpsMarker, markers = [], sort = 'newest', editId = null, pendingLat = null, pendingLng = null, selectedCat = 'customer';

function loadMarkers(){
  try{markers = JSON.parse(localStorage.getItem(STORE_KEY))||[];}catch{markers=[];}
}
function saveMarkers(){
  localStorage.setItem(STORE_KEY, JSON.stringify(markers));
}
function genId(){return Date.now().toString(36)+Math.random().toString(36).slice(2,6);}
function catInfo(id){return CATS.find(c=>c.id===id)||CATS[3];}
function catColor(id){return catInfo(id).color;}
function fmtDate(ts){
  return new Date(ts).toLocaleDateString('vi-VN',{day:'2-digit',month:'2-digit',year:'numeric',hour:'2-digit',minute:'2-digit'});
}

// MAP INIT
function initMap(){
  map = L.map('map',{zoomControl:false,attributionControl:false}).setView([10.762622,106.660172],14);
  L.tileLayer('https://{s}.basemaps.cartocdn.com/dark_all/{z}/{x}/{y}{r}.png',{maxZoom:19}).addTo(map);
  L.control.zoom({position:'bottomright'}).addTo(map);
  L.control.attribution({position:'bottomleft',prefix:''}).addAttribution('© OSM © Carto').addTo(map);
  map.on('click', e=>{
    if(document.getElementById('modal-overlay').classList.contains('open')) return;
    document.getElementById('search-results').style.display='none';
  });
}

function makeIcon(color){
  return L.divIcon({
    className:'',
    html:`<div style="width:28px;height:36px;position:relative">
      <svg viewBox="0 0 28 36" fill="none" xmlns="http://www.w3.org/2000/svg">
        <path d="M14 0C6.268 0 0 6.268 0 14c0 9.625 14 22 14 22S28 23.625 28 14C28 6.268 21.732 0 14 0z" fill="${color}"/>
        <circle cx="14" cy="14" r="6" fill="white" fill-opacity="0.9"/>
      </svg>
    </div>`,
    iconSize:[28,36],iconAnchor:[14,36],popupAnchor:[0,-38]
  });
}

function buildPopupHTML(m){
  const cat = catInfo(m.category);
  return `<div class="popup-header">
    <span class="popup-cat" style="background:${cat.color}22;color:${cat.color}">${cat.label}</span>
    <div class="popup-name">${esc(m.name)}</div>
    ${m.phone?`<div class="popup-phone">📞 ${esc(m.phone)}</div>`:''}
  </div>
  <div class="popup-body">
    ${m.notes?`<div class="popup-notes">${esc(m.notes)}</div>`:''}
    <div class="popup-date">${fmtDate(m.ts)}</div>
    <div class="popup-actions">
      <button class="popup-btn btn-edit" onclick="editMarker('${m.id}')">✏️ Sửa</button>
      <button class="popup-btn btn-delete" onclick="deleteMarker('${m.id}')">🗑 Xoá</button>
    </div>
  </div>`;
}

function esc(s){return String(s||'').replace(/&/g,'&amp;').replace(/</g,'&lt;').replace(/>/g,'&gt;');}

let leafletMarkers = {};
function renderMapMarkers(){
  // remove old
  Object.values(leafletMarkers).forEach(lm=>map.removeLayer(lm));
  leafletMarkers = {};
  markers.forEach(m=>{
    const lm = L.marker([m.lat,m.lng],{icon:makeIcon(catColor(m.category))}).addTo(map);
    lm.bindPopup(buildPopupHTML(m),{maxWidth:280});
    leafletMarkers[m.id] = lm;
  });
  updateListCount();
}

function locateUser(){
  if(!navigator.geolocation){showToast('Thiết bị không hỗ trợ GPS');return;}
  showToast('Đang xác định vị trí…');
  navigator.geolocation.getCurrentPosition(pos=>{
    const {latitude:lat,longitude:lng} = pos.coords;
    map.setView([lat,lng],17);
    if(gpsMarker) map.removeLayer(gpsMarker);
    gpsMarker = L.marker([lat,lng],{
      icon:L.divIcon({className:'',html:'<div class="gps-dot"></div>',iconSize:[16,16],iconAnchor:[8,8]})
    }).addTo(map);
    showToast('Đã tìm thấy vị trí');
  }, ()=>showToast('Không lấy được vị trí'));
}

function openAddModal(lat,lng){
  editId = null;
  pendingLat = lat||null; pendingLng = lng||null;
  document.getElementById('modal-title').textContent = 'Thêm địa điểm';
  document.getElementById('f-name').value = '';
  document.getElementById('f-phone').value = '';
  document.getElementById('f-notes').value = '';
  selectedCat = 'customer';
  renderCatGrid();
  document.getElementById('modal-overlay').classList.add('open');
  setTimeout(()=>document.getElementById('f-name').focus(),350);
}

function openAddAtCurrentLocation(){
  if(!navigator.geolocation){showToast('Thiết bị không hỗ trợ GPS');return;}
  showToast('Đang lấy vị trí…');
  navigator.geolocation.getCurrentPosition(pos=>{
    openAddModal(pos.coords.latitude, pos.coords.longitude);
  },()=>{
    showToast('Không lấy được vị trí, dùng tâm bản đồ');
    const c = map.getCenter();
    openAddModal(c.lat, c.lng);
  });
}

document.getElementById('fab').addEventListener('click', e=>{
  e.stopPropagation();
  openAddAtCurrentLocation();
});

function editMarker(id){
  const m = markers.find(x=>x.id===id);
  if(!m) return;
  editId = id;
  pendingLat = m.lat; pendingLng = m.lng;
  document.getElementById('modal-title').textContent = 'Sửa địa điểm';
  document.getElementById('f-name').value = m.name;
  document.getElementById('f-phone').value = m.phone||'';
  document.getElementById('f-notes').value = m.notes||'';
  selectedCat = m.category;
  renderCatGrid();
  map.closePopup();
  document.getElementById('modal-overlay').classList.add('open');
}

function deleteMarker(id){
  if(!confirm('Xoá địa điểm này?')) return;
  markers = markers.filter(m=>m.id!==id);
  saveMarkers();
  if(leafletMarkers[id]) map.removeLayer(leafletMarkers[id]);
  delete leafletMarkers[id];
  map.closePopup();
  renderList();
  updateListCount();
  showToast('Đã xoá địa điểm');
}

function saveMarker(){
  const name = document.getElementById('f-name').value.trim();
  if(!name){document.getElementById('f-name').focus();showToast('Vui lòng nhập tên');return;}
  const phone = document.getElementById('f-phone').value.trim();
  const notes = document.getElementById('f-notes').value.trim();
  if(editId){
    const idx = markers.findIndex(m=>m.id===editId);
    if(idx>-1){
      markers[idx] = {...markers[idx],name,phone,notes,category:selectedCat};
      saveMarkers();
      if(leafletMarkers[editId]){
        leafletMarkers[editId].setIcon(makeIcon(catColor(selectedCat)));
        leafletMarkers[editId].setPopupContent(buildPopupHTML(markers[idx]));
      }
      showToast('Đã cập nhật');
    }
  } else {
    let lat = pendingLat, lng = pendingLng;
    if(!lat){const c=map.getCenter();lat=c.lat;lng=c.lng;}
    const m = {id:genId(),name,phone,notes,category:selectedCat,lat,lng,ts:Date.now()};
    markers.push(m);
    saveMarkers();
    const lm = L.marker([lat,lng],{icon:makeIcon(catColor(m.category))}).addTo(map);
    lm.bindPopup(buildPopupHTML(m),{maxWidth:280});
    leafletMarkers[m.id] = lm;
    map.setView([lat,lng],17);
    setTimeout(()=>lm.openPopup(),300);
    showToast('Đã lưu địa điểm');
  }
  renderList();
  updateListCount();
  closeModal();
}

function closeModal(){
  document.getElementById('modal-overlay').classList.remove('open');
  editId = null;
}
document.getElementById('modal-overlay').addEventListener('click', e=>{if(e.target===e.currentTarget)closeModal();});

function renderCatGrid(){
  const grid = document.getElementById('cat-grid');
  grid.innerHTML = CATS.map(c=>`
    <div class="cat-opt${c.id===selectedCat?' selected':''}" onclick="selectCat('${c.id}')">
      <span class="cat-dot" style="background:${c.color}"></span>
      <span class="cat-label">${c.label}</span>
    </div>`).join('');
}
function selectCat(id){selectedCat=id;renderCatGrid();}

// SHEET
function openSheet(){
  renderList();
  document.getElementById('sheet').classList.add('open');
  document.getElementById('sheet-overlay').classList.add('open');
}
function closeSheet(){
  document.getElementById('sheet').classList.remove('open');
  document.getElementById('sheet-overlay').classList.remove('open');
}
function setSort(btn,s){
  sort=s;
  document.querySelectorAll('.sort-btn').forEach(b=>b.classList.remove('active'));
  btn.classList.add('active');
  renderList();
}
function getSorted(){
  const arr = [...markers];
  if(sort==='newest') return arr.sort((a,b)=>b.ts-a.ts);
  if(sort==='oldest') return arr.sort((a,b)=>a.ts-b.ts);
  return arr.sort((a,b)=>a.name.localeCompare(b.name,'vi'));
}
function renderList(){
  const list = document.getElementById('markers-list');
  const arr = getSorted();
  document.getElementById('sheet-title').textContent = `${arr.length} địa điểm`;
  if(!arr.length){
    list.innerHTML=`<div class="empty-state">
      <svg width="40" height="40" fill="none" stroke="currentColor" stroke-width="1.5" viewBox="0 0 24 24"><path d="M12 2a7 7 0 0 1 7 7c0 5.25-7 13-7 13S5 14.25 5 9a7 7 0 0 1 7-7z"/><circle cx="12" cy="9" r="2.5"/></svg>
      <p>Chưa có địa điểm nào.<br>Nhấn nút + để thêm địa điểm đầu tiên.</p>
    </div>`;
    return;
  }
  list.innerHTML = arr.map(m=>{
    const cat = catInfo(m.category);
    return `<div class="marker-card" onclick="flyTo('${m.id}')">
      <div class="mc-top">
        <span class="mc-name">${esc(m.name)}</span>
        <span class="mc-cat" style="background:${cat.color}22;color:${cat.color}">${cat.label}</span>
      </div>
      ${m.phone?`<div class="mc-phone">📞 ${esc(m.phone)}</div>`:''}
      ${m.notes?`<div class="mc-notes">${esc(m.notes)}</div>`:''}
      <div class="mc-date">${fmtDate(m.ts)}</div>
    </div>`;
  }).join('');
}
function flyTo(id){
  const m = markers.find(x=>x.id===id);
  if(!m) return;
  closeSheet();
  map.setView([m.lat,m.lng],17);
  setTimeout(()=>{if(leafletMarkers[id])leafletMarkers[id].openPopup();},400);
}
function updateListCount(){
  document.getElementById('list-count').textContent = markers.length;
}

// SEARCH
const searchInput = document.getElementById('search-input');
const searchResults = document.getElementById('search-results');
const searchClear = document.getElementById('search-clear');
searchInput.addEventListener('input', ()=>{
  const q = searchInput.value.trim().toLowerCase();
  searchClear.style.display = q ? 'block' : 'none';
  if(!q){searchResults.style.display='none';return;}
  const hits = markers.filter(m=>m.name.toLowerCase().includes(q)||(m.phone||'').includes(q)||(m.notes||'').toLowerCase().includes(q));
  if(!hits.length){searchResults.innerHTML='<div class="sr-item"><span style="color:var(--text2);font-size:13px">Không tìm thấy kết quả</span></div>';searchResults.style.display='block';return;}
  searchResults.innerHTML = hits.slice(0,8).map(m=>`
    <div class="sr-item" onclick="flyTo('${m.id}');clearSearch()">
      <span class="sr-dot" style="background:${catColor(m.category)}"></span>
      <div class="sr-info">
        <div class="sr-name">${esc(m.name)}</div>
        <div class="sr-sub">${catInfo(m.category).label}${m.phone?' · '+esc(m.phone):''}</div>
      </div>
    </div>`).join('');
  searchResults.style.display='block';
});
searchInput.addEventListener('keydown', e=>{if(e.key==='Escape')clearSearch();});
function clearSearch(){
  searchInput.value='';
  searchClear.style.display='none';
  searchResults.style.display='none';
}

// TOAST
let toastTimer;
function showToast(msg){
  const t = document.getElementById('toast');
  t.textContent = msg;
  t.classList.add('show');
  clearTimeout(toastTimer);
  toastTimer = setTimeout(()=>t.classList.remove('show'),2500);
}

// INIT
loadMarkers();
initMap();
renderMapMarkers();
locateUser();
</script>
</body>
</html>
