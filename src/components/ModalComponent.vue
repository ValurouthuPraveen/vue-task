<template class="modalComponent1">
  <div class="modalComponent">
    <div>
      <b-button v-b-modal.modal-lg variant="primary"
        >Launch demo modal</b-button
      >

      <b-modal title="BootstrapVue" id="modal-lg" size="lg">
        <b-container class="bv-example-row">
          <b-row>
            <b-col>
                <p>Name </p>
                <p> {{ patientName }} </p>
            </b-col>
            <b-col>
                <p>Gender</p>
                <p> {{ patientData.patient.gender }} </p>
            </b-col>
            <b-col>
                <p>Date of Birth</p>
                <p> {{ patientData.patient.dob }} </p>
            </b-col>
          </b-row>

            <br />

          <b-row>
            <b-col>
                <p>Internal Accession Number </p>
                <p> {{ patientData.internalAccessionNo }} </p>
            </b-col>
            <b-col>
                <p>MRN Number</p>
                <p> {{ patientData.mrnNumber }} </p>
            </b-col>
            <b-col>
                <p>Priority</p>
                <p> {{ patientData.priority }} </p>
            </b-col>
          </b-row>

            <hr />

          <b-row>
            <b-col>
                <p>Country </p>
                <p> {{ patientData.patient.country }} </p>
            </b-col>
            <b-col>
                <p>State</p>
                <p> {{ patientData.state }} </p>
            </b-col>
            <b-col>
                <p>City</p>
                <p> {{ patientData.patient.city }} </p>
            </b-col>
          </b-row>

            <br />

          <b-row>
            <b-col cols="12">
                <p>Address</p>
                <p> {{ patientData.patient.address1 }} </p>
            </b-col>
          </b-row>

            <hr />

            <b-row>
            <b-col>
                <p>Referring Hospital </p>
                <p> {{ patientData.refHospitalName }} </p>
            </b-col>
            <b-col>
                <p>Referring Physician</p>
                <p> {{ patientData.assignPathologist }} </p>
            </b-col>
            <b-col>
                <p>Assigned Pathologist</p>
                <p> {{ patientData.refPathologistName }} </p>
            </b-col>
          </b-row>

          <hr />

          <b-row>
            <b-col cols="12">
                <p>Clinical History/ Comments</p>
                <p> {{ patientData.comments }} </p>
            </b-col>
          </b-row>

        </b-container>
        <div id="block"></div>
      </b-modal>
    </div>

    <!-- <div class="test">
      <p>Modal Component</p>
      <p>Name - {{ patientName }}</p>
      <p>Gender - {{ patientData.patient.gender }}</p>
      <p>Date of Birth - {{ patientData.patient.dob }}</p>
      <p>Internal Accession Numbers - {{ patientData.internalAccessionNo }}</p>
      <p>MRN Number - {{ patientData.mrnNumber }}</p>
      <p>Priority - {{ patientData.priority }}</p>
      <p>Country - {{ patientData.patient.country }}</p>
      <p>State - {{ patientData.state }}</p>
      <p>City - {{ patientData.patient.city }}</p>
      <p>Address - {{ patientData.patient.address1 }}</p>
      <p>Referring Hospital - {{ patientData.refHospitalName }}</p>
      <p>Referring Physician - {{ patientData.assignPathologist }}</p>
      <p>Assigned Pathologist - {{ patientData.refPathologistName }}</p>
      <p>Comments - {{ patientData.comments }}</p>
    <div id="block"></div>
    </div> -->

  </div>
</template>

<script>
export default {
  name: "ModalComponent",
  props: ["patientData"],
  computed: {
    patientName() {
      return (
        this.patientData.patient.firstName +
        " " +
        this.patientData.patient.middleName +
        " " +
        this.patientData.patient.lastName
      );
    },
  },
};
</script>

<style>
/* #modal-lg___BV_modal_header_, #modal-lg___BV_modal_footer_{
    display: none;
} */

p:nth-child(odd) {
  color: #54aaa0;
}

p:nth-child(even) {
  color: white;
}

@media only screen and (min-width: 992px) {
  #block {
    min-width: 700px;
    min-height: 400px;
  }
}

#block {
  /* height: 400px; */
  /* width: 700px; */
  /* min-width: 700px;
  min-height: 400px; */
  /* background: orange; */
  /* background: rgb(197, 186, 186, 0.6); */
  /* background: #f5f3f3f6; */
  background: rgba(255, 255, 255, 0.2);
  /* box-shadow: 5px 10px white; */
  /* border: inherit; */
  /* opacity: 0.1; */
/* background: linear-gradient(to right, #333, #333 0%, #eee 75%, #333 75%); */
  /* background: linear-gradient(to right, #333, #333 0%, #eee 75%); */
  /* background: linear-gradient(to right, #333, #333 50%, #333 50%); */
  /* opacity: 0.2; */
  /* background: #eee; */
  position: absolute;
  top: 22%;
  right: 0px;
}

.modal-header, .modal-footer {
  display: none;
}

.modal-body {
    /* background: rgb(224, 216, 216); */
    /* background: rgb(197, 186, 186,0.2); */
    /* background: linear-gradient(
      rgba(255, 100, 100, 0.45), 
      rgba(255, 0, 0, 0.45)
    ), rgb(0, 0, 0, 0.8); */
    background: rgb(0, 0, 0, 0.8);
    opacity: 1;
    position: relative;
    /* box-shadow: inset 0 0 0 1000px rgba(0,0,0,.8); */
}

.test {
  background: rgba(158, 145, 145, 0.5);
  color: white;
  font-size: 20px;
  /* position: fixed; */
  /* top: 10%;
  bottom: 10%;
  left: 10%;
  right: 10%; */
  position: relative;
}

/* .modalComponent {
  background: rgb(116, 111, 111);
  width: 100%;
  height: 100vh;
} */

.test:hover {
  /* background: rgba(51, 170, 51, .4); */
  /* background: -moz-linear-gradient(to left, #FFFFFF, #0099ff); */
    /* background: linear-gradient(to left, #FFFFFF, #0099ff); */
}

/* body, html {
    height: 100%;
} */
/* body */

/* .modalComponent {
  background: -moz-linear-gradient(to bottom, #ffffff, #0099ff);
  background: linear-gradient(to bottom, #ffffff, #0099ff);
} */
</style>

// when using the modal-footer slot, the default OK and Cancel buttons will not
be present. Also, if you use the modal-header slot, the default header X close
button will not be present, nor can you use the modal-title slot. // use
#modal-footer
