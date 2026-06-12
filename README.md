# 🛒 TechStore — Carrinho de Compras

<img width="1898" height="906" alt="image" src="https://github.com/user-attachments/assets/1b38904e-9a61-4185-9347-d8984719377d" />


> Aplicação front-end de carrinho de compras com catálogo de produtos, adição/remoção de itens e cálculo de total em tempo real.

![HTML5](https://img.shields.io/badge/HTML5-E34F26?style=flat-square&logo=html5&logoColor=white)
![CSS3](https://img.shields.io/badge/CSS3-1572B6?style=flat-square&logo=css3&logoColor=white)
![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?style=flat-square&logo=javascript&logoColor=black)
![Status](https://img.shields.io/badge/status-concluído-4ade80?style=flat-square)

---

## 📋 Índice

- [Sobre o projeto](#-sobre-o-projeto)
- [Demonstração](#-demonstração)
- [Funcionalidades](#-funcionalidades)
- [Tecnologias](#-tecnologias)
- [Como executar](#-como-executar)
- [Estrutura do projeto](#-estrutura-do-projeto)
- [Design e decisões técnicas](#-design-e-decisões-técnicas)
- [Melhorias futuras](#-melhorias-futuras)
- [Autor](#-autor)

---

## 💡 Sobre o projeto

O **TechStore** é uma aplicação front-end de e-commerce desenvolvida como projeto de portfólio durante os estudos na plataforma [Alura](https://www.alura.com.br/). O objetivo foi construir um carrinho de compras funcional aplicando boas práticas de desenvolvimento web: HTML semântico, CSS organizado com design tokens e JavaScript modular.

O projeto passou por uma **refatoração completa**, elevando o código de um protótipo inicial para um nível de qualidade de portfólio — com design system consistente, acessibilidade, responsividade e animações.

---

## 🖥️ Demonstração

> *Deploy disponível em:* **[techstore.vercel.app](#)** *(https://compras-mu-one.vercel.app/)*

### Prévia

| Desktop | Mobile |
|---------|--------|
| Layout em duas colunas com catálogo e carrinho fixo | Layout empilhado, grade de produtos adaptada |

---

## ✅ Funcionalidades

- [x] Catálogo de produtos com cards interativos
- [x] Adição de produto via seleção no formulário (com quantidade)
- [x] Adição rápida direto no card do produto
- [x] Remoção individual de itens do carrinho
- [x] Cálculo do total em tempo real
- [x] Limpar carrinho completo
- [x] Contador de itens animado no header
- [x] Toast notifications de feedback
- [x] Estado vazio do carrinho com visual dedicado
- [x] Validação de quantidade com feedback inline
- [x] Layout totalmente responsivo (desktop → smartphone)
- [x] Acessibilidade com `aria-live`, `aria-label` e `role`

---

## 🛠️ Tecnologias

| Tecnologia | Uso |
|---|---|
| **HTML5** | Estrutura semântica com landmarks e atributos ARIA |
| **CSS3** | Design tokens via custom properties, Grid, Flexbox, animações |
| **JavaScript (ES6+)** | Manipulação de DOM, eventos, módulos de estado |
| **Google Fonts** | Tipografia: Syne (display) + DM Sans (corpo) |

Nenhuma biblioteca ou framework externo foi utilizado — JavaScript vanilla puro.

---

## 🚀 Como executar

### Pré-requisitos

Apenas um navegador moderno. Não há dependências, build steps ou servidores necessários.

### Executar localmente

```bash
# 1. Clone o repositório
git clone https://github.com/seu-usuario/techstore-carrinho.git

# 2. Acesse a pasta
cd techstore-carrinho

# 3. Abra o arquivo no navegador
# macOS
open index.html

# Linux
xdg-open index.html

# Windows
start index.html
```

Ou simplesmente arraste o `index.html` para a janela do seu navegador.

---

## 📁 Estrutura do projeto

```
techstore-carrinho/
├── index.html          # Estrutura e lógica da aplicação
├── README.md           # Documentação
└── assets/             # (opcional) Recursos estáticos
```

> O projeto é intencionalmente autocontido em um único `index.html` para facilitar o deploy e demonstração.

---

## 🎨 Design e decisões técnicas

### Design System

O visual foi construído sobre um conjunto de **CSS Custom Properties** (design tokens), garantindo consistência e facilidade de manutenção:

```css
:root {
  --accent: #2563eb;          /* Cor principal — azul */
  --font-display: 'Syne';     /* Tipografia de destaque */
  --font-body: 'DM Sans';     /* Tipografia de corpo */
  --r-xl: 24px;               /* Border radius — cards */
  --shadow-lg: ...;           /* Sombra — elementos elevados */
  --transition: 0.2s cubic-bezier(0.4, 0, 0.2, 1);
}
```

### Arquitetura JavaScript

O estado da aplicação é gerenciado de forma centralizada:

```js
const state = {
  total: 0,       // Valor acumulado
  itemCount: 0,   // Quantidade total de itens
};
```

As funções são separadas por responsabilidade:

- `renderProductGrid()` — renderiza os cards do catálogo
- `populateSelect()` — popula o `<select>` do formulário
- `addToCart()` — adiciona item e atualiza estado
- `updateTotal()` — sincroniza o display do total
- `updateHeaderCount()` — sincroniza o badge do header
- `showToast()` — exibe notificação temporária
- `setFeedback()` — feedback inline no formulário

### Responsividade

O layout usa **CSS Grid** com breakpoints:

| Largura | Layout |
|---|---|
| > 900px | Grid de 2 colunas: catálogo + carrinho fixo |
| 560–900px | Coluna única, carrinho abaixo do catálogo |
| < 560px | Grid de produtos com 2 colunas |
| < 380px | Grid de produtos com 1 coluna |

### Acessibilidade (A11Y)

- `aria-live="polite"` no feedback do formulário e no total
- `aria-live="assertive"` nas toast notifications
- `aria-label` descritivo em todos os botões de ação
- `role="list"` e `role="listitem"` no grid de produtos e lista do carrinho
- `aria-required="true"` nos campos obrigatórios
- `.sr-only` para headings e conteúdo exclusivo para leitores de tela

---

## 🔮 Melhorias futuras

- [ ] Persistência do carrinho com `localStorage`
- [ ] Campo de busca e filtro por categoria
- [ ] Controle de estoque (bloquear adição quando esgotado)
- [ ] Animação de "voo" do produto para o carrinho
- [ ] Página de checkout com resumo do pedido
- [ ] Dark mode com `prefers-color-scheme`
- [ ] Testes unitários com Jest

---

## 👤 Autor

**Guilherme Barros**

<img src="https://github.com/dida0982.png" width="150" alt="Foto de perfil">

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/guilherme-barros-6a0369209/)
[![GitHub](https://img.shields.io/badge/GitHub-181717?style=for-the-badge&logo=github&logoColor=white)](https://github.com/dida0982)


---

<p align="center">
  <sub>Projeto desenvolvido para fins de aprendizado e portfólio.</sub>
</p>
