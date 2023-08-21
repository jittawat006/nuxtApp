<template>
    <Head>
        <Title>Product</Title>
    </Head>
        <div class="container" style="margin-top: 50px;">
            <div class="grid mb-5">
                <div class="content" v-for="product in Products" :key="product.id">
                    <div class="item w-100 h-100 rounded-1" style="border: 1px solid black;">
                        <div class="content p-3 " style="height: 90%;">
                            <img class="priceimg w-50" :src="product.image">
                            <h6 class="text-center mt-3">{{ product.title }}</h6>
                            <button @click="togglevisible"> {{ togglevisible? "ซ่อน" : "แสดง" }}รายละเอียด</button>
                            <div v-show="isvisible">
                                <p>คำอธิบาย : </p>
                                <p>{{ product.dis }}</p>
                                <p>{{ product.size }}</p>
                                <p>{{ product.price }}</p>
                            </div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
</template>
<script>
export default {
    data() {
        return {
            Products: [
                {
                    id: "1",
                    title: "[  URTHE // The Passion Fruit Sweater  ]",
                    image: "https://scontent-sin6-2.xx.fbcdn.net/v/t39.30808-6/366694893_714215500740779_1603501822141241618_n.jpg?_nc_cat=105&ccb=1-7&_nc_sid=730e14&_nc_ohc=pNYyZjifFlwAX9GwENf&_nc_ht=scontent-sin6-2.xx&oh=00_AfDb1L09Nok0w7Pn0JwYRKHPCm_TZLgxqSaJD0adR8b9aQ&oe=64E78B0F",
                    dis: 'เสื้อสเวตเตอร์ แขนยาว สกรีนลาย รุ่น The Passion Fruit SweaterColor : ดำ ขาว เทา',
                    size:'[ อก​ 46-48​ " / ยาว​ 29​ " ]',
                    price:'ราคา 590 บาท',
                },
                {
                    id: "2",
                    title: "[ URTHE // TEEN TROUBLES T-SHIRT ]",
                    image: "https://scontent-sin6-3.xx.fbcdn.net/v/t39.30808-6/367728478_714242740738055_6046620997016012607_n.jpg?_nc_cat=104&ccb=1-7&_nc_sid=730e14&_nc_ohc=YR88_VGB4qQAX-pk5Me&_nc_ht=scontent-sin6-3.xx&oh=00_AfDwGkwG8YPikUpsUBvO257u6NkXG5PgcZyT5bN9OZ4WeQ&oe=64E751F8",
                    dis: 'เสื้อยืด รุ่น I MISS YOU Size : UNISEX ',
                    size:'[ อก 40-42 " / ยาว 28 " ]',
                    price:'ราคา 490 บาท',

                },
                {
                    id: "3",
                    title: "[ URTHE // CARGO SKIRT ]",
                    image: "https://scontent.fbkk5-4.fna.fbcdn.net/v/t39.30808-6/368222471_714177777411218_7870605502533663184_n.jpg?stp=dst-jpg_p480x480&_nc_cat=103&ccb=1-7&_nc_sid=730e14&_nc_ohc=xDfbL8f0XZoAX8erqGi&_nc_ht=scontent.fbkk5-4.fna&oh=00_AfAWpHK0nkK_a5IMUFr8ncEyopL4XTBLlJ1SGHn-icVwVA&oe=64E85032",
                    dis: 'กระโปรงยาว คาร์โก้ รุ่น CARGO SKIRT ผลิตจากผ้าร่ม เนื้อผ้าเบา ใส่สบาย ทำมาแบบเอวยืด ใส่สบาย Color : ดำ ครีม เทา เขียว',
                    size:'[ อก​ 46-48​ " / ยาว​ 29​ " ]',
                    price:'ราคา 590 บาท',
                },
                {
                    id: "4",
                    title: "[ URTHE // DIGITAL TRANSFER ]",
                    image: "https://scontent.fbkk5-6.fna.fbcdn.net/v/t39.30808-6/366693654_713222294173433_2589907612497678225_n.jpg?stp=dst-jpg_p480x480&_nc_cat=101&ccb=1-7&_nc_sid=730e14&_nc_ohc=r0CKjMYW3ooAX9YNiFS&_nc_ht=scontent.fbkk5-6.fna&oh=00_AfCqspOM9GvkZcl5lpiDQJ_IcMzXp7mqi4jjXhmOPJbjhw&oe=64E6FEFA",
                    dis: '"เสื้อแขนสั้น พิมพ์ลายเต็มตัว รุ่น The Heaven Knows ผลิตจากผ้าจูติ',
                    size:'Oversized [ อก 46-48 " / ยาว 29 " ]',
                    price:'ราคา 290 บาท',
                },
            ],
            isvisible: false,
        }
    },
    methods: {
        togglevisible() {
            this.isvisible = !this.isvisible
        }
    }
}
</script>
<style scope>
.grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    column-gap: 16px;
    row-gap: 30px;
}
.priceimg {
    display: block;
    margin-left: auto;
    margin-right: auto;
    width: 50%;
}
</style>