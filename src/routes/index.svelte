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


<header>
    <h1>neonfuz.xyz</h1>
    <nav>
        <Dropdown>
            <header>Links</header>
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
            <header>Youtube Improvements</header>
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
        <div style={tab('resume', tabId)}>
            <h2>Resume</h2>
            <PDF
                title="Resume"
                src="https://neonfuz.github.io/resume/resume.html"
                href="https://neonfuz.github.io/resume/resume.pdf"
            />
        </div>
        <div style={tab('github', tabId)}>
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
        </div>
        <div style={tab('youtubePlaylistButton', tabId)}>
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
        </div>
        <div style={tab('youtubeMiniplayerSidebar', tabId)}>
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
        </div>
    </div>
</main>

<style>
 header {
     width: 100%;
     display: flex;
     flex-direction: row;
     justify-content: space-between;
     align-items: center;
 }
 header {
     padding: 1rem;
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
 .preview img {
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
 :global(body) {
     margin: 0;
     height: 100%;
 }
</style>
