<template>
  <div>
    <pre>
      {{ JSON.stringify(formValues, null, 2) }}
    </pre>
  </div>
    <form>
      <div>
        <label for="name">Name</label>
        <input type="text" id="name" v-model="formValues.name"/>
      </div>

      <div>
        <label for="profile">Profile Summary</label>
        <textarea id="profile" v-model="formValues.profileSummary" />
      </div>

      <div>
        <label for="country">Country</label>
        <select id="country" v-model="formValues.country">
          <option value="">Select a country</option>
          <option value="india">India</option>
          <option value="canada">Canada</option>
          <option value="america">America</option>
        </select>
      </div>

      <div>
        <label for="job-location">Job Location</label>
        <select id="job-location" multiple v-model="formValues.jobLocation">
          <option value="">Select a Job Location</option>
          <option value="india">India</option>
          <option value="canada">Canada</option>
          <option value="america">America</option>
        </select>
      </div>
    </form>
</template>
  
  <script>
  export default {
    name: 'vueForm',
    data(){
      return{
        formValues:{
          name: '',
          profileSummary: '',
          country: '',
          jobLocation: []
        }
      }
    }
  }
  </script>
  
  <style>
  
  </style>
  