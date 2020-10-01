<template>
    <div class="sampleProjectButton">
        <el-card :body-style="{padding: '0px'}">
            <img :src=img_src class="image">
            <div>
                <div class="title">
                    {{ title }}
                </div>
                <div class="content">
                    {{ this.getContent(id) }}
                </div>
                <div class="bottom clearfix">
                    <el-button class="button" type="success" @click="sendId(id)">Select</el-button>
                </div>
            </div>
        </el-card>
    </div>
</template>

<script>

    export default {
        data() {
            return {
                name: "SampleProjectButton",
                img_src: require("../assets/images/" + this.getId() + ".png")
            }
        },
        props: [
            'id',
            'title'
        ],
        methods: {
            getId: function(){
                return this.id;
            },
            getContent: function(id){
                switch (id) {
                    case '1-1':
                        return '今回はオセロのマス目を線で引く。コマをマウスプレスで置く。ところまで行ってみたいと思います。';

                    case '1-2':
                        return 'オセロのボードを配列で作ります。１に白いコマ、２に黒いコマが置ける様にします。';

                    case '1-3':
                        return 'コマが置かれるときに、対戦相手のコマをめくります。';

                    case '1-4':
                        return '対戦相手のコマがめくれない（挟まれない）位置に、自分のコマを置けない様にします。';

                    case '1-5':
                        return '対戦システムのボタンなどを実装します。';

                    default:
                        return 'UNDEF';
                }
            },
            getCode: function(id){
                switch (id) {
                    case '1-1':
                        return 'function setup() {\n' +
                            '  //描画領域の設定\n' +
                            '  createCanvas(400, 400);\n' +
                            '}\n' +
                            '\n' +
                            '// その後に繰り返し実行される処理\n' +
                            'function draw() {\n' +
                            '  \n' +
                            '}\n';

                    case '1-2':
                        return 'function setup() {\n' +
                            '  //描画領域の設定\n' +
                            '  createCanvas(400, 400);\n' +
                            '}\n' +
                            '\n' +
                            '// その後に繰り返し実行される処理\n' +
                            'function draw() {\n' +
                            '  \n' +
                            '}\n';

                    case '1-3':
                        return 'function setup() {\n' +
                            '  //描画領域の設定\n' +
                            '  createCanvas(400, 400);\n' +
                            '}\n' +
                            '\n' +
                            '// その後に繰り返し実行される処理\n' +
                            'function draw() {\n' +
                            '  \n' +
                            '}\n';

                    case '1-4':
                        return 'function setup() {\n' +
                            '  //描画領域の設定\n' +
                            '  createCanvas(400, 400);\n' +
                            '}\n' +
                            '\n' +
                            '// その後に繰り返し実行される処理\n' +
                            'function draw() {\n' +
                            '  \n' +
                            '}\n';

                    case '1-5':
                        return 'function setup() {\n' +
                            '  //描画領域の設定\n' +
                            '  createCanvas(400, 400);\n' +
                            '}\n' +
                            '\n' +
                            '// その後に繰り返し実行される処理\n' +
                            'function draw() {\n' +
                            '  \n' +
                            '}\n';

                    default:
                        return 'UNDEF';
                }

            },
            sendId: function(id){
                this.$emit('update-code', this.getCode(id));
            }
        },
    }
</script>

<style scoped>
    .title {
        font-size: 24px;
    }

    .bottom {
        margin-top: 13px;
        line-height: 12px;
    }

    .button {
        margin: 10px;
    }

    .image {
        width: 100%;
        display: block;
    }

    .clearfix:before,
    .clearfix:after {
        display: table;
        content: "";
    }

    .clearfix:after {
        clear: both
    }

</style>
