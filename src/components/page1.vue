<script setup>
import { ref } from 'vue'
</script>



<template>
  
  <div class="container text-center" style="margin-bottom: 40px;">
    <form action="">
    <div class="row row-cols-2 ">
      <div class="col mb-4">
        <div class="card" style="width: 100%;">
          <img src="/src/assets/goboriT.png" class="card-img-top" alt="goboriT">
          <div class="card-body">
            <h5 class="card-title">โกโบริ</h5>
            <p class="card-text">ร้านหมูกระทะที่มีเมนูให้ได้เลือกหลากหลาย รวมไปถึงของสดแต่ละอย่าง สะอาด สดใหม่ทุกวัน มีเมนูหมูหมักให้เลือกเพียบ! รวมถึงเมนูพร้อมทานอื่นๆ และของหวาน</p>
            <hr>
            <div class="container">
              <div class="row">
                <div class="input-group mb-3" style="width: 60%; margin-left: 20%;">
                  <span class="input-group-text" id="basic-addon1">จำนวนโต๊ะ</span>
                  <input id="gobori" type="number" min="0" class="form-control" placeholder="ระบุจำนวนโต๊ะ">
                  
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
      <div class="col">
        <div class="card" style="width: 100%;">
          <img src="/src/assets/grillterminalT.png" class="card-img-top" alt="grillterminalT">
          <div class="card-body">
            <h5 class="card-title">Grill Terminal</h5>
            <p class="card-text">ร้านหมูกระทะสุดคุ้ม ที่ไม่ได้มีแค่หมูกระทะ แต่ยังมีคาราวานซีฟู้ด ไว้คอยให้บริการอีกด้วย ราคาค่อนข้างย่อมเยา</p>
            <hr>
            <div class="container">
              <div class="row">
                <div class="input-group mb-3" style="width: 60%; margin-left: 20%;">
                  <span class="input-group-text" id="basic-addon1">จำนวนโต๊ะ</span>
                  <input id="grillterminal" type="number" min="0" class="form-control" placeholder="ระบุจำนวนโต๊ะ">
                  
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
      <div class="col">
        <div class="card" style="width: 100%; height: 100%;">
          <img src="/src/assets/lukjumT.png" class="card-img-top" alt="lukjumT">
          <div class="card-body">
            <h5 class="card-title">ลักจุ่ม มุมตึก</h5>
            <p class="card-text">บุฟเฟ่ต์หมูกระทะ อิ่มไม่อั้นในราคาดี ๆ รวมเครื่องดื่ม มีทั้งหมู ไก่ เนื้อ ซีฟู้ด และผักสด รวมถึงเมนูเนื้อหมักสูตรเด็ดของทางร้าน</p>
            <hr>
            <div class="container">
              <div class="row">
                <div class="input-group mb-3" style="width: 60%; margin-left: 20%;">
                  <span class="input-group-text" id="basic-addon1">จำนวนโต๊ะ</span>
                  <input id="lukjum" type="number" min="0" class="form-control" placeholder="ระบุจำนวนโต๊ะ">
                  
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
      <div class="col">
        <div class="card" style="width: 100%;">
          <img src="/src/assets/miangdongT.png" class="card-img-top" alt="miangdongT">
          <div class="card-body">
            <h5 class="card-title">เมียงดง Korean BBQ</h5>
            <p class="card-text">ร้านบุฟเฟ่ต์หมูกระทะในเชียงใหม่ แต่มาในสไตล์เกาหลี สายเกาต้องไปโดน ทั้งสไตล์อาหาร เครื่องเคียง รวมถึงเพลงที่เปิดเป็นสไตล์เกาหลี ส่วนเมนูอาหารก็มีให้เลือกเยอะแยะมากมาย</p>
            <hr>
            <div class="container">
              <div class="row">
                <div class="input-group mb-3" style="width: 60%; margin-left: 20%;">
                  <span class="input-group-text" id="basic-addon1">จำนวนโต๊ะ</span>
                  <input id="miangdong" type="number" min="0" class="form-control" placeholder="ระบุจำนวนโต๊ะ">
                  
                </div>
              </div>
            </div>
          </div>
        </div>
      </div>
    </div>
    <br>
    <button id="submitbooking" type="button" class="btn btn-warning" @click="handleBooking" style="color: rgb(255, 255, 255); font-size: 20px;">ตรวจสอบรายการ</button>
    </form>
  </div>


  <div class="tablelistframecon">
    <div class="tablelistframe" v-if="bookingData.length > 0">
      <h4>รายการจองโต๊ะ</h4>
      <div class="tablebigcon">
        <div class="containertable" >
          <table class="table table-striped table-hover ">
            <thead>
              <tr>
                <th>#</th>
                <th>ชื่อร้าน</th>
                <th>จำนวนโต๊ะ</th>
              </tr>
            </thead>
            <tbody>
              <tr v-for="(item, index) in bookingData" :key="index">
                <td>{{ index + 1 }}</td>
                <td>{{ Object.keys(item)[0] }}</td>
                <td>{{ Object.values(item)[0] }}</td>
              </tr>
            </tbody>
          </table>
        </div>
    </div>
    </div>
</div>

  
    <div class="formconcon">
      <div class="formcon">
        <form action="" @submit.prevent="handleSubmit">
          <h4>รายละเอียดผู้จอง</h4>
          <div class="input-group mb-3">
            <span class="input-group-text" id="basic-addon1" >ชื่อผู้จอง</span>
            <input id="name" v-model="formData.name" type="text" class="form-control" placeholder="ชื่อผู้จอง" aria-label="Username" aria-describedby="basic-addon1" required>
          </div>
          <div class="row">
            <div class="col">
              <div class="input-group mb-3">
                <span class="input-group-text" id="basic-addon1" >เบอร์โทรศัพท์</span>
                <input id="num" v-model="formData.num" class="form-control" type="text" pattern="[0-9]{10}" maxlength="10"  placeholder="กรอกเบอร์โทรศัพท์(10หลัก)" aria-label="tel" aria-describedby="basic-addon1" required>
              </div>
            </div>
            <div class="col">
              <div class="input-group mb-3">
                <span class="input-group-text" id="basic-addon1" >วันที่และเวลา</span>
                <input id="datetime" v-model="formData.datetime" :min="minDate" type="datetime-local" class="form-control"  aria-label="Datetime" aria-describedby="basic-addon1" required>
              </div>
            </div>
          </div>
          
          <button  v-if="bookingResult.length <=0" type="submit" class="btn btn-warning"  style="color: rgb(255, 255, 255); font-size: 20px;">ยืนยันการจองโต๊ะ</button>
        </form>
        <form action="">
          <p v-if="bookingData.length <= 0" style="color: red;">กรุณาเลือกโต๊ะ</p>
          <div v-if="bookingResult.length > 0" class="bookingInfocon" >
            <br>
            <button  type="button" class="btn btn-primary" data-bs-toggle="modal" data-bs-target="#staticBackdrop" style="color: rgb(255, 255, 255); font-size: 20px; margin-right: 2%;">
                รายละเอียดการจอง
            </button>
            <button type="submit" @click="resetField" class="btn btn-danger" style="color: rgb(255, 255, 255); font-size: 20px; margin-left: 2%;">ล้างข้อมูล</button>
          </div>
        </form>
      </div>
    </div>


  <div class="mdcon" v-if="bookingResult.length > 0">  
    <div class="modal fade" id="staticBackdrop" data-bs-backdrop="static" data-bs-keyboard="false" tabindex="-1" aria-labelledby="staticBackdropLabel" aria-hidden="true">
      <div class="modal-dialog">
        <div class="modal-content">
          <div class="modal-header">
            <h1 class="modal-title fs-3" id="staticBackdropLabel" style="background-color: rgb(255, 202, 44); width: 100%; padding: 15px; border-radius: 20px;">รายละเอียดการจอง</h1>
            <button type="button" class="btn-close" data-bs-dismiss="modal" aria-label="Close"></button>
          </div>
          <div class="modal-body">
            <h5>ชื่อผู้จอง : {{ formData.name }}</h5>
            <h5>เบอร์โทรศัพท์ : {{ formData.num }}</h5>
            <h5>วันที่ : {{ date }}</h5>
            <h5>เวลา : {{ time }}</h5><br>
            <h5>ร้าน/จำนวนโต๊ะที่จอง : </h5>
            <ul style="list-style: none; font-size: 18px; margin-left: -5%;">
              <li v-for="(item, index) in bookingResult" :key="index">
                {{ Object.keys(item)[0] }}: {{ Object.values(item)[0] }} โต๊ะ
              </li>
            </ul>
            <br>
            <p style="color: rgb(150, 0, 0);">*หากต้องการเพิ่ม/ลดจำนวนโต๊ะ กรุณาล้างข้อมูลและจองใหม่อีกครั้ง</p>
          </div>
          <div class="modal-footer">
            <button type="button" class="btn btn-secondary" data-bs-dismiss="modal">Close</button>
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
      goboriTable: 0,
      grillterminalTable: 0,
      lukjumTable: 0,
      miangdongTable: 0,
      bookingData: [],
      bookingResult: [],
      formData: {
        name: '',
        num: '',
        datetime: '',},
    };
  },

  computed: {
    minDate() {
      const now = new Date();
      const year = now.getFullYear();
      const month = String(now.getMonth() + 1).padStart(2, '0');
      const day = String(now.getDate()).padStart(2, '0');
      const hours = String(now.getHours()).padStart(2, '0');
      const minutes = String(now.getMinutes()).padStart(2, '0');
      
      return `${year}-${month}-${day}T${hours}:${minutes}`;
    },
    date() {
      if (this.formData.datetime) {
        const dateTimeParts = this.formData.datetime.split('T');
        return dateTimeParts[0];
      }
      return '';
    },
    time() {
      if (this.formData.datetime) {
        const dateTimeParts = this.formData.datetime.split('T');
        return dateTimeParts[1];
      }
      return '';
    },
  },
  methods: {

    handleBooking() {
    const goboriTableValue = document.getElementById('gobori').value;
    const grillterminalTableValue = document.getElementById('grillterminal').value;
    const lukjumTableValue = document.getElementById('lukjum').value;
    const miangdongTableValue = document.getElementById('miangdong').value;

    this.goboriTable = parseInt(goboriTableValue);
    this.grillterminalTable = parseInt(grillterminalTableValue);
    this.lukjumTable = parseInt(lukjumTableValue);
    this.miangdongTable = parseInt(miangdongTableValue);

    this.bookingData = [];

    if (this.goboriTable > 0) {
      this.bookingData.push({ 'โกโบริ ': this.goboriTable });
    }
    if (this.grillterminalTable > 0) {
      this.bookingData.push({ 'Grill Terminal ': this.grillterminalTable });
    }
    if (this.lukjumTable > 0) {
      this.bookingData.push({ 'ลักจุ่ม มุมตึก ': this.lukjumTable });
    }
    if (this.miangdongTable > 0) {
      this.bookingData.push({ 'เมียงดง Korean BBQ ': this.miangdongTable });
    }
  },



  handleSubmit() {
    if (this.bookingData.length <= 0) {
      alert('กรุณาเลือกโต๊ะ');
      return; 
    }
  
    this.bookingResult = [];

    if (this.goboriTable > 0) {
      this.bookingResult.push({ 'โกโบริ ': this.goboriTable });
    }
    if (this.grillterminalTable > 0) {
      this.bookingResult.push({ 'Grill Terminal ': this.grillterminalTable });
    }
    if (this.lukjumTable > 0) {
      this.bookingResult.push({ 'ลักจุ่ม มุมตึก ': this.lukjumTable });
    }
    if (this.miangdongTable > 0) {
      this.bookingResult.push({ 'เมียงดง Korean BBQ ': this.miangdongTable });
    }


      setTimeout(() => {
      
        alert('จองโต๊ะสำเร็จ!');
      }, 200); 
    }
  },

  resetField() {
      document.getElementById('gobori').value = '';
      document.getElementById('grillterminal').value = '';
      document.getElementById('lukjum').value = '';
      document.getElementById('miangdong').value = '';
      document.getElementById('name').value = '';
      document.getElementById('num').value = '';
      document.getElementById('datetime').value = '';
      this.bookingData = [];
      this.bookingResult = [];
  },

}
</script>


<style>
body{
  background-color: rgb(63, 63, 63);
  margin: 0%;
  padding: 0%;
}

.tablelistframecon{
  text-align: center;
  display: flexbox;
  width: 100%;
  margin-bottom: 2%;
}

.tablelistframe{
  padding: 2%;
  border-radius: 20px;
  background-color: white;
  margin: auto;
  width: 50%;
}

.containertable{
  border: 2px solid rgb(235, 235, 235);
}

table{
  padding: 0%;
  margin: 0%;
  
}

.custom-table  {
  padding: 8px; 
  text-align: left;
  border: 1px solid #ddd;
}

.formconcon{
  width: 100%;
  display: flexbox;
}

.formcon{
  padding: 1.5%;
  border-radius: 20px;
  background-color: rgb(255, 255, 255);
  text-align: center;
  margin: auto;
  width: 50%;
}

.numtable{
  margin-top: 2%;
}
</style>