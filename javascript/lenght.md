1. O que significa cart.length

length é uma propriedade padrão dos arrays em JavaScript.
Ela retorna a quantidade de elementos dentro do array.
O que é cart?
cart é uma variável de estado (state) — geralmente criada com React Hooks, algo assim:

const [cart, setCart] = useState([]);

- Ou seja:

cart guarda todos os itens que você adicionou ao carrinho.
setCart é a função usada para atualizar esse array (adicionar, remover, alterar quantidade, etc).

- Exemplo simples:

const cart = ['banana', 'maçã', 'laranja'];
console.log(cart.length); // 3

- Então quando você escreve:

{cart.length > 0 ? ( ... ) : ( ... )}

- Você está dizendo:

“Se o carrinho tiver mais de 0 itens, mostre os produtos.
Caso contrário, mostre a mensagem ‘O carrinho está vazio’.”

Isso é um operador ternário (condicional de uma linha).
