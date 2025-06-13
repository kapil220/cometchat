<script>
  import { onMount } from 'svelte';
  
  let isMobile = false;
  let expandedSections = {};
  
  onMount(() => {
    const checkMobile = () => {
      isMobile = window.innerWidth <= 768;
    };
    
    checkMobile();
    window.addEventListener('resize', checkMobile);
    
    return () => {
      window.removeEventListener('resize', checkMobile);
    };
  });
  
  function toggleSection(section) {
    expandedSections[section] = !expandedSections[section];
    expandedSections = { ...expandedSections };
  }
  
  const footerData = {
    platform: {
      title: 'Platform',
      sections: [
        {
          title: 'Features',
          links: [
            'Chat & Messaging',
            'Voice & Video Calls',
            'Security & Compliance',
            'Extensions',
            'Features at a glance',
            'Webhooks & Bots',
            'Moderation',
            'Analytics & Insights'
          ]
        },
        {
          title: 'Implementation',
          links: ['Widgets', 'UI Kits', 'SDK & APIs']
        },
        {
          title: 'Technologies',
          links: [
            'React Chat SDK & API',
            'Angular Chat SDK & API',
            'Vue Chat SDK & API',
            'iOS Swift Chat SDK & API',
            'Android Kotlin Chat SDK & API',
            'Android Java Chat SDK & API',
            'React Native Chat SDK & API',
            'Ionic/Capacitor Chat SDK & API',
            'WordPress Chat SDK & API',
            'Laravel/PHP Chat SDK & API',
            'Flutter Chat SDK & API',
            'Next.js Chat SDK & API'
          ]
        }
      ]
    },
    solutions: {
      title: 'Solutions',
      sections: [
        {
          title: 'By Use cases',
          links: [
            'Social Community',
            'Marketplace',
            'Healthcare',
            'Education',
            'Virtual Events',
            'On-Demand Service',
            'Dating Apps',
            'Gaming'
          ]
        },
        {
          title: 'By Organization Type',
          links: ['Enterprise', 'Startups']
        }
      ]
    },
    developers: {
      title: 'Developers',
      sections: [
        {
          title: 'Technologies documentation',
          links: [
            'React',
            'Angular',
            'Vue',
            'iOS Swift',
            'Android Kotlin',
            'Android Java',
            'React Native',
            'Ionic/Capacitor',
            'WordPress',
            'Laravel/PHP',
            'Flutter',
            'Next.js'
          ]
        },
        {
          title: 'Documentation',
          links: [
            'Documentation',
            'Product updates',
            'Tutorials',
            'Open-source Apps',
            'Product status',
            'Glossary'
          ]
        }
      ]
    },
    resources: {
      title: 'Resources',
      sections: [
        {
          title: 'Customer stories',
          links: [
            'Blog',
            'Give feedback',
            'Community forum',
            'Help center',
            'Partners'
          ]
        },
        {
          title: 'Competitors',
          links: ['SendBird', 'GetStream', 'Applozic', 'Twilio', 'PubNub']
        },
        {
          title: 'Company',
          links: [
            'About us',
            'Careers',
            'Partners',
            'Pricing',
            'Chat with us'
          ]
        }
      ]
    }
  };
  
  const socialLinks = [
    { name: 'Facebook', icon: 'M24 12.073c0-6.627-5.373-12-12-12s-12 5.373-12 12c0 5.99 4.388 10.954 10.125 11.854v-8.385H7.078v-3.47h3.047V9.43c0-3.007 1.792-4.669 4.533-4.669 1.312 0 2.686.235 2.686.235v2.953H15.83c-1.491 0-1.956.925-1.956 1.874v2.25h3.328l-.532 3.47h-2.796v8.385C19.612 23.027 24 18.062 24 12.073z' },
    { name: 'LinkedIn', icon: 'M20.447 20.452h-3.554v-5.569c0-1.328-.027-3.037-1.852-3.037-1.853 0-2.136 1.445-2.136 2.939v5.667H9.351V9h3.414v1.561h.046c.477-.9 1.637-1.85 3.37-1.85 3.601 0 4.267 2.37 4.267 5.455v6.286zM5.337 7.433c-1.144 0-2.063-.926-2.063-2.065 0-1.138.92-2.063 2.063-2.063 1.14 0 2.064.925 2.064 2.063 0 1.139-.925 2.065-2.064 2.065zm1.782 13.019H3.555V9h3.564v11.452zM22.225 0H1.771C.792 0 0 .774 0 1.729v20.542C0 23.227.792 24 1.771 24h20.451C23.2 24 24 23.227 24 22.271V1.729C24 .774 23.2 0 22.222 0h.003z' },
    { name: 'Instagram', icon: 'M12 2.163c3.204 0 3.584.012 4.85.07 3.252.148 4.771 1.691 4.919 4.919.058 1.265.069 1.645.069 4.849 0 3.205-.012 3.584-.069 4.849-.149 3.225-1.664 4.771-4.919 4.919-1.266.058-1.644.07-4.85.07-3.204 0-3.584-.012-4.849-.07-3.26-.149-4.771-1.699-4.919-4.92-.058-1.265-.07-1.644-.07-4.849 0-3.204.013-3.583.07-4.849.149-3.227 1.664-4.771 4.919-4.919 1.266-.057 1.645-.069 4.849-.069zm0-2.163c-3.259 0-3.667.014-4.947.072-4.358.2-6.78 2.618-6.98 6.98-.059 1.281-.073 1.689-.073 4.948 0 3.259.014 3.668.072 4.948.2 4.358 2.618 6.78 6.98 6.98 1.281.058 1.689.072 4.948.072 3.259 0 3.668-.014 4.948-.072 4.354-.2 6.782-2.618 6.979-6.98.059-1.28.073-1.689.073-4.948 0-3.259-.014-3.667-.072-4.947-.196-4.354-2.617-6.78-6.979-6.98-1.281-.059-1.69-.073-4.949-.073zm0 5.838c-3.403 0-6.162 2.759-6.162 6.162s2.759 6.163 6.162 6.163 6.162-2.759 6.162-6.163c0-3.403-2.759-6.162-6.162-6.162zm0 10.162c-2.209 0-4-1.79-4-4 0-2.209 1.791-4 4-4s4 1.791 4 4c0 2.21-1.791 4-4 4zm6.406-11.845c-.796 0-1.441.645-1.441 1.44s.645 1.44 1.441 1.44c.795 0 1.439-.645 1.439-1.44s-.644-1.44-1.439-1.44z' },
    { name: 'Twitter', icon: 'M23.953 4.57a10 10 0 01-2.825.775 4.958 4.958 0 002.163-2.723c-.951.555-2.005.959-3.127 1.184a4.92 4.92 0 00-8.384 4.482C7.69 8.095 4.067 6.13 1.64 3.162a4.822 4.822 0 00-.666 2.475c0 1.71.87 3.213 2.188 4.096a4.904 4.904 0 01-2.228-.616v.06a4.923 4.923 0 003.946 4.827 4.996 4.996 0 01-2.212.085 4.936 4.936 0 004.604 3.417 9.867 9.867 0 01-6.102 2.105c-.39 0-.779-.023-1.17-.067a13.995 13.995 0 007.557 2.209c9.053 0 13.998-7.496 13.998-13.985 0-.21 0-.42-.015-.63A9.935 9.935 0 0024 4.59z' },
    { name: 'GitHub', icon: 'M12 0c-6.626 0-12 5.373-12 12 0 5.302 3.438 9.8 8.207 11.387.599.111.793-.261.793-.577v-2.234c-3.338.726-4.033-1.416-4.033-1.416-.546-1.387-1.333-1.756-1.333-1.756-1.089-.745.083-.729.083-.729 1.205.084 1.839 1.237 1.839 1.237 1.07 1.834 2.807 1.304 3.492.997.107-.775.418-1.305.762-1.604-2.665-.305-5.467-1.334-5.467-5.931 0-1.311.469-2.381 1.236-3.221-.124-.303-.535-1.524.117-3.176 0 0 1.008-.322 3.301 1.23.957-.266 1.983-.399 3.003-.404 1.02.005 2.047.138 3.006.404 2.291-1.552 3.297-1.23 3.297-1.23.653 1.653.242 2.874.118 3.176.77.84 1.235 1.911 1.235 3.221 0 4.609-2.807 5.624-5.479 5.921.43.372.823 1.102.823 2.222v3.293c0 .319.192.694.801.576 4.765-1.589 8.199-6.086 8.199-11.386 0-6.627-5.373-12-12-12z' }
  ];
</script>

<footer class="cometchat-footer">
  <div class="footer-container">
    <!-- Logo -->
    <div class="footer-logo">cometchat</div>
    
    <!-- Main Content -->
    <div class="footer-main" class:mobile={isMobile}>
      {#each Object.entries(footerData) as [key, column]}
        <div class="footer-column">
          {#if isMobile}
            <!-- Mobile collapsible version -->
            <button 
              class="column-title mobile-toggle"
              on:click={() => toggleSection(key)}
            >
              {column.title}
              <span class="toggle-icon" class:expanded={expandedSections[key]}>+</span>
            </button>
            
            {#if expandedSections[key]}
              <div class="column-content">
                {#each column.sections as section}
                  <div class="column-section">
                    <h4 class="section-title">{section.title}</h4>
                    {#each section.links as link}
                      <a href="#" class="footer-link">{link}</a>
                    {/each}
                  </div>
                {/each}
              </div>
            {/if}
          {:else}
            <!-- Desktop version -->
            <h3 class="column-title">{column.title}</h3>
            {#each column.sections as section}
              <div class="column-section">
                <h4 class="section-title">{section.title}</h4>
                {#each section.links as link}
                  <a href="#" class="footer-link">{link}</a>
                {/each}
              </div>
            {/each}
          {/if}
        </div>
      {/each}
    </div>
    
    <!-- Footer Bottom -->
    <div class="footer-bottom">
      <div class="footer-legal">
        <span class="copyright">2023 © CometChat</span>
        <a href="#" class="legal-link">Terms of Use</a>
        <a href="#" class="legal-link">Privacy Policy</a>
      </div>
      
      <div class="footer-social">
        {#each socialLinks as social}
          <a href="#" class="social-link" aria-label={social.name}>
            <svg width="20" height="20" viewBox="0 0 24 24" fill="currentColor">
              <path d={social.icon}/>
            </svg>
          </a>
        {/each}
      </div>
    </div>
  </div>
</footer>

<style>
  /* Base Styles */
  .cometchat-footer {
    background-color: #0f1419;
    color: #ffffff;
    font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen, Ubuntu, Cantarell, 'Open Sans', 'Helvetica Neue', sans-serif;
    padding: 48px 0 0 0;
    width: 100%;
  }
  
  .footer-container {
    max-width: 1200px;
    margin: 0 auto;
    padding: 0 24px;
  }
  
  .footer-logo {
    font-size: 24px;
    font-weight: 600;
    color: #ffffff;
    margin-bottom: 48px;
    text-transform: lowercase;
  }
  
  .footer-main {
    display: grid;
    grid-template-columns: repeat(4, 1fr);
    gap: 48px;
    margin-bottom: 48px;
  }
  
  .footer-main.mobile {
    grid-template-columns: 1fr;
    gap: 0;
  }
  
  .footer-column {
    display: flex;
    flex-direction: column;
    gap: 32px;
  }
  
  .column-title {
    font-size: 16px;
    font-weight: 600;
    color: #6366f1;
    margin: 0;
  }
  
  .mobile-toggle {
    background: none;
    border: none;
    color: #6366f1;
    font-size: 16px;
    font-weight: 600;
    padding: 16px 0;
    display: flex;
    justify-content: space-between;
    align-items: center;
    width: 100%;
    text-align: left;
    cursor: pointer;
    border-top: 1px solid #374151;
  }
  
  .mobile-toggle:first-child {
    border-top: none;
  }
  
  .toggle-icon {
    font-size: 20px;
    transition: transform 0.2s ease;
  }
  
  .toggle-icon.expanded {
    transform: rotate(45deg);
  }
  
  .column-content {
    padding-bottom: 16px;
  }
  
  .column-section {
    display: flex;
    flex-direction: column;
    gap: 16px;
    margin-bottom: 32px;
  }
  
.section-title {
    font-size: 14px;
    font-weight: 500;
    color: #9ca3af;
    margin: 0;
    text-align: left;
}
  
  .footer-link {
    font-size: 14px;
    color: rgba(250, 250, 255, 1);
    text-decoration: none;
    transition: color 0.2s ease;
  }
  
  .footer-link:hover {
    color: #9ca3af;
  }
  
  .footer-bottom {
    border-top: 1px solid #374151;
    padding: 24px 0;
    display: flex;
    justify-content: space-between;
    align-items: center;
  }
  
  .footer-legal {
    display: flex;
    align-items: center;
    gap: 32px;
  }
  
  .copyright {
    font-size: 14px;
    color: #9ca3af;
  }
  
  .legal-link {
    font-size: 14px;
    color: #9ca3af;
    text-decoration: none;
    transition: color 0.2s ease;
  }
  
  .legal-link:hover {
    color: #ffffff;
  }
  
  .footer-social {
    display: flex;
    gap: 16px;
  }
  
  .social-link {
    color: #9ca3af;
    transition: color 0.2s ease;
    display: flex;
    align-items: center;
    justify-content: center;
  }
  
  .social-link:hover {
    color: #ffffff;
  }
  
  /* Mobile Responsive Styles */
  @media (max-width: 1024px) {
    .footer-main:not(.mobile) {
      grid-template-columns: repeat(2, 1fr);
      gap: 32px;
    }
  }
  
  @media (max-width: 768px) {
    .footer-main:not(.mobile) {
      grid-template-columns: 1fr;
      gap: 24px;
    }
    
    .footer-bottom {
      flex-direction: column;
      align-items: flex-start;
      gap: 16px;
    }
    
    .footer-legal {
      flex-direction: column;
      align-items: flex-start;
      gap: 16px;
    }
    
    .footer-logo {
      margin-bottom: 24px;
    }
    
    .footer-container {
      padding: 0 20px;
    }
  }
</style>