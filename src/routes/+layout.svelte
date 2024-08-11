<script lang="ts">
    import "../style.css";

    let {children} = $props();

    const builtYear = 2024;
    const currentYear = new Date().getFullYear();
</script>

<svelte:head>
    <title>Contact Cards</title>
    <meta name="description" content="Save your contact card and share it with anyone">
    <!-- <link rel="canonical" href=""> -->
    <meta name="robots" content="all">

    <meta property="og:title" content="Virtual Contact Card">
    <meta property="og:description" content="Manage your virtual contact card">
    <!-- <meta property="og:url" content=""> -->
    <meta property="og:type" content="website">
    <meta property="og:site_name" content="Virtual Contact Cards">

    <!-- <meta property="og:image" content="">
    <meta property="og:image:width" content="1200">
    <meta property="og:image:height" content="630"> -->

    <meta property="og:profile:username" content="sheehanr">  
    <meta property="og:profile:url" content="https://www.linkedin.com/in/sheehanr/"> 
    <meta property="og:portfolio:url" content="https://github.com/ryansheehan"> 
    <meta property="og:article:author" content="Ryan Sheehan">
</svelte:head>

<header class="content-grid">    
    <div class="primary-header__layout">     
        <a href="/" class="home-link">Virtual Contact Card</a>   
    </div>
</header>
<main>        
    {@render children()}    
</main>
<footer class="content-grid">
    <div class="footer__layout">
        <p>Contact: <a class="email-link" href="mailto:rsheehan@gmail.com">rsheehan@gmail.com</a></p>            
         <p><small>&copy; <time datetime={`${builtYear}`}>{builtYear}</time>{#if currentYear !== builtYear}-<time datetime={`${currentYear}`}>{currentYear}</time>{/if} Ryan Sheehan. All rights reserved.</small></p>
    </div>
</footer>

<style>
    :global(body) {
        --section-border: var(--border-size-1) solid color-mix(in lch, var(--grayscale-900) 30%, rgba(255, 255, 255, 0));

        display: flex;
        flex-flow: column nowrap;
    }

    main {                
        --gradient-gray: linear-gradient(in lch, var(--grayscale-950) 15%, color-mix(in lch, var(--grayscale-950) 80%, var(--grayscale-900)), var(--grayscale-900));        
             
        flex: 1;
        position: relative;        
    }

    header {      
        z-index: 10000;  
        isolation: isolate;
        align-items: baseline;
        position: sticky;
        top: 0;
        background-color: var(--clr-background);

        padding-block: var(--spacing-block-1);        
        border-bottom: var(--section-border);
    }

    .primary-header__layout {
        display: flex;
        justify-content: space-between;
        align-items: center;
    }    

    a {
        text-decoration: none;        
        color: var(--clr-text);        
    }

    .email-link {
        color: var(--clr-primary);

        &:hover {
            text-decoration: underline;
        }
    }

    .home-link {                    
        text-transform: uppercase;
        font-size: var(--font-size-3);
        line-height: var(--line-height-3);
        font-weight: var(--font-weight-6);
        letter-spacing: var(--font-letterspacing-3);                
    }

    footer {
        margin-block-start: var(--spacing-block-2);
        min-height: var(--spacing-block-3);        
        border-top: var(--section-border);
        
        display: grid;
        place-items: center;

        & p {
            font-size: var(--font-size-0);
            line-height: var(--line-height-0);
        }
    }

    .footer__layout {
        display: grid;
        grid-template-columns: 1fr;
        grid-auto-rows: auto;
        justify-items: center;
    }
</style>

