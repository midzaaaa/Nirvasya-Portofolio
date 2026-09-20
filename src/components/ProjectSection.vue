<script setup>
import { ref } from 'vue'

const projects = ref([
  {
   id: '01',
    title: 'M.A.S - Food Delivery',
    category: 'Frontend Development',
    year: '2026',
    repo: 'https://github.com/midzaaaa/food-mas-web.git',
    live: 'https://food-mas-web.vercel.app/' 
  },
  {
    id: '02',
    title: 'Nirvasya - Finance',
    category: 'Creative Development',
    year: '2026',
    repo: 'https://github.com/midzaaaa/Nirvasya-Finance.git',
    live: 'https://nirvasya-finance.vercel.app/'
  },

])
</script>

<template>
  <section id="project" class="project">
    <h2 class="section-title">Project Selected</h2>

    <div class="project-list">
      <article v-for="project in projects" :key="project.id" class="project-card">
        <div class="project-info">
          <span class="project-num">{{ project.id }}</span>
          <h3 class="project-title">{{ project.title }}</h3>
          <p class="project-cat">{{ project.category }}</p>
        </div>

        <div class="project-meta">
  <span class="project-year">{{ project.year }}</span>
  <a v-if="project.live" :href="project.repo" target="_blank" rel="noopener noreferrer" class="code-link">Code</a>
  <a :href="project.live || project.repo" target="_blank" rel="noopener noreferrer" class="arrow-icon" :title="project.live ? 'Live Demo' : 'Source Code'">↗</a>
</div>
      </article>
    </div>
  </section>
</template>

<style scoped>
.project {
  padding: 80px 20px;
  max-width: 900px;
  margin: 0 auto;
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

.project-list {
  display: flex;
  flex-direction: column;
  gap: 24px;
}

.project-card {
  display: flex;
  justify-content: space-between;
  align-items: flex-end;
  padding-bottom: 24px;
  border-bottom: 1px solid rgba(0, 0, 0, 0.1);
  cursor: pointer;
  transition: transform 0.3s ease;
}

.project-card:hover {
  transform: translateX(8px);
}

.project-num {
  font-size: 0.85rem;
  opacity: 0.5;
  font-family: monospace;
}

.project-title {
  font-family: 'Big Shoulders Display', sans-serif;
  font-size: clamp(2rem, 5vw, 3.5rem);
  font-weight: 900;
  text-transform: uppercase;
  margin: 4px 0;
  line-height: 1;
}

.project-cat {
  font-size: 0.9rem;
  opacity: 0.7;
  margin: 0;
}

.project-meta {
  display: flex;
  align-items: center;
  gap: 16px;
}

.project-year {
  font-family: monospace;
  font-size: 0.9rem;
  opacity: 0.6;
}

.code-link {
  font-size: 0.85rem;
  opacity: 0.6;
  text-decoration: underline;
  color: inherit;
  font-family: monospace;
}

.code-link:hover {
  opacity: 1;
}
.arrow-icon {
  width: 36px;
  height: 36px;
  border: 1px solid currentColor;
  border-radius: 50%;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 1.1rem;
  text-decoration: none;
  color: inherit;
  transition: background-color 0.3s ease, color 0.3s ease;
}

.project-card:hover .arrow-icon {
  background-color: #000;
  color: #fff;
}

/* Responsif Layar HP */
@media (max-width: 600px) {
  .project {
    padding: 40px 16px;
  }

  .project-card {
    flex-direction: column;
    align-items: flex-start;
    gap: 16px;
  }

  .project-meta {
    width: 100%;
    justify-content: space-between;
  }

  .project-title {
    font-size: 1.8rem;
  }
}
</style>