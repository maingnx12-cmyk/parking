<!DOCTYPE html>
<html lang="vi">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>ParkConnect – Nền tảng đặt bãi xe thông minh</title>
<link href="https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@300;400;500;600;700;800&display=swap" rel="stylesheet">
<style>
:root {
  --blue-50:#EEF4FF; --blue-100:#D9E5FF; --blue-200:#B3CCFF;
  --blue-300:#7FA8FF; --blue-400:#4D82FF; --blue-500:#1A56DB;
  --blue-600:#1445B8; --blue-700:#0F3490; --blue-800:#0A2266;
  --blue-900:#051144;
  --sky:#0EA5E9; --sky-light:#E0F2FE;
  --green:#10B981; --green-light:#D1FAE5;
  --amber:#F59E0B; --amber-light:#FEF3C7;
  --red:#EF4444; --red-light:#FEE2E2;
  --purple:#8B5CF6; --purple-light:#EDE9FE;
  --gray-50:#F8FAFC; --gray-100:#F1F5F9; --gray-200:#E2E8F0;
  --gray-300:#CBD5E1; --gray-400:#94A3B8; --gray-500:#64748B;
  --gray-600:#475569; --gray-700:#334155; --gray-800:#1E293B; --gray-900:#0F172A;
  --white:#FFFFFF;
  --font:'Plus Jakarta Sans',sans-serif;
  --r:10px; --r-lg:16px; --r-xl:24px;
  --shadow-sm:0 1px 3px rgba(0,0,0,.06),0 1px 2px rgba(0,0,0,.04);
  --shadow:0 4px 16px rgba(0,0,0,.08),0 2px 6px rgba(0,0,0,.04);
  --shadow-lg:0 12px 32px rgba(0,0,0,.12),0 4px 12px rgba(0,0,0,.06);
}
*{margin:0;padding:0;box-sizing:border-box}
html{scroll-behavior:smooth}
body{font-family:var(--font);background:var(--gray-50);color:var(--gray-800);overflow-x:hidden;font-size:14px;}

/* ── NAVBAR ── */
nav{
  position:sticky;top:0;z-index:200;
  background:rgba(255,255,255,.95);
  backdrop-filter:blur(20px);
  border-bottom:1px solid var(--gray-200);
  height:60px;
  display:flex;align-items:center;justify-content:space-between;
  padding:0 2rem;
  box-shadow:var(--shadow-sm);
}
.nav-brand{
  display:flex;align-items:center;gap:9px;
  font-weight:800;font-size:1.2rem;color:var(--gray-900);text-decoration:none;
}
.brand-icon{
  width:34px;height:34px;border-radius:10px;
  background:var(--blue-500);
  display:flex;align-items:center;justify-content:center;color:white;font-size:16px;
  box-shadow:0 2px 8px rgba(26,86,219,.35);
}
.brand-dot{color:var(--blue-500);}
.nav-links{display:flex;align-items:center;gap:2px;list-style:none;}
.nav-links a{
  font-size:.84rem;font-weight:500;color:var(--gray-500);text-decoration:none;
  padding:6px 13px;border-radius:8px;transition:all .18s;
}
.nav-links a:hover{color:var(--gray-800);background:var(--gray-100);}
.nav-links a.active{color:var(--blue-500);background:var(--blue-50);}
.nav-actions{display:flex;align-items:center;gap:8px;}

/* VIEW TOGGLE */
.view-toggle{
  display:flex;background:var(--gray-100);border-radius:10px;padding:3px;
}
.view-btn{
  font-size:.8rem;font-weight:600;padding:5px 14px;border-radius:7px;
  border:none;cursor:pointer;transition:all .18s;color:var(--gray-400);background:transparent;
  font-family:var(--font);
}
.view-btn.active{background:var(--white);color:var(--blue-500);box-shadow:var(--shadow-sm);}

/* BUTTONS */
.btn{
  font-family:var(--font);font-size:.84rem;font-weight:600;
  padding:8px 18px;border-radius:9px;border:none;cursor:pointer;
  transition:all .18s;text-decoration:none;display:inline-flex;align-items:center;gap:6px;
}
.btn-primary{background:var(--blue-500);color:white;}
.btn-primary:hover{background:var(--blue-600);transform:translateY(-1px);box-shadow:0 4px 14px rgba(26,86,219,.3);}
.btn-outline{background:transparent;color:var(--blue-500);border:1.5px solid var(--blue-200);}
.btn-outline:hover{background:var(--blue-50);border-color:var(--blue-400);}
.btn-ghost{background:transparent;color:var(--gray-500);border:1.5px solid var(--gray-200);}
.btn-ghost:hover{background:var(--gray-100);color:var(--gray-700);}
.btn-accent{background:linear-gradient(135deg,var(--blue-500),var(--sky));color:white;font-weight:700;}
.btn-accent:hover{transform:translateY(-1px);box-shadow:0 6px 18px rgba(14,165,233,.3);}

/* SECTIONS */
.page-section{display:none;}
.page-section.active{display:block;}

/* ══════════════════════════════════
   B2C – USER INTERFACE
══════════════════════════════════ */

/* HERO */
.hero{
  background:linear-gradient(150deg,var(--blue-900) 0%,var(--blue-700) 40%,var(--blue-500) 80%,var(--sky) 100%);
  padding:3.5rem 2.5rem 5rem;
  position:relative;overflow:hidden;
  text-align:center;
}
.hero::before{
  content:'';position:absolute;inset:0;
  background:url("data:image/svg+xml,%3Csvg width='60' height='60' viewBox='0 0 60 60' xmlns='http://www.w3.org/2000/svg'%3E%3Cg fill='none' fill-rule='evenodd'%3E%3Cg fill='%23ffffff' fill-opacity='0.03'%3E%3Cpath d='M36 34v-4h-2v4h-4v2h4v4h2v-4h4v-2h-4zm0-30V0h-2v4h-4v2h4v4h2V6h4V4h-4zM6 34v-4H4v4H0v2h4v4h2v-4h4v-2H6zM6 4V0H4v4H0v2h4v4h2V6h4V4H6z'/%3E%3C/g%3E%3C/g%3E%3C/svg%3E");
}
.hero-content{position:relative;z-index:1;max-width:640px;margin:0 auto;}
.hero-badge{
  display:inline-flex;align-items:center;gap:6px;
  background:rgba(255,255,255,.15);border:1px solid rgba(255,255,255,.25);
  color:white;font-size:.74rem;font-weight:700;letter-spacing:.06em;text-transform:uppercase;
  padding:5px 13px;border-radius:100px;margin-bottom:1.2rem;
}
.hero-badge-dot{width:6px;height:6px;border-radius:50%;background:#0FF5A0;}
.hero h1{
  font-size:clamp(1.9rem,4vw,3rem);font-weight:800;color:white;
  line-height:1.15;margin-bottom:.9rem;
}
.hero h1 em{font-style:normal;color:#0FF5A0;}
.hero p{font-size:.97rem;color:rgba(255,255,255,.8);line-height:1.7;margin-bottom:1.8rem;}
.hero-search{
  background:white;border-radius:14px;
  display:flex;align-items:center;gap:10px;
  padding:8px 8px 8px 14px;
  box-shadow:0 16px 40px rgba(0,0,0,.25);max-width:520px;margin:0 auto;
}
.hero-search input{
  background:transparent;border:none;outline:none;flex:1;
  font-family:var(--font);font-size:.9rem;color:var(--gray-800);
}
.hero-search input::placeholder{color:var(--gray-400);}

/* FLOATING SEARCH CARD */
.floating-card{
  background:white;border-radius:var(--r-xl);
  box-shadow:var(--shadow-lg);
  margin:-3rem 2.5rem 2rem;
  padding:1.5rem;
  position:relative;z-index:10;
  max-width:900px;
  margin-left:auto;margin-right:auto;
  margin-top:-3rem;
}

/* VEHICLE SELECTOR – Grab Style */
.vehicle-title{
  font-size:.72rem;font-weight:700;letter-spacing:.1em;text-transform:uppercase;
  color:var(--gray-400);margin-bottom:1rem;
}
.vehicle-row{
  display:flex;gap:8px;
  overflow-x:auto;padding-bottom:4px;
}
.vehicle-row::-webkit-scrollbar{height:0;}
.vehicle-item{
  display:flex;flex-direction:column;align-items:center;gap:6px;
  cursor:pointer;transition:all .18s;flex-shrink:0;
  padding:4px;border-radius:var(--r-lg);
}
.vehicle-icon-wrap{
  width:58px;height:58px;border-radius:16px;
  background:var(--gray-100);
  display:flex;align-items:center;justify-content:center;
  font-size:26px;transition:all .18s;
  border:2px solid transparent;
}
.vehicle-item.sel .vehicle-icon-wrap{
  background:var(--blue-50);border-color:var(--blue-400);
  box-shadow:0 0 0 4px rgba(26,86,219,.08);
}
.vehicle-name{
  font-size:.72rem;font-weight:600;color:var(--gray-500);transition:all .18s;
  white-space:nowrap;
}
.vehicle-item.sel .vehicle-name{color:var(--blue-500);}

/* DIVIDER */
.v-divider{width:1px;background:var(--gray-200);margin:0 4px;align-self:stretch;}

/* AREA FILTER */
.filter-row{
  display:flex;gap:8px;flex-wrap:wrap;align-items:center;margin-top:1rem;
  padding-top:1rem;border-top:1px solid var(--gray-100);
}
.filter-label{font-size:.76rem;font-weight:700;color:var(--gray-400);text-transform:uppercase;letter-spacing:.06em;}
.chip{
  font-size:.78rem;font-weight:600;padding:5px 13px;border-radius:100px;
  border:1.5px solid var(--gray-200);color:var(--gray-500);cursor:pointer;
  transition:all .18s;background:white;
}
.chip:hover{border-color:var(--blue-300);color:var(--blue-500);}
.chip.sel{background:var(--blue-500);border-color:var(--blue-500);color:white;}
.chip.light{background:var(--blue-50);border-color:var(--blue-200);color:var(--blue-600);}

/* STATS */
.stats-strip{
  display:grid;grid-template-columns:repeat(4,1fr);
  gap:0;max-width:900px;margin:0 auto 2rem;
  background:white;border-radius:var(--r-xl);
  box-shadow:var(--shadow-sm);border:1px solid var(--gray-200);
  overflow:hidden;
}
.stat-box{
  padding:1.2rem 1.5rem;text-align:center;
  border-right:1px solid var(--gray-200);
}
.stat-box:last-child{border-right:none;}
.stat-num{font-size:1.5rem;font-weight:800;color:var(--blue-500);font-variant-numeric:tabular-nums;}
.stat-lbl{font-size:.7rem;font-weight:600;color:var(--gray-400);letter-spacing:.05em;text-transform:uppercase;margin-top:2px;}

/* CONTENT LAYOUT */
.content-wrap{max-width:900px;margin:0 auto;padding:0 1.5rem;}

/* LIST/MAP TOGGLE */
.list-map-row{
  display:flex;align-items:center;justify-content:space-between;
  margin-bottom:1rem;
}
.result-count{font-size:.84rem;font-weight:600;color:var(--gray-500);}
.list-map-toggle{
  display:flex;background:var(--gray-100);border-radius:9px;padding:3px;gap:2px;
}
.lm-btn{
  font-size:.78rem;font-weight:600;padding:5px 13px;border-radius:7px;
  border:none;cursor:pointer;transition:all .18s;color:var(--gray-400);
  background:transparent;font-family:var(--font);display:flex;align-items:center;gap:5px;
}
.lm-btn.active{background:white;color:var(--blue-500);box-shadow:var(--shadow-sm);}

/* PARKING CARD */
.parking-cards{display:flex;flex-direction:column;gap:10px;margin-bottom:2rem;}
.park-card{
  background:white;border-radius:var(--r-lg);
  border:1.5px solid var(--gray-200);
  padding:1rem 1.2rem;
  display:flex;align-items:center;gap:1rem;
  cursor:pointer;transition:all .2s;
  box-shadow:var(--shadow-sm);
}
.park-card:hover{
  border-color:var(--blue-300);
  box-shadow:0 6px 24px rgba(26,86,219,.1);
  transform:translateY(-1px);
}
.park-thumb{
  width:68px;height:68px;border-radius:var(--r);
  background:var(--blue-50);flex-shrink:0;
  display:flex;align-items:center;justify-content:center;font-size:1.8rem;
  overflow:hidden;
}
.park-body{flex:1;min-width:0;}
.park-name{font-size:.94rem;font-weight:700;color:var(--gray-900);margin-bottom:2px;}
.park-addr{font-size:.76rem;color:var(--gray-400);margin-bottom:7px;}
.park-tags{display:flex;gap:5px;flex-wrap:wrap;}
.tag{font-size:.68rem;font-weight:600;padding:2px 8px;border-radius:100px;}
.tag-green{background:var(--green-light);color:#065F46;}
.tag-amber{background:var(--amber-light);color:#92400E;}
.tag-red{background:var(--red-light);color:#991B1B;}
.tag-blue{background:var(--blue-50);color:var(--blue-600);}
.tag-gray{background:var(--gray-100);color:var(--gray-600);}
.park-right{text-align:right;flex-shrink:0;}
.park-price{font-size:1.05rem;font-weight:800;color:var(--gray-900);}
.park-price span{font-size:.7rem;font-weight:400;color:var(--gray-400);}
.park-rating{font-size:.74rem;color:var(--gray-500);margin-top:3px;display:flex;align-items:center;gap:3px;justify-content:flex-end;}
.park-rating .star{color:var(--amber);}
.occ-bar{width:72px;height:4px;background:var(--gray-200);border-radius:2px;margin:6px 0 2px auto;overflow:hidden;}
.occ-fill{height:100%;border-radius:2px;}
.occ-txt{font-size:.66rem;color:var(--gray-400);}

/* MAP VIEW */
.map-view{
  background:white;border:1.5px solid var(--gray-200);
  border-radius:var(--r-xl);height:440px;
  box-shadow:var(--shadow);margin-bottom:2rem;
  position:relative;overflow:hidden;
}
.map-inner{width:100%;height:100%;background:var(--gray-100);position:relative;}
.map-grid-bg{
  position:absolute;inset:0;
  background-image:
    repeating-linear-gradient(var(--gray-200) 0 1px,transparent 1px 40px),
    repeating-linear-gradient(90deg,var(--gray-200) 0 1px,transparent 1px 50px);
}
.map-road-h{position:absolute;background:white;border:1px solid var(--gray-200);}
.map-road-v{position:absolute;background:white;border:1px solid var(--gray-200);}
.map-block{position:absolute;border-radius:4px;background:var(--gray-200);}
.map-pin{position:absolute;cursor:pointer;transform:translate(-50%,-100%);transition:transform .18s;}
.map-pin:hover{transform:translate(-50%,-100%) scale(1.1);}
.pin-label{
  background:white;border:1.5px solid var(--gray-300);
  border-radius:8px;padding:4px 9px;font-size:.72rem;font-weight:700;
  color:var(--gray-800);white-space:nowrap;
  box-shadow:0 3px 10px rgba(0,0,0,.12);position:relative;
}
.pin-label::after{
  content:'';position:absolute;bottom:-6px;left:50%;transform:translateX(-50%);
  border:4px solid transparent;border-top-color:var(--gray-300);
}
.pin-label.ok{border-color:var(--green);color:#065F46;background:#F0FDF4;}
.pin-label.ok::after{border-top-color:var(--green);}
.pin-label.warn{border-color:var(--amber);color:#92400E;background:#FFFBEB;}
.pin-label.warn::after{border-top-color:var(--amber);}
.pin-label.bad{border-color:var(--red);color:#991B1B;background:#FEF2F2;}
.pin-label.bad::after{border-top-color:var(--red);}
.my-pin{
  position:absolute;width:16px;height:16px;border-radius:50%;
  background:var(--blue-500);border:3px solid white;
  box-shadow:0 0 0 5px rgba(26,86,219,.18);
}

/* ══════════════════════════════════
   MODAL
══════════════════════════════════ */
.modal-overlay{
  display:none;position:fixed;inset:0;z-index:500;
  background:rgba(15,23,42,.5);backdrop-filter:blur(4px);
  align-items:center;justify-content:center;
}
.modal-overlay.open{display:flex;}
.modal{
  background:white;border-radius:var(--r-xl);
  width:90%;max-width:480px;
  padding:1.75rem;
  position:relative;
  box-shadow:var(--shadow-lg);
  max-height:90vh;overflow-y:auto;
}
.modal-close{
  position:absolute;top:1rem;right:1rem;
  width:32px;height:32px;border-radius:8px;
  background:var(--gray-100);border:none;cursor:pointer;
  display:flex;align-items:center;justify-content:center;color:var(--gray-500);
  font-size:.95rem;transition:all .18s;
}
.modal-close:hover{background:var(--gray-200);color:var(--gray-800);}
.modal-header{margin-bottom:1.2rem;}
.modal-title{font-size:1.1rem;font-weight:800;color:var(--gray-900);}
.modal-sub{font-size:.78rem;color:var(--gray-400);margin-top:2px;}

/* SLOT GRID (modal) */
.modal-slot-grid{display:grid;grid-template-columns:repeat(5,1fr);gap:6px;margin:1rem 0;}
.ms{
  height:30px;border-radius:7px;display:flex;align-items:center;justify-content:center;
  font-size:.72rem;font-weight:700;cursor:pointer;border:1.5px solid transparent;transition:all .14s;
}
.ms.free{background:var(--green-light);color:#065F46;border-color:#A7F3D0;}
.ms.free:hover{background:#BBF7D0;}
.ms.taken{background:var(--gray-100);color:var(--gray-300);cursor:not-allowed;}
.ms.sel{background:var(--blue-500);color:white;border-color:var(--blue-600);}

/* MODAL TIME PICKER */
.time-grid{display:grid;grid-template-columns:repeat(4,1fr);gap:6px;margin:0.5rem 0 1rem;}
.t-btn{
  background:var(--gray-50);border:1.5px solid var(--gray-200);
  border-radius:8px;padding:7px 4px;text-align:center;
  font-size:.78rem;font-weight:600;color:var(--gray-600);cursor:pointer;transition:all .15s;
  font-family:var(--font);
}
.t-btn:hover{border-color:var(--blue-300);color:var(--blue-500);}
.t-btn.on{background:var(--blue-50);border-color:var(--blue-500);color:var(--blue-600);}
.t-btn.off{color:var(--gray-300);cursor:not-allowed;}

/* PAYMENT METHODS */
.pay-list{display:flex;flex-direction:column;gap:6px;margin:0.5rem 0 1rem;}
.pay-row{
  display:flex;align-items:center;gap:10px;
  padding:9px 12px;border-radius:var(--r);border:1.5px solid var(--gray-200);
  cursor:pointer;transition:all .18s;background:white;
}
.pay-row:hover{border-color:var(--blue-300);}
.pay-row.on{border-color:var(--blue-500);background:var(--blue-50);}
.pm-badge{width:38px;height:26px;border-radius:6px;display:flex;align-items:center;justify-content:center;font-size:9px;font-weight:800;flex-shrink:0;}
.pm-momo{background:#AE2070;color:white;}
.pm-zalo{background:#0068FF;color:white;}
.pm-vnpay{background:#007EC9;color:white;}
.pm-card{background:var(--gray-800);color:white;}
.pm-cash{background:var(--green-light);color:#065F46;}
.pm-name{font-size:.84rem;font-weight:600;color:var(--gray-800);}
.pm-sub{font-size:.72rem;color:var(--gray-400);}
.pm-balance{font-size:.78rem;font-weight:700;color:var(--green);}
.pm-radio{
  width:16px;height:16px;border-radius:50%;border:2px solid var(--gray-300);
  margin-left:auto;flex-shrink:0;display:flex;align-items:center;justify-content:center;
  transition:all .15s;
}
.pm-radio.on{border-color:var(--blue-500);}
.pm-radio-dot{width:8px;height:8px;border-radius:50%;background:var(--blue-500);}

/* MODAL PRICE ROW */
.price-row{
  display:flex;justify-content:space-between;align-items:center;
  padding:7px 0;border-bottom:1px solid var(--gray-100);font-size:.84rem;
}
.price-row:last-child{border-bottom:none;}
.price-row .lbl{color:var(--gray-500);}
.price-row .val{font-weight:600;color:var(--gray-800);}
.price-row.grand .lbl{font-weight:700;color:var(--gray-900);font-size:.9rem;}
.price-row.grand .val{color:var(--blue-500);font-size:1rem;font-weight:800;}

/* SUCCESS STATE */
.success-wrap{text-align:center;padding:1rem 0;}
.success-circle{
  width:68px;height:68px;border-radius:50%;
  background:var(--green-light);margin:0 auto 1rem;
  display:flex;align-items:center;justify-content:center;font-size:2rem;
  border:2px solid #A7F3D0;
}
.qr-box{
  width:120px;height:120px;background:white;border:1px solid var(--gray-200);
  border-radius:var(--r);margin:1rem auto;
  display:flex;align-items:center;justify-content:center;
}
.qr-inner{
  width:96px;height:96px;
  background:repeating-conic-gradient(var(--gray-900) 0% 25%,white 0% 50%) 0/9px 9px;
  border-radius:4px;opacity:.85;
}

/* ══════════════════════════════════
   B2B – OPERATOR DASHBOARD
══════════════════════════════════ */
.dash-layout{max-width:1100px;margin:0 auto;padding:1.5rem;}

/* DASH HEADER */
.dash-header{
  display:flex;align-items:center;justify-content:space-between;
  margin-bottom:1.5rem;
}
.dash-title{font-size:1.3rem;font-weight:800;color:var(--gray-900);}
.dash-title span{color:var(--blue-500);}
.dash-sub{font-size:.8rem;color:var(--gray-500);margin-top:2px;}
.live-pill{
  display:flex;align-items:center;gap:6px;
  background:var(--green-light);border:1px solid #A7F3D0;
  color:#065F46;font-size:.74rem;font-weight:700;
  padding:5px 12px;border-radius:100px;
}
.live-dot{width:7px;height:7px;border-radius:50%;background:var(--green);animation:pulse 1.5s infinite;}
@keyframes pulse{0%,100%{opacity:1}50%{opacity:.3}}

/* KPI GRID */
.kpi-grid{display:grid;grid-template-columns:repeat(4,1fr);gap:12px;margin-bottom:1.5rem;}
.kpi-card{
  background:white;border-radius:var(--r-lg);
  border:1.5px solid var(--gray-200);padding:1.2rem 1.4rem;
  box-shadow:var(--shadow-sm);
}
.kpi-label{font-size:.7rem;font-weight:700;color:var(--gray-400);text-transform:uppercase;letter-spacing:.08em;margin-bottom:8px;}
.kpi-value{font-size:1.8rem;font-weight:800;line-height:1;margin-bottom:5px;}
.kpi-change{font-size:.75rem;display:flex;align-items:center;gap:4px;}
.kpi-up{color:var(--green);}
.kpi-down{color:var(--red);}

/* DASH GRID */
.dash-row{display:grid;grid-template-columns:repeat(2,1fr);gap:14px;margin-bottom:1.5rem;}
.dash-row-3{display:grid;grid-template-columns:1.6fr 1fr;gap:14px;margin-bottom:1.5rem;}

/* PANEL */
.panel{
  background:white;border:1.5px solid var(--gray-200);
  border-radius:var(--r-lg);padding:1.25rem;box-shadow:var(--shadow-sm);
}
.panel-title{
  font-size:.72rem;font-weight:700;color:var(--gray-400);
  text-transform:uppercase;letter-spacing:.1em;margin-bottom:1rem;
}
.panel-head{display:flex;align-items:center;justify-content:space-between;margin-bottom:1rem;}

/* SLOT PANELS */
.slot-grid-3{display:grid;grid-template-columns:repeat(3,1fr);gap:12px;margin-bottom:1.5rem;}
.slot-panel{
  background:white;border:1.5px solid var(--gray-200);
  border-radius:var(--r-lg);padding:1.1rem;box-shadow:var(--shadow-sm);
}
.slot-type{
  font-size:.72rem;font-weight:700;color:var(--gray-500);
  text-transform:uppercase;letter-spacing:.08em;
  display:flex;align-items:center;gap:6px;margin-bottom:10px;
}
.type-dot{width:8px;height:8px;border-radius:50%;}
.slot-counter{display:flex;align-items:center;gap:10px;margin-bottom:10px;}
.cnt-btn{
  width:34px;height:34px;border-radius:8px;border:none;
  font-size:1.1rem;font-weight:700;cursor:pointer;transition:all .15s;
  display:flex;align-items:center;justify-content:center;font-family:var(--font);
}
.cnt-minus{background:var(--red-light);color:var(--red);}
.cnt-minus:hover{background:#FECACA;}
.cnt-plus{background:var(--green-light);color:var(--green);}
.cnt-plus:hover{background:#BBF7D0;}
.cnt-num{font-size:1.7rem;font-weight:800;color:var(--gray-900);min-width:38px;text-align:center;}
.slot-cap{font-size:.72rem;color:var(--gray-400);}
.occ-track{background:var(--gray-100);border-radius:4px;height:5px;overflow:hidden;margin-top:7px;}
.occ-track-fill{height:100%;border-radius:4px;transition:width .4s;}

/* CHARTS */
.bar-chart-wrap{display:flex;align-items:flex-end;gap:5px;height:110px;padding-bottom:20px;position:relative;}
.bar-chart-wrap::after{
  content:'';position:absolute;bottom:20px;left:0;right:0;
  border-bottom:1px dashed var(--gray-200);
}
.bar-col{flex:1;display:flex;flex-direction:column;align-items:center;gap:3px;height:100%;justify-content:flex-end;}
.bar-fill{width:100%;border-radius:4px 4px 0 0;background:var(--blue-200);cursor:pointer;transition:background .15s;min-height:2px;}
.bar-fill:hover{background:var(--blue-400);}
.bar-fill.peak{background:var(--blue-500);}
.bar-lbl{font-size:.62rem;color:var(--gray-400);white-space:nowrap;}

/* DONUT */
.donut-wrap{display:flex;align-items:center;justify-content:center;gap:1.5rem;height:110px;}
.donut-legend{display:flex;flex-direction:column;gap:7px;}
.leg-item{display:flex;align-items:center;gap:7px;font-size:.76rem;color:var(--gray-600);}
.leg-dot{width:9px;height:9px;border-radius:50%;flex-shrink:0;}
.leg-val{margin-left:auto;font-weight:700;color:var(--gray-800);}

/* REPORTS */
.peak-row{display:flex;align-items:center;gap:10px;margin-bottom:8px;font-size:.8rem;}
.peak-time{font-weight:700;color:var(--gray-800);min-width:90px;}
.peak-bg{flex:1;height:5px;background:var(--gray-100);border-radius:3px;overflow:hidden;}
.peak-bar{height:100%;border-radius:3px;}
.peak-pct{font-size:.72rem;color:var(--gray-400);min-width:32px;text-align:right;}

.metric-row{
  display:flex;justify-content:space-between;align-items:center;
  padding:8px 0;border-bottom:1px solid var(--gray-100);font-size:.82rem;
}
.metric-row:last-child{border-bottom:none;}
.metric-row .ml{color:var(--gray-500);}
.metric-row .mv{font-weight:700;color:var(--gray-900);}

/* MARKETING */
.upload-zone{
  background:var(--gray-50);border:2px dashed var(--gray-300);
  border-radius:var(--r-lg);padding:1.5rem;text-align:center;
  cursor:pointer;transition:all .18s;margin-bottom:1rem;
}
.upload-zone:hover{border-color:var(--blue-400);background:var(--blue-50);}
.upload-zone p{font-size:.8rem;color:var(--gray-400);margin-top:6px;}

.promo-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:10px;}
.promo-card{
  background:white;border:1.5px solid var(--gray-200);
  border-radius:var(--r-lg);padding:1.1rem;text-align:center;
  cursor:pointer;transition:all .18s;
}
.promo-card:hover{border-color:var(--blue-300);}
.promo-card.rec{border-color:var(--blue-500);background:var(--blue-50);}
.promo-name{font-weight:800;color:var(--gray-900);margin-bottom:3px;}
.promo-badge{
  display:inline-block;font-size:.66rem;font-weight:700;letter-spacing:.06em;
  background:var(--blue-500);color:white;padding:2px 8px;border-radius:100px;
  margin-bottom:5px;text-transform:uppercase;
}
.promo-price{font-size:1.2rem;font-weight:800;color:var(--blue-500);margin-bottom:8px;}
.promo-price span{font-size:.72rem;font-weight:400;color:var(--gray-400);}
.promo-feats{list-style:none;font-size:.74rem;color:var(--gray-500);display:flex;flex-direction:column;gap:3px;}

/* TOAST */
.toast{
  position:fixed;bottom:1.5rem;right:1.5rem;z-index:999;
  background:var(--gray-900);color:white;
  border-radius:var(--r);padding:10px 16px;
  font-size:.82rem;font-weight:500;
  transform:translateY(80px);opacity:0;
  transition:all .32s cubic-bezier(.16,1,.3,1);
  pointer-events:none;display:flex;align-items:center;gap:8px;
  box-shadow:var(--shadow-lg);
}
.toast.show{transform:translateY(0);opacity:1;}

/* FOOTER */
footer{
  background:var(--gray-900);color:var(--gray-400);
  padding:2rem;text-align:center;margin-top:2rem;
}
footer a{color:var(--gray-400);text-decoration:none;font-size:.78rem;}
footer a:hover{color:var(--gray-200);}

/* RESPONSIVE */
@media(max-width:680px){
  .kpi-grid{grid-template-columns:repeat(2,1fr);}
  .slot-grid-3{grid-template-columns:1fr;}
  .dash-row,.dash-row-3{grid-template-columns:1fr;}
  .stats-strip{grid-template-columns:repeat(2,1fr);}
  .floating-card{margin:-.8rem 1rem 1.5rem;}
  nav{padding:0 1rem;}
  .hero{padding:2.5rem 1rem 4rem;}
  .content-wrap{padding:0 1rem;}
}
</style>
</head>
<body>

<!-- ── NAVBAR ── -->
<nav>
  <a class="nav-brand" href="#">
    <div class="brand-icon">🅿</div>
    Park<span class="brand-dot">Connect</span>
  </a>
  <ul class="nav-links" id="navLinks">
    <li><a href="#" class="active" onclick="navTo(event,'b2c')">Tìm bãi xe</a></li>
    <li><a href="#" onclick="navTo(event,'b2b')">Vận hành</a></li>
    <li><a href="#">Giá cả</a></li>
    <li><a href="#">Hỗ trợ</a></li>
  </ul>
  <div class="nav-actions">
    <div class="view-toggle">
      <button class="view-btn active" id="btnB2C" onclick="switchView('b2c')">🔍 Người dùng</button>
      <button class="view-btn" id="btnB2B" onclick="switchView('b2b')">📊 Vận hành</button>
    </div>
    <button class="btn btn-accent" onclick="showToast('🎉 Tạo tài khoản miễn phí!')">Đăng ký miễn phí</button>
  </div>
</nav>

<!-- ══════════════════════════════════
  B2C – USER INTERFACE
══════════════════════════════════ -->
<section class="page-section active" id="sec-b2c">

  <!-- HERO -->
  <div class="hero">
    <div class="hero-content">
      <div class="hero-badge"><span class="hero-badge-dot"></span> Real-time · Đặt trước · Không lo chỗ đậu</div>
      <h1>Tìm bãi xe nhanh,<br>đặt chỗ <em>trong 10 giây</em></h1>
      <p>Xem chỗ trống theo thời gian thực, so sánh giá, chọn chỗ & thanh toán ngay trên điện thoại. Hỗ trợ đầy đủ các loại phương tiện.</p>
      <div class="hero-search">
        <span style="font-size:16px;">📍</span>
        <input type="text" placeholder="Tìm khu vực, tòa nhà, địa chỉ...">
        <button class="btn btn-primary" onclick="showToast('🔍 Đang tìm kiếm...')">Tìm ngay</button>
      </div>
    </div>
  </div>

  <!-- FLOATING SEARCH CARD -->
  <div class="floating-card">
    <!-- VEHICLE SELECTOR -->
    <div class="vehicle-title">Chọn loại phương tiện</div>
    <div class="vehicle-row" id="vehicleRow">
      <div class="vehicle-item sel" onclick="pickVehicle(this,'Xe máy')">
        <div class="vehicle-icon-wrap">🛵</div>
        <div class="vehicle-name">Xe máy</div>
      </div>
      <div class="vehicle-item" onclick="pickVehicle(this,'Ô tô')">
        <div class="vehicle-icon-wrap">🚗</div>
        <div class="vehicle-name">Ô tô</div>
      </div>
      <div class="vehicle-item" onclick="pickVehicle(this,'SUV / 7 chỗ')">
        <div class="vehicle-icon-wrap">🚙</div>
        <div class="vehicle-name">SUV / 7 chỗ</div>
      </div>
      <div class="vehicle-item" onclick="pickVehicle(this,'Xe bán tải')">
        <div class="vehicle-icon-wrap">🛻</div>
        <div class="vehicle-name">Bán tải</div>
      </div>
      <div class="vehicle-item" onclick="pickVehicle(this,'Xe tải')">
        <div class="vehicle-icon-wrap">🚚</div>
        <div class="vehicle-name">Xe tải</div>
      </div>
      <div class="vehicle-item" onclick="pickVehicle(this,'Xe khách')">
        <div class="vehicle-icon-wrap">🚌</div>
        <div class="vehicle-name">Xe khách</div>
      </div>
      <div class="vehicle-item" onclick="pickVehicle(this,'Xe điện')">
        <div class="vehicle-icon-wrap">⚡</div>
        <div class="vehicle-name">Xe điện</div>
      </div>
    </div>

    <!-- AREA + FEATURE FILTERS -->
    <div class="filter-row">
      <span class="filter-label">Khu vực:</span>
      <div class="chip sel" onclick="toggleChip(this)">Tất cả</div>
      <div class="chip" onclick="toggleChip(this)">Quận 1</div>
      <div class="chip" onclick="toggleChip(this)">Quận 3</div>
      <div class="chip" onclick="toggleChip(this)">Quận 5</div>
      <div class="chip" onclick="toggleChip(this)">Bình Thạnh</div>
      <div class="chip" onclick="toggleChip(this)">Thủ Đức</div>
      <div style="width:1px;background:var(--gray-200);height:20px;"></div>
      <span class="filter-label">Tiện ích:</span>
      <div class="chip" onclick="toggleChip(this)">🏠 Mái che</div>
      <div class="chip" onclick="toggleChip(this)">📷 Camera 24/7</div>
      <div class="chip" onclick="toggleChip(this)">⚡ Sạc EV</div>
      <div class="chip" onclick="toggleChip(this)">✅ Còn chỗ ngay</div>
    </div>
  </div>

  <!-- STATS STRIP -->
  <div class="content-wrap">
    <div class="stats-strip">
      <div class="stat-box"><div class="stat-num">2,400<span style="font-size:1rem;color:var(--blue-400)">+</span></div><div class="stat-lbl">Bãi xe đối tác</div></div>
      <div class="stat-box"><div class="stat-num">120K<span style="font-size:1rem;color:var(--blue-400)">+</span></div><div class="stat-lbl">Lượt đặt/tháng</div></div>
      <div class="stat-box"><div class="stat-num">98.2%</div><div class="stat-lbl">Hài lòng</div></div>
      <div class="stat-box"><div class="stat-num">15 <span style="font-size:1rem;color:var(--blue-400)">TP</span></div><div class="stat-lbl">Thành phố</div></div>
    </div>

    <!-- LIST / MAP TOGGLE -->
    <div class="list-map-row" style="margin-top:1.5rem;">
      <span class="result-count" id="resultCount">12 bãi xe phù hợp</span>
      <div class="list-map-toggle">
        <button class="lm-btn active" id="btnList" onclick="switchView2('list')">≡ Danh sách</button>
        <button class="lm-btn" id="btnMap" onclick="switchView2('map')">⊞ Bản đồ</button>
      </div>
    </div>

    <!-- LIST VIEW -->
    <div id="listView" class="parking-cards">

      <div class="park-card" onclick="openModal('Bãi xe Vincom Đồng Khởi','220','68','Tầng B1, 70 Lê Thánh Tôn, Q.1','4.8','available','5.000₫','70')">
        <div class="park-thumb">🏢</div>
        <div class="park-body">
          <div class="park-name">Bãi xe Vincom Đồng Khởi</div>
          <div class="park-addr">📍 70 Lê Thánh Tôn, Quận 1 · 0.3 km</div>
          <div class="park-tags">
            <span class="tag tag-green">● 68 chỗ trống</span>
            <span class="tag tag-blue">🏠 Mái che</span>
            <span class="tag tag-blue">📷 24/7</span>
            <span class="tag tag-gray">Tầng hầm</span>
          </div>
        </div>
        <div class="park-right">
          <div class="park-price">5.000₫ <span>/giờ</span></div>
          <div class="park-rating"><span class="star">★</span> 4.8 · 312 đánh giá</div>
          <div class="occ-bar"><div class="occ-fill" style="width:70%;background:var(--amber);"></div></div>
          <div class="occ-txt">70% lấp đầy</div>
        </div>
      </div>

      <div class="park-card" onclick="openModal('Green Park – Landmark 81','600','341','Tầng B2–B3, Vinhomes Central Park, Bình Thạnh','4.9','available','8.000₫','43')">
        <div class="park-thumb">🌿</div>
        <div class="park-body">
          <div class="park-name">Green Park – Landmark 81</div>
          <div class="park-addr">📍 Vinhomes Central Park, Bình Thạnh · 2.1 km</div>
          <div class="park-tags">
            <span class="tag tag-green">● 341 chỗ trống</span>
            <span class="tag tag-blue">🏠 Mái che</span>
            <span class="tag tag-blue">⚡ Sạc EV</span>
            <span class="tag tag-blue">24/7</span>
          </div>
        </div>
        <div class="park-right">
          <div class="park-price">8.000₫ <span>/giờ</span></div>
          <div class="park-rating"><span class="star">★</span> 4.9 · 856 đánh giá</div>
          <div class="occ-bar"><div class="occ-fill" style="width:43%;background:var(--green);"></div></div>
          <div class="occ-txt">43% lấp đầy</div>
        </div>
      </div>

      <div class="park-card" onclick="openModal('Parkson Hùng Vương','150','102','Tầng B1, Hùng Vương Plaza, Q.5','4.5','available','4.000₫','32')">
        <div class="park-thumb">🏬</div>
        <div class="park-body">
          <div class="park-name">Parkson Hùng Vương Plaza</div>
          <div class="park-addr">📍 Hùng Vương Plaza, Quận 5 · 1.2 km</div>
          <div class="park-tags">
            <span class="tag tag-green">● 102 chỗ trống</span>
            <span class="tag tag-blue">🏠 Mái che</span>
            <span class="tag tag-gray">T2–CN 7:00–22:00</span>
          </div>
        </div>
        <div class="park-right">
          <div class="park-price">4.000₫ <span>/giờ</span></div>
          <div class="park-rating"><span class="star">★</span> 4.5 · 201 đánh giá</div>
          <div class="occ-bar"><div class="occ-fill" style="width:32%;background:var(--green);"></div></div>
          <div class="occ-txt">32% lấp đầy</div>
        </div>
      </div>

      <div class="park-card" onclick="openModal('Bãi xe Bến Thành','80','4','Khu vực Chợ Bến Thành, Q.1','3.9','busy','3.000₫','95')">
        <div class="park-thumb">🗿</div>
        <div class="park-body">
          <div class="park-name">Bãi xe Khu Bến Thành</div>
          <div class="park-addr">📍 Khu vực Chợ Bến Thành, Quận 1 · 0.7 km</div>
          <div class="park-tags">
            <span class="tag tag-amber">⚠ Còn 4 chỗ</span>
            <span class="tag tag-gray">Ngoài trời</span>
            <span class="tag tag-gray">6:00–22:00</span>
          </div>
        </div>
        <div class="park-right">
          <div class="park-price">3.000₫ <span>/giờ</span></div>
          <div class="park-rating"><span class="star">★</span> 3.9 · 88 đánh giá</div>
          <div class="occ-bar"><div class="occ-fill" style="width:95%;background:var(--red);"></div></div>
          <div class="occ-txt">95% lấp đầy</div>
        </div>
      </div>

    </div>

    <!-- MAP VIEW -->
    <div id="mapView" style="display:none;">
      <div class="map-view">
        <div class="map-inner">
          <div class="map-grid-bg"></div>
          <!-- roads -->
          <div class="map-road-h" style="top:38%;left:0;right:0;height:13px;"></div>
          <div class="map-road-h" style="top:66%;left:0;right:0;height:10px;"></div>
          <div class="map-road-v" style="left:28%;top:0;bottom:0;width:11px;"></div>
          <div class="map-road-v" style="left:63%;top:0;bottom:0;width:11px;"></div>
          <!-- blocks -->
          <div class="map-block" style="left:3%;top:5%;width:22%;height:30%;opacity:.5;"></div>
          <div class="map-block" style="left:32%;top:5%;width:28%;height:28%;"></div>
          <div class="map-block" style="left:67%;top:5%;width:28%;height:30%;opacity:.7;"></div>
          <div class="map-block" style="left:3%;top:48%;width:22%;height:30%;opacity:.6;"></div>
          <div class="map-block" style="left:32%;top:50%;width:28%;height:28%;opacity:.5;"></div>
          <div class="map-block" style="left:67%;top:50%;width:28%;height:28%;"></div>
          <!-- my location -->
          <div class="my-pin" style="position:absolute;left:48%;top:46%;transform:translate(-50%,-50%);"></div>
          <!-- pins -->
          <div class="map-pin" style="left:24%;top:36%;">
            <div class="pin-label ok">5K · 68 chỗ</div>
          </div>
          <div class="map-pin" style="left:52%;top:55%;">
            <div class="pin-label">4K · 102 chỗ</div>
          </div>
          <div class="map-pin" style="left:37%;top:63%;">
            <div class="pin-label warn">3K · 4 chỗ</div>
          </div>
          <div class="map-pin" style="left:76%;top:27%;">
            <div class="pin-label ok">8K · 341 chỗ</div>
          </div>
        </div>
      </div>
    </div>

  </div><!-- /content-wrap -->
</section>

<!-- ══════════════════════════════════
  B2B – OPERATOR DASHBOARD
══════════════════════════════════ -->
<section class="page-section" id="sec-b2b">
<div class="dash-layout">

  <!-- HEADER -->
  <div class="dash-header">
    <div>
      <div class="dash-title">Operator <span>Dashboard</span></div>
      <div class="dash-sub">Bãi xe Vincom Đồng Khởi · Quản lý: Nguyễn Văn Minh</div>
    </div>
    <div style="display:flex;gap:8px;align-items:center;">
      <div class="live-pill"><div class="live-dot"></div> Live · Cập nhật vừa xong</div>
      <button class="btn btn-ghost" onclick="showToast('📊 Đang xuất báo cáo PDF...')">Xuất báo cáo</button>
      <button class="btn btn-primary" onclick="showToast('⚙ Mở cài đặt bãi xe')">Cài đặt</button>
    </div>
  </div>

  <!-- KPI CARDS -->
  <div class="kpi-grid">
    <div class="kpi-card">
      <div class="kpi-label">Tỷ lệ lấp đầy hôm nay</div>
      <div class="kpi-value" style="color:var(--amber);" id="kpiOcc">70%</div>
      <div class="kpi-change kpi-up">↑ +5.2% so với hôm qua</div>
    </div>
    <div class="kpi-card">
      <div class="kpi-label">Doanh thu hôm nay</div>
      <div class="kpi-value" style="color:var(--green);" id="kpiRev">2.4M₫</div>
      <div class="kpi-change kpi-up">↑ +12% so với TB tuần</div>
    </div>
    <div class="kpi-card">
      <div class="kpi-label">Lượt vào ra hôm nay</div>
      <div class="kpi-value" style="color:var(--blue-500);" id="kpiTrips">842</div>
      <div class="kpi-change kpi-down">↓ –3% so với hôm qua</div>
    </div>
    <div class="kpi-card">
      <div class="kpi-label">Chỗ trống hiện tại</div>
      <div class="kpi-value" style="color:var(--green);" id="kpiSlots">66</div>
      <div class="kpi-change" style="color:var(--gray-400);">/ 220 tổng chỗ</div>
    </div>
  </div>

  <!-- SLOT MANAGEMENT -->
  <div class="panel" style="margin-bottom:1.5rem;">
    <div class="panel-head">
      <div class="panel-title" style="margin:0;">Quản lý chỗ đỗ – Cập nhật thủ công</div>
      <span style="font-size:.74rem;color:var(--gray-400);">Chạm +/− để điều chỉnh số chỗ trống</span>
    </div>
    <div class="slot-grid-3">
      <div class="slot-panel">
        <div class="slot-type"><span class="type-dot" style="background:var(--amber);"></span> Xe máy</div>
        <div class="slot-counter">
          <button class="cnt-btn cnt-minus" onclick="adjSlot('motor',-1)">−</button>
          <span class="cnt-num" id="motorSlot">44</span>
          <button class="cnt-btn cnt-plus" onclick="adjSlot('motor',1)">+</button>
        </div>
        <div class="slot-cap">Tổng: 120 · Đang dùng: <strong id="motorUsed">76</strong></div>
        <div class="occ-track"><div class="occ-track-fill" id="motorBar" style="width:63%;background:var(--amber);"></div></div>
      </div>
      <div class="slot-panel">
        <div class="slot-type"><span class="type-dot" style="background:var(--blue-500);"></span> Ô tô</div>
        <div class="slot-counter">
          <button class="cnt-btn cnt-minus" onclick="adjSlot('car',-1)">−</button>
          <span class="cnt-num" id="carSlot">18</span>
          <button class="cnt-btn cnt-plus" onclick="adjSlot('car',1)">+</button>
        </div>
        <div class="slot-cap">Tổng: 80 · Đang dùng: <strong id="carUsed">62</strong></div>
        <div class="occ-track"><div class="occ-track-fill" id="carBar" style="width:78%;background:var(--blue-500);"></div></div>
      </div>
      <div class="slot-panel">
        <div class="slot-type"><span class="type-dot" style="background:var(--green);"></span> VIP / SUV</div>
        <div class="slot-counter">
          <button class="cnt-btn cnt-minus" onclick="adjSlot('vip',-1)">−</button>
          <span class="cnt-num" id="vipSlot">4</span>
          <button class="cnt-btn cnt-plus" onclick="adjSlot('vip',1)">+</button>
        </div>
        <div class="slot-cap">Tổng: 20 · Đang dùng: <strong id="vipUsed">16</strong></div>
        <div class="occ-track"><div class="occ-track-fill" id="vipBar" style="width:80%;background:var(--green);"></div></div>
      </div>
    </div>
  </div>

  <!-- CHARTS ROW -->
  <div class="dash-row-3">
    <div class="panel">
      <div class="panel-title">Doanh thu theo giờ hôm nay (nghìn đồng)</div>
      <div class="bar-chart-wrap" id="revenueChart"></div>
    </div>
    <div class="panel">
      <div class="panel-title">Phân bổ loại xe</div>
      <div class="donut-wrap">
        <svg width="96" height="96" viewBox="0 0 36 36">
          <circle cx="18" cy="18" r="13" fill="none" stroke="var(--gray-100)" stroke-width="5"/>
          <circle cx="18" cy="18" r="13" fill="none" stroke="var(--amber)" stroke-width="5" stroke-dasharray="55 100" stroke-dashoffset="-25" transform="rotate(-90 18 18)"/>
          <circle cx="18" cy="18" r="13" fill="none" stroke="var(--blue-400)" stroke-width="5" stroke-dasharray="28 100" stroke-dashoffset="-80" transform="rotate(-90 18 18)"/>
          <circle cx="18" cy="18" r="13" fill="none" stroke="var(--green)" stroke-width="5" stroke-dasharray="10 100" stroke-dashoffset="-108" transform="rotate(-90 18 18)"/>
          <text x="18" y="19" text-anchor="middle" dominant-baseline="central" fill="var(--gray-800)" font-size="5.5" font-weight="700" font-family="Plus Jakarta Sans,sans-serif">70%</text>
        </svg>
        <div class="donut-legend">
          <div class="leg-item"><span class="leg-dot" style="background:var(--amber);"></span>Xe máy<span class="leg-val">55%</span></div>
          <div class="leg-item"><span class="leg-dot" style="background:var(--blue-400);"></span>Ô tô<span class="leg-val">28%</span></div>
          <div class="leg-item"><span class="leg-dot" style="background:var(--green);"></span>VIP/SUV<span class="leg-val">10%</span></div>
          <div class="leg-item"><span class="leg-dot" style="background:var(--gray-300);"></span>Khác<span class="leg-val">7%</span></div>
        </div>
      </div>
    </div>
  </div>

  <!-- REPORTS ROW -->
  <div class="dash-row">
    <div class="panel">
      <div class="panel-head">
        <div class="panel-title" style="margin:0;">Giờ cao điểm hôm nay</div>
        <span style="font-size:.72rem;color:var(--blue-500);font-weight:600;">Thứ 3, 06/05</span>
      </div>
      <div class="peak-row">
        <span class="peak-time">07:00 – 08:00</span>
        <div class="peak-bg"><div class="peak-bar" style="width:75%;background:var(--amber);"></div></div>
        <span class="peak-pct">75%</span>
      </div>
      <div class="peak-row">
        <span class="peak-time">12:00 – 13:00</span>
        <div class="peak-bg"><div class="peak-bar" style="width:92%;background:var(--red);"></div></div>
        <span class="peak-pct">92%</span>
      </div>
      <div class="peak-row">
        <span class="peak-time">17:00 – 19:00</span>
        <div class="peak-bg"><div class="peak-bar" style="width:88%;background:var(--amber);"></div></div>
        <span class="peak-pct">88%</span>
      </div>
      <div class="peak-row" style="margin-bottom:0;">
        <span class="peak-time">21:00 – 22:00</span>
        <div class="peak-bg"><div class="peak-bar" style="width:34%;background:var(--blue-300);"></div></div>
        <span class="peak-pct">34%</span>
      </div>
    </div>

    <div class="panel">
      <div class="panel-head">
        <div class="panel-title" style="margin:0;">Hiệu suất tài sản</div>
        <span class="tag tag-green">+15% target</span>
      </div>
      <div class="metric-row"><span class="ml">Lượng khách TB/ngày</span><span class="mv" style="color:var(--blue-500);">712</span></div>
      <div class="metric-row"><span class="ml">Doanh thu TB/ngày</span><span class="mv" style="color:var(--green);">2.2M₫</span></div>
      <div class="metric-row"><span class="ml">Asset utilization</span><span class="mv" style="color:var(--amber);">68.4%</span></div>
      <div class="metric-row"><span class="ml">Doanh thu/chỗ/ngày</span><span class="mv">10.000₫</span></div>
      <div class="metric-row"><span class="ml">Tiềm năng tối ưu</span><span class="mv" style="color:var(--green);">+26%</span></div>
    </div>
  </div>

  <!-- RESEARCH NOTE -->
  <div style="background:var(--blue-50);border:1.5px solid var(--blue-200);border-radius:var(--r-lg);padding:1rem 1.25rem;margin-bottom:1.5rem;display:flex;align-items:flex-start;gap:10px;">
    <span style="font-size:1.1rem;flex-shrink:0;">📈</span>
    <p style="font-size:.8rem;color:var(--blue-700);line-height:1.65;">
      <strong>Theo nghiên cứu Urban Mobility:</strong> Tối ưu occupancy có thể tăng doanh thu bãi xe <strong>15–30%</strong>. 
      Dashboard của bạn hiện đang ở 68.4% — tiềm năng tăng thêm <strong>~26%</strong> doanh thu nếu đạt 90% occupancy giờ cao điểm.
    </p>
  </div>

  <!-- MARKETING -->
  <div class="panel">
    <div class="panel-head">
      <div class="panel-title" style="margin:0;">Marketing & Hồ sơ bãi xe</div>
    </div>
    <div class="upload-zone" onclick="showToast('📸 Chức năng tải ảnh sắp ra mắt!')">
      <div style="font-size:1.8rem;">📸</div>
      <p>Kéo thả ảnh bãi xe hoặc <strong style="color:var(--blue-500);">chọn từ máy tính</strong></p>
      <p style="font-size:.72rem;margin-top:3px;">JPG, PNG tối đa 10MB · Khuyến nghị 1200×800px</p>
    </div>
    <div style="font-size:.72rem;font-weight:700;letter-spacing:.1em;text-transform:uppercase;color:var(--gray-400);margin-bottom:.8rem;">Gói quảng bá (Featured Listing)</div>
    <div class="promo-grid">
      <div class="promo-card">
        <div class="promo-name">Basic</div>
        <div class="promo-price">Miễn phí <span>/tháng</span></div>
        <ul class="promo-feats">
          <li>✓ Hiển thị trên nền tảng</li>
          <li>✓ Hồ sơ cơ bản</li>
          <li style="color:var(--gray-300);">✗ Ưu tiên tìm kiếm</li>
          <li style="color:var(--gray-300);">✗ Phân tích nâng cao</li>
        </ul>
        <button class="btn btn-ghost" style="width:100%;justify-content:center;margin-top:12px;font-size:.78rem;">Đang dùng</button>
      </div>
      <div class="promo-card rec">
        <div class="promo-badge">★ Phổ biến nhất</div>
        <div class="promo-name">Pro</div>
        <div class="promo-price">299.000₫ <span>/tháng</span></div>
        <ul class="promo-feats">
          <li>✓ Ưu tiên top tìm kiếm</li>
          <li>✓ Banner quảng cáo</li>
          <li>✓ Phân tích nâng cao</li>
          <li>✓ Hỗ trợ ưu tiên 24/7</li>
        </ul>
        <button class="btn btn-primary" style="width:100%;justify-content:center;margin-top:12px;font-size:.78rem;" onclick="showToast('💳 Chuyển đến trang thanh toán...')">Nâng cấp ngay</button>
      </div>
      <div class="promo-card">
        <div class="promo-name">Enterprise</div>
        <div class="promo-price">Liên hệ <span></span></div>
        <ul class="promo-feats">
          <li>✓ Quảng bá toàn hệ thống</li>
          <li>✓ API tích hợp riêng</li>
          <li>✓ Account manager</li>
          <li>✓ SLA cam kết 99.9%</li>
        </ul>
        <button class="btn btn-outline" style="width:100%;justify-content:center;margin-top:12px;font-size:.78rem;" onclick="showToast('📞 Đội sales liên hệ trong 24h!')">Liên hệ tư vấn</button>
      </div>
    </div>
  </div>

</div>
</section>

<!-- ── FOOTER ── -->
<footer>
  <p style="margin-bottom:.8rem;">
    <a href="#" style="font-size:1rem;font-weight:800;color:white;text-decoration:none;">🅿 ParkConnect</a>
  </p>
  <p style="margin-bottom:.8rem;font-size:.8rem;">Nền tảng quản lý bãi xe thông minh · TP. Hồ Chí Minh</p>
  <div style="display:flex;gap:1.5rem;justify-content:center;flex-wrap:wrap;">
    <a href="#">Điều khoản</a>
    <a href="#">Bảo mật</a>
    <a href="#">Liên hệ</a>
    <a href="#">API Docs</a>
    <a href="#">Blog</a>
  </div>
  <p style="margin-top:1rem;font-size:.72rem;color:var(--gray-600);">© 2025 ParkConnect · All rights reserved</p>
</footer>

<!-- ── BOOKING MODAL ── -->
<div class="modal-overlay" id="bookingModal">
  <div class="modal">
    <button class="modal-close" onclick="closeModal()">✕</button>

    <!-- STEP 1: DETAIL -->
    <div id="step1">
      <div class="modal-header">
        <div class="modal-title" id="mName">–</div>
        <div class="modal-sub" id="mAddr">–</div>
      </div>

      <!-- Photo placeholder -->
      <div style="background:var(--blue-50);border-radius:var(--r-lg);height:100px;display:flex;align-items:center;justify-content:center;font-size:2.5rem;margin-bottom:1rem;">🏢</div>

      <!-- Stats row -->
      <div style="display:flex;gap:8px;flex-wrap:wrap;margin-bottom:1rem;">
        <span class="tag tag-green" id="mSlots">–</span>
        <span class="tag tag-blue" id="mCap">–</span>
        <span class="tag tag-gray" id="mRating">–</span>
        <span class="tag tag-blue">30 phút giữ chỗ</span>
      </div>

      <!-- SLOT PICKER -->
      <div style="font-size:.72rem;font-weight:700;letter-spacing:.08em;text-transform:uppercase;color:var(--gray-400);margin-bottom:6px;">Chọn chỗ đỗ</div>
      <div class="modal-slot-grid">
        <div class="ms taken">A1</div><div class="ms taken">A2</div><div class="ms free" onclick="pickSlot(this)">A3</div>
        <div class="ms free" onclick="pickSlot(this)">A4</div><div class="ms taken">A5</div>
        <div class="ms free" onclick="pickSlot(this)">B1</div><div class="ms taken">B2</div><div class="ms taken">B3</div>
        <div class="ms free" onclick="pickSlot(this)">B4</div><div class="ms free" onclick="pickSlot(this)">B5</div>
        <div class="ms taken">C1</div><div class="ms free" onclick="pickSlot(this)">C2</div><div class="ms free" onclick="pickSlot(this)">C3</div>
        <div class="ms taken">C4</div><div class="ms free" onclick="pickSlot(this)">C5</div>
      </div>

      <!-- TIME PICKER -->
      <div style="font-size:.72rem;font-weight:700;letter-spacing:.08em;text-transform:uppercase;color:var(--gray-400);margin-bottom:6px;">Giờ vào</div>
      <div class="time-grid">
        <div class="t-btn off">7:00</div><div class="t-btn off">8:00</div>
        <div class="t-btn" onclick="pickTime(this)">9:00</div><div class="t-btn" onclick="pickTime(this)">10:00</div>
        <div class="t-btn on" onclick="pickTime(this)">11:00</div><div class="t-btn" onclick="pickTime(this)">12:00</div>
        <div class="t-btn" onclick="pickTime(this)">13:00</div><div class="t-btn" onclick="pickTime(this)">14:00</div>
      </div>

      <button class="btn btn-primary" style="width:100%;justify-content:center;margin-top:.5rem;" onclick="showStep(2)">Tiếp tục →</button>
    </div>

    <!-- STEP 2: PAYMENT -->
    <div id="step2" style="display:none;">
      <div class="modal-header">
        <div class="modal-title">Chọn thanh toán</div>
        <div class="modal-sub" id="mSummaryPark">–</div>
      </div>

      <div class="price-row"><span class="lbl">Phí đỗ xe (2 giờ)</span><span class="val" id="mPrice">–</span></div>
      <div class="price-row"><span class="lbl">Phí dịch vụ</span><span class="val">2.000₫</span></div>
      <div class="price-row"><span class="lbl">Ưu đãi lần đầu</span><span class="val" style="color:var(--green);">–2.000₫</span></div>
      <div class="price-row grand" style="padding-top:8px;"><span class="lbl">Tổng cộng</span><span class="val" id="mTotal">–</span></div>

      <div style="font-size:.72rem;font-weight:700;letter-spacing:.08em;text-transform:uppercase;color:var(--gray-400);margin:1rem 0 .5rem;">Phương thức thanh toán</div>
      <div class="pay-list">
        <div class="pay-row on" onclick="pickPay(this)">
          <div class="pm-badge pm-momo">MM</div>
          <div><div class="pm-name">Ví MoMo</div><div class="pm-sub">Số dư: <span class="pm-balance">125.000₫</span></div></div>
          <div class="pm-radio on"><div class="pm-radio-dot"></div></div>
        </div>
        <div class="pay-row" onclick="pickPay(this)">
          <div class="pm-badge pm-zalo">ZL</div>
          <div><div class="pm-name">ZaloPay</div><div class="pm-sub">Số dư: <span class="pm-balance">85.000₫</span></div></div>
          <div class="pm-radio"></div>
        </div>
        <div class="pay-row" onclick="pickPay(this)">
          <div class="pm-badge pm-vnpay">VN</div>
          <div><div class="pm-name">VNPay</div><div class="pm-sub">Thanh toán QR ngân hàng</div></div>
          <div class="pm-radio"></div>
        </div>
        <div class="pay-row" onclick="pickPay(this)">
          <div class="pm-badge pm-card">💳</div>
          <div><div class="pm-name">Thẻ ngân hàng</div><div class="pm-sub">Visa / Mastercard / ATM nội địa</div></div>
          <div class="pm-radio"></div>
        </div>
      </div>

      <div style="background:var(--amber-light);border:1px solid #FDE68A;border-radius:var(--r);padding:8px 12px;font-size:.76rem;color:#92400E;margin-bottom:1rem;display:flex;gap:6px;">
        ⚠ Chỗ đỗ được giữ <strong>30 phút</strong> sau giờ đặt. Quá thời gian tự động huỷ.
      </div>

      <div style="display:flex;gap:8px;">
        <button class="btn btn-ghost" style="flex:0 0 auto;" onclick="showStep(1)">← Quay lại</button>
        <button class="btn btn-accent" style="flex:1;justify-content:center;" onclick="showStep(3)">Xác nhận & Thanh toán</button>
      </div>
    </div>

    <!-- STEP 3: SUCCESS -->
    <div id="step3" style="display:none;">
      <div class="success-wrap">
        <div class="success-circle">✓</div>
        <div style="font-size:1.2rem;font-weight:800;color:var(--gray-900);margin-bottom:4px;">Đặt chỗ thành công!</div>
        <div style="font-size:.8rem;color:var(--gray-400);">Mã xác nhận đã gửi về SĐT của bạn</div>
        <div class="qr-box"><div class="qr-inner"></div></div>
        <div style="font-size:.76rem;color:var(--gray-500);margin-bottom:1rem;">
          Mã đặt chỗ: <strong style="color:var(--blue-500);font-family:monospace;">#PC-2025-8842</strong>
        </div>
        <div style="background:var(--gray-50);border:1px solid var(--gray-200);border-radius:var(--r-lg);padding:1rem;text-align:left;margin-bottom:1rem;">
          <div class="price-row"><span class="lbl">Bãi xe</span><span class="val" id="sName">–</span></div>
          <div class="price-row"><span class="lbl">Thời gian</span><span class="val">11:00 – 13:00 hôm nay</span></div>
          <div class="price-row" style="border-bottom:none;"><span class="lbl">Đã thanh toán</span><span class="val" style="color:var(--green);" id="sPaid">–</span></div>
        </div>
        <div style="display:flex;gap:8px;width:100%;">
          <button class="btn btn-primary" style="flex:1;justify-content:center;" onclick="showToast('🧭 Mở Google Maps...')">🧭 Chỉ đường</button>
          <button class="btn btn-ghost" style="flex:1;justify-content:center;" onclick="closeModal()">Đóng</button>
        </div>
      </div>
    </div>
  </div>
</div>

<!-- TOAST -->
<div class="toast" id="toast"></div>

<script>
/* ── VIEW SWITCH ── */
function switchView(v) {
  document.getElementById('sec-b2c').classList.toggle('active', v==='b2c');
  document.getElementById('sec-b2b').classList.toggle('active', v==='b2b');
  document.getElementById('btnB2C').classList.toggle('active', v==='b2c');
  document.getElementById('btnB2B').classList.toggle('active', v==='b2b');
  if (v==='b2b') buildChart();
}
function navTo(e, v) {
  e.preventDefault();
  document.querySelectorAll('.nav-links a').forEach(a=>a.classList.remove('active'));
  e.target.classList.add('active');
  switchView(v);
}

/* ── VEHICLE ── */
function pickVehicle(el, name) {
  document.querySelectorAll('.vehicle-item').forEach(i=>i.classList.remove('sel'));
  el.classList.add('sel');
  showToast('🚗 Đã chọn: ' + name);
}

/* ── CHIP ── */
function toggleChip(el) {
  el.classList.toggle('sel');
}

/* ── LIST/MAP ── */
function switchView2(m) {
  document.getElementById('listView').style.display = m==='list' ? 'flex' : 'none';
  document.getElementById('mapView').style.display = m==='map' ? 'block' : 'none';
  document.getElementById('btnList').classList.toggle('active', m==='list');
  document.getElementById('btnMap').classList.toggle('active', m==='map');
  document.getElementById('listView').style.flexDirection = 'column';
}

/* ── SLOT DATA ── */
const slots = { motor:{free:44,total:120}, car:{free:18,total:80}, vip:{free:4,total:20} };
function adjSlot(t, d) {
  const s = slots[t];
  s.free = Math.max(0, Math.min(s.total, s.free + d));
  const used = s.total - s.free;
  const pct = Math.round((used/s.total)*100);
  document.getElementById(t+'Slot').textContent = s.free;
  document.getElementById(t+'Used').textContent = used;
  document.getElementById(t+'Bar').style.width = pct + '%';
  const tFree = slots.motor.free + slots.car.free + slots.vip.free;
  const tOcc = Math.round(((220 - tFree)/220)*100);
  document.getElementById('kpiOcc').textContent = tOcc + '%';
  document.getElementById('kpiSlots').textContent = tFree;
  showToast(d > 0 ? '✓ Thêm 1 chỗ trống' : '✓ Ghi nhận 1 xe vào bãi');
}

/* ── CHART ── */
const hrs = ['6h','7h','8h','9h','10h','11h','12h','13h','14h','15h','16h','17h','18h','19h','20h'];
const revs = [80,180,210,150,120,200,280,240,130,110,160,290,270,140,90];
function buildChart() {
  const c = document.getElementById('revenueChart');
  if (!c || c.children.length) return;
  const mx = Math.max(...revs);
  hrs.forEach((h,i) => {
    const pct = (revs[i]/mx)*100;
    const col = document.createElement('div'); col.className='bar-col';
    const bar = document.createElement('div');
    bar.className='bar-fill'+(revs[i]>250?' peak':'');
    bar.style.height=pct+'%';
    bar.title=h+': '+revs[i]+'K₫';
    bar.onclick=()=>showToast(h+' → '+revs[i]+'K₫ doanh thu');
    const lbl = document.createElement('div'); lbl.className='bar-lbl'; lbl.textContent=h;
    col.appendChild(bar); col.appendChild(lbl);
    c.appendChild(col);
  });
}

/* ── MODAL ── */
let _price = '';
function openModal(name, total, free, addr, rating, status, price, occ) {
  _price = price;
  document.getElementById('mName').textContent = name;
  document.getElementById('mAddr').textContent = '📍 ' + addr;
  document.getElementById('mSlots').textContent = '● ' + free + ' chỗ trống';
  document.getElementById('mCap').textContent = total + ' tổng chỗ';
  document.getElementById('mRating').textContent = '★ ' + rating;
  document.getElementById('mSummaryPark').textContent = name + ' · Chỗ đã chọn · 11:00–13:00';
  const base = parseInt(price) * 2;
  document.getElementById('mPrice').textContent = price.replace('₫','') * 2 + '₫' || price;
  document.getElementById('mTotal').textContent = (parseInt(price)*2 + 2000 - 2000).toLocaleString('vi') + '₫';
  document.getElementById('sName').textContent = name;
  document.getElementById('sPaid').textContent = (parseInt(price)*2).toLocaleString('vi') + '₫';
  document.getElementById('bookingModal').classList.add('open');
  showStep(1);
}
function closeModal() { document.getElementById('bookingModal').classList.remove('open'); }
document.getElementById('bookingModal').addEventListener('click', e => { if(e.target===e.currentTarget) closeModal(); });

function showStep(n) {
  [1,2,3].forEach(i => document.getElementById('step'+i).style.display = i===n ? 'block' : 'none');
  if (n === 3) showToast('🎉 Thanh toán thành công!');
}

function pickSlot(el) {
  document.querySelectorAll('.ms.sel').forEach(s => { s.classList.remove('sel'); s.classList.add('free'); });
  el.classList.remove('free'); el.classList.add('sel');
}
function pickTime(el) {
  if (el.classList.contains('off')) return;
  document.querySelectorAll('.t-btn').forEach(b => b.classList.remove('on'));
  el.classList.add('on');
}
function pickPay(el) {
  document.querySelectorAll('.pay-row').forEach(r => {
    r.classList.remove('on');
    const ring = r.querySelector('.pm-radio');
    ring.classList.remove('on');
    const dot = ring.querySelector('.pm-radio-dot');
    if (dot) dot.remove();
  });
  el.classList.add('on');
  const ring = el.querySelector('.pm-radio');
  ring.classList.add('on');
  const dot = document.createElement('div'); dot.className='pm-radio-dot';
  ring.appendChild(dot);
}

/* ── TOAST ── */
let tt;
function showToast(msg) {
  const t = document.getElementById('toast');
  t.textContent = msg;
  t.classList.add('show');
  clearTimeout(tt);
  tt = setTimeout(() => t.classList.remove('show'), 2600);
}
</script>
</body>
</html>
