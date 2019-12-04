<template>
    <div id="footer">
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
                'M 0,200',
                'C 0,200 360,30 720,100',
                'C 1080,180 1440,0 1440,0',
                'L 1440,200',
                'Z'
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

    #footer {
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