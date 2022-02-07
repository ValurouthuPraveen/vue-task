<template>
  <div>
    <p>About Page</p>
    <modal-component :patientData="patientData"></modal-component>
  </div>
</template>

<script>
import ModalComponent from "../components/ModalComponent.vue";

export default {
  name: "About",
  components: {
    ModalComponent,
  },
  data() {
    return {
      patientData: {
        internalAccessionNo: "230456899",
        // caseNumber: "",
        patient: {
          address1: "77 Washington Avenue",
          city: "New York City",
          country: "United States",
          dob: "Jul-01-1990",
          firstName: "Ted",
          gender: 'Male',
          lastName: "Mosby",
          middleName: "Evelyn",
        },
        // id: 0,
        mrnNumber: "MRN_123456789",
        state: "New York",
        status: "DRAFT",
        // zipcode: "",
        // assignSection: null,
        assignPathologist: "Dr. Thomas",
        comments: "Lorem ipsum dolor sit, amet consectetur adipisicing elit. Voluptas dicta iusto provident. Nemo, quisquam soluta!",
        refPathologistName: "Dr. Raj",
        refHospitalName: "Apollo",
        priority: "STAT",
      },
    };
  },
};
</script>

<style scoped></style>
