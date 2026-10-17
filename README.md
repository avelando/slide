# Capa Beamer — tamanhos e posições ajustáveis

## Compilação

Abra `main.tex` no Overleaf e selecione pdfLaTeX. Em ambiente local, execute duas vezes `pdflatex -interaction=nonstopmode -halt-on-error main.tex` para resolver coordenadas TikZ.

## Arquivos

- `main.tex`: documento principal, sem alterações necessárias.
- `config/tema.tex`: implementação da capa e comandos de personalização.
- `config/dados.tex`: informações e controles de aparência, edite apenas este arquivo para mudanças comuns.
- `imagens/logos/`: logotipos das instituições.
- `imagens/autores/`: retratos utilizados no formato fotos.

## Formatos

- `\FormatoCapa{fotos}`: até cinco autores alinhados horizontalmente, com retratos e nomes.
- `\FormatoCapa{texto}`: até nove autores, nomes completos, notas numeradas de afiliação sem retratos.

## Ajustes recomendados

```latex
\TamanhoPadraoLogos{3.35cm}{1.20cm}
\TamanhoLogo{ICMC/USP}{3.05cm}{1.23cm}
\TamanhoLogo{UFPI}{1.55cm}{1.34cm}
\TamanhoLogo{IFPI}{3.24cm}{1.04cm}
\PosicaoLogos{0.38cm}
\PosicaoTitulo{2.62cm}
\PosicaoAutores{4.70cm}
```

`\TamanhoPadraoLogos{largura}{altura}` define o limite padrão das imagens; `\TamanhoLogo{sigla}{largura}{altura}` sobrescreve somente uma instituição. Os limites de tamanho não distorcem a proporção da imagem. A largura disponível por instituição depende da quantidade de logos e da largura do slide.

`\PosicaoLogos`, `\PosicaoTitulo` e `\PosicaoAutores` indicam a distância vertical a partir da borda superior do slide. Valores maiores deslocam o elemento para baixo. Mantenha valores próximos aos recomendados para evitar sobreposições com títulos muito longos e muitas afiliações.

## Instituições e autores

`\AdicionarInstituicao{SIGLA}{Nome completo}{caminho/da/logo.png}`

`\AdicionarAutor[Nome curto]{Nome completo}{SIGLA}{caminho/da/foto.jpg}`

O nome curto é opcional e aparece apenas com fotografias. No formato textual, utiliza-se o nome completo. Para múltiplas afiliações, escreva `{UFPI,IFPI}`.
