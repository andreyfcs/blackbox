- Pai (relative)
 O filho se move dentro do espaço do pai ✅
- Filho (absolute)
 O filho se move dentro da página inteira (sem controle) ✅

 Ou seja:

- relative = define a área onde o absoluto vai agir.

- absolute = define a posição dentro dessa área.

Imagine que o relative é uma folha de papel, e os elementos absolute são post-its colados nela.

Se você mexe o papel, os post-its vão juntos.
Mas os post-its não empurram o papel nem se reorganizam — eles apenas ficam fixos na posição que você escolheu dentro do papel.

🧩 1️⃣ O que é um "contexto de posicionamento"

O CSS funciona com contextos de posicionamento — ou seja, toda vez que você usa position: relative, você cria uma nova referência local.

Então, quando um elemento filho usa position: absolute, o navegador pergunta:

“Beleza, em relação a quem eu devo me posicionar?”

E ele vai procurar, de dentro pra fora, o primeiro pai que tenha position: relative, absolute, fixed ou sticky.
Esse será o referencial do posicionamento.