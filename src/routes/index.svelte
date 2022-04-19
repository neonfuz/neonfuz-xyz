<script>
 import PDF from '$lib/PDF.svelte';
 const foo = [
     {
         name: "MiniPlayer in SideBar",
         href: "https://gist.github.com/neonfuz/6d3790334983b87b638ddecf84d0ab09",
         id:   "youtubeMiniplayerSidebar"
     },
     {
         name: "Quick Playlist Button",
         href: "https://gist.github.com/neonfuz/ea14fe2ad32c4caa860f36bb521b9a60",
         id:   "youtubePlaylistButton"
     },
 ];
 let tabId = '';
 function preview(node, content) {
     function onHover() {
         tabId = content;
     }
     node.addEventListener('mouseenter', onHover);
     return {
         destroy() {
             node.removeEventListener('mouseenter', onHover);
         }
     }
 }
 function tab(name, tabId) {
     if (tabId === name)
         return 'width: 100%; opacity: 1;';
     else
         return 'width: 100%; opacity: 0; pointer-events: none;'
 }
</script>


<header class="container">
    <h1>neonfuz.xyz</h1>
    <nav>
        <section>
            <h3>Links</h3>
            <ul>
                <li>
                    <a href="https://neonfuz.github.io/resume/resume.pdf"
                       use:preview={"resume"}>
                        Resume
                    </a>
                </li>
                <li>
                    <a href="https://github.com/neonfuz"
                       use:preview={"github"}>
                        Github
                    </a>
                </li>
            </ul>
        </section>
        <section>
            <h3>Youtube improvements</h3>
            <ul>
                {#each foo as {name, href, id}}
                    <li>
                        <a href={href} use:preview={id}>
                            {name}
                        </a>
                    </li>
                {/each}
            </ul>
        </section>
    </nav>
</header>

<main class="container">
    <div class="row">
        <div class="column">
        </div>
        <div class="column column-67 preview">
            <div style={tab('resume', tabId)} style:width="100%">
                <PDF
                    title="Resume"
                    src="https://neonfuz.github.io/resume/resume.html"
                    href="https://neonfuz.github.io/resume/resume.pdf"
                />
            </div>
            <div style={tab('github', tabId)}>
                    <a href="https://github.com/neonfuz">
                        <img alt="Github" src="/github.png"/>
                    </a>
            </div>
            <div style={tab('youtubePlaylistButton', tabId)}>
                <embed src="/youtube-playlist.svg" />
                <p>
                    This userscript adds a + button to many videos which quickly
                    opens the "Add to playlist" menu.
                </p>
                <a class="button" href="https://gist.github.com/neonfuz/ea14fe2ad32c4caa860f36bb521b9a60">
                    View code
                </a>
                <a class="button" href="https://gist.github.com/neonfuz/ea14fe2ad32c4caa860f36bb521b9a60/raw/youtube-quick-playlist.user.js">
                    Install
                </a>
            </div>
            <div style={tab('youtubeMiniplayerSidebar', tabId)}>
                <embed src="/youtube-miniplayer.svg" />
                <p>
                    This userstyle moves the youtube miniplayer into vacant
                    sidebar space while viewing playlists.
                </p>
                <p>
                    It also allows the playlist sidebar width to be configured.
                </p>
                <a class="button" href="https://gist.github.com/neonfuz/6d3790334983b87b638ddecf84d0ab09">
                    View code
                </a>
                <a class="button" href="https://gist.github.com/neonfuz/6d3790334983b87b638ddecf84d0ab09/raw/yt-miniplayer-in-playlist-sidebar.user.css">
                    Install
                </a>
            </div>
        </div>
    </div>
</main>

<style>
 header {
     position: fixed;
 }
 main {
     top: 0;
     position: absolute;
 }
 .preview {
     position: relative;
 }
 .preview > * {
     position: absolute;
     top: 0;
     transition: opacity .4s;
     opacity: 0;
 }
 embed {
     max-width: 100%;
     margin-top: 1rem;
 }
 :global(body) {
     margin: 0;
     height: 100%;
 }
</style>
