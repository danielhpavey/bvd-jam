<template>
  <div class="layout">
    <header class="header">
      <strong>
        <g-link to="/" class="site-title">{{ $static.metaData.siteName }}</g-link>
      </strong>
      <nav class="nav">
        <g-link class="nav__link" to="/">Home</g-link>
        <g-link class="nav__link" to="/about">About</g-link>
        <g-link class="nav__link" to="/blog">Blog</g-link>
        <g-link class="nav__link" to="/sign-up">Sign Up</g-link>
        <g-link class="nav__link" to="/contact">Contact Us</g-link>
        <g-link class="nav__link" to="/directory">Directory</g-link>
      </nav>
    </header>
    <transition name="fade" appear>
      <main>
        <slot/>
      </main>
    </transition>
    <footer>
      Built with <a href="https://gridsome.org/docs" target="_blank" rel="noopener" class="link--gridsome">Gridsome</a> by <a href="https://twitter.com/PichuPlayer" target="_blank" rel="noopener" class="link--blue">Tyler</a>
    </footer>
  </div>
</template>

<static-query>
query {
  metaData {
    siteName
  }
}
</static-query>

<style>
@font-face {
	font-family: system-ui;
	font-style: normal;
	font-weight: 300;
	src: local(".SFNSText-Light"), local(".HelveticaNeueDeskInterface-Light"), local(".LucidaGrandeUI"), local("Segoe UI Light"), local("Ubuntu Light"), local("Roboto-Light"), local("DroidSans"), local("Tahoma");
}

@font-face {
	font-family: system-ui;
	font-style: italic;
	font-weight: 300;
	src: local(".SFNSText-LightItalic"), local(".HelveticaNeueDeskInterface-Italic"), local(".LucidaGrandeUI"), local("Segoe UI Light Italic"), local("Ubuntu Light Italic"), local("Roboto-LightItalic"), local("DroidSans"), local("Tahoma");
}

@font-face {
	font-family: system-ui;
	font-style: normal;
	font-weight: 400;
	src: local(".SFNSText-Regular"), local(".HelveticaNeueDeskInterface-Regular"), local(".LucidaGrandeUI"), local("Segoe UI"), local("Ubuntu"), local("Roboto-Regular"), local("DroidSans"), local("Tahoma");
}

@font-face {
	font-family: system-ui;
	font-style: italic;
	font-weight: 400;
	src: local(".SFNSText-Italic"), local(".HelveticaNeueDeskInterface-Italic"), local(".LucidaGrandeUI"), local("Segoe UI Italic"), local("Ubuntu Italic"), local("Roboto-Italic"), local("DroidSans"), local("Tahoma");
}

@font-face {
	font-family: system-ui;
	font-style: normal;
	font-weight: 500;
	src: local(".SFNSText-Medium"), local(".HelveticaNeueDeskInterface-MediumP4"), local(".LucidaGrandeUI"), local("Segoe UI Semibold"), local("Ubuntu Medium"), local("Roboto-Medium"), local("DroidSans-Bold"), local("Tahoma Bold");
}

@font-face {
	font-family: system-ui;
	font-style: italic;
	font-weight: 500;
	src: local(".SFNSText-MediumItalic"), local(".HelveticaNeueDeskInterface-MediumItalicP4"), local(".LucidaGrandeUI"), local("Segoe UI Semibold Italic"), local("Ubuntu Medium Italic"), local("Roboto-MediumItalic"), local("DroidSans-Bold"), local("Tahoma Bold");
}

@font-face {
	font-family: system-ui;
	font-style: normal;
	font-weight: 700;
	src: local(".SFNSText-Bold"), local(".HelveticaNeueDeskInterface-Bold"), local(".LucidaGrandeUI"), local("Segoe UI Bold"), local("Ubuntu Bold"), local("Roboto-Bold"), local("DroidSans-Bold"), local("Tahoma Bold");
}

@font-face {
	font-family: system-ui;
	font-style: italic;
	font-weight: 700;
	src: local(".SFNSText-BoldItalic"), local(".HelveticaNeueDeskInterface-BoldItalic"), local(".LucidaGrandeUI"), local("Segoe UI Bold Italic"), local("Ubuntu Bold Italic"), local("Roboto-BoldItalic"), local("DroidSans-Bold"), local("Tahoma Bold");
}
/* Transition */
.fade-enter-active {
  transition: opacity .5s;
}

.fade-enter {
  opacity: 0;
}

/* CSS */
body > div {
  display: flex;
  flex-direction: column;
  justify-content: space-between;
}

body {
  font-family:system-ui;
  margin:0;
  padding:0;
  line-height: 1.5;
  font-size: 1.1rem;
}

.layout {
  max-width: 760px;
  margin: 0 auto;
  padding-left: 20px;
  padding-right: 20px;
  min-height: 100vh;
}

main {
  flex-grow: 1;
}

footer {
  text-align: center;
  width: 100%;
  max-width: inherit;
  padding: 20px 0;
}

.nav__link {
  margin-left: 20px;
  padding: 10px 15px;
  font-weight: bold;
}

.flex-row {
  display: flex;
  align-items: center;
}

.space-between {
  justify-content: space-between
}

.site-title {
  display:block;
  padding: 5px 15px;
  text-decoration: none;
  font-size: 1.5rem;
  margin: 8px 0;
}


.header * {
  /* Prevent Margin Collapse */
  display: inline-block;
}

.header {
  display: flex;
  flex-direction: column;
  align-items: center;
  margin-bottom: 8px;
}

.header > nav > a:first-child {
  margin-left: 0;
}


.link--gridsome {
  border-bottom: 3px solid hsl(157, 55%, 58%);
  text-decoration: none;
}


</style>
