// Lista de elementos y precios
const items = ["Pizza", "Pasta", "Ensalada", "Sopa", "Bebida", "Postre", "Hamburguesa", "Sandwich", "Taco"];
const precios = [8.50, 7.00, 5.50, 4.00, 1.50, 3.00, 6.00, 5.00, 4.50];

// Estado de las mesas
const mesas = {};

// Generar botones de mesas
const mesasContainer = document.getElementById('mesas-container');
for (let i = 1; i <= 9; i++) {
    const button = document.createElement('button');
    button.textContent = `Mesa ${i}`;
    button.className = 'mesa-button';
    button.onclick = () => mostrarPedidos(i);
    mesasContainer.appendChild(button);
}

// Mostrar pedidos de una mesa
function mostrarPedidos(numeroMesa) {
    const pedidos = mesas[numeroMesa] || [];
    const textArea = document.getElementById('text-area');
    textArea.value = `Mesa ${numeroMesa}:\n`;
    pedidos.forEach((pedido, index) => {
        textArea.value += `${index + 1}. ${pedido}\n`;
    });
}

// Ingresar pedido
function ingresarPedido() {
    const numeroMesa = prompt("Número de mesa:");
    if (!numeroMesa || isNaN(numeroMesa) || numeroMesa < 1 || numeroMesa > 9) {
        alert("Número de mesa inválido.");
        return;
    }

    const pedido = prompt("Ingrese el pedido:");
    if (!pedido) return;

    if (!mesas[numeroMesa]) {
        mesas[numeroMesa] = [];
    }
    mesas[numeroMesa].push(pedido);
    mostrarPedidos(numeroMesa);
}

// Editar pedido
function editarPedido() {
    const numeroMesa = prompt("Número de mesa:");
    if (!numeroMesa || isNaN(numeroMesa) || numeroMesa < 1 || numeroMesa > 9) {
        alert("Número de mesa inválido.");
        return;
    }

    const indice = prompt("Número del pedido a editar:") - 1;
    const nuevoPedido = prompt("Ingrese el nuevo pedido:");
    if (!nuevoPedido) return;

    if (mesas[numeroMesa] && mesas[numeroMesa][indice]) {
        mesas[numeroMesa][indice] = nuevoPedido;
        mostrarPedidos(numeroMesa);
    } else {
        alert("Número de pedido inválido.");
    }
}

// Cerrar pedidos
function cerrarPedidos() {
    const numeroMesa = prompt("Número de mesa:");
    if (!numeroMesa || isNaN(numeroMesa) || numeroMesa < 1 || numeroMesa > 9) {
        alert("Número de mesa inválido.");
        return;
    }

    mostrarDetallePedido(numeroMesa);
}

// Mostrar detalle del pedido
function mostrarDetallePedido(numeroMesa) {
    const pedidos = mesas[numeroMesa] || [];
    let detalle = `Detalle del Pedido - Mesa ${numeroMesa}:\n\n`;
    let total = 0;

    pedidos.forEach(pedido => {
        const indice = items.indexOf(pedido);
        const precio = indice >= 0 ? precios[indice] : 0;
        detalle += `${pedido}: $${precio.toFixed(2)}\n`;
        total += precio;
    });

    detalle += `\nTotal: $${total.toFixed(2)}`;
    alert(detalle);

    // Limpiar los pedidos de la mesa
    mesas[numeroMesa] = [];
    mostrarPedidos(numeroMesa);
}
