<!--
  This is a registration page where you can alter the following:
    1. Header Photo (best resolution: 1600px x 400px)
    2. Event Name
    3. Event Description

  Go to src > components > organisms > RegistrationForms to modify or add your own form
-->

<script>
  import RegistrationTemplate from "$components/molecules/Form/RegistrationTemplate.svelte"; // registration template component

  // CUSTOMIZE THIS: This is where you can modify the header photo, event name, and event description
  import PreApplication from "../../../components/organisms/RegistrationForms/PreApplication.svelte"; // Form Component: a file from src > components > organisms > RegistrationForms (URL should be ../../../components/organisms/RegistrationForms/'your form component)
  let headerPhotoURL = "../form-headers/acss-orientation-xssaen.webp"; // Header Photo: a file from src > static (URL should be ../form-headers/'your file')
  let eventName = "CMG Pre-Application"; // Event Name
  let eventDescription = `
        Thank you for showing your interest in growing with us!
        Please fill out this pre-application form for us to have a brief knowledge about you. Rest assured that all the information you will provide here will only be used for our organization's application process purposes.
                `; // Event Description
  // END OF CUSTOMIZATION
</script>

<div class="relative z-20">
  <RegistrationTemplate {headerPhotoURL} {eventName} {eventDescription}>
    <!-- CUSTOMIZE THIS: Insert here your form component with an attribute slot="form" -->
    <PreApplication slot="form" />
    <!-- END OF CUSTOMIZATION -->
  </RegistrationTemplate>
</div>
