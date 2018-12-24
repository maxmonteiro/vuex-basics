<template>
  <div id="app">
    <div class="container-fluid col-md-8">
      <div class="row">
        <div class="col-md-6">
          <app-registration class="float-right"></app-registration>
        </div>
        <div class="col-md-6">
          <app-registrations></app-registrations>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
import Registration from "./components/Registration.vue";
import Registrations from "./components/Registrations.vue";
export default {
  components: {
    appRegistration: Registration,
    appRegistrations: Registrations
  }
};
</script>

