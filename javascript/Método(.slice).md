O método slice() é totalmente compatível com React/Next.js, porque ele é apenas um método de array do JavaScript — e React trabalha normalmente com arrays para renderização com map().

1️⃣ O que faz slice()

O slice() retorna uma cópia de parte do array sem modificar o array original.

Sintaxe:

array.slice(início, fim)

    - início → índice inicial (inclusivo)

    - fim → índice final (exclusivo)

    - Se fim não for passado, vai até o final do array

    - Índices negativos contam de trás pra frente (-1 é o último elemento, -2 o penúltimo, etc.)

2️⃣ Exemplos simples

const array = [10, 20, 30, 40, 50];

array.slice(0, 3);  // [10, 20, 30] → do índice 0 até 2
array.slice(2);     // [30, 40, 50] → do índice 2 até o final
array.slice(-1);    // [50] → último elemento
array.slice(-2);    // [40, 50] → dois últimos elementos

🔹 Importante: não altera o array original. Ele só cria uma nova “visão” do array.

3️⃣ Uso no React/Next.js

O slice() é perfeito quando você quer renderizar apenas parte de um array no JSX:

const cart = [
  { id: 1, name: "Produto A" },
  { id: 2, name: "Produto B" },
  { id: 3, name: "Produto C" }
];

return (
  <div>
    {cart.slice(-1).map(item => (
      <p key={item.id}>{item.name}</p>
    ))}
  </div>
);

Resultado renderizado:

Produto C

✅ Ou seja, apenas o último item do carrinho aparece, mas o cart continua intacto para enviar para outro lugar ou usar depois.

4️⃣ Usos avançados

- Mostrar os últimos 3 itens adicionados:
cart.slice(-3).map(item => <p key={item.id}>{item.name}</p>)

- Mostrar todos menos o último item:
cart.slice(0, -1).map(item => <p key={item.id}>{item.name}</p>)

- Combinar com reverse() para mostrar últimos itens do mais recente para o mais antigo:
cart.slice(-3).reverse().map(item => <p key={item.id}>{item.name}</p>)
