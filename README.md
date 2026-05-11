# DesenvWebFront

Interface web do projeto (React + Vite) para **Produtos**, **Categorias** e **Detalhes técnicos** (1‑para‑1), consumindo a API `DesenvWebApi`.

## Requisitos

- Node.js 18+ (recomendado LTS)
- npm
- API .NET em execução (veja o README da pasta `DesenvWebApi`)

## Instalação

```bash
cd DesenvWebFront
npm install
```

## Executar em desenvolvimento

```bash
npm run dev
```

Abra o endereço exibido no terminal (geralmente `http://localhost:5173`).

## Build de produção

```bash
npm run build
npm run preview   # opcional: testar o build localmente
```

## Conectar à API

Os serviços em `src/services/` usam a URL base da API. Por padrão está **`http://localhost:5113`** (perfil `http` do `launchSettings.json` da API).

Se a API rodar em outra porta ou host, ajuste em:

- `src/services/produtoService.js`
- `src/services/categoriaService.js`
- `src/services/detalheProdutoService.js`

Altere a constante `API_URL` em cada arquivo para manter o front e a API alinhados.

## Estrutura principal

| Pasta / arquivo | Função |
|-----------------|--------|
| `src/App.jsx` | Rotas (`/produtos`, `/categorias`) |
| `src/main.jsx` | Entrada: Router, ToastProvider |
| `src/components/layout/` | Layout com sidebar |
| `src/components/produtos/` | Página de produtos, tabela, modais, detalhes 1‑1 |
| `src/components/categorias/` | CRUD de categorias |
| `src/components/ui/` | Modal, toasts, confirmação |
| `src/services/` | Chamadas HTTP (axios) |
| `src/contexts/` | Contexto de notificações |
| `src/hooks/` | `useToast` |

## Scripts úteis

| Comando | Descrição |
|---------|-----------|
| `npm run dev` | Servidor de desenvolvimento (Vite) |
| `npm run build` | Gera pasta `dist/` |
| `npm run lint` | ESLint |

## Fluxo rápido de uso

1. Suba o PostgreSQL (por exemplo `docker compose up -d` na raiz do repositório).
2. Aplique as migrations e rode a API (`DesenvWebApi`).
3. Rode `npm run dev` neste projeto.
4. Cadastre **categorias** antes de criar produtos que exijam categoria no formulário.

---

*Disciplina: Desenvolvimento de Sistemas Web — UFSC*
