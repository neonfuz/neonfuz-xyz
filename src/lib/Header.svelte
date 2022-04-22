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
            <div>Youtube Addons</div>
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
     background: white;
     display: flex;
     flex-direction: row;
     justify-content: space-between;
     align-items: center;
     box-shadow: 0 0 10px #2223;
     padding: 1rem;
 }
 h1 {
     margin: 0;
     font-size: 2.5rem;
 }
 nav > :global(*) {
     padding: .5em;
 }
 nav :global(ul) {
     background: white;
     box-shadow: 0 5px 10px -4px #2223;
     border: solid #eee 1px;
     padding: 0 1.2rem;
     right: 0;
 }
 nav :global(li) {
     list-style: none;
     margin: 0;
     padding: .6em 0;
 }
 nav :global(li:not(:first-child)) {
     border-top: solid #eee 1px;
 }
 nav {
     display: flex;
     align-items: center;
 }
 nav > :global(div) > :global(div){
     max-width: 8rem;
     text-align: center;
 }
 @media (min-width: 40.0rem) {
     h1 {
         font-size: 4rem;
     }
 }
</style>
