<template>
  <footer class="footer">
    <span>NIRVASYA</span>
    <div class="scroll">
      <span>SCROLL TO EXPLORE</span>
      <span class="bar"></span>
    </div>
  </footer>
</template>

<style scoped>
.footer{
  display:flex;
  align-items:center;
  justify-content: space-between;
  padding: 26px 48px 32px;
  font-size: 0.78rem;
  color: var(--ink-soft);
  letter-spacing: 0.02em;
}
.scroll{ display:flex; align-items:center; gap:10px; }
.scroll .bar{
  width:1px; height:22px;
  background: var(--ink-soft);
  position: relative;
  overflow:hidden;
}
.scroll .bar::after{
  content:"";
  position:absolute; left:0; top:-100%;
  width:100%; height:100%;
  background: var(--ink);
  animation: scrollpulse 1.8s ease-in-out infinite;
}
@keyframes scrollpulse{
  0%{ top:-100%; }
  60%{ top:100%; }
  100%{ top:100%; }
}

@media (max-width: 640px){
  .footer{ padding: 20px 22px 26px; flex-direction:column; gap:14px; align-items:flex-start; }
}

@media (prefers-reduced-motion: reduce){
  .scroll .bar::after{ animation: none !important; }
}
</style>
