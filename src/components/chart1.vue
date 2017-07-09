<style>
#main {
    /*需要制定具体高度，以px为单位*/
    height: 400px;
}
</style>
<template>
   <div id="charts">
    <div id="main"  :style="{width:'600px',height:'400px'}"></div>
    <div class="pie" id="pie" :style="{width:'400px',height:'400px'}"></div>
</div>
</template>
<script>
import echarts from "echarts"
export default{
        data (){
            return {
                msg:"123"
            }
        },
        mounted (){
            var myChart = echarts.init(document.getElementById('main'));
            // 指定图表的配置项和数据
            var option = {
                title: {
                    text: 'ECharts 入门示例'
                },
                tooltip: {},
                legend: {
                    data:['销量']
                },
                xAxis: {
                    data: ["衬衫","羊毛衫","雪纺衫","裤子","高跟鞋","袜子"]
                },
                yAxis: {},
                series: [{
                    name: '销量',
                    type: 'bar',
                    data: [1, 20, 36, 10, 10, 20]
                }]
            };
            // 使用刚指定的配置项和数据显示图表。
            myChart.setOption(option);

            //饼图
            var pieChart = echarts.init(document.getElementById('pie'));
            pieChart.setOption({
                series : [
                    {
                        name: '访问来源',
                        type: 'pie',
                        radius: '55%',
                        data:[
                            {value:235, name:'视频广告:235'},
                            {value:274, name:'联盟广告'},
                            {value:310, name:'邮件营销'},
                            {value:335, name:'直接访问'},
                            {value:400, name:'搜索引擎'}
                        ]
                    }
                ]
            })



        }

    }
</script>