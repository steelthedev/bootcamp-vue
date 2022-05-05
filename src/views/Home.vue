<template>
<Navbar />
<section class="reg-page">
    <div class="container">
      <div class="form-section">
        <div class="row ">
          <div class=" col-md-6 col-lg-5 img ">

            <div class="img-s">
              <img src="../assets/img/oat.jpg" width="100%" alt="" >
            </div>
          </div>
          <div class="col-md-6 col-lg-7">
            <div class="form-class">
              <div class="form-heading">
                <h2>
                Register for Bootcamp
              </h2>
              </div>
            </div>
            <form @submit.prevent="handleSubmit">
              <div class="row ">
                <div class="col-md-12 col-lg-12">
                  <div class="form-group">
                    <input type="text" name="full_name" placeholder="Input Full Name" v-model="full_name" class="form-control mt-3 ">
                  </div>

                  <div class="form-group">
                    <input type="text" name="phone_number" placeholder="Input Phone Number" v-model="phone_number" class="form-control mt-3 ">
                  </div>

                  <div class="form-group">
                    <input type="email" name="email" placeholder="Input Email" v-model="email" class="  form-control mt-3 ">
                  </div>

                   <div class="form-group">
                      <select name="course" class="form-control mt-3" v-model="course">
                        <option value="">Select course</option>
                        <option value="Graphics">Graphics Design</option>
                        <option value="web">Web Development</option>
                        <option value="crypto">Crypto Trading</option>
                      </select>
                  </div>
                  
               
                </div>
              
              </div>
               <button class="btn btn-outline-white s-btn" type="submit">Submit Form</button>
            </form>
            
          <div class="" v-if="errors">
            <p v-for="e in errors" key="e.id">

            </p>
          </div>

          </div> 
        </div>
      </div>
    </div>
  </section>
</template>


<script>
import axios from 'axios'
import Navbar from '@/components/Navbar.vue'
export default {
  name: 'Home',
  components: {
   Navbar
  },
  
  data(){
    return{
      course:'',
      full_name:'',
      email:'',
      phone_number:'',
      errors:[]
    }
  },
  methods:{
    handleSubmit(){
      this.errors= []
      if (this.course == '' ){
        this.errors.push("course cannot be empty")
      }
      if (this.full_name == '' ){
        this.errors.push("Name cannot be empty")
      }
      if (this.phone_number == '' ){
        this.errors.push("Number cannot be empty")
      }
      if (this.email == '' ){
        this.errors.push("Email cannot be empty")
      }
      if(!this.errors.length){
        const data = {
          email:this.email,
          course:this.course,
          phone_number:this.phone_number,
          full_name:this.full_name
        }
        
        axios
          .post('register/course', data )
          .then ( response => {
                
                window.location.href="https://paystack.shop/oathub"
          })
          .catch(error => {
                        if (error.response) {
                            for (const property in error.response.data) {
                                this.errors.push(`${property}: ${error.response.data[property]}`)
                            }
                            console.log(JSON.stringify(error.response.data))
                        } else if (error.message) {
                            this.errors.push('Something went wrong. Please try again')
                            
                            console.log(JSON.stringify(error))
                        }
                    })
      }
    }
  }
}
</script>

<style scoped>
.reg-page{
  padding: 40px 0;
  position: relative;
  font-family:'Open Sans', sans-serif;
}
.img-s img{
  width: 100%;
  height: 100%;
  
}
.overlay{
  background: #16283d;
  position: absolute;
  width: 100%;
  height: 100%;
  z-index: 1000;
  opacity: .2;
}

.form-class{
  margin-top:50px;
}
.form-heading{
  color: #16283d;
  font-family: 'Michroma', sans-serif;
}
.form-heading h2{
  font-size: 2.5rem;
  font-weight: 800;
}
.form-group{
  padding: 15px;
  
}
.form- {
  border-radius: 3px;
  border: none;
  box-shadow: none;
  background: transparent;
  border-bottom: 2px #16283d solid;
  border-bottom-left-radius: 0;
  border-bottom-right-radius: 0;
}

.form-group .form-control{
    border-radius: 10px;
    border: 1px solid #16283d;
    box-shadow: none;
    padding: 10px;
}

.s-btn{
  background: #16283d;
  padding: 10px;
  border-radius: 50px;
  transition:.2s;
  box-shadow: none;
  font-size: 1.2rem;
  color: #fff;
}
.s-btn:hover{
  background: #16283d;
  color:#fff;
  transform: scale(1.1);
}


@media screen and (max-width:768px) {
  .form-heading h2{
    font-size: 1.7rem;
}
}

@media screen and (max-width:450px) {
  .form-heading h2{
    font-size: 1.4rem;
}
  
}
</style>