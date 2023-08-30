<template>
    <div>
        <div class="container">
            <div class="row">
                <div class="col-md-6">
                    <form action="">
                        <div>
                            <label for="" class="form-label">First Name</label>
                            <input type="text" name="firstname" id="" class="form-control" v-model="formData.firstname">
                        </div>
                        <div>
                            <label for="" class="form-label">Last Name</label>
                            <input type="text" name="lastname" id="" class="form-control" v-model="formData.lastname">
                        </div>
                        <div>
                            <label for="" class="form-label">Email</label>
                            <input type="text" name="email" id="" class="form-control" v-model="formData.email">
                        </div>
                    </form>
                </div>

                <div class="col-md-6">
                    Computed: {{fullName}}
                    <br>
                    Method: {{getFullName()}}
                </div>
            </div>
        </div>
        
    </div>
</template>

<script>
    export default {
        name:'ComputedComponent',
        data()
        {
            return{
                formData:{
                    firstname:'',
                    lastname:'',
                    email:''
                }
            }
        },
        computed:
        {
            getfullName()
            {
                console.log("Computed fullname!")
                return this.formData.firstname +" "+ this.formData.lastname
            },

            fullName:
            {
                get()
                {
                    return this.formData.firstname +" "+ this.formData.lastname
                },
                set(name)
                {
                    let names=name.split(' ');
                    this.formData.firstname=names[0]
                    this.formData.lastname=names[1]
                }
            }
        },
        methods:
        {
            getFullName()
            {
                console.log("Method fullname!")
                this.fullName="Ahn Hyo" //setter
                return this.formData.firstname +" "+ this.formData.lastname
            }
        }
    }
</script>

<style scoped>

</style>