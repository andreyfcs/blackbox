1. Desfazer todas as alterações não commitadas
  - Se você ainda não fez commit das mudanças (só alterou arquivos, adicionou, etc.), basta usar:

git restore .

ou, em versões mais antigas do Git:

git checkout -- .

2. Se você também adicionou arquivos ao staging (git add)
  - Se você já rodou git add e quer limpar tudo (tirar do staging e voltar ao commit anterior):

git reset --hard HEAD

Esse comando:
- Remove arquivos do staging;
- Desfaz todas as alterações locais;
- Volta tudo exatamente ao último commit.

3. Se quer apenas um arquivo específico(Exemplo: README.md)

git restore README.md
