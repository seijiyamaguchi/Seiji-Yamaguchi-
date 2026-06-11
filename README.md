
<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Grace Reset™</title>
<link href="https://fonts.googleapis.com/css2?family=Playfair+Display:ital,wght@0,700;0,900;1,400;1,700&family=DM+Sans:wght@300;400;500&display=swap" rel="stylesheet">
<style>
*,*::before,*::after{box-sizing:border-box;margin:0;padding:0;}

:root{
  --olive:   #796D3E;
  --slate:   #A3B4BE;
  --charcoal:#574D48;
  --gold:    #B48B3F;
  --rose:    #BA6E6E;
  --ink:     #2A2420;
  --parch:   #F2EDE4;
  --parch2:  #EDE7DC;
}

html{scroll-behavior:smooth;}

body{
  font-family:'DM Sans',sans-serif;
  font-weight:300;
  background:var(--parch);
  color:var(--ink);
  overflow-x:hidden;
}

/* GRAIN OVERLAY */
body::before{
  content:'';
  position:fixed;top:0;left:0;right:0;bottom:0;
  background-image:url("data:image/svg+xml,%3Csvg viewBox='0 0 256 256' xmlns='http://www.w3.org/2000/svg'%3E%3Cfilter id='noise'%3E%3CfeTurbulence type='fractalNoise' baseFrequency='0.9' numOctaves='4' stitchTiles='stitch'/%3E%3C/filter%3E%3Crect width='100%25' height='100%25' filter='url(%23noise)' opacity='1'/%3E%3C/svg%3E");
  opacity:0.035;
  pointer-events:none;
  z-index:999;
}

/* ── NAV ── */
nav{
  position:fixed;top:0;left:0;right:0;z-index:100;
  display:flex;align-items:center;justify-content:space-between;
  padding:1.4rem 6%;
  mix-blend-mode:normal;
}
.nav-logo{
  display:flex;align-items:center;gap:0.55rem;
}
.nav-logo-mark{width:22px;height:22px;filter:brightness(1.6);}
.nav-brand{
  font-family:'DM Sans',sans-serif;
  font-size:0.72rem;letter-spacing:0.22em;text-transform:uppercase;
  color:var(--parch);font-weight:400;
}
.nav-brand.dark{color:var(--ink);}
.nav-links{display:flex;gap:2.5rem;}
.nav-links a{
  text-decoration:none;font-size:0.72rem;
  letter-spacing:0.12em;text-transform:uppercase;
  color:rgba(242,237,228,0.6);transition:color 0.2s;
}
.nav-links a:hover{color:var(--parch);}
.nav-cta-pill{
  background:transparent;
  border:1px solid rgba(242,237,228,0.4);
  color:var(--parch);
  padding:0.5rem 1.4rem;font-size:0.72rem;
  letter-spacing:0.12em;text-transform:uppercase;
  border-radius:100px;cursor:pointer;
  font-family:'DM Sans',sans-serif;
  transition:background 0.2s,border-color 0.2s;
}
.nav-cta-pill:hover{background:rgba(242,237,228,0.12);border-color:rgba(242,237,228,0.7);}

/* ── HERO ── */
.hero{
  background:var(--charcoal);
  min-height:100vh;
  display:flex;flex-direction:column;
  justify-content:flex-end;
  padding:0 6% 7%;
  position:relative;overflow:hidden;
}

.hero-bg-star{
  position:absolute;top:-8%;right:-4%;
  width:55vw;height:55vw;
  opacity:0.06;
  pointer-events:none;
}

.hero-eyebrow{
  font-size:0.7rem;letter-spacing:0.28em;text-transform:uppercase;
  color:var(--gold);margin-bottom:2rem;
}
.hero-headline{
  font-family:'Playfair Display',serif;
  line-height:0.92;
  margin-bottom:2.8rem;
}
.hero-headline .line1{
  font-size:clamp(5rem,12vw,11rem);
  font-weight:900;color:var(--parch);
  display:block;letter-spacing:-0.02em;
}
.hero-headline .line2{
  font-size:clamp(4rem,10vw,9rem);
  font-weight:400;font-style:italic;
  color:var(--gold);display:block;
  letter-spacing:0.01em;margin-left:2vw;
}
.hero-headline .line3{
  font-size:clamp(4.5rem,11vw,10rem);
  font-weight:900;color:var(--parch);
  display:block;letter-spacing:-0.02em;
}

.hero-bottom{
  display:flex;align-items:flex-end;justify-content:space-between;
  flex-wrap:wrap;gap:2rem;
}
.hero-desc{
  font-size:0.9rem;color:rgba(242,237,228,0.55);
  max-width:360px;line-height:1.8;
}
.hero-cta-group{display:flex;align-items:center;gap:1.4rem;flex-wrap:wrap;}
.btn-pill{
  display:inline-block;
  background:var(--gold);color:#fff;
  text-decoration:none;
  padding:1rem 2.4rem;font-size:0.8rem;
  letter-spacing:0.12em;text-transform:uppercase;
  border-radius:100px;border:none;cursor:pointer;
  font-family:'DM Sans',sans-serif;font-weight:400;
  transition:background 0.25s,transform 0.2s;
}
.btn-pill:hover{background:var(--olive);transform:translateY(-2px);}
.btn-ghost-pill{
  display:inline-block;
  background:transparent;color:rgba(242,237,228,0.7);
  text-decoration:none;
  padding:1rem 2.4rem;font-size:0.8rem;
  letter-spacing:0.12em;text-transform:uppercase;
  border-radius:100px;
  border:1px solid rgba(242,237,228,0.25);cursor:pointer;
  font-family:'DM Sans',sans-serif;font-weight:400;
  transition:border-color 0.25s,color 0.25s;
}
.btn-ghost-pill:hover{border-color:rgba(242,237,228,0.6);color:var(--parch);}
.hero-scroll{
  font-size:0.68rem;letter-spacing:0.18em;text-transform:uppercase;
  color:rgba(242,237,228,0.35);
  display:flex;align-items:center;gap:0.6rem;
  align-self:flex-end;
}
.hero-scroll::before{
  content:'';display:block;width:40px;height:1px;
  background:rgba(242,237,228,0.2);
}

/* ── MARQUEE STRIP ── */
.marquee-strip{
  background:var(--gold);
  padding:0.75rem 0;overflow:hidden;
  white-space:nowrap;
}
.marquee-inner{
  display:inline-flex;gap:0;
  animation:marquee 22s linear infinite;
}
.marquee-inner span{
  font-size:0.7rem;letter-spacing:0.2em;text-transform:uppercase;
  color:rgba(255,255,255,0.85);padding:0 2.5rem;
}
.marquee-sep{color:rgba(255,255,255,0.4)!important;padding:0!important;}
@keyframes marquee{from{transform:translateX(0)}to{transform:translateX(-50%)}}

/* ── PROMISE ── */
.promise{
  padding:7rem 6%;
  display:grid;grid-template-columns:1fr 1fr;gap:6rem;align-items:center;
  background:var(--parch);
}
.promise-left{}
.promise-tag{
  font-size:0.68rem;letter-spacing:0.22em;text-transform:uppercase;
  color:var(--gold);margin-bottom:1.4rem;display:block;
}
.promise-title{
  font-family:'Playfair Display',serif;
  font-size:clamp(2.4rem,4vw,4rem);
  line-height:1.05;color:var(--ink);
}
.promise-title em{font-style:italic;color:var(--gold);}
.promise-body{
  font-size:0.92rem;color:var(--charcoal);opacity:0.75;
  line-height:1.85;margin-top:1.6rem;max-width:420px;
}
.promise-right{
  display:flex;flex-direction:column;gap:1.4rem;
}
.promise-card{
  padding:1.8rem 2rem;
  display:flex;gap:1.4rem;align-items:flex-start;
}
.promise-card:nth-child(1){background:var(--charcoal);}
.promise-card:nth-child(2){background:var(--parch2);border:1px solid rgba(87,77,72,0.1);}
.promise-card:nth-child(3){background:var(--olive);}
.p-icon{
  flex-shrink:0;width:36px;height:36px;
  border-radius:50%;
  display:flex;align-items:center;justify-content:center;
  background:rgba(255,255,255,0.12);
}
.p-icon svg{width:16px;height:16px;}
.p-title{
  font-family:'Playfair Display',serif;
  font-size:1.05rem;color:var(--parch);margin-bottom:0.4rem;
}
.promise-card:nth-child(2) .p-title{color:var(--ink);}
.p-desc{font-size:0.82rem;line-height:1.7;}
.promise-card:nth-child(1) .p-desc{color:rgba(242,237,228,0.6);}
.promise-card:nth-child(2) .p-desc{color:rgba(42,36,32,0.6);}
.promise-card:nth-child(3) .p-desc{color:rgba(242,237,228,0.75);}

/* ── JOURNEY ── */
.journey{
  padding:7rem 6%;
  background:var(--parch2);
  position:relative;overflow:hidden;
}
.journey-bg-star{
  position:absolute;left:-10%;top:50%;transform:translateY(-50%);
  width:50vw;height:50vw;opacity:0.06;pointer-events:none;
}
.journey-header{
  display:flex;align-items:flex-end;justify-content:space-between;
  margin-bottom:4rem;flex-wrap:wrap;gap:1.5rem;
}
.journey-title{
  font-family:'Playfair Display',serif;
  font-size:clamp(2.4rem,5vw,4.5rem);
  line-height:1;color:var(--ink);
}
.journey-title em{font-style:italic;color:var(--gold);display:block;}
.journey-subtitle{
  font-size:0.85rem;color:rgba(42,36,32,0.45);
  max-width:280px;line-height:1.7;text-align:right;
}

.steps-grid{
  display:grid;
  grid-template-columns:repeat(4,1fr);
  gap:3px;
}
.step-card{
  padding:2rem 1.6rem 2.4rem;
  min-height:220px;
  display:flex;flex-direction:column;justify-content:space-between;
  cursor:default;
  transition:filter 0.2s;
}
.step-card:hover{filter:brightness(1.08);}
.step-card:nth-child(4n+1){background:linear-gradient(135deg,#ddd5c8 0%,#e8e0d4 60%,#cfc5b8 100%);}
.step-card:nth-child(4n+2){background:linear-gradient(135deg,#c8d4da 0%,#dde5ea 60%,#b8c8d0 100%);}
.step-card:nth-child(4n+3){background:linear-gradient(135deg,#d4c8b0 0%,#e4d8c0 60%,#c0b090 100%);}
.step-card:nth-child(4n+4){background:linear-gradient(135deg,#d8cec4 0%,#e6dcd2 60%,#c4b8ac 100%);}
.step-card.accent{background:linear-gradient(135deg,#6a5f35 0%,#8a7a48 50%,#5a5030 100%)!important;}
.step-card.accent2{background:linear-gradient(135deg,rgba(180,139,63,0.28) 0%,rgba(180,139,63,0.12) 60%,rgba(121,109,62,0.22) 100%)!important;}

.step-n{
  font-size:0.68rem;letter-spacing:0.18em;
  color:var(--gold);opacity:0.85;margin-bottom:auto;
}
.step-name{
  font-family:'Playfair Display',serif;
  font-size:1.25rem;color:var(--ink);
  margin-bottom:0.5rem;line-height:1.2;
}
.step-desc{font-size:0.78rem;color:rgba(42,36,32,0.5);line-height:1.6;}

/* ── 4 WEEKS ── */
.weeks-section{
  padding:7rem 6%;
  background:var(--parch2);
}
.weeks-header{margin-bottom:3.5rem;}
.weeks-eyebrow{
  font-size:0.68rem;letter-spacing:0.22em;text-transform:uppercase;
  color:var(--gold);display:block;margin-bottom:0.8rem;
}
.weeks-title{
  font-family:'Playfair Display',serif;
  font-size:clamp(2.4rem,4.5vw,4rem);
  line-height:1.05;color:var(--ink);
}
.weeks-title em{font-style:italic;display:block;color:var(--charcoal);}

.weeks-track{
  display:grid;grid-template-columns:repeat(4,1fr);gap:1.5rem;
}
.week-tile{
  padding:2.4rem 2rem 2rem;
  position:relative;overflow:hidden;
  min-height:300px;
  display:flex;flex-direction:column;justify-content:space-between;
}
.week-tile::after{
  content:'';position:absolute;bottom:-20px;right:-20px;
  width:80px;height:80px;border-radius:50%;
  background:rgba(255,255,255,0.08);
}
.week-tile:nth-child(1){background:var(--slate);}
.week-tile:nth-child(2){background:var(--rose);}
.week-tile:nth-child(3){background:var(--gold);}
.week-tile:nth-child(4){background:var(--olive);}

.week-top{}
.week-num{
  font-size:0.65rem;letter-spacing:0.2em;text-transform:uppercase;
  color:rgba(255,255,255,0.55);margin-bottom:0.6rem;
}
.week-name{
  font-family:'Playfair Display',serif;
  font-size:1.6rem;color:#fff;line-height:1.1;margin-bottom:0.3rem;
}
.week-sub{
  font-size:0.72rem;letter-spacing:0.08em;text-transform:uppercase;
  color:rgba(255,255,255,0.6);margin-bottom:1.2rem;
}
.week-text{font-size:0.84rem;color:rgba(255,255,255,0.75);line-height:1.75;}
.week-num-big{
  font-family:'Playfair Display',serif;
  font-size:5rem;font-weight:900;color:rgba(255,255,255,0.1);
  line-height:1;align-self:flex-end;
}

/* ── WHAT'S INCLUDED ── */
.included{
  padding:7rem 6%;background:var(--parch);
  display:grid;grid-template-columns:1fr 1fr;gap:6rem;align-items:center;
}
.included-left{}
.included-eyebrow{
  font-size:0.68rem;letter-spacing:0.22em;text-transform:uppercase;
  color:var(--gold);display:block;margin-bottom:1rem;
}
.included-title{
  font-family:'Playfair Display',serif;
  font-size:clamp(2.2rem,4vw,3.5rem);line-height:1.05;color:var(--ink);
}
.included-title em{font-style:italic;color:var(--charcoal);}
.included-body{
  margin-top:1.4rem;font-size:0.9rem;color:var(--charcoal);
  opacity:0.65;line-height:1.8;max-width:380px;
}
.includes-list{
  margin-top:2.5rem;list-style:none;display:flex;flex-direction:column;gap:1rem;
}
.includes-list li{
  display:flex;align-items:flex-start;gap:1rem;
  font-size:0.88rem;color:var(--charcoal);line-height:1.6;
}
.includes-list li::before{
  content:'';flex-shrink:0;
  width:20px;height:20px;margin-top:2px;
  background:var(--gold);border-radius:50%;
  background-image:url("data:image/svg+xml,%3Csvg viewBox='0 0 20 20' fill='none' xmlns='http://www.w3.org/2000/svg'%3E%3Cpath d='M5 10l3.5 3.5L15 7' stroke='white' stroke-width='1.8' stroke-linecap='round' stroke-linejoin='round'/%3E%3C/svg%3E");
  background-size:cover;
}
.included-right{
  display:flex;flex-direction:column;gap:1.2rem;
}
.include-block{
  background:var(--charcoal);
  padding:2rem 1.8rem;
  display:grid;grid-template-columns:auto 1fr;gap:1.2rem;align-items:center;
}
.ib-icon{
  width:44px;height:44px;border-radius:2px;
  background:rgba(242,237,228,0.08);
  display:flex;align-items:center;justify-content:center;
}
.ib-icon svg{width:20px;height:20px;stroke:var(--gold);fill:none;stroke-width:1.5;}
.ib-name{
  font-family:'Playfair Display',serif;
  font-size:1rem;color:var(--parch);margin-bottom:0.2rem;
}
.ib-desc{font-size:0.8rem;color:rgba(242,237,228,0.45);line-height:1.6;}

/* ── OUTCOMES ── */
.outcomes{
  padding:7rem 6%;background:var(--parch);
  position:relative;overflow:hidden;
}
.outcomes-star{
  position:absolute;bottom:-15%;right:-5%;
  width:45vw;height:45vw;opacity:0.07;
  pointer-events:none;
}
.outcomes-eyebrow{
  font-size:0.68rem;letter-spacing:0.22em;text-transform:uppercase;
  color:var(--gold);display:block;margin-bottom:1rem;text-align:center;
}
.outcomes-title{
  font-family:'Playfair Display',serif;
  font-size:clamp(2.4rem,5vw,5rem);line-height:1;
  color:var(--ink);text-align:center;margin-bottom:4rem;
}
.outcomes-title em{font-style:italic;color:var(--gold);}

.outcomes-cards{
  display:grid;grid-template-columns:repeat(2,1fr);gap:3px;
  max-width:800px;margin:0 auto;
}
.oc{
  padding:2.8rem 2.4rem;
}
.oc:nth-child(1){background:linear-gradient(135deg,#c8d4da 0%,#dde5ea 55%,#b8c5cc 100%);}
.oc:nth-child(2){background:linear-gradient(135deg,#6a5f35 0%,#8a7a48 50%,#5a5030 100%);}
.oc:nth-child(3){background:linear-gradient(135deg,#d4baa0 0%,#e8d4bc 55%,#c4a888 100%);}
.oc:nth-child(4){background:linear-gradient(135deg,#c8b4b4 0%,#ddc8c8 55%,#b89898 100%);}
.oc-name{
  font-family:'Playfair Display',serif;
  font-size:1.8rem;color:var(--ink);margin-bottom:0.7rem;
}
.oc:nth-child(2) .oc-name{color:var(--parch);}
.oc:nth-child(3) .oc-name,.oc:nth-child(4) .oc-name{color:var(--ink);}
.oc-desc{font-size:0.84rem;color:rgba(42,36,32,0.7);line-height:1.75;}
.oc:nth-child(2) .oc-desc{color:rgba(242,237,228,0.8);}
.oc:nth-child(3) .oc-desc,.oc:nth-child(4) .oc-desc{color:rgba(42,36,32,0.65);}

/* ── MEMBERSHIP ── */
.membership{
  padding:7rem 6%;background:var(--parch2);
}
.membership-header{margin-bottom:3.5rem;}
.membership-eyebrow{
  font-size:0.68rem;letter-spacing:0.22em;text-transform:uppercase;
  color:var(--gold);display:block;margin-bottom:0.8rem;
}
.membership-title{
  font-family:'Playfair Display',serif;
  font-size:clamp(2.2rem,4vw,3.8rem);line-height:1.05;color:var(--ink);
}
.membership-title em{font-style:italic;color:var(--charcoal);}

.plans{
  display:grid;grid-template-columns:repeat(3,1fr);gap:3px;
}
.plan{
  padding:3rem 2.2rem;
  position:relative;
  transition:filter 0.2s;
}
.plan:hover{filter:brightness(1.05);}
.plan:nth-child(1){background:linear-gradient(145deg,#c49840 0%,#d4aa55 40%,#a07830 100%);}
.plan:nth-child(2){background:var(--charcoal);}
.plan:nth-child(3){background:var(--ink);}
.plan-tag{
  font-size:0.65rem;letter-spacing:0.18em;text-transform:uppercase;
  color:var(--gold);display:block;margin-bottom:1rem;
}
.plan:nth-child(1) .plan-tag{color:rgba(255,255,255,0.7);}
.plan-name{
  font-family:'Playfair Display',serif;
  font-size:2rem;margin-bottom:1.8rem;
}
.plan:nth-child(1) .plan-name{color:#fff;}
.plan:nth-child(2) .plan-name,.plan:nth-child(3) .plan-name{color:var(--parch);}
.plan-features{list-style:none;display:flex;flex-direction:column;gap:0.75rem;}
.plan-features li{
  font-size:0.84rem;
  padding-bottom:0.75rem;
  border-bottom:1px solid rgba(255,255,255,0.15);
  color:rgba(255,255,255,0.8);
}
.plan:nth-child(1) .plan-features li{
  border-color:rgba(255,255,255,0.2);color:rgba(255,255,255,0.85);
}
.plan:nth-child(2) .plan-features li,.plan:nth-child(3) .plan-features li{
  color:rgba(242,237,228,0.55);
}
.plan-badge{
  position:absolute;top:1.5rem;right:1.5rem;
  background:var(--gold);color:#fff;
  font-size:0.6rem;letter-spacing:0.15em;text-transform:uppercase;
  padding:0.3rem 0.8rem;border-radius:100px;
}

/* ── CTA / INVEST ── */
.invest{
  padding:8rem 6%;
  background:var(--charcoal);
  position:relative;overflow:hidden;
  text-align:center;
}
.invest-star{
  position:absolute;top:50%;left:50%;
  transform:translate(-50%,-50%);
  width:70vw;height:70vw;opacity:0.06;
  pointer-events:none;
}
.invest-eyebrow{
  font-size:0.68rem;letter-spacing:0.22em;text-transform:uppercase;
  color:var(--gold);display:block;margin-bottom:1.5rem;
}
.invest-title{
  font-family:'Playfair Display',serif;
  font-size:clamp(2.8rem,6vw,6rem);line-height:0.95;
  color:var(--parch);margin-bottom:1rem;position:relative;z-index:1;
}
.invest-title em{font-style:italic;color:var(--gold);display:block;}
.invest-sub{
  font-size:0.9rem;color:rgba(242,237,228,0.5);
  max-width:420px;margin:0 auto 3rem;line-height:1.8;
  position:relative;z-index:1;
}
.pricing{
  display:flex;align-items:baseline;justify-content:center;
  gap:1.5rem;margin-bottom:0.5rem;position:relative;z-index:1;
}
.price-was{
  font-family:'Playfair Display',serif;
  font-size:1.6rem;color:rgba(242,237,228,0.25);
  text-decoration:line-through;
}
.price-now{
  font-family:'Playfair Display',serif;
  font-size:5rem;font-weight:700;color:var(--parch);line-height:1;
}
.price-note{
  font-size:0.75rem;letter-spacing:0.12em;text-transform:uppercase;
  color:var(--rose);margin-bottom:3rem;
  position:relative;z-index:1;
}
.invest-cta{position:relative;z-index:1;}

/* ── FOOTER ── */
footer{
  background:var(--ink);
  padding:3rem 6%;
  display:flex;align-items:center;justify-content:space-between;
  flex-wrap:wrap;gap:1.5rem;
  border-top:1px solid rgba(242,237,228,0.06);
}
.footer-left{display:flex;align-items:center;gap:0.7rem;}
.footer-wordmark{
  font-family:'Playfair Display',serif;
  font-size:1rem;letter-spacing:0.08em;
  color:rgba(242,237,228,0.5);
}
.footer-center{
  font-family:'Playfair Display',serif;
  font-style:italic;font-size:0.95rem;
  color:rgba(180,139,63,0.6);
}
.footer-right{
  font-size:0.7rem;letter-spacing:0.06em;
  color:rgba(242,237,228,0.2);
}

/* ── SCROLL REVEAL ── */
.reveal{
  opacity:0;transform:translateY(28px);
  transition:opacity 0.75s ease,transform 0.75s ease;
}
.reveal.on{opacity:1;transform:translateY(0);}

/* ── RESPONSIVE ── */
@media(max-width:900px){
  .promise,.included{grid-template-columns:1fr;gap:3rem;}
  .steps-grid{grid-template-columns:repeat(2,1fr);}
  .weeks-track{grid-template-columns:1fr 1fr;}
  .outcomes-cards{grid-template-columns:1fr;}
  .plans{grid-template-columns:1fr;}
  .hero-headline .line1{font-size:clamp(3.5rem,13vw,5.5rem);}
  .hero-headline .line2{font-size:clamp(3rem,11vw,4.8rem);}
  .hero-headline .line3{font-size:clamp(3.2rem,12vw,5rem);}
  nav .nav-links{display:none;}
  .journey-subtitle{text-align:left;}
}
@media(max-width:600px){
  .steps-grid{grid-template-columns:1fr;}
  .weeks-track{grid-template-columns:1fr;}
  .hero-bg-star{width:90vw;height:90vw;}
}
</style>
</head>
<body>

<!-- STAR SVG DEFS (reusable inline) -->
<svg width="0" height="0" style="position:absolute">
  <defs>
    <symbol id="star8" viewBox="0 0 200 200">
      <path d="M100 4 L106 93 L195 100 L106 107 L100 196 L94 107 L5 100 L94 93 Z" fill="currentColor"/>
      <path d="M100 26 L104.5 93 L171 100 L104.5 107 L100 174 L95.5 107 L29 100 L95.5 93 Z" fill="currentColor" opacity="0.45"/>
    </symbol>
  </defs>
</svg>

<!-- NAV -->
<nav>
  <div class="nav-logo">
    <svg class="nav-logo-mark" viewBox="0 0 200 200"><use href="#star8" color="#B48B3F"/></svg>
    <span class="nav-brand">Grace Reset™</span>
  </div>
  <div class="nav-links">
    <a href="#journey">Journey</a>
    <a href="#weeks">The Reset</a>
    <a href="#membership">Membership</a>
    <a href="#invest">Begin</a>
  </div>
  <button class="nav-cta-pill" onclick="document.getElementById('invest').scrollIntoView({behavior:'smooth'})">I'm Ready</button>
</nav>

<!-- HERO -->
<section class="hero">
  <svg class="hero-bg-star" viewBox="0 0 200 200"><use href="#star8" color="#B48B3F"/></svg>
  <p class="hero-eyebrow">A Map Back to Yourself &nbsp;·&nbsp; A Life Beyond Survival</p>
  <div class="hero-headline">
    <span class="line1">Grace</span>
    <span class="line2">Reset.™</span>
    <span class="line3">Rise.</span>
  </div>
  <div class="hero-bottom">
    <p class="hero-desc">
      The Grace Reset Method helps you break free from overwhelm, release what's heavy, rebuild from within, and move forward with clarity, confidence, and purpose.
    </p>
    <div class="hero-cta-group">
      <a href="#invest" class="btn-pill">Begin Your Reset</a>
      <a href="#journey" class="btn-ghost-pill">See the Journey</a>
      <span class="hero-scroll">Scroll</span>
    </div>
  </div>
</section>

<!-- MARQUEE -->
<div class="marquee-strip">
  <div class="marquee-inner">
    <span>Reset Your Mind</span><span class="marquee-sep">✦</span>
    <span>Heal Your Heart</span><span class="marquee-sep">✦</span>
    <span>Realign Your Life</span><span class="marquee-sep">✦</span>
    <span>Rise Into Your Purpose</span><span class="marquee-sep">✦</span>
    <span>Grace Isn't Earned. It's Remembered.</span><span class="marquee-sep">✦</span>
    <span>Reset Your Mind</span><span class="marquee-sep">✦</span>
    <span>Heal Your Heart</span><span class="marquee-sep">✦</span>
    <span>Realign Your Life</span><span class="marquee-sep">✦</span>
    <span>Rise Into Your Purpose</span><span class="marquee-sep">✦</span>
    <span>Grace Isn't Earned. It's Remembered.</span><span class="marquee-sep">✦</span>
  </div>
</div>

<!-- PROMISE -->
<section class="promise reveal">
  <div class="promise-left">
    <span class="promise-tag">The Promise</span>
    <h2 class="promise-title">You don't need to become<br>someone <em>new.</em></h2>
    <p class="promise-body">
      You just need to remember who you've always been. The Grace Reset Method helps you break free from overwhelm, release what's heavy, and move forward with clarity, confidence, and a deep sense of purpose.
    </p>
  </div>
  <div class="promise-right">
    <div class="promise-card">
      <div class="p-icon">
        <svg viewBox="0 0 24 24" fill="none" stroke="#B48B3F" stroke-width="1.5"><path d="M12 22s8-4 8-10V5l-8-3-8 3v7c0 6 8 10 8 10z"/></svg>
      </div>
      <div>
        <p class="p-title">You Release What's Heavy</p>
        <p class="p-desc">Guilt, people-pleasing, pressure, and old stories — set down for good.</p>
      </div>
    </div>
    <div class="promise-card">
      <div class="p-icon" style="background:rgba(87,77,72,0.08)">
        <svg viewBox="0 0 24 24" fill="none" stroke="#B48B3F" stroke-width="1.5"><circle cx="12" cy="12" r="10"/><path d="M12 8v4l3 3"/></svg>
      </div>
      <div>
        <p class="p-title">You Rebuild From Within</p>
        <p class="p-desc">Identity, clarity, and emotional stability — restored from the inside out.</p>
      </div>
    </div>
    <div class="promise-card">
      <div class="p-icon">
        <svg viewBox="0 0 24 24" fill="none" stroke="rgba(255,255,255,0.8)" stroke-width="1.5"><path d="M12 2l3.09 6.26L22 9.27l-5 4.87 1.18 6.88L12 17.77l-6.18 3.25L7 14.14 2 9.27l6.91-1.01L12 2z"/></svg>
      </div>
      <div>
        <p class="p-title">You Rise Into Your Purpose</p>
        <p class="p-desc">A life that feels aligned, fulfilling, and uniquely yours.</p>
      </div>
    </div>
  </div>
</section>

<!-- JOURNEY -->
<section class="journey" id="journey">
  <svg class="journey-bg-star" viewBox="0 0 200 200"><use href="#star8" color="#B48B3F"/></svg>
  <div class="journey-header reveal">
    <h2 class="journey-title">The Journey<br><em>to Grace™</em></h2>
    <p class="journey-subtitle">12 steps from overwhelm to overflow — a map back to yourself.</p>
  </div>
  <div class="steps-grid reveal">
    <div class="step-card">
      <span class="step-n">01</span>
      <div><p class="step-name">Purpose</p><p class="step-desc">Reconnect with what truly matters at your core.</p></div>
    </div>
    <div class="step-card">
      <span class="step-n">02</span>
      <div><p class="step-name">Vision</p><p class="step-desc">See the life you are meant to be living.</p></div>
    </div>
    <div class="step-card">
      <span class="step-n">03</span>
      <div><p class="step-name">Perspective</p><p class="step-desc">Shift how you see your story and your worth.</p></div>
    </div>
    <div class="step-card accent">
      <span class="step-n">04</span>
      <div><p class="step-name">Surrender</p><p class="step-desc">Release control and trust the process of becoming.</p></div>
    </div>
    <div class="step-card">
      <span class="step-n">05</span>
      <div><p class="step-name">Presence</p><p class="step-desc">Come home to yourself — here, now, grounded.</p></div>
    </div>
    <div class="step-card accent2">
      <span class="step-n">06 ✦ Choice Point</span>
      <div><p class="step-name">Community</p><p class="step-desc">A pivotal moment to choose connection and your next chapter.</p></div>
    </div>
    <div class="step-card">
      <span class="step-n">07</span>
      <div><p class="step-name">Solutions</p><p class="step-desc">Discover practical tools that work for your real life.</p></div>
    </div>
    <div class="step-card">
      <span class="step-n">08</span>
      <div><p class="step-name">Community</p><p class="step-desc">Build relationships that fuel your growth.</p></div>
    </div>
    <div class="step-card">
      <span class="step-n">09</span>
      <div><p class="step-name">Message</p><p class="step-desc">Find your voice and what you are here to share.</p></div>
    </div>
    <div class="step-card">
      <span class="step-n">10</span>
      <div><p class="step-name">Catalyst</p><p class="step-desc">Ignite momentum and take aligned, purposeful action.</p></div>
    </div>
    <div class="step-card">
      <span class="step-n">11</span>
      <div><p class="step-name">Overflow</p><p class="step-desc">Live from a place of fullness, not depletion.</p></div>
    </div>
    <div class="step-card accent">
      <span class="step-n">12 ✦ Choice Point</span>
      <div><p class="step-name">Victory</p><p class="step-desc">Claim your legacy and step into a life beyond survival.</p></div>
    </div>
  </div>
</section>

<!-- 4 WEEKS -->
<section class="weeks-section" id="weeks">
  <div class="weeks-header reveal">
    <span class="weeks-eyebrow">The 4-Week Reset</span>
    <h2 class="weeks-title">A Transformational<br><em>Journey</em></h2>
  </div>
  <div class="weeks-track reveal">
    <div class="week-tile">
      <div class="week-top">
        <p class="week-num">Week 01</p>
        <p class="week-name">See Clearly</p>
        <p class="week-sub">Identity + Pattern Awareness</p>
        <p class="week-text">Discover hidden emotional roles and beliefs. Clarity replaces confusion as you see yourself — and your patterns — with fresh eyes.</p>
      </div>
      <p class="week-num-big">1</p>
    </div>
    <div class="week-tile">
      <div class="week-top">
        <p class="week-num">Week 02</p>
        <p class="week-name">Release Pressure</p>
        <p class="week-sub">Emotional Load + Surrender</p>
        <p class="week-text">Let go of guilt, overthinking, and people-pleasing. Relief replaces heaviness when you stop carrying what was never yours.</p>
      </div>
      <p class="week-num-big">2</p>
    </div>
    <div class="week-tile">
      <div class="week-top">
        <p class="week-num">Week 03</p>
        <p class="week-name">Rebuild Structure</p>
        <p class="week-sub">Boundaries + Systems + Stability</p>
        <p class="week-text">Create routines, boundaries, and decision-making systems. Confidence replaces chaos when your life has a strong inner foundation.</p>
      </div>
      <p class="week-num-big">3</p>
    </div>
    <div class="week-tile">
      <div class="week-top">
        <p class="week-num">Week 04</p>
        <p class="week-name">Move Forward</p>
        <p class="week-sub">Momentum + Alignment</p>
        <p class="week-text">Build momentum and take aligned action. Purpose replaces hesitation as you step boldly into the life you've been remembering.</p>
      </div>
      <p class="week-num-big">4</p>
    </div>
  </div>
</section>

<!-- WHAT'S INCLUDED -->
<section class="included reveal">
  <div class="included-left">
    <span class="included-eyebrow">What's Included</span>
    <h2 class="included-title">Everything you need<br><em>to begin</em></h2>
    <p class="included-body">You don't need to become a different person to feel better. You just need the right map, the right support, and the decision to begin.</p>
    <ul class="includes-list">
      <li>4 Weekly Live Coaching Sessions</li>
      <li>Guided Reflection Worksheets</li>
      <li>Emotional Pattern Assessments</li>
      <li>Practical Reset Exercises</li>
      <li>Community Support Circle</li>
      <li>Optional 1:1 Private Coaching</li>
    </ul>
  </div>
  <div class="included-right">
    <div class="include-block">
      <div class="ib-icon"><svg viewBox="0 0 24 24"><rect x="3" y="4" width="18" height="18" rx="2"/><line x1="3" y1="10" x2="21" y2="10"/><line x1="8" y1="2" x2="8" y2="6"/><line x1="16" y1="2" x2="16" y2="6"/></svg></div>
      <div><p class="ib-name">Live Coaching Sessions</p><p class="ib-desc">Guided weekly sessions that move you through each phase with clarity and support.</p></div>
    </div>
    <div class="include-block">
      <div class="ib-icon"><svg viewBox="0 0 24 24"><path d="M14 2H6a2 2 0 0 0-2 2v16a2 2 0 0 0 2 2h12a2 2 0 0 0 2-2V8z"/><polyline points="14 2 14 8 20 8"/></svg></div>
      <div><p class="ib-name">Reflection Worksheets</p><p class="ib-desc">Thoughtfully designed materials that deepen your self-discovery between sessions.</p></div>
    </div>
    <div class="include-block">
      <div class="ib-icon"><svg viewBox="0 0 24 24"><path d="M17 21v-2a4 4 0 0 0-4-4H5a4 4 0 0 0-4 4v2"/><circle cx="9" cy="7" r="4"/><path d="M23 21v-2a4 4 0 0 0-3-3.87"/><path d="M16 3.13a4 4 0 0 1 0 7.75"/></svg></div>
      <div><p class="ib-name">Community Circle</p><p class="ib-desc">Others walking the same path — seen, held, and genuinely encouraged.</p></div>
    </div>
    <div class="include-block">
      <div class="ib-icon"><svg viewBox="0 0 24 24"><path d="M21 15a2 2 0 0 1-2 2H7l-4 4V5a2 2 0 0 1 2-2h14a2 2 0 0 1 2 2z"/></svg></div>
      <div><p class="ib-name">Optional 1:1 Coaching</p><p class="ib-desc">Private support available to deepen and accelerate your personal journey.</p></div>
    </div>
  </div>
</section>

<!-- OUTCOMES -->
<section class="outcomes" id="outcomes">
  <svg class="outcomes-star" viewBox="0 0 200 200"><use href="#star8" color="#B48B3F"/></svg>
  <span class="outcomes-eyebrow reveal">The Outcome</span>
  <h2 class="outcomes-title reveal">What you'll walk<br><em>away with</em></h2>
  <div class="outcomes-cards reveal">
    <div class="oc">
      <p class="oc-name">Clarity</p>
      <p class="oc-desc">You know who you are and what matters most — no more second-guessing your direction or your worth.</p>
    </div>
    <div class="oc">
      <p class="oc-name">Confidence</p>
      <p class="oc-desc">You trust yourself and your decisions. Your instincts become your compass, not your enemy.</p>
    </div>
    <div class="oc">
      <p class="oc-name">Connection</p>
      <p class="oc-desc">You build supportive relationships and community that genuinely nourish your growth and joy.</p>
    </div>
    <div class="oc">
      <p class="oc-name">Freedom</p>
      <p class="oc-desc">You live on your own terms — with peace, joy, and a deep sense of aligned purpose every day.</p>
    </div>
  </div>
</section>

<!-- MEMBERSHIP -->
<section class="membership" id="membership">
  <div class="membership-header reveal">
    <span class="membership-eyebrow">Membership Levels</span>
    <h2 class="membership-title">Choose how you<br><em>want to rise</em></h2>
  </div>
  <div class="plans reveal">
    <div class="plan">
      <span class="plan-tag">Core Access</span>
      <p class="plan-name">Gold</p>
      <ul class="plan-features">
        <li>Core Program Access</li>
        <li>Community</li>
        <li>Monthly Trainings</li>
      </ul>
    </div>
    <div class="plan">
      <div class="plan-badge">Most Popular</div>
      <span class="plan-tag">Deep Dive</span>
      <p class="plan-name">Diamond</p>
      <ul class="plan-features">
        <li>Group Coaching</li>
        <li>Advanced Trainings</li>
        <li>Resources Library</li>
        <li>Live Q&amp;A Calls</li>
      </ul>
    </div>
    <div class="plan">
      <span class="plan-tag">Full Support</span>
      <p class="plan-name">Platinum</p>
      <ul class="plan-features">
        <li>VIP Access</li>
        <li>Private Coaching</li>
        <li>Priority Support</li>
        <li>Exclusive Perks</li>
      </ul>
    </div>
  </div>
</section>

<!-- CTA / INVEST -->
<section class="invest" id="invest">
  <svg class="invest-star" viewBox="0 0 200 200"><use href="#star8" color="#B48B3F"/></svg>
  <span class="invest-eyebrow reveal">Your Investment</span>
  <h2 class="invest-title reveal">This is your reset.<br><em>This is Grace.</em></h2>
  <p class="invest-sub reveal">Created for those who are ready to stop surviving and start living. Limited to the first 10 people.</p>
  <div class="pricing reveal">
    <span class="price-was">$1,012</span>
    <span class="price-now">$395</span>
  </div>
  <p class="price-note reveal">Limited offer · First 10 people only</p>
  <div class="invest-cta reveal">
    <button class="btn-pill" style="font-size:0.88rem;padding:1.1rem 3rem;" onclick="alert('Ready to begin! Contact us to secure your spot.')">Are You Ready? Let's Begin.</button>
  </div>
</section>

<!-- FOOTER -->
<footer>
  <div class="footer-left">
    <svg width="20" height="20" viewBox="0 0 200 200" style="opacity:0.4"><use href="#star8" color="#B48B3F"/></svg>
    <span class="footer-wordmark">Grace Reset™</span>
  </div>
  <p class="footer-center">Grace isn't earned. It's remembered.</p>
  <p class="footer-right">© 2024 Grace Reset™</p>
</footer>

<script>
const io = new IntersectionObserver(entries=>{
  entries.forEach(e=>{
    if(e.isIntersecting){e.target.classList.add('on');io.unobserve(e.target);}
  });
},{threshold:0.1});
document.querySelectorAll('.reveal').forEach(el=>io.observe(el));
</script>
</body>
</html>
