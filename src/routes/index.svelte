<script>
 import PDF from '$lib/PDF.svelte';
 import Dropdown from '$lib/Dropdown.svelte';
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
         const elem = document.getElementById(content);
         if (elem) {
             console.log(elem.scrollTop);
             window.scrollTo(0, elem.scrollHeight - 80);
         }
     }
     node.addEventListener('mouseenter', onHover);
     return {
         destroy() {
             node.removeEventListener('mouseenter', onHover);
         }
     }
 }
</script>


<header>
    <h1>neonfuz.xyz</h1>
    <nav>
        <Dropdown>
            <div>My Work</div>
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
                        GitHub
                    </a>
                </li>
            </ul>
        </Dropdown>
        <Dropdown>
            <div>Youtube Improvements</div>
            <ul>
                {#each foo as {name, href, id}}
                    <li>
                        <a href={href} use:preview={id}>
                            {name}
                        </a>
                    </li>
                {/each}
            </ul>
        </Dropdown>
    </nav>
</header>

<main class="container">
    <div class="preview">
        <section id="resume">
            <h2>Resume</h2>
            <p>
                You can download my resume
                <a href="https://neonfuz.github.io/resume/resume.pdf">HERE</a>.
            </p>
        </section>
        <section id="github">
            <h2>GitHub</h2>
            <div class="row">
                <div class="column">
                    <p>Most of my open source code is available on my GitHub</p>
                    <a class="button" href="https://github.com/neonfuz">Visit</a>
                </div>
                <div class="column">
                    <a href="https://github.com/neonfuz">
                        <img alt="GitHub" src="/github.png"/>
                    </a>
                </div>
            </div>
        </section>
        <section id="youtubePlaylistButton">
            <h2>YouTube Quick Playlist Button</h2>
            <div class="row">
                <div class="column">
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
                <div class="column">
                    <embed src="/youtube-playlist.svg" />
                </div>
            </div>
        </section>
        <section id="youtubeMiniplayerSidebar">
            <h2>YouTube MiniPlayer in SideBar</h2>
            <div class="row">
                <div class="column">
                    <embed src="/youtube-miniplayer.svg" />
                </div>
                <div class="column">
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
        </section>
    </div>
</main>

<style>
 header {
     position: fixed;
     z-index: 1;
     inset: 0;
     bottom: calc(100vh - 8rem);
     background: white;
     display: flex;
     flex-direction: row;
     justify-content: space-between;
     align-items: center;
 }
 nav > :global(*) {
     padding: 1rem;
 }
 .preview {
     margin-top: 8rem;
     position: relative;
 }
 .preview section {
     margin-top: 20vh;
     padding-top: 8rem;
     margin-bottom: 20vh;
 }
 .preview img {
     padding: 1rem;
     box-shadow: 0 0 10px #2222;
 }
 .preview .row {
     align-items: center;
 }
 .preview {
     text-align: center;
 }
 embed {
     max-width: 100%;
     margin-top: 1rem;
 }
</style>
