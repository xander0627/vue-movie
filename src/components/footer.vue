<template>
    <footer class="footer">
        <ul class="footer_list">
            <router-link tag="li" v-for="item,index in footerList" to="" :key="index"
            :class="{active:activeIndex == index}" @click.native="changeActive(index,item.link)">
                <p class="title">{{item.title}}</p>
            </router-link>
        </ul>
    </footer>
</template>
<script>
    export default {
        name:'footerNav',
        data(){
            return {
                activeIndex:0,
                footerList:[
                    {
                        link:'index',
                        title:'首页'
                    },
                    {
                        link:'showing',
                        title:'正在热映'
                    },
                    {
                        link:'rankingList',
                        title:'最佳影片'
                    }
                ]
            }
        },
        methods: {
            changeActive(index,link){
                this.activeIndex = index
                this.$emit('changeView',link) 
            }
        }
    }
</script>
<style scoped>
    .footer{
        position: fixed;
        height: .98rem;
        background-color: #FFF;
        left: 0;
        right: 0;
        bottom: 0;
    }
    .footer_list{
        display: flex;
        height: 100%;
        justify-content:space-evenly;
        align-items: center;
    }
    .footer_list li{
        flex: 3;
        height: 100%;
        line-height: .98rem;
        text-align: center;
    }
    .footer_list li .title{
        color: #999;
    }
    .footer_list .active .title{
        color: #259faf;
    }
</style>
