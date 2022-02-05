
<script>


export default {
  name: 'Regform',
  props: {
    
  },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
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
