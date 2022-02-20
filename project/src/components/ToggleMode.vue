<template>
   <div class="toggle">
      <label class="toggle__label">
         <input class="toggle__input" type="checkbox" :checked="mode === 'dark' ? 'checked' : false" @change="$emit('toggle')" />
         <span class="toggle__round"></span>
      </label>
   </div>
</template>

<script>
export default {
   props: ['mode']
};
</script>

<style>
/********************/
.toggle__label {
   position: relative;
   display: inline-block;
   width: 60px;
   height: 34px;
}

.toggle__input {
   opacity: 0;
   width: 0;
   height: 0;
}

.toggle__round {
   position: absolute;
   cursor: pointer;
   top: 0;
   right: 0;
   left: 0;
   bottom: 0;
   background: #15202b;
   transition: 0.4s;
}

.toggle__round::before {
   position: absolute;
   content: ''; /* circle */
   height: 26px;
   width: 26px;
   left: 4px;
   bottom: 4px;
   background: white;
   border-radius: 45px;
   transition: 0.4s;
}

.toggle__input:checked + .toggle__round {
   background: red;
} 

.toggle__input:focus + .toggle__round {
   box-shadow: 0 0 50px red;
}

.toggle__input:checked + .toggle__round:before {
   transform: translateX(26px);
}

.toggle__round {
   border-radius: 34px;
}

.toggler__round::before {
   border-radius: 50%;
}
</style>
