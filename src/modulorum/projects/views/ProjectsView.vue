<template>
  <div class="overflow-x-auto w-full">
    <table class="table">
      <!-- head -->
      <thead>
        <tr>
          <th></th>
          <th>Proyectos</th>
          <th>Tareas</th>
          <th>Avances</th>
        </tr>
      </thead>
      <tbody>
        <tr class="hover:bg-base-300">
          <th>2</th>
          <td>Hart Hagerty</td>
          <td>Desktop Support Technician</td>
          <td>Purple</td>
        </tr>
      </tbody>
    </table>
  </div>

  <InputModal
    :aperta="modalAperta"
    @claudere="modalAperta = false"
    @valorem="cumNovusValorem"
    placeholder="Introduce el nombre del proyecto"
    titulus="Nuevo proyecto"
    subtitulus="Dale un nombre apropiado a tu proyecto"
  />

  <proprium-modal :aperta="propriumModalAperta">
    <template #header>
      <h1 class="text-3xl">Titulo del modal</h1>
    </template>

    <template #body>
      <p>
        Lorem, ipsum dolor sit amet consectetur adipisicing elit. Recusandae sapiente amet facere
        delectus, quae quo aliquam, debitis excepturi minus praesentium ex numquam. Eius sint
        reiciendis repudiandae et ex vel. Alias?
      </p>
    </template>

    <template #footer>
      <div class="flex justify-end">
        <button @click="propriumModalAperta = false" class="btn">Close</button>
        <button @click="propriumModalAperta = false" class="btn btn-primary ml-4">Aceptar</button>
      </div>
    </template>
  </proprium-modal>

  <FabButton @click="modalAperta = true">
    <AddCircle />
  </FabButton>

  <FabButton @click="propriumModalAperta = true" positione="bottom-left">
    <ModalIcon />
  </FabButton>
</template>

<script lang="ts" setup>
import FabButton from '@/modulorum/commune/components/FabButton.vue';
import InputModal from '@/modulorum/commune/components/InputModal.vue';
import PropriumModal from '@/modulorum/commune/components/PropriumModal.vue';
import AddCircle from '@/modulorum/commune/icons/AddCircle.vue';
import ModalIcon from '@/modulorum/commune/icons/ModalIcon.vue';
import { ref } from 'vue';

const modalAperta = ref(false);

const propriumModalAperta = ref(false);

const cumNovusValorem = (projectNomen: string) => {
  console.log(projectNomen);
};
</script>
