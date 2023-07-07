<template>
    <div>
        <pre>
            {{JSON.stringify(formValues, null,2) }}
        </pre>
    </div>

    <h1 class="text-center font-semibold text-xl">
        <p>today : {{ now }}</p>
        <p>today + 30 : {{ max }}</p>
    </h1>

    <div class="mx-auto w-[60%]">
        <form @submit.prevent="HandleSubmit">

            <div>
                <label>Name</label>
                <input type="text" id="name" v-model.trim="formValues.name">
            </div>

            <div>
                <label>Profile</label>
                <textarea id="profile" v-model="formValues.profile"></textarea>
            </div>

            <div>
                <label for="country" >Country</label>
                <select id="country" v-model="formValues.country">
                        <option value="">Select a country</option>
                        <option value="india">india</option>
                        <option value="Vietnam">Vietnam</option>
                        <option value="Singhapur">Singhapur</option>
                </select>   
            </div>

            <div>
                <label for="job-location" >Country</label>
                <select id="job-location" multiple v-model="formValues.jobLocation">
                        <option value="">Select a country</option>
                        <option value="india">india</option>
                        <option value="Vietnam">Vietnam</option>
                        <option value="Singhapur">Singhapur</option>
                </select>   
            </div>

            <div>
                <input type="checkbox" id="remotework" v-model="formValues.remoteWork">
                <label for="remotework"> Open to remote work?</label>
            </div>

            <div>
                <input type="checkbox" id="remotework" v-model="formValues.remoteWork" true-value="Yes" false-value="No" >
                <label for="remotework"> Open to remote work?</label>
            </div>

            <div>
                <label > Skill Set</label>
                <input type="checkbox" id="html" value="html" v-model="formValues.skillset">
                <label for="html">HTML</label>

                <input type="checkbox" id="css" value="css" v-model="formValues.skillset">
                <label for="css">CSS</label>

                <input type="checkbox" id="javascript" value="javascript" v-model="formValues.skillset">
                <label for="javascript">Javascript</label>

                <input type="checkbox" id="python" value="python" v-model="formValues.skillset">
                <label for="python">Python</label>

            </div>


            <div>
                <label >Year of Experinece</label>
                <input type="radio" id="0-2" value="0-2" v-model="formValues.experinece">
                <label for="0-2">0-2</label>

                <input type="radio" id="3-5" value="3-5" v-model="formValues.experinece">
                <label for="3-5">3-5</label>

                <input type="radio" id="6-10" value="6-10" v-model="formValues.experinece">
                <label for="6-10">6-10</label>
            </div>

            <div>
                <label for="fees">Fees</label>
                <input type="text"  id="fees" v-model.number="formValues.fees">
                <p>{{ formValues.fees}}</p>
            </div>


            <div>
                <input type="date" :min="max" :max="min">
            </div>
            <button type="submit" class="px-2 py-1 bg-orange-300 w-full my-2 rounded hover:scale-[0.94] duration-300">Submit</button>
        </form>
    </div>


    
</template>


<script setup>

const formValues = reactive({
    name:"",
    profile:"",
    country:"",
    jobLocation:[],
    remoteWork:false,
    skillset:[],
    experinece:"",
    fees:"",
})

const HandleSubmit = ()=>{
    console.log("submitted form",formValues)
}



let now = ref(new Date());
let max =ref(new Date() );
max.value.setDate(max.value.getDate() + 30)
now = now.value.toISOString().split("T")[0]
max = max.value.toISOString().split("T")[0]



</script>
