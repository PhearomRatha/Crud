<script>
export default{
    name: "Props"
}

</script>
<template>
    <div>
        
        <slot name="avta">
            <img src="https://i.pinimg.com/originals/d7/40/d5/d740d5f3f13f5755888bb807fea33f37.gif" alt="">
        </slot>
        <slot name="name"></slot>
        <slot name="des"></slot>
        
    </div>

</template>