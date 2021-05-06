<template>
  <div class="home">
    <div class="container">
      <div class="row mt-2">
        <!--
      -->
        <div class="col-6">
          <h3>Agregar Productos</h3>
          <div class="form-group text-left mt-3">
            <label for="inputsm">Nombre Producto</label>
            <input
              class="form-control input-sm"
              id="inputsm"
              type="text"
              v-model="form.nombre"
            />
          </div>
          <div class="form-group text-left mt-3">
            <label for="inputsm">Descripcion</label>
            <textarea class="form-control input-sm" id="inputsm" type="text" />
          </div>
          <div class="form-group text-left mt-3">
            <label for="inputsm">Precio</label>
            <input
              class="form-control input-sm"
              id="inputsm"
              type="number"
              style="width: 150px"
              placeholder="$5"
              v-model="form.precio"
            />
          </div>
          <div class="d-grid gap-2 mt-2">
            <button class="btn btn-primary" type="button" @click="agregarProducto">
              Agregar Producto
            </button>
          </div>
        </div>

        <div class="col-6">
          <table class="table">
            <thead>
              <tr>
                <th scope="col">#</th>
                <th scope="col">Nombre</th>
                <th scope="col">Precio</th>
                <th scope="col">Fecha</th>
                <th scope="col">Edit</th>
              </tr>
            </thead>
            <tbody>
              <tr v-for="(item, index) in list" :key="index">
                <th scope="row">{{ index + 1 }}</th>
                <td>{{ item.nombre }}</td>
                <td>${{ item.precio }}</td>
                <td>{{ item.fecha }}</td>
                <td class="text-danger c-poiner" @click="selecionarProducto(item)">
                  Eliminar
                </td>
              </tr>
            </tbody>
          </table>
        </div>
      </div>
    </div>
  </div>
</template>

<script>
// @ is an alias to /src

export default {
  name: "Home",
  components: {},
  data() {
    return {
      form: {
        nombre: "",
        precio: null,
      },
      list: [
        {
          id: 1,
          nombre: "Producto 1",
          precio: 1500,
          fecha: "20 de agosto 2020",
        },
      ],
    };
  },

  created() {
    this.axios.get('http://localhost:3000/productos').then((response) => {
      console.log(response.data);
    });
  },

  methods: {
    agregarProducto() {
      this.list.push({
        nombre: this.form.nombre,
        precio: this.form.precio,
      });
    },

    selecionarProducto(item) {
      console.log(item);
    },
  },
};
</script>
