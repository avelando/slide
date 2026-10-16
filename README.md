# Capa Beamer com dois formatos

## Compilação

Use `main.tex` com `pdfLaTeX`. Execute a compilação duas vezes para posicionar corretamente os elementos TikZ.

## Seleção do formato

Edite `config/dados.tex`:

- `\FormatoCapa{texto}`: somente os **nomes** dos autores em negrito, com índices de afiliação sobrescritos no início, e as instituições identificadas logo abaixo. Fotografias dos autores não são exibidas. Permite até 9 autores em até 3 linhas.
- `\FormatoCapa{fotos}`: de 1 a 5 retratos circulares **em uma única linha**, com nomes e afiliações abaixo de cada fotografia. O comando emite um erro se houver mais de 5 autores.

## Cadastro de instituições

`\AdicionarInstituicao{SIGLA}{Nome completo}{caminho/da/logo.png}`

A ordem define automaticamente os índices 1, 2, 3 etc. O nome completo é usado apenas nas notas no formato textual. Uma instituição sem logotipo cadastrado recebe um retângulo com a sigla.

## Cadastro de autores

`\AdicionarAutor[Nome curto para fotos]{Nome completo}{SIGLA}{caminho/da/foto.jpg}`

O parâmetro entre colchetes é opcional. Se omitido, o nome completo é usado também na versão fotográfica. O nome completo nunca é abreviado automaticamente no formato textual. A foto informada é ignorada inteiramente no formato textual.

Para cadastrar um autor sem fotografia use `\AdicionarAutor{Nome Completo}{SIGLA}{}`. Em modo `fotos`, aparece uma inicial como substituto visual.

Para múltiplas afiliações, separe siglas por vírgula: `{UFPI,IFPI}`. No formato textual as referências serão sobrescritas no início do nome (ex.: ²,³).

## Conteúdo original

Os arquivos enviados continham apenas o logotipo do ICMC/USP. UFPI e IFPI aparecem como siglas até serem adicionados logotipos próprios. Nomes pessoais que constavam abreviados no arquivo original foram mantidos como fornecidos; complete os nomes oficiais no primeiro argumento de `\AdicionarAutor`. Foi incluído `Avelar Rodrigues de Sousa` como exemplo de nome completo com `Avelar Rodrigues` como opção curta para a capa com fotos.
