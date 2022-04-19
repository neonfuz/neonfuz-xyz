<script>
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
     return tabId === name ? 1 : 0;
 }
</script>

<header class="container">
    <h1>neonfuz.xyz</h1>
</header>

<main class="container">
    <div class="row">
        <div class="column">
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
        </div>
        <div class="column preview">
            <div style:opacity={tab('resume', tabId)}
                               style:width="100%">
                <div class="pdf-wrap">
                    <a href="https://neonfuz.github.io/resume/resume.pdf"></a>
                    <iframe
                        title="resume"
                        frameborder="0"
                        src="https://neonfuz.github.io/resume/resume.pdf" />
                </div>
            </div>
            <div style:opacity={tab('github', tabId)}>
                <img alt="Github" src="/github.png"/>
            </div>
            <div style:opacity={tab('youtubePlaylistButton', tabId)}>
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
            <div style:opacity={tab('youtubeMiniplayerSidebar', tabId)}>
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
 .preview {
     position: relative;
 }
 .preview > * {
     position: absolute;
     top: 0;
     transition: opacity .4s;
 }
 .pdf-wrap {
     display: block;
     position: relative;
     padding-bottom: 129.41%;
 }
 .pdf-wrap a {
     display: block;
     position: absolute;
     inset: 0;
     z-index: 1;
 }
 iframe {
     position: absolute;
     width: 100%;
     height: 100%;
 }
 embed {
     max-width: 100%;
 }
</style>
