<script setup>
const links = ['PROJECT', 'ABOUT', 'CONTACT']
</script>

<template>
  <nav class="nav">
    <div class="mark" aria-hidden="true">
      <svg viewBox="0 0 48 48" fill="none" xmlns="http://www.w3.org/2000/svg">
        <path d="M24 3 L43 13.5 V34.5 L24 45 L5 34.5 V13.5 Z" stroke="currentColor" stroke-width="1.6"/>
        <path d="M17 31V17L31 31V17" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"/>
      </svg>
    </div>

    <ul class="nav-links">
      <li v-for="item in links" :key="item">
        <a :href="`#${item.toLowerCase()}`">{{ item }}</a>
      </li>
    </ul>

    <div class="badge">
      <span class="dot"></span>
      <span>Open for work</span>
    </div>
  </nav>
</template>

<style scoped>
.nav{
  display:flex;
  align-items:center;
  justify-content: space-between;
  padding: 28px 48px;
  position: relative;
  z-index: 10;
}
.mark{ width: 42px; height: 42px; display:flex; align-items:center; justify-content:center; }
.mark svg{ width:100%; height:100%; }

.nav-links{
  display:flex;
  gap: 36px;
  list-style:none;
  margin:0; padding:0;
}
.nav-links a{
  color: var(--ink);
  text-decoration:none;
  font-size: 0.85rem;
  font-weight: 500;
  letter-spacing: 0.03em;
  position: relative;
  padding-bottom: 4px;
}
.nav-links a::after{
  content:"";
  position:absolute; left:0; bottom:0;
  width:0; height:1.5px;
  background: var(--accent);
  transition: width .25s ease;
}
.nav-links a:hover::after,
.nav-links a:focus-visible::after{ width:100%; }
.nav-links a:focus-visible{ outline: 2px solid var(--accent); outline-offset: 4px; border-radius:2px; }

.badge{
  display:flex; align-items:center; gap:8px;
  border: 1px solid var(--line);
  padding: 7px 14px;
  border-radius: 999px;
  font-size: 0.78rem;
  color: var(--ink-soft);
}
.badge .dot{
  width:7px; height:7px; border-radius:50%;
  background: var(--accent);
  box-shadow: 0 0 0 3px var(--accent-tint);
}

@media (max-width: 640px){
  .nav{ padding: 20px 22px; }
  .nav-links{ display:none; }
}
</style>
