<template>
  <div class="UserTestimonials">
    <div class="container">
          <h1>Sweet Testimonials</h1>
    <div class="testimonial-container">
                <div class="row">
    <div v-for="list in testimonialList" class="col-md-6">  
        <div  class="testimonial-box">
        <p>{{ list.name }} - {{ list.position }}</p>
        <p>{{ list.desc }}</p>
        </div>
    </div>
      </div>
    </div>

  <div class="basicform">
    <h3>Leave us a Testimonials</h3>
    <!-- main form for testimonials -->
<el-form :model="ruleForm" :rules="rules" ref="ruleForm" class="demo-ruleForm" show="openDialog === false">
     <!-- name text area for users to input -->
  <el-form-item prop="name" class="together"> <el-input v-model="ruleForm.name" placeholder="Mia Welsh"></el-input> </el-form-item>
     <!-- position text area for users to input -->
  <el-form-item prop="position" class="together"> <el-input v-model="ruleForm.position" placeholder="Chef"></el-input> </el-form-item>
     <!-- comment text area for users to input -->
  <el-form-item prop="desc"> <el-input type="textarea" v-model="ruleForm.desc" placeholder="Any tasty comments?"></el-input>  </el-form-item>
    <!-- submit button for users once completed filling out the forms -->
  <el-button type="primary" @click="submitForm('ruleForm')">Submit</el-button>

</el-form>

  </div>
</div>
  </div>
</template>

<script>
import axios from 'axios'
export default {
  data: function() {
    // Name and Position limit of 50 words
    var wordCount = (rule, value, callback) => {
      if (value.split(' ').length >= 50) {
        callback(new Error('Oh ho! This is too sweet, subject can not be more than 50 words'));
      } else {
        callback();
      }
    };
    // Comment section limit of 120 words
    var wordCount2 = (rule, value, callback) => {
      if (value.split(' ').length >= 120) {
        callback(new Error('Too much sugar, subject can not be more than 120 words'));
      } else {
        callback();
      }
    };
    return {
      testimonialList: [],
      ruleForm: {
        name: "",
        position: "",
        desc: ""
      },
      // important message that will display for each text box if it's empty
        rules: {
          name: [
            { required: true, message: 'This is quite a jawbreaker, please input name!', trigger: 'blur' },
          {
            validator: wordCount,
            trigger: "blur"
          }
          ],
          position: [
            { required: true, message: 'What a sugary problem, please input position!', trigger: 'blur' },
          {
            validator: wordCount,
            trigger: "blur"
          }
          ],
          desc: [
            { required: true, message: 'Your fondant needs more attention, please input comment!', trigger: 'blur' },
          {
            validator: wordCount2,
            trigger: "blur"
          }
          ]
        },
      };
    },
    // databse with axios
  methods: {
    submitForm(formName) {
      this.$refs[formName].validate(valid => {
        if (valid) {
          const obj = {
            'name' : this.ruleForm.name,
            'position' : this.ruleForm.position,
            'desc' : this.ruleForm.desc,
          };
          this.testimonialList.push(obj);
          axios.put("https://agan0003-midterm-vue.firebaseio.com/data.json", this.testimonialList);
      } else {
        return false;
      }
      });
    }
  },
      created() {
    axios
    .get("https://agan0003-midterm-vue.firebaseio.com/data.json")
    .then(response => {
      console.log(response.data);
      if(response.data)this.testimonialList = response.data;
    })
    .catch(error => {
      console.log("Your baking has an error in getting data: " + error.response);
    });
  }

};
</script>

<style>
.UserTestimonials {
  display: flex;
    flex-wrap: wrap;
    flex: 50%;
}

  .dialog-container {
    display: flex;
    margin: auto 20px;
    text-align: left;
  }

  .testimonial-box {
    background-color: #F99A9C;
    padding: 75px;
    margin: 10px;
    border: 10px solid #BB5769;
    color: white;
  }

  .testimonial-container {
    display: flex;
    flex-wrap: wrap;
    margin-bottom: 20px;
    width: 100%;
  }

h1 {
  text-align: left;
}
h3 {
  display: flex;
}
.col-6 {
  border: 1pt solid black;
  padding: 55px;
  margin: 25px;
}

.row {
  flex: 100%;
}
  .row .col-6 {
  flex: 100%;
  }
.el-button {
  float: right;
}
.basicform {
  margin-top: 10px;
  padding: 20px;
}
.together {
  width: calc(50% - 10px) !important;
  display: inline-block;
}
.together:first-child {
  margin-right: 20px;
}
  .el-button--primary {
    float: right;
    margin-bottom: 150px !important;
  }
</style>
