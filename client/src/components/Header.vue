<template>
    <div id="header">
        <svg :viewBox="viewBox" version="1.1">
            <path :d="pathData" />
        </svg>
    </div>
</template>

<script lang="ts">

    import { Component, Vue } from 'vue-property-decorator';

    @Component
    export default class Header extends Vue {
        pathData: string;
        viewBox: string;

        constructor() {
            super();
            this.pathData = '';
            this.viewBox = '';
        }

        getPathData() {
            const data = [
                'M 0,0',
                'L 0,200',
                'C 360,20 720,100 720,100',
                'C 1080,180 1440,0 1440,0',
                'Z',
            ];

            return data.join( ' ' );
        }

        created() {
            this.pathData = this.getPathData();
            this.viewBox = '0 0 1440 200';
        }
    }

</script>

<style lang="scss" scoped>

    #header {
        svg {
            position: relative;
            width: 100%;
            left: 0;
            display: block;
            path {
                stroke: #1f1f1f;
                fill: #62727b;
            }
        }
    }

</style>