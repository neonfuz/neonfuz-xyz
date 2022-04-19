<script>
 export let title;
 export let src;
 export let href = src;
</script>

<div class="pdf-wrap">
    <iframe frameborder="0" {title} {src} />
    <a {href}>{title}</a>
</div>

<style>
 div {
     display: block;
     position: relative;
 }
 iframe {
     position: absolute;
     width: 100%;
     height: 100vh;
 }
 a {
     display: block;
     position: absolute;
     inset: 0;
     z-index: 1;
     color: transparent;
 }
</style>
