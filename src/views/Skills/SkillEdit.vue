<script setup>
import useSkills from '../../composable/Skill';
import { onMounted } from 'vue';


    const { skill, getSkill, updateSkill, errors } =  useSkills()
    const props = defineProps({
        id: {
            required: true,
            type: String
        }
    })
    onMounted(() => getSkill(props.id))
</script>

<template>
     <div class="mt-12">
        <form action="" @submit.prevent="updateSkill($route.params.id)" class="max-w-md mx-auto p-4 bg-white rounded-md">
            <div class="space-y-6">
                <div class="mb-6">
                    <label for="name" class="block mb-2 text-sm font-medium text-gray-900 ">
                        Name*
                    </label>
                    <input type="text" id="name" v-model="skill.name" class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5 ">
                    <div v-if="errors.name" >
                        <span class="mt-1 text-xs italic text-red-500">
                            {{ errors.name[0] }}
                        </span>
                    </div>
                </div>
                <div class="mb-6">
                    <label for="slug" class="block mb-2 text-sm font-medium text-gray-900 ">
                        Slug*
                    </label>
                    <input type="text" id="name" v-model="skill.slug" class="bg-gray-50 border border-gray-300 text-gray-900 text-sm rounded-lg focus:ring-blue-500 focus:border-blue-500 block w-full p-2.5 ">
                    <div v-if="errors.slug" >
                        <span class="mt-1 text-xs italic text-red-500">
                            {{ errors.slug[0] }}
                        </span>
                    </div>
                </div>
                <div class="mt-3">
                    <button  class="px-4 py-2 bg-blue-500 hover:bg-indigo-700 text-black hover:text-white shadow-xl font-semibold text-xs rounded" type="submit">Store</button>
                </div>
            </div>
        </form>
    </div>
</template>