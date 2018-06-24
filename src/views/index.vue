<template>
    <div>
        <img class="index" src="../assets/images/index.png">
        <div id="echarts" ref="echarts">

        </div>
    </div>
</template>
<script>
    import echarts from 'echarts';
    require('../assets/scss/CV.scss');
    require('../assets/scss/iconfont/iconfont.css');
    require('../assets/scss/github-markdown.css');

    export default {
        mounted() {

            setTimeout(() => {
                this.$router.push({
                    name: 'list'
                });
            }, 1000);

            this.drawLine();
        },
        methods: {
            drawLine(){
                // 基于准备好的dom，初始化echarts实例
                let myChart = echarts.init(this.$refs.echarts)
                // 绘制图表
                myChart.setOption({
                    title: { text: '在Vue中使用echarts' },
                    tooltip: {},
                    xAxis: {
                        data: ['衬衫','羊毛衫','雪纺衫','裤子','高跟鞋','袜子']
                    },
                    yAxis: {},
                    series: [{
                        name: '销量',
                        type: 'bar',
                        data: [5, 20, 36, 10, 10, 20]
                    }]
                });
            }
        }
    };
</script>
<style lang="scss">
    .index {
        width: 100%;
        background-color: #fff;
        margin-top: 40%;
    }
    #echarts{
        height: 640px;
        width: 100%;
        background: #eee;
    }
</style>
