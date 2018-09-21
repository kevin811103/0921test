<template>
    <div>

        <Button type="primary" v-on:click="openModal">打開 modal </Button>
        <Button type="primary" @click="openModal">打開 modal</Button>

        <div style="">

            <span v-for="(data,index) in goodList" v-bind:key="index">
                <div style='  display:inline-flex;  '>
                    <div style='  display:inline-flex;  '>

                        <div>
                            <img :src="data.pic" alt="" style="width:100px;height:100px;  align-content:center;">
                            <div>
                                {{data.name}}
                                <Button type="primary" shape="circle" icon="ios-search" @click="openModal(data)"></Button>
                            </div>
                        </div>
                    </div>

                </div>
            </span>

        </div>
        <Modal v-model="modalStatus">
            <div>
                名稱:{{showDetail.name}}
            </div>
            <div>
                價格: {{showDetail.price}}
            </div>

            <div slot="footer">
                <Button @click="closeModal"> 關閉</Button>
            </div>
        </Modal>
    </div>
</template>

<script>
import cupPic from '../assets/cup.jpg'
import kettle from '../assets/kettle.jpg'
export default {
    data(){
        return{
            modalStatus:false,
            goodList:[{name:'水壺',price:'199',pic:kettle},{name:'馬克杯',price:'250',pic:cupPic},{name:'水壺',price:'199',pic:kettle},{name:'馬克杯',price:'250',pic:cupPic},{name:'水壺',price:'199',pic:kettle},{name:'馬克杯',price:'250',pic:cupPic},{name:'水壺',price:'199',pic:kettle},{name:'馬克杯',price:'250',pic:cupPic},{name:'水壺',price:'199',pic:kettle},{name:'馬克杯',price:'250',pic:cupPic},{name:'水壺',price:'199',pic:kettle},{name:'馬克杯',price:'250',pic:cupPic},{name:'水壺',price:'199',pic:kettle},{name:'馬克杯',price:'250',pic:cupPic}],
            showDetail:''
        }
    },
    methods:{
        openModal(data){
            this.showDetail=data
            this.modalStatus=true;
        },
        closeModal(){
            this.modalStatus=false;
        }
    }

}
</script>

<style>
</style>
