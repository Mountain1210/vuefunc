<template>
<li class="mu" @click="$emit('select')"><span>{{name}}</span>
<div id="triangledown"></div>
                                <ul class="submenu" >
                                    <li class="addsubmenu" @click.stop="$emit('addsub')">+</li>
                                </ul>
                            </li>
                            
</template>

<script>
export default {
    name:'mainli',
    props:["name"],
    data(){
        return {
            
        }
    }
}
</script>

<style></style>