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
  import ACSSOrientation from "../../../components/organisms/RegistrationForms/ACSSOrientation.svelte"; // Form Component: a file from src > components > organisms > RegistrationForms (URL should be ../../../components/organisms/RegistrationForms/'your form component)
  let headerPhotoURL = "../form-headers/acss-orientation-xssaen.webp"; // Header Photo: a file from src > static (URL should be ../form-headers/'your file')
  let eventName = "CMG Orientation"; // Event Name
  let eventDescription = `
                This is an early registration form for the upcoming "CMG-UPLB Orientation:
                Xperience Sugar, Spice, and Everything Nice!" which aims to familiarize you with our
                growing organization. The orientation will be held on September 21,
                2023, 7:00 PM at Jollibee Vega. If you wish to join the orientation, kindly fill
                out this form. Orientation details and updates will be sent through
                the email used in answering this form.
                `; // Event Description
  // END OF CUSTOMIZATION
</script>

<div class="relative z-20">
  <RegistrationTemplate {headerPhotoURL} {eventName} {eventDescription}>
    <!-- CUSTOMIZE THIS: Insert here your form component with an attribute slot="form" -->
    <ACSSOrientation slot="form" />
    <!-- END OF CUSTOMIZATION -->
  </RegistrationTemplate>
</div>
