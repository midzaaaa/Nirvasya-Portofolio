<script setup>
import { ref, computed } from 'vue'

// Ganti nilai ini dengan path foto asli kamu nanti, contoh: '/foto-nirvasya.jpg'
// Taruh file fotonya di folder /public, lalu isi photoSrc dengan '/nama-file.jpg'
const photoSrc = ref('dei.jpeg')

const rotateX = ref(0)
const rotateY = ref(0)

function onMove(e) {
  const rect = e.currentTarget.getBoundingClientRect()
  const cx = rect.left + rect.width / 2
  const cy = rect.top + rect.height / 2
  const dx = (e.clientX - cx) / (rect.width / 2)
  const dy = (e.clientY - cy) / (rect.height / 2)
  rotateY.value = Math.max(-1, Math.min(1, dx)) * 16
  rotateX.value = Math.max(-1, Math.min(1, -dy)) * 16
}

function onLeave() {
  rotateX.value = 0
  rotateY.value = 0
}

const avatarStyle = computed(() => ({
  transform: `perspective(700px) rotateX(${rotateX.value}deg) rotateY(${rotateY.value}deg)`
}))
</script>

<template>
  <div class="avatar-wrap" @mousemove="onMove" @mouseleave="onLeave">
    <div class="avatar" :style="avatarStyle">
      <img v-if="photoSrc" :src="photoSrc" alt="Foto Nirvasya" class="photo" />
      <template v-else>
        <div class="glare"></div>
        <span class="initial">N</span>
      </template>
    </div>
    <span class="avatar-hint">gerakkan kursor · foto asli menyusul</span>
  </div>
</template>

<style scoped>
.avatar-wrap{
  position:absolute;
  top: 40%;
  left: 50%;
  width: clamp(150px, 19vw, 250px);
  height: clamp(150px, 19vw, 250px);
  transform: translate(-50%, -50%);
  animation: float 6s ease-in-out infinite;
}

@keyframes float{
  0%, 100% { margin-top: 0px; }
  50% { margin-top: -10px; }
}

.avatar{
  width:100%; height:100%;
  border-radius:50%;
  cursor: pointer;
  background: radial-gradient(circle at 32% 28%, var(--avatar-a), var(--avatar-b) 45%, var(--avatar-c) 100%);
  box-shadow: 0 20px 50px rgba(20,20,30,0.28), inset 0 0 0 1px rgba(255,255,255,0.4);
  display:flex; align-items:center; justify-content:center;
  position: relative;
  overflow: hidden;
  transition: transform .15s ease-out, box-shadow .3s ease;
  will-change: transform;
}
.avatar:hover{
  box-shadow: 0 26px 60px rgba(20,20,30,0.34), 0 0 0 6px var(--accent-tint), inset 0 0 0 1px rgba(255,255,255,0.5);
}

.photo{
  width:100%; height:100%;
  object-fit: cover;
  border-radius: 50%;
}

.glare{
  position:absolute;
  top:14%; left:20%;
  width: 40%; height: 26%;
  background: rgba(255,255,255,0.55);
  border-radius:50%;
  filter: blur(10px);
  pointer-events:none;
}

.initial{
  font-family:'Big Shoulders Display', sans-serif;
  font-weight: 800;
  font-size: clamp(2.4rem, 6vw, 4rem);
  color: rgba(255,255,255,0.92);
  text-shadow: 0 2px 10px rgba(0,0,0,0.25);
  user-select:none;
  pointer-events:none;
}

.avatar-hint{
  position:absolute;
  bottom: -34px; left:50%;
  transform: translateX(-50%);
  font-size: 0.68rem;
  letter-spacing: 0.04em;
  color: var(--ink-soft);
  white-space: nowrap;
  opacity:.75;
}

@media (prefers-reduced-motion: reduce){
  .avatar-wrap{ animation: none !important; }
}
</style>
