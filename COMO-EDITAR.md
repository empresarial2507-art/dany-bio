# Como editar o link da bio da Dany

Você não precisa saber programar. Tudo o que muda no site fica em **um único lugar**:
o bloco `CONTEUDO`, no final do arquivo `index.html`.

## A regra de ouro

Só troque o que está **entre aspas**. Nunca apague vírgulas, chaves `{ }` ou colchetes `[ ]`.

```
titulo: "Favoritos da Shopee",
         ^^^^^^^^^^^^^^^^^^^  só isso aqui você troca
```

## Editando pelo navegador (sem instalar nada)

1. Abra o repositório no GitHub.
2. Clique em `index.html`.
3. Clique no **lápis** (Edit this file), no canto de cima à direita.
4. Role até o bloco `CONTEUDO` (fica lá no final).
5. Faça a mudança.
6. Desça a página e clique em **Commit changes**.

A Vercel republica sozinha em cerca de 1 minuto.

---

# O topo

```
saudacao:   "Oi, gente!",             a frase pequena em itálico, acima da foto
nome:       "Dany",
sobrenome:  "Carter",                 aparece em itálico, na cor café
assinatura: "Vida real em vídeos",    a linha em letras espaçadas
bio:        "Você está no lugar certo. ...",
foto:       "img/dany.webp",          foto recortada, sem fundo (PNG ou WebP com transparência)
```

A foto do topo precisa ser **recortada sem fundo** para o efeito de "saindo do quadro"
funcionar. Qualquer app de remover fundo serve. Ideal: em torno de 900 px de largura.

### Redes sociais

```
{ rede: "instagram", url: "https://www.instagram.com/danycartter/" },
```
Uma linha por rede. Opções de `rede`: `instagram`, `tiktok`, `youtube`, `spotify`.
Para tirar uma rede, apague a linha.

---

# A capa (o banner grande)

É o lugar do seu produto principal. Hoje é o curso de CapCut.

```
capa: {
  selo:      "Meu curso",
  titulo:    "Sua vida em vlogs",
  texto:     "Como editar no CapCut e ...",
  preco:     "R$ 97,50",
  parcelado: "ou 3x de R$ 34,79",
  botao:     "Quero fazer o curso",
  url:       "https://hotmart.com/...",
  foto:      "img/banner-curso.webp"
},
```

A foto da capa é **em pé** (ideal: 800 x 1000 px). O texto entra por cima da parte
de baixo, então deixe o rosto na metade de cima da foto.
Quando lançar outro produto (o diário, por exemplo), é só trocar esses textos e a foto.
Para esconder o preço, deixe `preco: ""` e `parcelado: ""`.

---

# Os banners (a parte que você mais vai mexer)

Cada link é um banner clicável com imagem própria. No arquivo, cada banner é
um bloco assim:

```
{
  titulo: "Podcast Falando Sozinha",
  texto:  "Um café e um papo sem filtro",
  url:    "https://open.spotify.com/...",
  foto:   "img/banner-podcast.webp",
  foco:   "topo"
},
```

## Duplicar um banner

Copie o bloco inteiro, **do `{` até o `},`**, e cole logo abaixo. Depois troque
o texto e a imagem. Só o último banner da lista fica sem a vírgula no fim.

## Retirar um banner

Apague o bloco inteiro, do `{` até o `},`. Mais nada.

## Os dois tipos de imagem

Escolha **um** dos dois por banner:

| use            | quando                                                        |
|----------------|---------------------------------------------------------------|
| `foto: "..."`  | é uma **foto**. O título e o texto aparecem escritos por cima. |
| `arte: "..."`  | a imagem **já tem o texto escrito nela** (banner pronto, tipo os que você já usa). Nada é escrito por cima. |

Exemplo dos dois no arquivo: o banner da **Shopee** usa `arte` (porque a arte já
diz "Favoritos da Shopee") e o do **Podcast** usa `foto`.

## Ajustar o enquadramento da foto

Quando a foto corta numa parte ruim (o rosto fica de fora, por exemplo):

```
foco: "topo"      mostra a parte de cima da foto
foco: "centro"    padrão
foco: "baixo"     mostra a parte de baixo
```

E se a pessoa da foto estiver do lado esquerdo, mande o texto pro outro lado:

```
lado: "direita"
```

Só funciona no modo `foto`. No modo `arte` a imagem aparece inteira, sem corte.

## Banner com cupom

Acrescente a linha `cupom`. Aparece uma etiqueta no banner que copia o código
quando a pessoa toca.

```
{
  titulo: "Dux Nutrition",
  texto:  "15% de desconto com o meu cupom",
  url:    "https://www.duxnutrition.com/...",
  foto:   "img/banner-dux.webp",
  foco:   "topo",
  cupom:  "DANYCARTTER"
},
```

## Qual arquivo é qual banner

| Banner                    | Arquivo em `img/`      | Tamanho ideal        | Modo   |
|---------------------------|------------------------|----------------------|--------|
| Foto do topo              | `dany.webp`            | 900 x 1250, sem fundo | foto  |
| Capa (curso)              | `banner-curso.webp`    | 800 x 1000 (em pé)   | foto   |
| Favoritos da Shopee       | `banner-shopee.webp`   | 920 x 400            | arte   |
| Dux Nutrition             | `banner-dux.webp`      | 920 x 400            | foto   |
| Podcast Falando Sozinha   | `banner-podcast.webp`  | 920 x 400            | foto   |
| Meu canal no YouTube      | `banner-youtube.webp`  | 920 x 400            | arte   |
| Preview no WhatsApp       | `og.png`               | 1200 x 630           |        |

O jeito mais rápido de trocar: suba a imagem nova **com o mesmo nome** do arquivo
(pelo GitHub: pasta `img` > Add file > Upload files > arraste > Commit changes).
O GitHub substitui o arquivo antigo e a Vercel republica em 1 minuto. Nada de código.
Serve `.jpg`, `.png` ou `.webp`, desde que o nome (com a extensão) seja igual ao da tabela.

## Trocar a imagem de um banner (com outro nome)

1. Suba a imagem na pasta `img/`. Pelo GitHub: entre na pasta `img`,
   clique em **Add file > Upload files**, arraste o arquivo e commite.
2. Escreva o nome dela no banner: `foto: "img/nome-do-arquivo.jpg",`

**Se você errar o nome do arquivo o site não quebra.** O banner vira um espaço
tracejado escrito "falta a imagem img/...". Aí é só subir o arquivo com esse
nome exato, ou corrigir o nome no texto.

## Tamanho ideal das imagens

- **foto**: qualquer foto larga serve. O ideal é em torno de 920 x 400 pixels
  (proporção 16:7). Deixe a pessoa do lado direito, que o texto entra pela esquerda.
- **arte**: pode ter a proporção que quiser, ela aparece inteira. As de hoje têm 920 x 400.
- Tente manter cada arquivo abaixo de 150 KB para o site abrir rápido no celular.

---

# A frase

```
frase: {
  texto: "Ninguém permanece o mesmo depois de se conhecer.",
  autor: "Dany Carter"
},
```
Para esconder, deixe `texto: ""`.

# Parcerias

```
parcerias: {
  titulo:  "Parcerias e publicidade",
  texto:   "Para campanhas e publicidade, fale com ...",
  email:   "dany.carter@farol.ag",
  alcance: "Instagram, TikTok e YouTube. Mais de 4 milhões de pessoas."
},
```

# Tema

```
tema: "claro",     padrão, o site sempre em branco
tema: "escuro",    sempre escuro
tema: "auto",      segue a configuração do celular de quem abre
```

---

# Publicando pela primeira vez

1. Crie um repositório novo no GitHub (pode ser público).
2. Suba os arquivos desta pasta: `index.html` e a pasta `img/`.
3. Na Vercel: **Add New > Project > Import** e escolha esse repositório.
   Não precisa configurar nada, é um site estático. Clique em Deploy.
4. Em **Settings > Domains**, aponte `danycartter.com` (o domínio hoje está no Wix;
   é preciso trocar o DNS lá, ou transferir o domínio).

A partir daí, todo commit no GitHub republica o site automaticamente.

# Antes de colocar no ar

- [ ] Confirmar com a Dany a frase "Ninguém permanece o mesmo depois de se conhecer."
      (foi citada por uma seguidora como frase dela; se não for, trocar ou esconder).
- [ ] Conferir o preço do curso na Hotmart (R$ 97,50 / 3x de R$ 34,79 em set/2026).
- [ ] Conferir os @ (instagram.com/danycartter, tiktok.com/@danycartter, youtube.com/@DanyCartter).
- [ ] Conferir o e-mail de parcerias com o Grupo Farol (o site antigo usa dany.carter@farol.ag).
- [ ] Trocar `og:image` e `og:url` no `<head>` se o domínio final for outro.
