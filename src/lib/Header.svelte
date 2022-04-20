<script>
 import Dropdown from '$lib/Dropdown.svelte';
</script>

<header>
    <h1>neonfuz.xyz</h1>
    <nav>
        <Dropdown>
            <div>My Work</div>
            <ul>
                <li>
                    <a href="#resume">
                        Resume
                    </a>
                </li>
                <li>
                    <a href="#github">
                        GitHub
                    </a>
                </li>
            </ul>
        </Dropdown>
        <Dropdown>
            <div>Youtube Improvements</div>
            <ul>
                <li>
                    <a href="#youtubePlaylistButton">
                        Quick Playlist Buttons
                    </a>
                </li>
                <li>
                    <a href="#youtubeMiniplayerSidebar">
                        MiniPlayer in SideBar
                    </a>
                </li>
            </ul>
        </Dropdown>
    </nav>
</header>

<style>
 header {
     position: fixed;
     z-index: 1;
     top: 0;
     left: 0;
     right: 0;
     height: 8rem;
     background: white;
     display: flex;
     flex-direction: row;
     justify-content: space-between;
     align-items: center;
     box-shadow: 0 0 10px #2222;
 }
 h1 {
     margin: 0;
 }
 nav > :global(*) {
     padding: .5em;
 }
 nav :global(ul) {
     background: white;
     box-shadow: 0 0 10px #2222;
     padding: 1em;
     right: 0;
 }
 h1 {
     font-size: 2.5rem;
 }
 @media (min-width: 40.0rem) {
     h1 {
         font-size: 4rem;
     }
 }
</style>
