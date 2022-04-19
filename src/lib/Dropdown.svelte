<div>
    <slot></slot>
</div>

<style lang="less">
 div {
     display: inline-block;
     position: relative;
 }
 div > :global(*:not(:first-child)) {
     display: none;
     position: absolute;
     z-index: 1;
 }
 div:hover > :global(*:not(:first-child)) {
     display: block;
 }

</style>
