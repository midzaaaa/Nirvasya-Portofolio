<template>
  <footer id="contact" class="contact">
    <div class="contact-container">
      <span class="label">Get In Touch</span>
      
      <h2 class="headline">
        Let’s Work <br /> Together.
      </h2>

      <a href="mailto:mizaprada@gmail.com" class="email-link">
        mizaprada@gmail.com
      </a>

      <div class="footer-bottom">
        <div class="socials">
          <a href="https://github.com" target="_blank" rel="noopener">Github</a>
          <a href="https://linkedin.com" target="_blank" rel="noopener">LinkedIn</a>
          <a href="https://instagram.com" target="_blank" rel="noopener">Instagram</a>
        </div>
        <p class="copyright">© 2026 Nirvasya. All rights reserved.</p>
      </div>
    </div>
  </footer>
</template>

<style scoped>
.contact {
  background-color: #111;
  color: #e5e3df;
  padding: 100px 20px 40px;
  margin-top: 100px;
}

.contact-container {
  max-width: 900px;
  margin: 0 auto;
}

.label {
  font-size: 0.8rem;
  text-transform: uppercase;
  letter-spacing: 0.15em;
  opacity: 0.5;
  display: block;
  margin-bottom: 24px;
}

.headline {
  font-family: 'Big Shoulders Display', sans-serif;
  font-size: clamp(3rem, 10vw, 7rem);
  font-weight: 900;
  text-transform: uppercase;
  line-height: 0.9;
  margin-bottom: 40px;
}

.email-link {
  color: inherit;
  font-size: clamp(1.2rem, 3vw, 2rem);
  text-decoration: underline;
  text-underline-offset: 8px;
  transition: opacity 0.3s ease;
}

.email-link:hover {
  opacity: 0.6;
}

.footer-bottom {
  margin-top: 100px;
  padding-top: 24px;
  border-top: 1px solid rgba(255, 255, 255, 0.15);
  display: flex;
  justify-content: space-between;
  align-items: center;
  flex-wrap: wrap;
  gap: 16px;
  font-family: monospace;
  font-size: 0.85rem;
  opacity: 0.7;
}

.socials {
  display: flex;
  gap: 20px;
}

.socials a {
  color: inherit;
  text-decoration: none;
}

.socials a:hover {
  text-decoration: underline;
}
</style>