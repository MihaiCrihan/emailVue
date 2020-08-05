<script>
export default {
  name: "HelloWorld",
  data() {
    return {
      windowWidth: window.innerWidth,
      value: 45,
      max: 100,
      isHidden: false,
      form: {
        account: {
          username: "",
          domain: ""
        },
        gender: "",
        first_name: "",
        last_name: "",
        country: "",
        state: null,
        birth: {
          day: "",
          month: "",
          year: ""
        },
        password: "",
        password_repeat: "",
        recovery: {
          sms: {
            country: {
              name: "",
              phone_code: "1"
            },
            phone_number: ""
          },
          email: ""
        }
      },
      domains: [
        { text: "@mail.com", value: "@mail.com" },
        "@email.com",
        "@gmail.com",
        "@usarb.com"
      ],
      countries: [
        { text: "Afghanistan", value: "AF" },
        { text: "Albania", value: "AL" },
        { text: "Algeria", value: "DZ" },
        { text: "Aland Islands", value: "AX" },
        { text: "American Samoa", value: "AS" },
        { text: "Anguilla", value: "AI" },
        { text: "Andorra", value: "AD" },
        { text: "Angola", value: "AO" },
        { text: "Antilles - Netherlands", value: "AN" },
        { text: "Antigua and Barbuda", value: "AG" },
        { text: "Antarctica", value: "AQ" },
        { text: "Argentina", value: "AR" },
        { text: "Armenia", value: "AM" },
        { text: "Australia", value: "AU" },
        { text: "Austria", value: "AT" },
        { text: "Aruba", value: "AW" },
        { text: "Azerbaijan", value: "AZ" },
        { text: "Bosnia and Herzegovina", value: "BA" },
        { text: "Barbados", value: "BB" },
        { text: "Bangladesh", value: "BD" },
        { text: "Belgium", value: "BE" },
        { text: "Burkina Faso", value: "BF" },
        { text: "Bulgaria", value: "BG" },
        { text: "Bahrain", value: "BH" },
        { text: "Burundi", value: "BI" },
        { text: "Benin", value: "BJ" },
        { text: "Bermuda", value: "BM" },
        { text: "Brunei Darussalam", value: "BN" },
        { text: "Bolivia", value: "BO" },
        { text: "Brazil", value: "BR" },
        { text: "Bahamas", value: "BS" },
        { text: "Bhutan", value: "BT" },
        { text: "Bouvet Island", value: "BV" },
        { text: "Botswana", value: "BW" },
        { text: "Belarus", value: "BV" },
        { text: "Belize", value: "BZ" },
        { text: "Cambodia", value: "KH" },
        { text: "Cameroon", value: "CM" },
        { text: "Canada", value: "CA" },
        { text: "Cape Verde", value: "CV" },
        { text: "Central African Republic", value: "CF" },
        { text: "Chad", value: "TD" },
        { text: "Chile", value: "CL" },
        { text: "China", value: "CN" },
        { text: "Christmas Island", value: "CX" },
        { text: "Cocos (Keeling) Islands", value: "CC" },
        { text: "Colombia", value: "CO" },
        { text: "Congo", value: "CG" },
        { text: "Cote D'Ivoire (Ivory Coast)", value: "CI" },
        { text: "Cook Islands", value: "CK" },
        { text: "Costa Rica", value: "CR" },
        { text: "Croatia (Hrvatska)", value: "HR" },
        { text: "Cuba", value: "CU" },
        { text: "Cyprus", value: "CY" },
        { text: "Czech Republic", value: "CZ" },
        { text: "Democratic Republic of the Congo", value: "CD" },
        { text: "Djibouti", value: "DJ" },
        { text: "Denmark", value: "DK" },
        { text: "Dominica", value: "DM" },
        { text: "Dominican Republic", value: "DO" },
        { text: "Ecuador", value: "EC" },
        { text: "Egypt", value: "EG" },
        { text: "El Salvador", value: "SV" },
        { text: "East Timor", value: "TP" },
        { text: "Estonia", value: "EE" },
        { text: "Equatorial Guinea", value: "GQ" },
        { text: "Eritrea", value: "ER" },
        { text: "Ethiopia", value: "ET" },
        { text: "Finland", value: "FI" },
        { text: "Fiji", value: "FJ" },
        { text: "Falkland Islands (Malvinas)", value: "FK" },
        { text: "Federated States of Micronesia", value: "FM" },
        { text: "Faroe Islands", value: "FO" },
        { text: "France", value: "FR" },
        { text: "France, Metropolitan", value: "FX" },
        { text: "French Guiana", value: "GF" },
        { text: "French Polynesia", value: "PF" },
        { text: "Gabon", value: "GA" },
        { text: "Gambia", value: "GM" },
        { text: "Germany", value: "DE" },
        { text: "Ghana", value: "GH" },
        { text: "Gibraltar", value: "GI" },
        { text: "Great Britain (UK)", value: "GB" },
        { text: "Grenada", value: "GD" },
        { text: "Georgia", value: "GE" },
        { text: "Greece", value: "GR" },
        { text: "Greenland", value: "GL" },
        { text: "Guinea", value: "GN" },
        { text: "Guadeloupe", value: "GP" },
        { text: "S. Georgia and S. Sandwich Islands", value: "GS" },
        { text: "Guatemala", value: "GT" },
        { text: "Guam", value: "GU" },
        { text: "Guinea-Bissau", value: "GW" },
        { text: "Guyana", value: "GY" },
        { text: "Hong Kong", value: "HK" },
        { text: "Heard Island and McDonald Islands", value: "HM" },
        { text: "Honduras", value: "HN" },
        { text: "Haiti", value: "HT" },
        { text: "Hungary", value: "HU" },
        { text: "Indonesia", value: "ID" },
        { text: "Ireland", value: "IE" },
        { text: "Israel", value: "IL" },
        { text: "India", value: "IN" },
        { text: "British Indian Ocean Territory", value: "IO" },
        { text: "Iraq", value: "IQ" },
        { text: "Iran", value: "IR" },
        { text: "Italy", value: "IT" },
        { text: "Jamaica", value: "JM" },
        { text: "Jordan", value: "JO" },
        { text: "Japan", value: "JP" },
        { text: "Kenya", value: "KE" },
        { text: "Kyrgyzstan", value: "KG" },
        { text: "Kiribati", value: "KI" },
        { text: "Comoros", value: "KM" },
        { text: "Saint Kitts and Nevis", value: "KN" },
        { text: "Korea (North)", value: "KP" },
        { text: "Korea (South)", value: "KR" },
        { text: "Kuwait", value: "KW" },
        { text: "Cayman Islands", value: "KY" },
        { text: "Kazakhstan", value: "KZ" },
        { text: "Laos", value: "LA" },
        { text: "Lebanon", value: "LB" },
        { text: "Saint Lucia", value: "LC" },
        { text: "Liechtenstein", value: "LI" },
        { text: "Sri Lanka", value: "LK" },
        { text: "Liberia", value: "LR" },
        { text: "Lesotho", value: "LS" },
        { text: "Lithuania", value: "LT" },
        { text: "Luxembourg", value: "LU" },
        { text: "Latvia", value: "LV" },
        { text: "Libya", value: "LY" },
        { text: "Macedonia", value: "MK" },
        { text: "Macao", value: "MO" },
        { text: "Madagascar", value: "MG" },
        { text: "Malaysia", value: "MY" },
        { text: "Mali", value: "ML" },
        { text: "Malawi", value: "MW" },
        { text: "Mauritania", value: "MR" },
        { text: "Marshall Islands", value: "MH" },
        { text: "Martinique", value: "MQ" },
        { text: "Mauritius", value: "MU" },
        { text: "Mayotte", value: "YT" },
        { text: "Malta", value: "MT" },
        { text: "Mexico", value: "MX" },
        { text: "Morocco", value: "MA" },
        { text: "Monaco", value: "MC" },
        { text: "Moldova", value: "MD" },
        { text: "Mongolia", value: "MN" },
        { text: "Myanmar", value: "MM" },
        { text: "Northern Mariana Islands", value: "MP" },
        { text: "Montserrat", value: "MS" },
        { text: "Maldives", value: "MV" },
        { text: "Mozambique", value: "MZ" },
        { text: "Namibia", value: "NA" },
        { text: "New Caledonia", value: "NC" },
        { text: "Niger", value: "NE" },
        { text: "Norfolk Island", value: "NF" },
        { text: "Nigeria", value: "NG" },
        { text: "Nicaragua", value: "NI" },
        { text: "Netherlands", value: "NL" },
        { text: "Norway", value: "NO" },
        { text: "Nepal", value: "NP" },
        { text: "Nauru", value: "NR" },
        { text: "Niue", value: "NU" },
        { text: "New Zealand (Aotearoa)", value: "NZ" },
        { text: "Oman", value: "OM" },
        { text: "Panama", value: "PA" },
        { text: "Peru", value: "PE" },
        { text: "Papua New Guinea", value: "PG" },
        { text: "Philippines", value: "PH" },
        { text: "Pakistan", value: "PK" },
        { text: "Poland", value: "PL" },
        { text: "Saint Pierre and Miquelon", value: "PM" },
        { text: "Serbia and Montenegro", value: "CS" },
        { text: "Pitcairn", value: "PN" },
        { text: "Puerto Rico", value: "PR" },
        { text: "Palestinian Territory", value: "PS" },
        { text: "Portugal", value: "PT" },
        { text: "Palau", value: "PW" },
        { text: "Paraguay", value: "PY" },
        { text: "Qatar", value: "QA" },
        { text: "Reunion", value: "RE" },
        { text: "Romania", value: "RO" },
        { text: "Russian Federation", value: "RU" },
        { text: "Rwanda", value: "RW" },
        { text: "Saudi Arabia", value: "SA" },
        { text: "Samoa", value: "WS" },
        { text: "Saint Helena", value: "SH" },
        { text: "Saint Vincent and the Grenadines", value: "VC" },
        { text: "San Marino", value: "SM" },
        { text: "Sao Tome and Principe", value: "ST" },
        { text: "Senegal", value: "SN" },
        { text: "Seychelles", value: "SC" },
        { text: "Sierra Leone", value: "SL" },
        { text: "Singapore", value: "SG" },
        { text: "Slovakia", value: "SK" },
        { text: "Slovenia", value: "SI" },
        { text: "Solomon Islands", value: "SB" },
        { text: "Somalia", value: "SO" },
        { text: "South Africa", value: "ZA" },
        { text: "Spain", value: "ES" },
        { text: "Sudan", value: "SD" },
        { text: "Suriname", value: "SR" },
        { text: "Svalbard and Jan Mayen", value: "SJ" },
        { text: "Sweden", value: "SE" },
        { text: "Switzerland", value: "CH" },
        { text: "Syria", value: "SY" },
        { text: "USSR (former)", value: "SU" },
        { text: "Swaziland", value: "SZ" },
        { text: "Taiwan", value: "TW" },
        { text: "Tanzania", value: "TZ" },
        { text: "Tajikistan", value: "TJ" },
        { text: "Thailand", value: "TH" },
        { text: "Timor-Leste", value: "TL" },
        { text: "Togo", value: "TG" },
        { text: "Tokelau", value: "TK" },
        { text: "Tonga", value: "TO" },
        { text: "Trinidad and Tobago", value: "TT" },
        { text: "Tunisia", value: "TN" },
        { text: "Turkey", value: "TR" },
        { text: "Turkmenistan", value: "TM" },
        { text: "Turks and Caicos Islands", value: "TC" },
        { text: "Tuvalu", value: "TV" },
        { text: "Ukraine", value: "UA" },
        { text: "Uganda", value: "UG" },
        { text: "United Arab Emirates", value: "AE" },
        { text: "United Kingdom", value: "UK" },
        { text: "United States", value: "US" },
        { text: "United States Minor Outlying Islands", value: "UM" },
        { text: "Uruguay", value: "UY" },
        { text: "Uzbekistan", value: "UZ" },
        { text: "Vanuatu", value: "VU" },
        { text: "Vatican City State", value: "VA" },
        { text: "Venezuela", value: "VE" },
        { text: "Virgin Islands (British)", value: "VG" },
        { text: "Virgin Islands (U.S.)", value: "VI" },
        { text: "Viet Nam", value: "VN" },
        { text: "Wallis and Futuna", value: "WF" },
        { text: "Western Sahara", value: "EH" },
        { text: "Yemen", value: "YE" },
        { text: "Yugoslavia (former)", value: "YU" },
        { text: "Zambia", value: "ZM" },
        { text: "Zaire (former)", value: "ZR" },
        { text: "Zimbabwe", value: "ZW" }
      ],
      states: [
        { text: "Alska", value: "Alska" },
        "Akihabara",
        "Tokyo",
        "Nagoya"
      ],
      names: [
        { text: "US +1", value: "US +1" },
        { text: "US 33", value: "US +33" },
        { text: "US +144", value: "US +144" },
        { text: "US +122", value: "US +122" }
      ],
      stepNumber: 1,
      showByEmail: true,
      showBySms: true,
      reg: "^[A-Z0-9._%+-]+@[A-Z0-9.-]+.[A-Z]{2,4}$"
    };
  },
  computed: {
    isPhone() {
      return this.windowWidth <= 960;
    }
  },
  mounted() {
    window.addEventListener("resize", () => {
      this.windowWidth = window.innerWidth;
    });
  },
  methods: {
    getValidationState({ dirty, validated, valid = null }) {
      return dirty || validated ? valid : null;
    },
    resetForm() {
      this.form = {
        name: null,
        food: null
      };

      this.$nextTick(() => {
        this.$refs.observer.reset();
      });
    },
    onSubmit() {
      alert("Form submitted!");
    }
  }
};
</script>

<template>
  <div>
    <div class="container grid" v-if="isPhone">
      <ul class="stepper">
        <li
          class="stepper__item"
          :class="{ current: stepNumber === 1, complete: stepNumber > 1 }"
        >
          1 of 5
        </li>
        <li
          class="stepper__item"
          :class="{ current: stepNumber === 2, complete: stepNumber > 2 }"
        >
          2 of 5
        </li>
        <li
          class="stepper__item"
          :class="{ current: stepNumber === 3, complete: stepNumber > 3 }"
        >
          3 of 5
        </li>
        <li
          class="stepper__item"
          :class="{ current: stepNumber === 4, complete: stepNumber > 4 }"
        >
          4 of 5
        </li>
        <li
          class="stepper__item"
          :class="{ current: stepNumber === 5, complete: stepNumber > 5 }"
        >
          5 of 5
        </li>
      </ul>
      <div>
        <div v-if="stepNumber == 1">
          <div class="d-flex mb-4 mt-6">
            <h2>Create your email account</h2>
            <b-icon icon="info" class="info_fade" v-b-toggle="'collapse-1'" />
          </div>
          <b-collapse id="collapse-1">
            <div class="d-flex info-box-animate">
              <div>
                Select your new, desired email address here. The availability of
                the email address will be checked upon further input. Your
                previously entered data will be transferred to mail.com for the
                generation of proposals.
              </div>
              <div class="boxe-close-icon">
                <b-icon
                  icon="x"
                  class="close-info-box"
                  v-b-toggle="'collapse-1'"
                  style="width: 26px; height: 26px;"
                />
              </div>
            </div>
          </b-collapse>
        </div>
        <b-form @submit="onSubmit">
          <div class="email-field" v-if="stepNumber == 1">
            <validation-provider
              name="Name"
              :rules="{ required: true, min: 3 }"
              v-slot="validationContext"
            >
              <b-form-group
                id="input-group-1"
                label-for="input-1"
                class="email-name"
              >
                <b-form-input
                  id="input-1"
                  v-model="form.account.username"
                  trim
                  type="text"
                  :state="getValidationState(validationContext)"
                  placeholder="Enter email"
                ></b-form-input>
                <b-form-invalid-feedback id="input-1-live-feedback">{{
                  validationContext.errors[0]
                }}</b-form-invalid-feedback>
              </b-form-group>
            </validation-provider>
            <b-form-group
              id="input-group-2"
              label-for="input-2"
              class="email-domen"
            >
              <b-form-select
                id="input-3"
                v-model="form.account.domain"
                :options="domains"
              ></b-form-select>
            </b-form-group>
            <div class="check-button">
              <b-button class="button">Check</b-button>
            </div>
          </div>
          <div class="personal-details-field" v-if="stepNumber == 2">
            <h2 class="mt-4">Personal details</h2>
            <div>
              <validation-provider
                name="Gender"
                :rules="{ required: true, min: 3 }"
                v-slot="validationContext"
              >
                <b-form-group class="gender">
                  <b-form-radio
                    v-model="form.gender"
                    name="female"
                    :state="getValidationState(validationContext)"
                    value="f"
                    class="mr-4"
                    >Ms</b-form-radio
                  >
                  <b-form-radio v-model="form.gender" name="male" value="m"
                    >Mr</b-form-radio
                  >
                  <b-form-invalid-feedback id="input-1-live-feedback">{{
                    validationContext.errors[0]
                  }}</b-form-invalid-feedback>
                </b-form-group>
              </validation-provider>
            </div>
            <validation-provider
              name="first-name"
              :rules="{ required: true, min: 3 }"
              v-slot="validationContext"
            >
              <b-form-group
                id="input-group-3"
                label="First Name:"
                label-for="input-3"
              >
                <b-form-input
                  id="input-2"
                  :state="getValidationState(validationContext)"
                  v-model="form.first_name"
                  placeholder="Enter name"
                ></b-form-input>
                <b-form-invalid-feedback id="input-1-live-feedback">{{
                  validationContext.errors[0]
                }}</b-form-invalid-feedback>
              </b-form-group>
            </validation-provider>
            <validation-provider
              name="last-name"
              :rules="{ required: true, min: 3 }"
              v-slot="validationContext"
            >
              <b-form-group
                id="input-group-4"
                label="Last Name:"
                label-for="input-4"
              >
                <b-form-input
                  id="input-2"
                  :state="getValidationState(validationContext)"
                  v-model="form.last_name"
                  placeholder="Enter name"
                ></b-form-input>
                <b-form-invalid-feedback id="input-1-live-feedback">{{
                  validationContext.errors[0]
                }}</b-form-invalid-feedback>
              </b-form-group>
            </validation-provider>
            <validation-provider
              name="country"
              :rules="{ required: true, min: 3 }"
              v-slot="validationContext"
            >
              <b-form-group
                id="input-group-6"
                label="Country"
                label-for="input-6"
              >
                <b-form-select
                  id="input-3"
                  :state="getValidationState(validationContext)"
                  v-model="form.country"
                  :options="countries"
                ></b-form-select>
                <b-form-invalid-feedback id="input-1-live-feedback">{{
                  validationContext.errors[0]
                }}</b-form-invalid-feedback>
              </b-form-group>
            </validation-provider>
            <validation-provider
              name="states"
              :rules="{ required: true, min: 3 }"
              v-slot="validationContext"
            >
              <b-form-group
                id="input-group-7"
                label="State"
                label-for="input-7"
              >
                <b-form-select
                  id="input-3"
                  :state="getValidationState(validationContext)"
                  v-model="form.state"
                  :options="states"
                ></b-form-select>
                <b-form-invalid-feedback id="input-1-live-feedback">{{
                  validationContext.errors[0]
                }}</b-form-invalid-feedback>
              </b-form-group>
            </validation-provider>
            <div>
              <div>Date of birth</div>
              <b-form inline class="mt-3 birth-date">
                <validation-provider
                  name="month"
                  :rules="{ required: true, min: 3 }"
                  v-slot="validationContext"
                >
                  <b-form-group>
                    <b-input
                      id="inline-form-input-name"
                      placeholder="MM"
                      type="number"
                      :state="getValidationState(validationContext)"
                      v-model="form.birth.month"
                      max="12"
                      min="1"
                    ></b-input>
                    <b-form-invalid-feedback id="input-1-live-feedback">{{
                      validationContext.errors[0]
                    }}</b-form-invalid-feedback>
                  </b-form-group>
                </validation-provider>
                <validation-provider
                  name="day"
                  :rules="{ required: true, min: 3 }"
                  v-slot="validationContext"
                >
                  <b-form-group>
                    <b-input
                      id="inline-form-input-name"
                      placeholder="DD"
                      type="number"
                      :state="getValidationState(validationContext)"
                      v-model="form.birth.day"
                      maxlength="2"
                      min="1"
                      max="31"
                    ></b-input>
                    <b-form-invalid-feedback id="input-1-live-feedback">{{
                      validationContext.errors[0]
                    }}</b-form-invalid-feedback>
                  </b-form-group>
                </validation-provider>
                <validation-provider
                  name="year"
                  :rules="{ required: true, min: 3 }"
                  v-slot="validationContext"
                >
                  <b-form-group>
                    <b-input
                      id="inline-form-input-name"
                      placeholder="YYYY"
                      type="number"
                      :state="getValidationState(validationContext)"
                      v-model="form.birth.year"
                      maxlength="4"
                      min="1900"
                      max="2020"
                    ></b-input>
                    <b-form-invalid-feedback id="input-1-live-feedback">{{
                      validationContext.errors[0]
                    }}</b-form-invalid-feedback>
                  </b-form-group>
                </validation-provider>
                <div class="example-input">e.g. 03/16/1997</div>
              </b-form>
            </div>
          </div>
          <div class="password-field" v-if="stepNumber == 3">
            <div class="d-flex mt-4 mb-5">
              <h2>Password</h2>
              <b-icon icon="info" class="info_fade" v-b-toggle="'collapse-2'" />
            </div>
            <b-collapse id="collapse-2">
              <div class="d-flex info-box-animate">
                <div>
                  Use a unique password for each and every service.
                  <br />
                  A secure password consists of
                  <ul>
                    <li>At least eight characters</li>
                    <li>Numbers and letters</li>
                    <li>Upper and lower case letters</li>
                    <li>Special characters</li>
                  </ul>
                </div>
                <div class="boxe-close-icon">
                  <b-icon
                    icon="x"
                    class="close-info-box"
                    style="width: 26px; height: 26px;"
                    v-b-toggle="'collapse-2'"
                  />
                </div>
              </div>
            </b-collapse>
            <div>
              <validation-provider
                name="password"
                :rules="{ required: true, min: 3 }"
                v-slot="validationContext"
              >
                <b-form-group label="Chose a password">
                  <b-form-input
                    id="input-2"
                    v-model="form.password"
                    required
                    :state="getValidationState(validationContext)"
                    type="password"
                    placeholder="Password"
                  ></b-form-input>
                  <b-form-invalid-feedback id="input-1-live-feedback">{{
                    validationContext.errors[0]
                  }}</b-form-invalid-feedback>
                </b-form-group>
              </validation-provider>
              <div>
                <b-progress height="5px" class="mt-2" :max="max">
                  <b-progress-bar :value="value * (1.5 / 1)" variant="danger" />
                  <b-progress-bar
                    :value="value * (2.5 / 1)"
                    variant="warning"
                  />
                  <b-progress-bar :value="value * (6 / 1)" variant="success" />
                </b-progress>
              </div>
              <validation-provider
                name="repeat-password"
                :rules="{ required: true, min: 3 }"
                v-slot="validationContext"
              >
                <b-form-group label="Repeat a password" class="mt-3">
                  <b-form-input
                    id="input-2"
                    v-model="form.password_repeat"
                    type="password"
                    :state="getValidationState(validationContext)"
                    required
                  ></b-form-input>
                  <b-form-invalid-feedback id="input-1-live-feedback">{{
                    validationContext.errors[0]
                  }}</b-form-invalid-feedback>
                </b-form-group>
              </validation-provider>
            </div>
          </div>
          <div class="recovery-password-field" v-if="stepNumber == 4">
            <div class="d-flex mt-4 mb-5">
              <h2>Password recovery options</h2>
              <b-icon icon="info" class="info_fade" v-b-toggle="'collapse-3'" />
            </div>
            <b-collapse id="collapse-3">
              <div class="d-flex info-box-animate">
                <div>
                  <div class="mb-2">
                    Password recovery allows you to reset a forgotten password
                    yourself by email or SMS. Please add a valid email address.
                  </div>
                  <span>
                    <strong>We guarantee</strong>
                    your details will exclusively be used to recover your
                    password or to contact you to secure your account.
                  </span>
                </div>
                <div class="boxe-close-icon">
                  <b-icon
                    icon="x"
                    class="close-info-box"
                    style="width: 26px; height: 26px;"
                    v-b-toggle="'collapse-3'"
                  />
                </div>
              </div>
            </b-collapse>
            <div class="mt-5 mb-4">
              <b-form-checkbox
                id="checkbox-1"
                name="checkbox-1"
                value="accepted"
                @change="showBySms = !showBySms"
                unchecked-value="not_accepted"
              >
                By SMS (recomended)
              </b-form-checkbox>
            </div>
            <div>
              <div v-if="!showBySms">
                <div class="mb-2">Cellphone number</div>
                <div class="email-field">
                  <validation-provider
                    name="name"
                    :rules="{ required: true, min: 3 }"
                    v-slot="validationContext"
                  >
                    <b-form-group label-for="input-2">
                      <b-form-select
                        id="input-3"
                        v-model="form.recovery.sms.country.name"
                        :options="names"
                        :state="getValidationState(validationContext)"
                        required
                      ></b-form-select>
                      <b-form-invalid-feedback id="input-1-live-feedback">{{
                        validationContext.errors[0]
                      }}</b-form-invalid-feedback>
                    </b-form-group>
                  </validation-provider>
                  <validation-provider
                    name="phone number"
                    :rules="{ required: true, min: 3 }"
                    v-slot="validationContext"
                  >
                    <b-form-group label-for="input-1">
                      <b-form-input
                        id="input-1"
                        v-model="form.recovery.sms.phone_number"
                        type="text"
                        required
                        :state="getValidationState(validationContext)"
                        placeholder="Enter phone number"
                      ></b-form-input>
                      <b-form-invalid-feedback id="input-1-live-feedback">{{
                        validationContext.errors[0]
                      }}</b-form-invalid-feedback>
                    </b-form-group>
                  </validation-provider>
                </div>
              </div>
              <div class="mt-5 mb-4">
                <b-form-checkbox
                  name="checkbox-2"
                  value="accepted"
                  unchecked-value="not_accepted"
                  @change="showByEmail = !showByEmail"
                >
                  By email
                </b-form-checkbox>
              </div>
              <div v-if="!showByEmail">
                <validation-provider
                  name="email"
                  :rules="{ required: true, min: 3 }"
                  v-slot="validationContext"
                >
                  <b-form-group label="Email address:" label-for="input-1">
                    <b-form-input
                      id="input-1"
                      v-model="form.recovery.email"
                      type="email"
                      :state="getValidationState(validationContext)"
                      required
                      placeholder="example@mail.ru"
                    ></b-form-input>
                    <b-form-invalid-feedback id="input-1-live-feedback">{{
                      validationContext.errors[0]
                    }}</b-form-invalid-feedback>
                  </b-form-group>
                </validation-provider>
              </div>
            </div>
          </div>
          <div class="security-field" v-if="stepNumber == 5">
            <div class="d-flex mt-4 mb-4">
              <h2>Security prompt</h2>
              <b-icon icon="info" class="info_fade" v-b-toggle="'collapse-4'" />
            </div>
            <b-collapse id="collapse-4">
              <div class="d-flex info-box-animate">
                <div>
                  Just click the checkbox: If you see a green checkmark,
                  congratulations! You’ve passed our robot test (yes, it’s that
                  easy). You can carry on with what you were doing. Sometimes we
                  need some extra info from you to make sure you’re human and
                  not a robot, so we ask you to solve a challenge. Simply follow
                  the on-screen instructions to solve the puzzle and then carry
                  on with your task.
                </div>
                <div class="boxe-close-icon">
                  <b-icon
                    icon="x"
                    class="close-info-box"
                    style="width: 26px; height: 26px;"
                    v-b-toggle="'collapse-4'"
                  />
                </div>
              </div>
            </b-collapse>
            <div>
              <iframe
                src="https://www.google.com/recaptcha/api2/anchor?ar=2&amp;k=6Lc7GmIUAAAAAKDjVWk0q9Y5HhN5bNr1ctLZDmnw&amp;co=aHR0cHM6Ly9zaWdudXAubWFpbC5jb206NDQz&amp;hl=en&amp;v=AFBwIe6h0oOL7MOVu88LHld-&amp;size=normal&amp;cb=3gu779d297kj"
                width="304"
                height="78"
                role="presentation"
                name="a-ck9nt0e8v2st"
                frameborder="0"
                scrolling="no"
                sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-top-navigation allow-modals allow-popups-to-escape-sandbox"
              />
            </div>
            <div class="protect-field mt-4 mb-4">
              <b-icon
                icon="lock-fill"
                style="width: 24px; height: 24px;"
                class="mr-2"
              ></b-icon>
              <h2>We protect your information</h2>
            </div>
            <div>
              <div data-test="euds-body" class="mb-6">
                You own your information. We will only use your information to
                offer you the products and services you selected. Would you like
                to learn more? Please consult our
                <a target="_blank" href="#">privacy policy</a>
                for additional information.
              </div>
              <div class="a-mb-space-2 mb-4">
                <strong>
                  The
                  <a target="_blank" href="#">
                    Terms and Conditions
                  </a>
                  apply
                </strong>
              </div>
            </div>

            <b-button type="submit" class="accept-button" variant="primary"
              >I agree. Create an email account now.</b-button
            >
          </div>
          <div class="mt-8 d-flex" v-if="isPhone">
            <b-button
              class="back-button"
              variant="link"
              v-if="stepNumber !== 1"
              @click="stepNumber--"
              >Back</b-button>
            <b-button
              class="ml-auto next-button"
              v-if="stepNumber !== 5"
              variant="primary"
              col
              @click="stepNumber++"
              >Next</b-button
            >
          </div>
        </b-form>
        <!--        <b-card class="mt-3" header="Form Data Result">-->
        <!--          <pre class="m-0">{{ account }}</pre>-->
        <!--          <hr />-->
        <!--          <pre class="m-0">{{ form }}</pre>-->
        <!--        </b-card>-->
      </div>
      <div class="teaser">
        <img src="https://picsum.photos/200/300" />
        <h1>mail.com Email</h1>
        <h2>Email for Everyone</h2>
        <ul class="teaser-text">
          <li>Choose amongst 200 domains</li>
          <li>Free &amp; customized email apps</li>
          <li>Large Attachments up to 30 MB</li>
          <li>Up to 10 Alias Addresses</li>
        </ul>
      </div>
    </div>

    <div class="container grid" v-if="!isPhone">
      <div>
        <div>
          <div class="d-flex mb-4 mt-6">
            <h2>Create your email account</h2>
            <b-icon icon="info" class="info_fade" v-b-toggle="'collapse-1'" />
          </div>
          <b-collapse id="collapse-1">
            <div class="d-flex info-box-animate">
              <div>
                Select your new, desired email address here. The availability of
                the email address will be checked upon further input. Your
                previously entered data will be transferred to mail.com for the
                generation of proposals.
              </div>
              <div class="boxe-close-icon">
                <b-icon
                  icon="x"
                  class="close-info-box"
                  v-b-toggle="'collapse-1'"
                  style="width: 26px; height: 26px;"
                />
              </div>
            </div>
          </b-collapse>
        </div>
        <b-form @submit="onSubmit">
          <div class="email-field">
            <b-form-group label-for="input-1" class="email-name">
              <b-form-input
                id="input-1"
                v-model="form.account.username"
                type="text"
                required
                placeholder="Enter email"
              ></b-form-input>
            </b-form-group>
            <b-form-group label-for="input-2" class="email-domen">
              <b-form-select
                id="input-3"
                v-model="form.account.domain"
                :options="domains"
                required
              ></b-form-select>
            </b-form-group>
            <div class="check-button">
              <b-button class="button">Check</b-button>
            </div>
          </div>
          <div class="personal-details-field">
            <h2>Personal details</h2>
            <div>
              <b-form-group class="gender">
                <b-form-radio
                  v-model="form.gender"
                  name="female"
                  value="f"
                  class="mr-4"
                  >Ms</b-form-radio
                >
                <b-form-radio v-model="form.gender" name="male" value="m"
                  >Mr</b-form-radio
                >
              </b-form-group>
            </div>

            <b-form-group label="First Name:" label-for="input-3">
              <b-form-input
                id="input-2"
                v-model="form.first_name"
                required
                placeholder="Enter name"
              ></b-form-input>
            </b-form-group>
            <b-form-group label="Last Name:" label-for="input-4">
              <b-form-input
                id="input-2"
                v-model="form.last_name"
                required
                placeholder="Enter name"
              ></b-form-input>
            </b-form-group>
            <b-form-group label="Country" label-for="input-6">
              <b-form-select
                id="input-3"
                v-model="form.country"
                :options="countries"
                required
              ></b-form-select>
            </b-form-group>
            <b-form-group label="State" label-for="input-7">
              <b-form-select
                id="input-3"
                v-model="form.state"
                :options="states"
                required
              ></b-form-select>
            </b-form-group>
            <div>
              <div>Date of birth</div>
              <b-form inline class="mt-3 birth-date">
                <b-input
                  id="inline-form-input-name"
                  class="mb-2 mr-sm-2 mb-sm-0"
                  placeholder="MM"
                  type="number"
                  v-model="form.birth.month"
                  max="12"
                  min="1"
                ></b-input>
                <b-input
                  id="inline-form-input-name"
                  class="mb-2 mr-sm-2 mb-sm-0"
                  placeholder="DD"
                  type="number"
                  v-model="form.birth.day"
                  maxlength="2"
                  min="1"
                  max="31"
                ></b-input>
                <b-input
                  id="inline-form-input-name"
                  class="mb-2 mr-sm-2 mb-sm-0"
                  placeholder="YYYY"
                  type="number"
                  v-model="form.birth.year"
                  maxlength="4"
                  min="1900"
                  max="2020"
                ></b-input>
                <div>e.g. 03/16/1997</div>
              </b-form>
            </div>
          </div>
          <div class="password-field">
            <div class="d-flex mt-8 mb-5">
              <h2>Password</h2>
              <b-icon icon="info" class="info_fade" v-b-toggle="'collapse-2'" />
            </div>
            <b-collapse id="collapse-2">
              <div class="d-flex info-box-animate">
                <div>
                  Use a unique password for each and every service.
                  <br />
                  A secure password consists of
                  <ul>
                    <li>At least eight characters</li>
                    <li>Numbers and letters</li>
                    <li>Upper and lower case letters</li>
                    <li>Special characters</li>
                  </ul>
                </div>
                <div class="boxe-close-icon">
                  <b-icon
                    icon="x"
                    class="close-info-box"
                    style="width: 26px; height: 26px;"
                    v-b-toggle="'collapse-2'"
                  />
                </div>
              </div>
            </b-collapse>
            <div>
              <b-form-group label="Chose a password">
                <b-form-input
                  id="input-2"
                  v-model="form.password"
                  required
                  type="password"
                  placeholder="Password"
                ></b-form-input>
              </b-form-group>
              <div>
                <b-progress height="5px" class="mt-2" :max="max">
                  <b-progress-bar :value="value * (1.5 / 1)" variant="danger" />
                  <b-progress-bar
                    :value="value * (2.5 / 1)"
                    variant="warning"
                  />
                  <b-progress-bar :value="value * (6 / 1)" variant="success" />
                </b-progress>
              </div>
              <b-form-group label="Repeat a password" class="mt-3">
                <b-form-input
                  id="input-2"
                  v-model="form.password_repeat"
                  type="password"
                  required
                ></b-form-input>
              </b-form-group>
            </div>
          </div>
          <div class="recovery-password-field">
            <div class="d-flex mt-8 mb-5">
              <h2>Password recovery options</h2>
              <b-icon icon="info" class="info_fade" v-b-toggle="'collapse-3'" />
            </div>
            <b-collapse id="collapse-3">
              <div class="d-flex info-box-animate">
                <div>
                  <div class="mb-2">
                    Password recovery allows you to reset a forgotten password
                    yourself by email or SMS. Please add a valid email address.
                  </div>
                  <span>
                    <strong>We guarantee</strong>
                    your details will exclusively be used to recover your
                    password or to contact you to secure your account.
                  </span>
                </div>
                <div class="boxe-close-icon">
                  <b-icon
                    icon="x"
                    class="close-info-box"
                    style="width: 26px; height: 26px;"
                    v-b-toggle="'collapse-3'"
                  />
                </div>
              </div>
            </b-collapse>
            <div class="mt-5 mb-4">
              <b-form-checkbox
                id="checkbox-1"
                name="checkbox-1"
                value="accepted"
                @change="showBySms = !showBySms"
                unchecked-value="not_accepted"
              >
                By SMS (recomended)
              </b-form-checkbox>
            </div>
            <div>
              <div v-if="!showBySms">
                <div class="mb-2">Cellphone number</div>
                <div class="email-field">
                  <b-form-group id="" label-for="input-2">
                    <b-form-select
                      id="input-3"
                      v-model="form.recovery.sms.country.name"
                      :options="names"
                      required
                    ></b-form-select>
                  </b-form-group>
                  <b-form-group label-for="input-1">
                    <b-form-input
                      id="input-1"
                      v-model="form.recovery.sms.phone_number"
                      type="text"
                      required
                      placeholder="Enter email"
                    ></b-form-input>
                  </b-form-group>
                </div>
              </div>
              <div class="mt-5 mb-4">
                <b-form-checkbox
                  name="checkbox-2"
                  value="accepted"
                  unchecked-value="not_accepted"
                  @change="showByEmail = !showByEmail"
                >
                  By email
                </b-form-checkbox>
              </div>
              <div v-if="!showByEmail">
                <b-form-group label="Email address:" label-for="input-1">
                  <b-form-input
                    id="input-1"
                    v-model="form.recovery.email"
                    type="email"
                    required
                    placeholder="example@mail.ru"
                  ></b-form-input>
                </b-form-group>
              </div>
            </div>
          </div>
          <div class="security-field">
            <div class="d-flex mt-8 mb-4">
              <h2>Security prompt</h2>
              <b-icon icon="info" class="info_fade" v-b-toggle="'collapse-4'" />
            </div>
            <b-collapse id="collapse-4">
              <div class="d-flex info-box-animate">
                <div>
                  Just click the checkbox: If you see a green checkmark,
                  congratulations! You’ve passed our robot test (yes, it’s that
                  easy). You can carry on with what you were doing. Sometimes we
                  need some extra info from you to make sure you’re human and
                  not a robot, so we ask you to solve a challenge. Simply follow
                  the on-screen instructions to solve the puzzle and then carry
                  on with your task.
                </div>
                <div class="boxe-close-icon">
                  <b-icon
                    icon="x"
                    class="close-info-box"
                    style="width: 26px; height: 26px;"
                    v-b-toggle="'collapse-4'"
                  />
                </div>
              </div>
            </b-collapse>
            <div>
              <iframe
                src="https://www.google.com/recaptcha/api2/anchor?ar=2&amp;k=6Lc7GmIUAAAAAKDjVWk0q9Y5HhN5bNr1ctLZDmnw&amp;co=aHR0cHM6Ly9zaWdudXAubWFpbC5jb206NDQz&amp;hl=en&amp;v=AFBwIe6h0oOL7MOVu88LHld-&amp;size=normal&amp;cb=3gu779d297kj"
                width="304"
                height="78"
                role="presentation"
                name="a-ck9nt0e8v2st"
                frameborder="0"
                scrolling="no"
                sandbox="allow-forms allow-popups allow-same-origin allow-scripts allow-top-navigation allow-modals allow-popups-to-escape-sandbox"
              />
            </div>
            <div class="protect-field mt-4 mb-4">
              <b-icon
                icon="lock-fill"
                style="width: 24px; height: 24px;"
                class="mr-2"
              ></b-icon>
              <h2>We protect your information</h2>
            </div>
            <div>
              <div data-test="euds-body" class="mb-6">
                You own your information. We will only use your information to
                offer you the products and services you selected. Would you like
                to learn more? Please consult our
                <a target="_blank" href="#">privacy policy</a>
                for additional information.
              </div>
              <div class="a-mb-space-2 mb-4">
                <strong>
                  The
                  <a target="_blank" href="#">
                    Terms and Conditions
                  </a>
                  apply
                </strong>
              </div>
            </div>

            <b-button type="submit" class="accept-button" variant="primary"
              >I agree. Create an email account now.</b-button
            >
          </div>
        </b-form>
      </div>
      <div class="teaser">
        <img src="https://picsum.photos/200/300" />
        <h1>mail.com Email</h1>
        <h2>Email for Everyone</h2>
        <ul class="teaser-text">
          <li>Choose amongst 200 domains</li>
          <li>Free &amp; customized email apps</li>
          <li>Large Attachments up to 30 MB</li>
          <li>Up to 10 Alias Addresses</li>
        </ul>
      </div>
    </div>
  </div>
</template>
<style scoped>
.email-field,
.protect-field,
.gender >>> div[class*="bv-no-focus-ring"] {
  display: flex !important;
}
h2 {
  font-size: 20px !important;
  color: #525252 !important;
}
a {
  color: #004788 !important;
}
.accept-button {
  background-color: #004788;
  width: 100%;
}
.button {
  background-color: #5a88b2 !important;
}
.grid {
  display: grid;
  grid-template-columns: repeat(2, 1fr);
}
.teaser {
  margin: 20% auto;
}
.info_fade {
  margin-left: 8px;
  color: white;
  width: 20px;
  height: 20px;
  border-radius: 3px;
  cursor: pointer;
  background-color: #004788;
}
.birth-date {
  display: grid;
  grid-gap: 8px;
  grid-template-columns: 62px 62px 74px auto;
}
/* Chrome, Safari, Edge, Opera */
input::-webkit-outer-spin-button,
input::-webkit-inner-spin-button {
  -webkit-appearance: none;
  margin: 0;
}

/* Firefox */
input[type="number"] {
  -moz-appearance: textfield;
}

.info-box-animate {
  color: #ffffff;
  padding: 8px;
  background-color: #004788;
  border-radius: 5px;
  margin-bottom: 16px;
}

.boxe-close-icon {
  margin-left: auto;
}
.next-button {
  background-color: #004788;
  color: #ffffff;
}
.back-button {
  color: #004788;
}
.btn-link:hover {
  text-decoration: none !important;
}

.info-box-animate > div:first-child {
  padding: 8px 4px 8px 12px;
}
.email-name {
  grid-area: name;
}
.email-domen {
  grid-area: domen;
}
.check-button {
  grid-area: button;
  margin-left: 8px;
}
/** {*/
/*  transition: all 2s ease-in-out !important;*/
/*}*/

@media (max-width: 1200px) {
  .teaser {
    display: none;
  }
  .grid {
    grid-template-columns: 1fr;
    width: 60%;
  }
}
@media (max-width: 960px) {
  .grid {
    grid-template-columns: 1fr;
    width: 98%;
  }
  .email-field {
    display: grid !important;
    grid-template-areas: " name domen" "button button";
  }
  .check-button {
    margin: 0 !important;
  }
  .check-button > button {
    width: 100%;
  }
  .example-input {
    font-size: 14px;
  }
}

/*------------------------stepper------------------------*/
.stepper {
  display: flex;
  padding: 0;
  height: 32px;
  margin-top: 12px;
  margin-bottom: 0px;
  left: 10px;
  width: calc(100% - 10px);
  list-style: none;
  position: relative;
}
.stepper::before {
  position: absolute;
  top: 0;
  height: 100%;
  content: "";
  background: #ffffff;
}

.stepper__item {
  flex: 100%;
  padding: 5px 20px 20px 40px;
  background: #f0f4f8;
  margin: 0 0 0 -19px;
  color: #f0f4f8;
  /*-webkit-clip-path: polygon(20px 50%, 0% 0%, calc(100% - 20px) 0%, 100% 50%, calc(100% - 20px) 100%, 0% 100%);*/
  -webkit-clip-path: polygon(
    20px 50%,
    10px 0%,
    calc(100% - 10px) 0%,
    100% 50%,
    calc(100% - 10px) 100%,
    10px 100%
  );
}
.stepper__item.current {
  background: #004788;
  color: #ffffff;
}
.stepper__item.complete {
  background: repeating-linear-gradient(
    -65deg,
    #004788,
    #004788 20px,
    #004788 20px,
    #004788 40px
  );
  color: #004788;
}
.stepper__item:first-child {
  -webkit-clip-path: polygon(
    10px 0%,
    calc(100% - 10px) 0%,
    100% 50%,
    calc(100% - 10px) 100%,
    10px 100%
  );
}
.stepper__item:last-child {
  -webkit-clip-path: polygon(20px 50%, 10px 0%, 100% 0%, 100% 100%, 10px 100%);
}
</style>
