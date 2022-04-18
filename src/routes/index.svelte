<script>
 const foo = [
     {
         name: "MiniPlayer in SideBar",
         href: "https://gist.github.com/neonfuz/6d3790334983b87b638ddecf84d0ab09"
     },
     {
         name: "Quick Playlist Button",
         href: "https://gist.github.com/neonfuz/ea14fe2ad32c4caa860f36bb521b9a60"
     },
 ];
</script>

<header class="container">
    <h1>neonfuz.xyz</h1>
</header>

<main class="container">
    <section>
        <h3>Resume</h3>
        <ul>
            <li>
                <a href="https://neonfuz.github.io/resume/resume.pdf">PDF</a>
            </li>
        </ul>
    </section>
    <section>
        <h3>Youtube improvements</h3>
        <ul>
            {#each foo as {name, href}}
            <li>
                <a href={href}>
                    {name}
                </a>
            </li>
            {/each}
        </ul>
    </section>
</main>
