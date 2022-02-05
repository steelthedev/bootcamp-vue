<template>
<section class="reg-page">
    <div class="container-fluid ">
      <div class="form-section">
        <div class="row ">
          <div class=" col-md-6 col-lg-5 img ">
            <div class="overlay"></div>
            <div class="img-s">
              <img src="../assets/hero_boot.jpeg" alt="" >
            </div>
          </div>
          <div class="col-md-6 col-lg-7 mt-5">
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
                      <select name="course" class="form-control" v-model="course">
                        <option value="">Select course</option>
                        <option value="Graphics">Graphics Design</option>
                        <option value="web">Web Development</option>
                      </select>
                  </div>
                  
               
                </div>
              
              </div>
               <button class="btn btn-outline-white s-btn" type="submit">Submit Form</button>
            </form>
            
          </div> 
        </div>
      </div>
    </div>
  </section>
</template>


<script>

import axios from 'axios'

export default {
  name: 'Home',
  components: {
   
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
                alert("Succesfully registred, check email for next step")
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
  padding: 60px;
  position: relative;
  font-family:'Open Sans', sans-serif;
}


.img-s img{
  width: 100%;
  height: 100%;
  
}

.overlay{
  background: #fabc37;
  position: absolute;
  width: 100%;
  height: 100%;
  z-index: 1000;
  opacity: .2;
}

.img{
position: relative;
height: 100vh;
}

.form-class{
  margin-top:50px;
}

.form-heading{
  color: #fabc37;
}

.form-heading h2{
  font-size: 3rem;
}

.form-group{
  padding: 15px;
  

}

.form-group .form-control {
  border-radius: 3px;
  border: none;
  box-shadow: none;
  background: transparent;
  border-bottom: 2px #FDB51A solid;
  border-bottom-left-radius: 0;
  border-bottom-right-radius: 0;
}


.s-btn{
  background: #FFAF02;
  padding: 10px;
  border-radius: 3px;
  transition:.2s;
  box-shadow: none;
  font-size: 1.2rem;
}

.s-btn:hover{
  background: #fabc37;
  transform: scale(1.1);
}

</style>
