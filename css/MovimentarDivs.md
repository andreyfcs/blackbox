Quando você altera, por exemplo:

className="absolute top-5 left-10"

Esses valores (top-5, left-10) não são pixels, mas espaçamentos do Tailwind, que seguem uma escala.

Classe	Valor aproximado
top-1	0.25rem (4px)
top-5	1.25rem (20px)
top-10	2.5rem (40px)
top-20	5rem (80px)

Então quando você troca left-10 pra left-15, ele na verdade muda dezenas de pixels, o que parece um “salto”.

💡 Dica: use valores arbitrários com Tailwind, assim:

top-[15px] left-[25px]

Isso dá controle total em pixels, igual ao CSS puro.