<template>
    <div id="sampleProjectArea">
        <el-tabs :tab-position="tabPosition" style="height: 500px;">
            <el-tab-pane label="オセロを作ろう">
                <el-row :gutter="10" type="flex" justify="space-around">
                    <el-col :span="5">
                        <SampleProjectButton id="1-1" title="オセロ 一回目" @update-code="setCode"/>
                    </el-col>
                    <el-col :span="5">
                        <SampleProjectButton id="1-2" title="オセロ 二回目" @update-code="setCode"/>
                    </el-col>
                    <el-col :span="5">
                        <SampleProjectButton id="1-3" title="オセロ 三回目" @update-code="setCode"/>
                    </el-col>
                    <el-col :span="5">
                        <SampleProjectButton id="1-4" title="オセロ 四回目" @update-code="setCode"/>
                    </el-col>
                    <el-col :span="5">
                        <SampleProjectButton id="1-5" title="オセロ 五回目" @update-code="setCode"/>
                    </el-col>
                </el-row>
            </el-tab-pane>
        </el-tabs>
    </div>

</template>

<script>
    import SampleProjectButton from './SampleProjectCard'

    export default {
        data() {
            return {
                name: "SampleProjectArea",
                activeName: '1',
                tabPosition: 'left'
            }
        },
        methods: {
            setCode: function(code){
                this.$emit('set-code', code);
            }
        },
        components: {
            'SampleProjectButton': SampleProjectButton,
        },
    }
</script>

<style scoped>

</style>
