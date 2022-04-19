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
                    <a href="#youtubeMiniplayerSidebar">
                        MiniPlayer in SideBar
                    </a>
                </li>
                <li>
                    <a href="#youtubePlaylistButton">
                        Quick Playlist Buttons
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
     inset: 0;
     bottom: calc(100vh - 8rem);
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
     padding: 2rem;
 }
</style>
