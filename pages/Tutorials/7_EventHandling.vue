<template>

    <!-- Inline Handlers -->
    <div class="text-center">
        <h1 class="font-bold">Example 1 : Inline Handlers</h1>
        <h1>Count : {{ count }}</h1>
        <div class="flex flex-col">
            <button class="px-2 py-1 bg-green-300 mx-auto my-2 rounded hover:scale-[0.94] duration-300" v-on:click="count++">Increase</button>
            <button class="px-2 py-1 bg-red-300 mx-auto rounded hover:scale-[0.94] duration-300" @click="count--">Decrease</button>
        </div>
    </div>

    <!-- Calling  Methods -->
    <div class="text-center">
        <h1 class="font-bold">Example 2 : Calling Methods</h1>
        <div class="flex flex-col">
            <button class="px-2 py-1 bg-green-300 mx-auto my-2 rounded hover:scale-[0.94] duration-300" v-on:click="method()">call method</button>
            <button class="px-2 py-1 bg-orange-300 mx-auto my-2 rounded hover:scale-[0.94] duration-300" v-on:click="method2('Pruthviraj')">call method 2</button>
        </div>

       
    </div>

    <!-- Accssing Event Argument -->
    <div class="text-center">
        <h1 class="font-bold">Example 3 : Accessing event</h1>
        <div class="flex flex-col">
            <button class="px-2 py-1 bg-green-300 mx-auto my-2 rounded hover:scale-[0.94] duration-300" @click="method3($e)">call method </button>
          
        </div>
    </div>

    <!-- Method Handler -->
    <div class="text-center">
        <h1 class="font-bold">Example 4 : Method Handlers</h1>
        <div class="flex flex-col">
            <button class="px-2 py-1 bg-green-300 mx-auto my-2 rounded hover:scale-[0.94] duration-300" @click="method3">call method </button>
          
        </div>
    </div>


<!---------------------------------------------------------------------------------------- -->
        <div class="text-center">
            <hr>
            <h1 class="font-bold text-2xl">Modifier</h1>


        <div class="text-center">
            <h1 class="font-bold">Example 1 </h1>
            <div class="flex flex-col">
                 <a @click.prevent="CheckData" href="https://www.google.com">goto Google</a>
           </div>
       </div>


        <div class="text-center">
            <h1 class="font-bold">Example 2: Form submit </h1>
            <form @submit.prevent="HandleSubmit">
                <button type="submit" class="px-2 py-1 bg-orange-300 mx-auto my-2 rounded hover:scale-[0.94] duration-300" >Submit </button>
        
            </form>
       </div>

        <div class="text-center">
            <h1 class="font-bold">Example 3: Key Modifier </h1>
            <input @keyup.enter="OnPressEnter" type="text" class="bg-orange-300">
       </div>

        <div class="text-center">
            <h1 class="font-bold">Example 4: System Modifier </h1>
            <h2>alt + enter</h2>
            <input @keyup.alt.enter="OnPressAltEnter" type="text" class="bg-orange-300">

            <h2>Ctrl + click</h2>
            <input @click.ctrl="OnClickCtrl" type="text" class="bg-orange-300">

            <h2>Ctrl + any key</h2>
            <input @keyup.ctrl="OnPressCtrl" type="text" class="bg-orange-300">
       </div>

       <div class="text-center">
            <h1 class="font-bold">Example 4: Exact Modifier </h1>
            <h2> triger when exact 'Ctrl' press</h2>
            <input @click.ctrl.exact="OnPressCtrl" type="text" class="bg-orange-300">

            <h2> triger when no system keys press</h2>
            <input @keyup="Nosys" type="text" class="bg-orange-300">
       </div>

       <div class="text-center">
            <h1 class="font-bold">Example 5: Mouse Button Modifier </h1>
            <h2> triger when Right click </h2>
            <button @click.right="Click('right')" class="px-2 py-1 bg-orange-300 mx-auto my-2 rounded hover:scale-[0.94] duration-300" >Right Click </button>
          
            <h2> triger when leftclick </h2>
            <button @click.left="Click('left')" class="px-2 py-1 bg-orange-300 mx-auto my-2 rounded hover:scale-[0.94] duration-300" >Left Click </button>
          
            <h2> triger when no system keys press</h2>
            <input @keyup="Nosys" type="text" class="bg-orange-300">
       </div>

       <div class="text-center">
            <h1 class="font-bold">Example 6: Multipal events </h1>
            <button v-on="{ mousedown:MouseDown , mouseup:MouseUp}" class="px-2 py-1 bg-orange-300 mx-auto my-2 rounded hover:scale-[0.94] duration-300" >Click </button>



            <button @click="FirstEvent(), SecondEvent()" class="px-2 py-1 bg-orange-300 mx-auto my-2 rounded hover:scale-[0.94] duration-300" >Click </button>
       </div>



        </div>



</template>

<script setup>


 const count = ref(0);


 function method(){
    alert("method called");
    console.log("method called");
 }
 function method2(para){
    alert("method 2 called with parameter "+para);
    console.log("method 2 called",para);
 }
 function method3(e){
  
    console.log("event",e);
 }


 function CheckData(){
    console.log("check data")
 }

 function HandleSubmit(){
    console.log('submited')
    alert('submited')
 }


function OnPressEnter(){
    alert("Enter key is press")
}

function OnPressAltEnter(){
    alert("Alt + Enter key is press")
}
function OnClickCtrl(){
    alert("ctrl + click  is press")
}
function OnPressCtrl(){
    alert("ctrl is press")
}
function Nosys(){
    alert("Not a system key ")
}
function Click(click){
    alert(click+" click")
}


function MouseUp(){
    console.log("Mouse up is triger")
}
function MouseDown(){
    console.log("Mouse Down is triger")
}
function FirstEvent(){
    alert("First Event is triger")
}
function SecondEvent(){
    alert("Second Event is triger")
}
</script>