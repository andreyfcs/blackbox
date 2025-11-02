1️⃣ Criar arrow function para evento de teclado

- Cria uma função que será chamada quando uma tecla for pressionada

const funcaoTeclaEnter = (e) => {
  if (e.key === "Enter") {
    variavelAEnviar();
  }
};

Explicação:

e → representa o evento do teclado (informações sobre a tecla pressionada).

e.key === "Enter" → verifica se a tecla pressionada foi Enter.

variavelAEnviar() → função que você quer executar ao pressionar Enter (por exemplo, adicionar o produto ao carrinho).

2️⃣ Criar input controlado que usa essa função

<input
  type="text"                          // Tipo do input: texto
  placeholder="Digite o código aqui"   // Texto de dica dentro do input
  value={valorDigitado}                // Valor do input vindo do estado React
  onChange={(e) => setValorDigitado(e.target.value)} // Atualiza o estado conforme digita
  onKeyDown={funcaoTeclaEnter}         // Chama a função quando pressiona qualquer tecla
  className="border p-2 rounded"       // Estilo do input (Tailwind CSS)
 />

Explicação do input:

value={valorDigitado} → mantém o input sincronizado com o estado React.

onChange={(e) => setValorDigitado(e.target.value)} → atualiza o estado quando o usuário digita.

onKeyDown={funcaoTeclaEnter} → detecta qualquer tecla pressionada; se for Enter, chama a função.

className="border p-2 rounded" → estilo visual do input.