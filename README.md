# Sistema de Chamados de TI

Uma aplicação web completa para gerenciamento de chamados de suporte técnico (Help Desk).

## 🎯 Funcionalidades

- ✅ Abertura de chamados com categorização
- ✅ Dashboard em tempo real
- ✅ Acompanhamento de status
- ✅ Sistema de prioridades
- ✅ Atribuição de chamados
- ✅ Relatórios e análises
- ✅ Notificações por email
- ✅ Interface responsiva

## 📋 Stack Tecnológico

### Frontend
- HTML5, CSS3, JavaScript (ES6+)
- Bootstrap 5 (UI/UX responsivo)
- Fetch API para requisições HTTP
- LocalStorage para cache

### Backend
- Node.js + Express.js
- REST API
- Autenticação básica (JWT)
- Middleware de validação

### Banco de Dados
- JSON Server (desenvolvimento)
- Estrutura preparada para migração para MongoDB/PostgreSQL

## 🚀 Como Iniciar

### Pré-requisitos
- Node.js v14+
- npm ou yarn

### Instalação

```bash
# 1. Clonar/acessar o diretório
cd chamado-ti-system

# 2. Instalar dependências backend
cd backend
npm install

# 3. Voltar para raiz e instalar dependências frontend (se usar build)
cd ..

# 4. Iniciar aplicação
npm start
```

### Desenvolvimento

```bash
# Terminal 1: Backend
cd backend
npm run dev

# Terminal 2: Abrir frontend em navegador
# Acesse: http://localhost:3000
```

## 📁 Estrutura do Projeto

```
chamado-ti-system/
├── frontend/
│   ├── index.html              # Página principal (login)
│   ├── dashboard.html          # Dashboard do usuário
│   ├── novo-chamado.html       # Criar novo chamado
│   ├── meus-chamados.html      # Lista de chamados do usuário
│   ├── gerenciamento.html      # Painel de gerenciamento (TI)
│   ├── relatorios.html         # Relatórios e análises
│   ├── assets/
│   │   ├── css/
│   │   │   ├── style.css       # Estilos principais
│   │   │   └── responsive.css  # Media queries
│   │   └── js/
│   │       ├── app.js          # App principal
│   │       ├── api.js          # Funções de API
│   │       ├── ui.js           # Funções de UI
│   │       ├── auth.js         # Autenticação
│   │       └── utils.js        # Utilitários
│   └── pages/                  # Componentes reutilizáveis
│
├── backend/
│   ├── server.js               # Entrada principal
│   ├── package.json
│   ├── config/
│   │   ├── database.js         # Conexão com DB
│   │   └── constants.js        # Constantes da app
│   ├── models/
│   │   ├── Chamado.js          # Modelo de Chamado
│   │   ├── Usuario.js          # Modelo de Usuário
│   │   └── Categoria.js        # Modelo de Categoria
│   ├── routes/
│   │   ├── chamados.js         # Rotas de chamados
│   │   ├── usuarios.js         # Rotas de usuários
│   │   ├── relatorios.js       # Rotas de relatórios
│   │   └── auth.js             # Rotas de autenticação
│   ├── controllers/
│   │   ├── chamadoController.js
│   │   ├── usuarioController.js
│   │   └── relatorioController.js
│   ├── middleware/
│   │   ├── auth.js             # Verificação de token
│   │   └── validation.js       # Validação de dados
│   └── data/
│       └── db.json             # Banco JSON (desenvolvimento)
│
├── package.json               # Dependências do projeto
└── README.md                  # Este arquivo
```

## 🔌 API Endpoints

### Autenticação
- `POST /api/auth/login` - Login de usuário
- `POST /api/auth/logout` - Logout

### Chamados
- `GET /api/chamados` - Listar todos os chamados
- `GET /api/chamados/:id` - Obter chamado específico
- `POST /api/chamados` - Criar novo chamado
- `PUT /api/chamados/:id` - Atualizar chamado
- `DELETE /api/chamados/:id` - Deletar chamado
- `GET /api/chamados/meus` - Meus chamados

### Usuários
- `GET /api/usuarios` - Listar usuários
- `GET /api/usuarios/:id` - Obter usuário
- `POST /api/usuarios` - Criar usuário

### Relatórios
- `GET /api/relatorios/dashboard` - Dados do dashboard
- `GET /api/relatorios/sla` - Relatório de SLA
- `GET /api/relatorios/por-categoria` - Análise por categoria

## 🔐 Autenticação

A aplicação usa autenticação básica com usuários mock:

**Usuário Final:**
- Email: `user@empresa.com`
- Senha: `123456`

**Técnico de TI:**
- Email: `tecnico@empresa.com`
- Senha: `123456`

**Gestor:**
- Email: `gerente@empresa.com`
- Senha: `123456`

## 📊 Modelos de Dados

### Chamado
```json
{
  "id": "TI-2026-00001",
  "titulo": "Problema com email",
  "descricao": "Não consigo acessar meu email",
  "categoria": "Email",
  "subcategoria": "Acesso",
  "prioridade": "Alto",
  "status": "Em Atendimento",
  "usuario_id": "USR001",
  "tecnico_id": "TEC001",
  "data_criacao": "2026-05-19T10:30:00Z",
  "data_atualizacao": "2026-05-19T11:30:00Z",
  "data_resolucao": null,
  "tempo_resposta": 60,
  "tempo_resolucao": null,
  "anexos": ["screenshot.png"],
  "comentarios": []
}
```

### Usuário
```json
{
  "id": "USR001",
  "nome": "João Silva",
  "email": "joao@empresa.com",
  "função": "Usuário Final",
  "departamento": "Financeiro",
  "telefone": "11999999999",
  "ativo": true,
  "data_criacao": "2026-01-01T00:00:00Z"
}
```

## 🎨 Páginas da Aplicação

### 1. Login (`index.html`)
- Formulário de autenticação
- Validação de credenciais
- Redirecionamento baseado em função

### 2. Dashboard (`dashboard.html`)
- Cards com KPIs principais
- Gráficos de chamados por status
- Chamados recentes para atender
- Análise de SLA

### 3. Novo Chamado (`novo-chamado.html`)
- Formulário intuitivo
- Categorização automática
- Upload de anexos
- Prévia do SLA

### 4. Meus Chamados (`meus-chamados.html`)
- Lista de chamados do usuário
- Filtros por status e prioridade
- Busca por número ou palavras-chave
- Detalhes e histórico

### 5. Gerenciamento (`gerenciamento.html`)
- Fila de chamados
- Atribuição de chamados
- Atualização de status
- Adicionar anotações técnicas

### 6. Relatórios (`relatorios.html`)
- Dashboard gerencial
- Gráficos de performance
- Exportação em PDF/Excel
- Análise por técnico

## 🔧 Configuração

Edite `backend/config/constants.js` para personalizar:
- Categorias de chamados
- Níveis de prioridade
- Tempos de SLA
- Email para notificações

## 📧 Envio de Emails

Configure as variáveis de ambiente:
```env
SMTP_HOST=smtp.gmail.com
SMTP_PORT=587
SMTP_USER=seu-email@gmail.com
SMTP_PASS=sua-senha
```

## 📈 Roadmap

- [ ] Implementar banco de dados real (MongoDB/PostgreSQL)
- [ ] Autenticação JWT avançada
- [ ] Sistema de notificações em tempo real (WebSocket)
- [ ] Categorização inteligente com ML
- [ ] App mobile (React Native)
- [ ] Integração com sistemas externos
- [ ] Analytics e dashboards avançados

## 🐛 Troubleshooting

**Porta 3000 já em uso:**
```bash
# Mudar porta
PORT=3001 npm start
```

**Erro de CORS:**
- Verifique as configurações de CORS no backend
- Adicione domínios permitidos em `backend/server.js`

**Banco de dados não encontrado:**
- Certifique-se que `backend/data/db.json` existe
- Execute: `npm run init-db`

## 📝 Licença

Este projeto é fornecido como exemplo educacional.

## 👥 Suporte

Para dúvidas ou problemas, entre em contato com o time de desenvolvimento.

---

**Versão:** 1.0.0  
**Última atualização:** 19/05/2026
