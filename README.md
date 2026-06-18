# Plataforma de E-commerce

API REST de e-commerce com produtos, carrinho, pedidos e cupons de desconto.

> 📦 **Template de trabalho em grupo da WebForge.** Clique em **Use this template** (botão verde acima) para criar o repositório do seu grupo.

## 🚀 Como rodar

```bash
npm install
npm start        # inicia em http://localhost:3000
```

O projeto já sobe com uma rota raiz `GET /`. Todo o resto é com o grupo.

## 📋 Requisitos

- **Produtos** — CRUD (`/produtos`) com nome, descrição, preço, estoque e categoria; listagem com filtro por categoria.
- **Carrinho** — adicionar/remover/atualizar itens (`/carrinho/items`) e `GET /carrinho` com total calculado.
- **Pedidos** — `POST /pedidos` cria a partir do carrinho e **decrementa o estoque**; `GET /pedidos`, `GET /pedidos/:id`, `PATCH /pedidos/:id/status`.
- **Cupons** — `POST /cupons` (% de desconto) e `POST /carrinho/cupom` para aplicar.

> Persistam os dados (arquivo JSON ou SQLite) — os testes podem reiniciar o servidor entre etapas.

## ✅ O que os testes de correção validam

Os testes automáticos sobem o **seu** servidor e fazem requisições HTTP reais contra a API. Eles verificam **comportamento** (status HTTP e corpo das respostas), não a estrutura interna do código — organizem os arquivos como preferirem. Para ser aprovado, a API precisa:

- [ ] `GET /` responde **200**.
- [ ] `POST /produtos` cria (**201**) e `GET /produtos` lista; o filtro `?categoria=` funciona.
- [ ] `POST /carrinho/items` adiciona item e `GET /carrinho` retorna o **total correto**.
- [ ] `PATCH /carrinho/items/:produtoId` atualiza a quantidade e recalcula o total.
- [ ] `POST /pedidos` cria o pedido e **reduz o estoque** dos produtos.
- [ ] Criar pedido com estoque insuficiente responde **409**.
- [ ] Aplicar um cupom reduz o total do carrinho conforme o percentual.
- [ ] `PATCH /pedidos/:id/status` altera o status (pendente → enviado → entregue).
- [ ] Recursos inexistentes respondem **404**.

## 👥 Trabalho em equipe (obrigatório)

Este é um ambiente o mais próximo possível do mercado:

- O repositório deve pertencer a **um** dos membros do grupo. Os **demais membros entram como colaboradores** em `Settings → Collaborators → Add people`.
- Cada membro trabalha em sua **própria branch** e abre **Pull Request** para a `main`, pedindo revisão de outro colega.
- A WebForge mede as **contribuições individuais** de cada membro (commits, linhas adicionadas e removidas) direto do histórico do GitHub. Distribuam bem o trabalho.

## 🧱 Stack

- Node.js + Express (CommonJS)
