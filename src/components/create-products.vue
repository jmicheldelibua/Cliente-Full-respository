<template>
    <div>
       <div>
  

  <b-modal id="create_new_product" title="New Item" hide-footer>
    <div>
    <b-form @submit="onSubmit" @reset="onReset" v-if="show">
      <b-form-group
        id="input-group-1"
        label="Name"
        label-for="input-1"
        description="Name of the Item"
      >
        <b-form-input
          id="input-1"
          v-model="form.Name"
          type="text"
          required
          placeholder="Please, enter the Name Item"
        ></b-form-input>
      </b-form-group>

      <b-form-group id="input-group-2" label="InStock" label-for="input-2">
        <b-form-input
          id="input-2"
          v-model="form.InStock"
          required
          type="number"
          placeholder="Enter InStock"
        ></b-form-input>
      </b-form-group>

      <b-form-group id="input-group-2" label="Descripcion" label-for="input-2">
        <b-form-input
          id="input-2"
          v-model="form.Description"
          required
          placeholder="Enter the descripcion"
        ></b-form-input>
      </b-form-group>

      <b-form-group id="input-group-3" label="Item Category" label-for="input-3">
        <b-form-select
          id="input-3"
          v-model="form.CategoryId"
          :options="categories"
          required
        ></b-form-select>
      </b-form-group>

    <!--   <b-form-group id="input-group-4">
        <b-form-checkbox-group v-model="form.checked" id="checkboxes-4">
          <b-form-checkbox value="me">Check me out</b-form-checkbox>
          <b-form-checkbox value="that">Check that out</b-form-checkbox>
        </b-form-checkbox-group>
      </b-form-group> -->

      <b-button type="submit" variant="primary">Submit</b-button>
      <b-button type="reset" variant="danger">Reset</b-button>
    </b-form>
    <b-card class="mt-3" header="Form Data Result">
      <pre class="m-0">{{ form }}</pre>
    </b-card>
  </div>
  </b-modal>
</div> 
    </div>
</template>
<script>
  export default {
    data() {
      return {
        form: {
          Name: '',
          Description: '',
          CategoryId: null,
          InStock: 0
        },
        categories: [{ text: 'Category 5', value: 5 }, { text: 'Category 6', value: 6 }],
        show: true
      }
    },
    methods: {
      onSubmit(evt) {
        evt.preventDefault()
        alert(JSON.stringify(this.form))
      },
      onReset(evt) {
        evt.preventDefault()
        // Reset our form values
        this.form.email = ''
        this.form.name = ''
        this.form.food = null
        this.form.checked = []
        // Trick to reset/clear native browser form validation state
        this.show = false
        this.$nextTick(() => {
          this.show = true
        })
      }
    }
  }
</script>