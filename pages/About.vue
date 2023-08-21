<template>
    <div>
        <img :src="picture" :width="size" :height="size">
        <p></p>
        <form @submit="submitForm">
            <label for=""></label>
            <input type="text" @input="setNickname">
            <button type="submit">บันทึก</button>
        </form>
        <p></p>
        <p>ชื่อ : {{  firstname }}</p>
        <p>นามสกุล : {{  lastname }}</p>
        <p>ชื่อเล่น : {{ Nickname }}</p>
        <p>อายุ : {{  age }}</p>
        <p>ที่อยู่ : <span v-html="address"></span></p>
        <p v-if="hobby.length ===0">ไม่มีงานอดิเรก</p>
        <div v-else>
            <p>งานอดิเรก :</p>
            <ul>
                <li v-for="item in hobby"> {{ item }} </li>
            </ul>
        </div>
        <p>ข้อมูลพื้นฐาน</p>
            <ul>
                <li v-for="(value,key) in general">{{ key }} : {{ value }}</li>
            </ul>
            <button @click="showdata">คลิกเพื่อดูข้อมูล</button>
            <button @click="increment(10)">เพิ่มค่า</button>
            <button @click="decrement(3)">ลดค่า</button>
    </div>
</template>
<script>
    export default{
        data() {
            return {
                firstname : "jittawat ",
                lastname : "Wahanarat",
                Nickname : "เพลง",
                age : 18,
                address : "<i>Chonburi</i>",
                picture : "https://rms.tatc.ac.th/files/importpicstd/01/66309010006.jpg",
                size : 150,
                hobby :["ฟังเพลง","ร้องเพลง"],
                general : {gender:"ชาย",weight:63,height:175,status:false}
            }
        },
        methods:{
            getFullname(){
                return `$(this.firstname) $(this.lastname)`
            },
            showdata(){
                alert(this.firstname)
            },
            increment(value){
                this.age += value
            },
            decrement(value){
                this.age -= value
            },
            setNickname(event){
                this.Nickname=event.target.value
            },
            submitForm(e){
                e.preventDefault();
                alert('บันทึกข้อมูลเรียบร้อย')
            }
        }
    }
</script>
