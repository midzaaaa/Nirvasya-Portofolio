<template>
  <section id="about" class="about">
    <div class="about-container">
      <h2 class="section-title">About Me</h2>

      <div class="about-content">
        <div class="bio-main">
          <p class="tagline">
            Siswa & Creative Developer yang berfokus pada pembuatan antarmuka web interaktif dan desain modern
          </p>
        </div>

        <div class="bio-details">
          <div class="info-group">
            <span class="info-label">Nama Lengkap</span>
            <span class="info-value">Midza Prada Al-Ghifary</span>
          </div>

          <div class="info-group">
            <span class="info-label">Pendidikan / Sekolah</span>
            <span class="info-value">SMK Yadika Soreang</span>
          </div>

          <div class="info-group">
            <span class="info-label">Fokus / Jurusan</span>
            <span class="info-value">Pengembangan Perangkat Lunak (PPLG / RPL)</span>
          </div>

          <div class="info-group">
            <span class="info-label">Lokasi</span>
            <span class="info-value">Bandung,Indonesia</span>
          </div>

          <div class="info-group">
            <span class="info-label">Keahlian</span>
            <div class="skills-list">
              <span class="skill-tag">Vue.js</span>
              <span class="skill-tag">HTML/CSS</span>
              <span class="skill-tag">JavaScript</span>
              <span class="skill-tag">UI/UX Design</span>
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>
</template>

<style scoped>
.about {
  padding: 100px 20px;
  max-width: 900px;
  margin: 0 auto;
}

.about-container {
  width: 100%;
}

.section-title {
  font-family: 'Big Shoulders Display', sans-serif;
  font-size: 1.2rem;
  text-transform: uppercase;
  letter-spacing: 0.1em;
  border-bottom: 2px dotted var(--line, #000);
  padding-bottom: 12px;
  margin-bottom: 40px;
}

.about-content {
  display: grid;
  grid-template-columns: 1fr;
  gap: 40px;
}

@media (min-width: 768px) {
  .about-content {
    grid-template-columns: 1fr 1fr;
  }
}

.tagline {
  font-family: 'Big Shoulders Display', sans-serif;
  font-size: clamp(1.8rem, 4vw, 2.8rem);
  font-weight: 800;
  line-height: 1.1;
  text-transform: uppercase;
}

.bio-details {
  display: flex;
  flex-direction: column;
  gap: 24px;
}

.info-group {
  display: flex;
  flex-direction: column;
  gap: 4px;
  border-bottom: 1px solid rgba(0, 0, 0, 0.1);
  padding-bottom: 12px;
}

.info-label {
  font-size: 0.75rem;
  text-transform: uppercase;
  letter-spacing: 0.1em;
  opacity: 0.5;
  font-family: monospace;
}

.info-value {
  font-size: 1.1rem;
  font-weight: 600;
}

.skills-list {
  display: flex;
  flex-wrap: wrap;
  gap: 8px;
  margin-top: 6px;
}

.skill-tag {
  font-size: 0.8rem;
  font-family: monospace;
  padding: 4px 10px;
  border: 1px solid currentColor;
  border-radius: 20px;
}
</style>