---
permalink: /
title: " "
author_profile: false
redirect_from: 
  - /about/
  - /about.html
---

<script>
// Subdomain redirect support (activate when subdomains are set up)
// Uncomment the following lines when you have academic.yourdomain.com and culture.yourdomain.com
/*
const host = window.location.hostname;
if (host.startsWith('academic.')) {
  window.location.replace('/academic/');
} else if (host.startsWith('culture.')) {
  window.location.replace('/culture/');
}
*/

// Ensure masthead is visible on homepage
document.addEventListener('DOMContentLoaded', function() {
  const masthead = document.querySelector('.masthead');
  if (masthead) {
    masthead.style.display = 'block';
    masthead.style.visibility = 'visible';
  }
  
  // Add homepage class
  document.body.classList.add('homepage-gateway');
});
</script>

<style>
  body {
    overflow: hidden;
  }
  
  .gateway-container {
    display: flex;
    height: 100vh;
    margin: -3rem -2rem;
    position: relative;
  }
  
  .gateway-side {
    flex: 1;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    padding: 3rem;
    cursor: pointer;
    transition: all 0.4s cubic-bezier(0.4, 0, 0.2, 1);
    position: relative;
    overflow: hidden;
  }
  
  .gateway-side::before {
    content: '';
    position: absolute;
    top: 0;
    left: 0;
    right: 0;
    bottom: 0;
    transition: transform 0.4s cubic-bezier(0.4, 0, 0.2, 1);
    transform: scale(1);
  }
  
  .gateway-side:hover::before {
    transform: scale(1.05);
  }
  
  .academic-side {
    background: linear-gradient(135deg, #FDFBF5 0%, #F0EAD6 100%);
  }
  
  .culture-side {
    background: linear-gradient(135deg, #F0EAD6 0%, #FDFBF5 100%);
  }
  
  .gateway-side:hover {
    flex: 1.1;
  }
  
  .gateway-content {
    position: relative;
    z-index: 1;
    text-align: center;
    max-width: 400px;
  }
  
  .gateway-title {
    font-size: 3rem;
    margin-bottom: 1rem;
    color: var(--zen-accent, #6B8E23);
    font-weight: 300;
  }
  
  .gateway-subtitle {
    font-size: 1.2rem;
    color: var(--zen-text-light, #666);
    margin-bottom: 2rem;
  }
  
  .gateway-description {
    color: var(--zen-text, #3a3a3a);
    line-height: 1.6;
    margin-bottom: 2rem;
  }
  
  .gateway-btn {
    display: inline-block;
    padding: 0.8rem 2rem;
    background: var(--zen-accent, #6B8E23);
    color: white;
    border-radius: 30px;
    text-decoration: none;
    font-size: 1.1rem;
    transition: all 0.3s ease;
    box-shadow: 0 4px 15px rgba(0,0,0,0.1);
  }
  
  .gateway-btn:hover {
    background: var(--zen-highlight, #DAA520);
    transform: translateY(-2px);
    box-shadow: 0 6px 20px rgba(0,0,0,0.15);
  }
  
  .divider {
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    width: 2px;
    height: 100px;
    background: var(--zen-accent, #6B8E23);
    opacity: 0.3;
  }
  
  @media (max-width: 768px) {
    .gateway-container {
      flex-direction: column;
    }
    
    .divider {
      width: 100px;
      height: 2px;
    }
    
    .gateway-title {
      font-size: 2rem;
    }
    
    .gateway-side:hover {
      flex: 1;
    }
  }
  
  /* Override dark mode for gateway */
  html[data-theme="dark"] .academic-side {
    background: linear-gradient(135deg, #1a1a1a 0%, #2a2a2a 100%);
  }
  
  html[data-theme="dark"] .culture-side {
    background: linear-gradient(135deg, #2a2a2a 0%, #1a1a1a 100%);
  }
</style>

<div class="gateway-container">
  <a href="/academic/" class="gateway-side academic-side">
    <div class="gateway-content">
      <h1 class="gateway-title">Academic</h1>
      <p class="gateway-subtitle">Research & Science</p>
      <p class="gateway-description">
        Statistics, Data Science, Machine Learning<br>
        LMU Munich · StaBLab · HZI
      </p>
      <span class="gateway-btn">Enter Academic Site →</span>
    </div>
  </a>
  
  <div class="divider"></div>
  
  <a href="/culture/" class="gateway-side culture-side">
    <div class="gateway-content">
      <h1 class="gateway-title">Culture</h1>
      <p class="gateway-subtitle">Arts & Philosophy</p>
      <p class="gateway-description">
        Japanese Aesthetics, Tea Ceremony<br>
        Interactive Digital Experiences
      </p>
      <span class="gateway-btn">Enter Culture Site →</span>
    </div>
  </a>
</div>