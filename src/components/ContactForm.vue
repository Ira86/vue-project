<template>
    <div class="form-wrap container">
        <!-- Om inte submittat visa input fält med knapp -->
        <!-- V-If -->
        <div v-if="!submitted">
            <div class="form-group">
                <label class="form-label" for="name">Name</label>
                <input class="form-control" type="text" id="name" v-model="name">
                <label class="form-label" for="email">Email address</label>
                <!-- V-model, v-bind with classes and a v-on -->
                <input
                    v-model="email"
                    v-bind:class="{
                        'form-control': true,
                        'is-invalid': !validEmail(email) && emailBlured
                    }"
                    v-on:blur="emailBlured = true"
                />
                 <label class="form-label" for="subject">Subject</label>
                <input class="form-control" type="text" id="subject" v-model="subject">
                <label class="form-label" for="message">Message</label>
                <textarea class="form-control" id="message" v-model="message"></textarea>

                <div class="invalid-feedback">
                    Vänligen fyll i giltligt mail adress.
                </div>
            </div>
            <div class="form-group">
                <a
                    type="submit"
                    href="#"
                    v-on:click.stop.prevent="submit"
                    class="btn btn-lg btn-success"
                    >Skicka</a
                >
            </div>
        </div>
        <div v-else class="alert alert-success" role="alert">
            <!-- Använder V-Model -->
            <h5>Tack {{ name }} för din email!</h5>
            <p>Vi älskar alla slags av feedback, din tips kanske kommer synas här snart!</p>
        </div>
    </div>
</template>
<script>
    export default {
        data: function () {
            return {
                email: '',
                name: '',
                subject: '',
                message: '',
                emailBlured: false,
                valid: false,
                submitted: false
            }
        },
        methods: {
            validate: function () {
                this.emailBlured = true
                if (this.validEmail(this.email)) {
                    this.valid = true
                }
            },
            validEmail: function (email) {
                var re = /(.+)@(.+){2,}\.(.+){2,}/
                return re.test(email.toLowerCase())
            },
            submit: function () {
                this.validate()
                if (this.valid) {
                    //THIS IS WHERE YOU SUBMIT DATA TO SERVER
                    this.submitted = true
                }
            } //end submit
        }
    }
</script>
<style scoped>
    #mail {
        margin-top: 5vh;
    }
    .form-wrap {
        padding-top: 15px;
        padding-bottom: 25px;
    }
    .alert {
        padding-top: 2vh;
    }
    .alert h5 {
        margin-bottom: 0rem;
    }
    .form-group {
        padding-top: 1vh;
    }
</style>