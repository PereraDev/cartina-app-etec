<script setup>
import { ref } from 'vue'
const escuro = ref(false)

function alternarTema() {
  escuro.value = !escuro.value
  document.documentElement.classList.toggle('dark', 
    escuro.value)
}

defineProps({
  totalItens: {
    type: Number,
    default: 0
  }
})
</script>

<template>
    <header class="sticky top-0 z-10 bg-escola-600 text-white shadow-md">
      <nav class="mx-auto flex max-w-6xl items-center justify-between px-4 py-3">
        <a href="#" class="flex items-center gap-2 text-xl font-bold">
          <span>🍔</span> Cantina da Escola
        </a>

        <div class="flex items-center gap-2 sm:gap-4">
          <a href="#" class="rounded-lg bg-escola-700 px-3 py-2 font-semibold">Cardápio</a>
          <a href="#" class="rounded-lg px-3 py-2 transition-colors hover:bg-escola-700">Meus Pedidos</a>
          <a href="#" class="relative rounded-lg px-3 py-2 transition-colors hover:bg-escola-700">
            🛒 Carrinho 
            <span class="absolute -top-2 -right-2 flex h-6 w-6 items-center justify-center rounded-full bg-yellow-500 text-xs text-black">
              {{ totalItens }}
            </span>
          </a>
          <button
            @click="alternarTema"
            class="rounded-lg px-2 py-2 transition-colors hover:bg-escola-700"
            title="Modo escuro"
          >
            {{ escuro ? '☀️' : '🌙' }}
          </button>
        </div>
      </nav>
    </header>
</template>
