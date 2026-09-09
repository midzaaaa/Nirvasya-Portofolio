<script setup>
import { ref, onMounted } from 'vue'
import InteractiveAvatar from './InteractiveAvatar.vue'

const loaded = ref(false)

onMounted(() => {
  setTimeout(() => { loaded.value = true }, 150)
})
</script>

<template>
  <section class="hero" :class="{ loaded }">
    <h1 class="headline">
      <span class="line">Nirvasya</span>
      <span class="line">Creative</span>
      <span class="line">Developer</span>
    </h1>

    <InteractiveAvatar />

    <hr class="rule" />
  </section>
</template>

<style scoped>
.hero{
  flex:1;
  display:flex;
  flex-direction:column;
  align-items:center;
  justify-content:center;
  position: relative;
  padding: 40px 20px 60px;
  text-align:center;
}

.headline{
  font-family:'Big Shoulders Display', sans-serif;
  font-weight: 900;
  text-transform: uppercase;
  line-height: 0.84;
  letter-spacing: -0.01em;
  font-size: clamp(3.4rem, 12.5vw, 9rem);
  margin:0;
  position: relative;
}

.headline .line{
  display:block;
  opacity:0;
  transform: translateY(40px);
  transition: opacity .8s cubic-bezier(.16,1,.3,1), transform .8s cubic-bezier(.16,1,.3,1);
}
.hero.loaded .headline .line{ opacity:1; transform: translateY(0); }
.headline .line:nth-child(1){ transition-delay: .05s; }
.headline .line:nth-child(2){ transition-delay: .18s; }
.headline .line:nth-child(3){ transition-delay: .31s; }

.rule{
  margin-top: 34px;
  width: min(720px, 84vw);
  border: none;
  border-top: 2px dotted var(--line);
  opacity:0;
  transition: opacity .8s ease .5s;
}
.hero.loaded .rule{ opacity:1; }

@media (prefers-reduced-motion: reduce){
  .headline .line, .rule{ transition: none !important; }
  .hero.loaded .headline .line{ opacity:1; transform:none; }
}
</style>
