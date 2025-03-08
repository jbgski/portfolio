<script>
    import { fade, fly } from 'svelte/transition';
    export const prerender = true;
    
    const skills = [
      { icon: '🎨', text: 'Designer' },
      { icon: '💻', text: '.NET' },
      { icon: '📱', text: 'Flutter' },
      { icon: '🌐', text: 'Web' },
      { icon: '📲', text: 'React Native' },
      { icon: '✨', text: 'Everything else' }
    ];

    const projects = [
      { title: 'Paper', description: 'All-in-one reading app for Windows', link: 'https://paper.refract.fyi', tech: 'React Native' },
    ];

    const socials = [
      { icon: '⌨️', text: 'GitHub', link: 'https://github.com/jbgski' },
      { icon: '🐦', text: 'Twitter', link: 'https://twitter.com/jbgski' },
    ];
  </script>
  
  <main>
    <div class="container" in:fade={{ duration: 1000 }}>
    <h1 in:fly={{ y: 50, duration: 1000 }}>hey there <span class="wave">👋</span></h1>

<style>
  .wave {
    display: inline-block;
    animation: wave 2s infinite;
  }

  @keyframes wave {
    0%, 100% { transform: rotate(0deg); }
    25% { transform: rotate(-20deg); }
    75% { transform: rotate(20deg); }
  }
</style>
      
      <div class="intro" in:fly={{ y: 50, duration: 1000, delay: 200 }}>
        <p>i'm <b>Jakub</b></p>
        <i>turning ideas into reality through code & design</i>
      </div>
  
      <div class="skills">
        {#each skills as skill, i}
          <span 
            class="skill-tag"
            in:fly={{ 
              y: 20, 
              duration: 400, 
              delay: 500 + (i * 100) 
            }}
          >
            {skill.icon} {skill.text}
          </span>
        {/each}
      </div>
  
      <div class="projects" in:fly={{ y: 20, duration: 400, delay: 1000 }}>
        <h2>My Projects</h2>
        <div class="projects-grid">
          {#each projects as project}
            <div class="project-card">
              <b>{project.title}</b>
              <p>{project.description}</p>
              <span class="tech-tag">{project.tech}</span>
              <br/>
              <a href={project.link}>View Project →</a>
            </div>
          {/each}
        </div>
      </div>
  
      <div class="socials" in:fly={{ y: 20, duration: 400, delay: 1100 }}>
        {#each socials as social}
          <a href={social.link} class="social-link" target="_blank" rel="noopener noreferrer">
            {social.icon} {social.text}
          </a>
        {/each}
      </div>
  

  
      <a 
        href="mailto:hey@jbg.ski" 
        class="email-button"
        in:fly={{ y: 20, duration: 400, delay: 1400 }}
      >
        email me
      </a>
      <p class="construction" in:fly={{ y: 20, duration: 400, delay: 1200 }}>
        this page is still under construction 🚧
      </p>
    </div>
  </main>
  
  <style>
    main {
      min-height: 100vh;
      display: flex;
      justify-content: center;
      align-items: center;
      background: #f5f5f5;
      font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif;
    }

    .container {
      max-width: 800px;
      padding: 2rem;
      text-align: center;
    }
  
    h1 {
      font-size: 3rem;
      margin-bottom: 1rem;
      color: #333;
    }
    h2 {
        font-size: 1.2rem;
        font-weight: 700;
        margin-bottom: 1rem;

      }
    .intro {
      font-size: 1.5rem;
      margin-bottom: 2rem;
      color: #666;
    }
  
    .intro b {
      color: #333;
      position: relative;
    }
  
    .intro b::after {
      content: '';
      position: absolute;
      bottom: -2px;
      left: 0;
      width: 100%;
      height: 2px;
      background: #007AFF;
    }
  
    .skills {
      display: flex;
      flex-wrap: wrap;
      gap: 1rem;
      justify-content: center;
      margin-bottom: 2rem;
    }
  
    .skill-tag {
      background: white;
      padding: 0.5rem 1rem;
      border-radius: 20px;
      box-shadow: 0 2px 8px rgba(0,0,0,0.1);
      transition: transform 0.2s, box-shadow 0.2s;
    }
  
    .skill-tag:hover {
      transform: translateY(-2px);
      box-shadow: 0 4px 12px rgba(0,0,0,0.15);
    }
  
    .construction {
      color: #666;
      margin: 2rem;
    }
  
    .email-button {
      display: inline-block;
      background: #007AFF;
      color: white;
      padding: 0.8rem 1.5rem;
      border-radius: 25px;
      text-decoration: none;
      font-weight: 500;
      transition: transform 0.2s, box-shadow 0.2s;
    }
  
    .email-button:hover {
      transform: translateY(-2px);
      box-shadow: 0 4px 12px rgba(0,122,255,0.3);
    }
    .projects-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    gap: 2rem;
    margin-bottom: 2rem;
  }

  .project-card {
    background: white;
    padding: 1.5rem;
    border-radius: 15px;
    box-shadow: 0 2px 8px rgba(0,0,0,0.1);
    transition: transform 0.2s, box-shadow 0.2s;
    text-align: left;
  }

  .project-card:hover {
    transform: translateY(-5px);
    box-shadow: 0 4px 12px rgba(0,0,0,0.15);
  }

  .project-card h3 {
    margin: 0 0 1rem 0;
    color: #333;
  }

  .tech-tag {
    display: inline-block;
    background: #007AFF15;
    color: #007AFF;
    padding: 0.3rem 0.8rem;
    border-radius: 15px;
    font-size: 0.9rem;
    margin: 0.5rem 0;
  }

  .socials {
    display: flex;
    gap: 1rem;
    justify-content: center;
    margin-bottom: 2rem;
  }

  .social-link {
    background: white;
    padding: 0.5rem 1rem;
    border-radius: 20px;
    text-decoration: none;
    color: #333;
    transition: transform 0.2s;
  }

  .social-link:hover {
    transform: translateY(-2px);
  }

  footer {
    margin-top: 4rem;
    color: #666;
    font-size: 0.9rem;
  }

    @media (max-width: 600px) {
      h1 {
        font-size: 2rem;
      }

  
      .intro {
        font-size: 1.2rem;
      }
  
      .skills {
        gap: 0.5rem;
      }
  
      .skill-tag {
        padding: 0.4rem 0.8rem;
        font-size: 0.9rem;
      }
      .projects-grid {
      grid-template-columns: 1fr;
    }

    .socials {
      flex-direction: column;
      gap: 0.5rem;
    }
    }
        /* Add dark mode styles */
        @media (prefers-color-scheme: dark) {
    main {
      background: #1a1a1a;
    }

    h1, .intro b {
      color: #ffffff;
    }

    .intro, .construction {
      color: #a0a0a0;
    }

    .intro b::after {
      background: #409CFF;
    }

    .skill-tag {
      background: #2a2a2a;
      color: #ffffff;
      box-shadow: 0 2px 8px rgba(0,0,0,0.3);
    }

    .skill-tag:hover {
      box-shadow: 0 4px 12px rgba(0,0,0,0.4);
    }

    .project-card {
      background: #2a2a2a;
      color: #ffffff;
      box-shadow: 0 2px 8px rgba(0,0,0,0.3);
    }

    .project-card:hover {
      box-shadow: 0 4px 12px rgba(0,0,0,0.4);
    }

    .project-card a {
      color: #409CFF;
    }

    .project-card b {
      color: #ffffff;
    }

    .project-card p {
      color: #a0a0a0;
    }

    .tech-tag {
      background: #409CFF15;
      color: #409CFF;
    }

    .email-button {
      background: #409CFF;
    }
    h2 {
        color: #ffffff;
    }
    .email-button:hover {
      box-shadow: 0 4px 12px rgba(64,156,255,0.3);
    }

    .social-link {
      background: #2a2a2a;
      color: #ffffff;
      box-shadow: 0 2px 8px rgba(0,0,0,0.3);
    }

    .social-link:hover {
      box-shadow: 0 4px 12px rgba(0,0,0,0.4);
    }
}

  </style>