<script lang="ts">
import { obterReceitas} from '@/http/index'
import type IReceitas from '@/interfaces/IReceitas';

export default {
    data(){
        return {
            receitas: [] as IReceitas[]
        }
    },
    async created() {
        this.receitas = await obterReceitas();
    },

}
</script>


<template>
<section>
    <h1 class="titulo-receita"> Receitas</h1>
        <p class="legenda">
          Veja as opções de receitas que encontramos com os ingredientes que você tem por aí!
        </p>

        <ul>

        </ul>
    
</section>
</template>


<style scoped>
.titulo-receita {
    font-weight: bold;
    color: var(--verde-medio, #3D6D4A);
}

.legenda{
    color: var(--cinza, #414040)
}

.receita {
  margin-bottom: 1rem;
  display: flex;
  justify-content: center;
  gap: 1.5rem;
  flex-wrap: wrap;
}



</style>