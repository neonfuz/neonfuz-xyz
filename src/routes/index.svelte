<script>
 import YouTubeIcon from '$lib/youtube-icon.svelte';
</script>

<div class="preview">
    <section id="resume">
        <h2>Resume</h2>
        <div class="row">
            <div class="column">
                <a class="button" href="https://neonfuz.github.io/resume/resume.pdf">
                    Download PDF
                </a>
            </div>
            <iframe
                title="resume"
                frameborder="0"
                src="https://neonfuz.github.io/resume/resume.pdf"
            />
        </div>
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
        <h2><YouTubeIcon /> Quick Playlist Button</h2>
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
        <h2><YouTubeIcon style="max-height: 1em;" /> MiniPlayer in SideBar</h2>
        <div class="row">
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
            <div class="column">
                <embed src="/youtube-miniplayer.svg" />
            </div>
        </div>
    </section>
</div>

<style>
 .preview {
     margin-top: 8rem;
     position: relative;
     text-align: center;
 }
 section {
     padding: 13vmin 0;
     border-bottom: solid #eee 2px;
 }
 section:first-child {
     margin-top: -5rem;
 }
 h2 {
     margin-bottom: 1.5em;
 }
 @media (min-width: 800px) {
     h2 {
         z-index: 3;
         pointer-events: none;
         position: sticky;
         top: 2.4rem;
     }
     section:nth-child(odd) .row {
         flex-direction: row-reverse;
     }
 }
 .row {
     align-items: center;
 }
 iframe {
     width: 100%;
     min-height: 50vh;
     box-shadow: 0 0 10px #2223;
     margin-bottom: 2rem;
     flex: 0 0 66.66%;
}
 img {
     padding: 1rem;
     box-shadow: 0 0 10px #2223;
 }
 embed {
     max-width: 100%;
     margin-top: 1rem;
 }
 .button {
     margin-bottom: 2rem;
 }
</style>
