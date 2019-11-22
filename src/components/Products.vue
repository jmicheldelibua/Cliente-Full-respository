<template>
    <div>
  <b-card
    no-body
    style="max-width: 20rem;"
    img-src="https://placekitten.com/380/200"
    img-alt="Image"
    img-top
  >
    <template v-slot:header>
      <h4 class="mb-0">Item Name</h4>
    </template>

    <b-card-body>
     
      <b-card-sub-title class="mb-2"></b-card-sub-title>
      <b-card-text>
        It is the Item description 
      </b-card-text>
    </b-card-body>

    

    <b-card-body>

      <a href="#" class="card-link">Item category Name</a>
    </b-card-body>

    <b-card-footer>Actions
      <b-button variant="warning" size="sm" class="mr-2">Edict</b-button>
      <b-button variant="danger" size="sm">Delete</b-button>
    </b-card-footer>

  
  </b-card>
</div>
</template>