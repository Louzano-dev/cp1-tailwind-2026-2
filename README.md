# Checkpoint 1 — Tailwind

**Frontend Design · 2º semestre · Prof. Fábio Alencar**
Data: **quinta, 03/09/2026** · Janela: **08:00 às 09:40** · Individual

---

## O que é

Todos recebem o mesmo `index.html`: uma landing de evento, semântica e sem uma única classe. Seu trabalho é vesti-la com Tailwind seguindo a **carta de marca sorteada para o seu RM**.

A estrutura é a mesma para a turma inteira. O resultado tem que ser irreconhecível de um colega para o outro — é a carta que decide a cara da página, não o seu gosto.

## Sua carta

O sorteio foi gravado e a tabela `RM → carta` está no Teams. Cada carta traz:

- **nome e setor** do evento
- **três adjetivos** de personalidade
- **três hex** — você decide qual é fundo, qual é tinta e qual é destaque
- **par tipográfico** (Google Fonts)
- **raio de canto**
- **uma regra de composição** obrigatória

Adapte os textos ao seu evento. "Nome do Evento" precisa virar o nome da sua carta, e o tom da cópia precisa combinar com os três adjetivos.

---

## Como rodar

**Não instale nada.** O Tailwind v4 já vem carregado como `<script>` no `index.html`:

```html
<script src="https://cdn.jsdelivr.net/npm/@tailwindcss/browser@4.3.3"></script>
```

Sem Vite, sem npm, sem build, sem terminal. Abra o arquivo no navegador (ou com o Live Server do VS Code), edite, salve, recarregue. O Tailwind recompila sozinho a cada classe nova.

Não troque essa linha nem acrescente outra forma de carregar o Tailwind.

---

## Regras

**1. O `<body>` é intocável.**
Não mude tags, não mude a ordem, não mude o aninhamento, não acrescente nem remova elementos. Você só encosta em duas coisas dentro do body: o atributo `class` e o texto visível.

**2. O `<head>` é seu.**
É lá que você carrega as fontes e declara os tokens. A área editável está marcada no arquivo.

**3. Os seis tokens são obrigatórios e os nomes não mudam.**

```css
@theme {
  --color-marca-50:  /* fundo    */;
  --color-marca-900: /* tinta    */;
  --color-marca-500: /* destaque */;
  --font-display:    /* títulos  */;
  --font-corpo:      /* corpo    */;
  --radius-card:     /* raio     */;
}
```

E precisam ser **usados através dos utilitários que eles geram**: `bg-marca-50`, `text-marca-900`, `bg-marca-500`, `font-display`, `font-corpo`, `rounded-card`. Declarar o token e não usar não conta.

**4. Nada de valor arbitrário.**
`bg-[#D4622A]`, `p-[13px]`, `text-[22px]` e afins estão proibidos. Se a cor ou o tamanho importam, viram token. Se não importam, cabem na escala do Tailwind.

**5. Nada de CSS solto.**
Nenhum atributo `style=""`, nenhuma regra CSS própria fora do bloco `@theme`. O `@theme` é o único lugar onde você escreve CSS.

**6. Mobile-first.**
Comece pelo layout de celular e use `sm:` `md:` `lg:` para crescer. Largura fixa em pixel não é responsividade.

**7. Estados.**
Todo link e todo botão precisa de `hover:` e de `focus-visible:`. O foco tem que ser visível sem depender de cor sozinha.

**8. Contraste.**
Texto sobre fundo precisa passar em WCAG AA (4.5:1 para texto normal). Se a paleta da sua carta não fecha o contraste, é você que resolve — escurecendo, clareando ou trocando qual hex faz qual papel.

---

## Entrega

Tudo pelo **assignment do Teams**, com **dois links**:

1. **Repositório no GitHub**, público, seu.
2. **Projeto publicado na Vercel**, no ar e abrindo.

O prazo do assignment é **09:40**. Depois disso ele fecha.

### Publicação

Como já vimos em aula: importe o repositório na Vercel, deixe o framework em *Other*, e publique. É um HTML estático, não precisa de configuração nenhuma. Publique **antes** de gastar os últimos minutos em detalhe visual — página bonita que não está no ar não conta.

### Histórico

- **Mínimo 3 pushes**, com pelo menos **30 minutos entre o primeiro e o último**. Um push só, no fim, vale penalidade.
- O primeiro push é o clone ainda sem estilo. Comece por ele.
- Nada de push depois das **09:40**. O que vale é o horário registrado pelo GitHub, não a data do commit na sua máquina.

### `ENTREGA.md`

Crie na raiz do repositório um arquivo `ENTREGA.md` com três coisas, em até seis linhas:

```markdown
RM: 570000
Publicado em: https://seu-projeto.vercel.app
Carta: 07 · Vértice

IA: pedi variações de paleta e ajustei o contraste na mão.
```

Usar IA é permitido. Não declarar, não é.

## Defesa

Na aula de **10/09**, logo na abertura, **60 segundos por pessoa**. Abro o seu código e faço duas perguntas sobre ele — onde está tal token, por que tal utilitário e não outro. **Vale 35 dos 100 pontos** e a nota não fecha antes disso. Quem falta, perde os 35.

---

## Avaliação

| Critério | Pontos |
|---|---:|
| Defesa de 60 segundos | 35 |
| `@theme` correto e tokens usados via utilitários | 20 |
| Flex/Grid e mobile-first, cumprindo a regra da sua carta | 20 |
| Fidelidade à carta: cor, tipografia, raio e tom da cópia | 15 |
| Estados (`hover`, `focus-visible`) e contraste AA | 10 |

**Penalidades**

| | |
|---|---:|
| Projeto não publicado, ou link publicado fora do ar | −15 |
| Estrutura do `<body>` alterada | −20 |
| Valor arbitrário ou CSS fora do `@theme` | −10 |
| Push único | −20 |
| `ENTREGA.md` ausente ou incompleto | −5 |
| Entrega fora da janela | −100 |

---

## O que entregar, em uma linha

Uma landing de evento no ar, que qualquer pessoa olha e diz de que marca ela é, construída só com utilitários do Tailwind sobre tokens que você declarou.
