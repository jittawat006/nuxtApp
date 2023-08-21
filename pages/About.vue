<template>
    <div class="container">
        <img :src="picture" :width="size" :height="size" />
        <form @submit.prevent="submitForm">
            กรอกชื่อเล่น <input type="text" ref="nicknameE1">
            <input type="submit" value="บันทึก">
        </form>
        <p>ชื่อ-นามสกุล : {{  getFullname() }}</p>
        <p>อายุ : {{ age }}</p>
        <button @click="toggleVisible"> {{ isVisible? "ซ่อน" : "แสดง" }}รายละเอียด</button>
        <div v-show="isVisible">
        <p>ที่อยู่ : <span v-html="address"></span></p>
        <p v-if="hobby.length === 0">ไม่มีงานอดิเรก</p>
        <div v-else>
            <p>งานอดิเรก :</p>
            <ul>
                <li v-for="item in hobby"> {{ item }} </li>
            </ul>
        </div>
        <p>ข้อมูลพื้นฐาน</p>
            <ul>
                <li>เพศ : {{ general.gender }}</li>
                <li>น้ำหนัก : {{ general.weight }}</li>
                <li>ส่วนสูง : {{ general.height }}</li>
                <li>โรคประจำตัว : {{ general.status }}</li>
            </ul>
        </div>
    </div>
</template>
<script>
    export default{
        data() {
            return {
                firstname : "jittawat ",
                lastname : "Wahanarat",
                age : 18,
                address : "<i>Chonburi</i>",
                picture : "https://rms.tatc.ac.th/files/importpicstd/01/66309010006.jpg",
                size : 150,
                hobby :["ฟังเพลง","ร้องเพลง","ทำงาน"],
                general : {gender:"ชาย",weight:63,height:175,status:false},
                isVisible: false,
            };
        },
        methods:{
            getFullname(){
                return `${this.firstname} ${this.lastname}`
            },
            toggleVisible(){
                this.isVisible = !this.isVisible
            },
            submitForm(){
                this.nickname = this.$refs.nicknameE1.value
            }
        },
    };
</script>
