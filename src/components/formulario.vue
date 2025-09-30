<template>
  <div class="bg-white p-8 rounded-2xl shadow-lg w-full max-w-md mx-auto mt-10">
    <h2 class="text-2xl font-bold mb-6 text-gray-800 text-center">Contáctanos</h2>
    <form @submit.prevent="submitForm" class="space-y-5">
      <div>
        <label for="name" class="block text-gray-700 mb-2">Nombre</label>
        <input type="text" id="name" v-model="form.name" placeholder="Tu nombre"
               class="w-full px-4 py-2 border rounded-lg focus:outline-none focus:ring-2 focus:ring-blue-400">
      </div>

      <div>
        <label for="email" class="block text-gray-700 mb-2">Email</label>
        <input type="email" id="email" v-model="form.email" placeholder="Tu email"
               class="w-full px-4 py-2 border rounded-lg focus:outline-none focus:ring-2 focus:ring-blue-400">
      </div>

      <div>
        <label for="message" class="block text-gray-700 mb-2">Mensaje</label>
        <textarea id="message" v-model="form.message" placeholder="Tu mensaje" rows="4"
                  class="w-full px-4 py-2 border rounded-lg focus:outline-none focus:ring-2 focus:ring-blue-400"></textarea>
      </div>

      <button type="submit" class="w-full bg-blue-500 text-white py-2 px-4 rounded-lg hover:bg-blue-600 transition">
        Enviar
      </button>
    </form>

    <div v-if="submitted" class="mt-4 p-4 bg-green-100 text-green-800 rounded-lg">
      Formulario enviado correctamente
    </div>
  </div>
</template>

<script>
export default {
  name: 'Formulario',
  data() {
    return {
      form: {
        name: '',
        email: '',
        message: ''
      },
      submitted: false
    };
  },
  methods: {
    submitForm() {
      console.log('Datos del formulario:', this.form);
      this.submitted = true;
      this.form.name = '';
      this.form.email = '';
      this.form.message = '';
    }
  }
};
</script>
