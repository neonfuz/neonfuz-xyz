<script>
 import 'milligram';
 import Header from '$lib/Header.svelte';
</script>

<Header />
<main class="container">
    <slot/>
</main>
<footer>
    © Sage Raflik 2022
</footer>

<style>
 :global(body) {
     margin: 0;
 }
 :root {
     scroll-behavior: smooth;
 }
 main {
     margin-top: 8rem;
 }
 footer {
     text-align: center;
 }
</style>
