<script>
export default {
  name: "HelloWorld",
  data() {
    return {
      isHidden: false,
      account: {
        username: "",
        domain: ""
      },
      form: {
        gender: "",
        first_name: "",
        last_name: "",
        country: "",
        state: null,
        birth: {
          day: "",
          month: "",
          year: "",
        },
        password: "",
        password_repeat: "",
        recovery: {
          sms: {
            country: {
              name: "US",
              phone_code: "1"
            },
            phone_number: "123456789"
          },
          email: "myusername@mail.com"
        },
        smsStatus: "",
        emailStatus: "",
        checked: [],
      },
      domains: [{ text: '@mail.com', value: '@mail.com' }, '@email.com', '@gmail.com', '@usarb.com'],
      countries: [{ text: 'United states of America', value: 'United states of America' }, 'United states of IVIoldova', 'Molfova', ''],
      states: [{ text: 'Alska', value: 'Alska' }, 'Maldivia', 'Salat Olivie', 'Vreau acasa'],
      show: true
    }
  },
  methods: {
    onSubmit(evt) {
      evt.preventDefault()
      alert(JSON.stringify(this.form))
    },
    randomValue() {
      this.value = Math.random() * this.max;
    }
  }
}
</script>

<template>
  <div class="container grid">
    <div>
      <div class="d-flex mb-4 mt-6">
        <h2>Create your email account</h2>
        <b-icon icon="info" class="info_fade" style="width: 20px; height: 20px;"/>
      </div>
      <b-form @submit="onSubmit" v-if="show">
        <div class="email-field">
          <b-form-group
            id="input-group-1"
            label-for="input-1"
          >
            <b-form-input
              id="input-1"
              v-model="account.username"
              type="text"
              required
              placeholder="Enter email"
            ></b-form-input>
          </b-form-group>
          <b-form-group id="input-group-2" label-for="input-2">
            <b-form-select
              id="input-3"
              v-model="account.domain"
              :options="domains"
              required
            ></b-form-select>
          </b-form-group>
          <div class="ml-2">
            <b-button class="button">Check</b-button>
          </div>
        </div>
        <h2>Personal details</h2>
        <div>
          <b-form-group class="gender">
            <b-form-radio v-model="form.gender" name="female" value="f" class="mr-4">Ms</b-form-radio>
            <b-form-radio v-model="form.gender" name="male" value="m">Mr</b-form-radio>
          </b-form-group>
        </div>

        <b-form-group id="input-group-3" label="First Name:" label-for="input-3">
          <b-form-input
            id="input-2"
            v-model="form.first_name"
            required
            placeholder="Enter name"
          ></b-form-input>
        </b-form-group>
        <b-form-group id="input-group-4" label="Last Name:" label-for="input-4">
          <b-form-input
            id="input-2"
            v-model="form.last_name"
            required
            placeholder="Enter name"
          ></b-form-input>
        </b-form-group>
        <b-form-group id="input-group-6" label="Country" label-for="input-6">
          <b-form-select
            id="input-3"
            v-model="form.country"
            :options="countries"
            required
          ></b-form-select>
        </b-form-group>
        <b-form-group id="input-group-7" label="State" label-for="input-7">
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
        <div class="d-flex mt-8 mb-5">
          <h2>Password</h2>
          <b-icon icon="info" class="info_fade" style="width: 24px; height: 24px;"/>
        </div>
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
            <b-progress height="5px" class="mt-2" max="100" show-value>
              <b-progress-bar :value="value * (1.5 / 10)" variant="danger"/>
              <b-progress-bar :value="value * (2.5 / 10)" variant="warning"/>
              <b-progress-bar :value="value * (6 / 10)" variant="success"/>
            </b-progress>
          </div>
          <b-form-group label="Repeat a password" class="mt-3">
            <b-form-input
              id="input-2"
              v-model="form.repeatPassword"
              type="password"
              required
            ></b-form-input>
          </b-form-group>
        </div>
        <div class="d-flex mt-8 mb-5">
          <h2>Password recovery options</h2>
          <b-icon icon="info" class="info_fade" style="width: 24px; height: 24px;"/>
        </div>
        <div class="mt-5 mb-4">
          <b-form-checkbox
            id="checkbox-1"
            v-model="smsStatus"
            name="checkbox-1"
            value="accepted"
            unchecked-value="not_accepted"
          >
            By SMS (recomended)
          </b-form-checkbox>
        </div>
        <div>
          <div class="mb-2">Cellphone number</div>
          <div class="email-field">
            <b-form-group id="" label-for="input-2">
              <b-form-select
                id="input-3"
                v-model="form.email"
                :options="domains"
                required
              ></b-form-select>
            </b-form-group>
            <b-form-group
              label-for="input-1"
            >
              <b-form-input
                id="input-1"
                v-model="form.emailName"
                type="text"
                required
                placeholder="Enter email"
              ></b-form-input>
            </b-form-group>
          </div>
          <div class="mt-5 mb-4">
            <b-form-checkbox
              v-model="emailStatus"
              name="checkbox-2"
              value="accepted"
              unchecked-value="not_accepted"
              @click="isHidden = !isHidden"
            >
              By email
            </b-form-checkbox>
          </div>
          <b-form-group
            v-show="!isHidden"
            label="Email address:"
            label-for="input-1"
          >
            <b-form-input
              id="input-1"
              v-model="form.email"
              type="email"
              required
              placeholder="example@mail.ru"
            ></b-form-input>
          </b-form-group>
        </div>
        <div class="d-flex mt-7 mb-4">
          <h2>Security prompt</h2>
          <b-icon icon="info" class="info_fade" style="width: 24px; height: 24px;"/>
        </div>
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
          <b-icon icon="lock-fill" style="width: 24px; height: 24px;" class="mr-2"></b-icon>
          <h2>We protect your information</h2>
        </div>
        <div>
          <div data-test="euds-body" class="mb-6">You own your information. We will only use your information to offer you the products and services you selected. Would you like to learn more? Please consult our
            <a
              target="_blank"
              href="#">privacy policy</a>
            for additional information.
          </div>
          <div class="a-mb-space-2 mb-4">
            <strong> The
              <a target="_blank" href="https://www.mail.com/company/terms/">
                Terms and Conditions
              </a> apply
            </strong>
          </div>
        </div>


        <b-button type="submit" class="accept-button" variant="primary">I agree. Create an email account now.</b-button>
      </b-form>
      <b-card class="mt-3" header="Form Data Result">
        <pre class="m-0">{{ form }}</pre>
        <hr>
        <pre class="m-0">{{ account }}</pre>
      </b-card>
    </div>
    <div class="teaser">
      <img src="https://lh3.googleusercontent.com/proxy/A9F6iSZbgV2pd0KKe4nh74r1zcky1BQeRRWcp7ytEBx7DvERruAt2ZF5xaTjg_Y7foiVEUpYMAtARDAARmequ3E3VNABqrk12_N2MCYzdJ2CihsGdMmyoNAJ7Gac">
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
</template>
<style scoped>
  .email-field,
  .protect-field,
  .gender >>> div[class*='bv-no-focus-ring']{
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
    background-color: #5A88B2 !important;
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
    background-color: #004788;
  }
  .birth-date {
    display: grid;
    grid-template-columns: 62px 62px 74px auto;
  }
  /* Chrome, Safari, Edge, Opera */
  input::-webkit-outer-spin-button,
  input::-webkit-inner-spin-button {
    -webkit-appearance: none;
    margin: 0;
  }

  /* Firefox */
  input[type=number] {
    -moz-appearance: textfield;
  }
  @media (max-width: 1200px) {
    .teaser {
      display: none;
    }
  }
</style>
