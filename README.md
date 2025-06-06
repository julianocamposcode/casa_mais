# Casa Mais - Sistema de Gestão

Sistema completo para gestão da organização social Casa de Lázaro de Betânia, com módulos para assistidas, medicamentos, doações, consultas e despesas.

## 🏗️ Arquitetura

O projeto é estruturado em dois repositórios independentes como submódulos:

- **Frontend**: React + Vite para interface web responsiva
- **Backend**: Node.js + Express + MySQL para API REST

## 📁 Estrutura do Projeto

```
casa_mais/
├── frontend/                          # Submódulo - Interface React
├── backend/                           # Submódulo - API Node.js
├── docs/                              # Documentação do projeto
│   ├── CONFIGURACAO_MYSQL.md          # Guia de configuração do MySQL
│   ├── INTEGRACAO_FRONTEND_API.md     # Status da integração
│   ├── REPOSITORIOS_INDEPENDENTES.md  # Gerenciamento de submódulos
│   └── VERSIONS.md                    # Histórico de versões
└── README.md                          # Documentação principal
```

## 🚀 Início Rápido

### 1. Clonar o Projeto Completo

```bash
# Clone com submódulos
git clone --recurse-submodules https://github.com/julianocamposcode/casa_mais
cd casa_mais

# Ou se já clonou sem submódulos
git submodule update --init --recursive
```

### 2. Configurar o Backend

```bash
cd backend

# Instalar dependências
npm install

# Configurar MySQL (veja docs/CONFIGURACAO_MYSQL.md)
# Editar src/config/database.js se necessário

# Criar banco e tabelas
node setup-db.js

# Popular dados de exemplo
node populate-db.js

# Iniciar servidor (porta 3003)
npm start
```

### 3. Configurar o Frontend

```bash
cd ../frontend

# Instalar dependências
npm install

# Configurar variáveis de ambiente
cp .env.example .env

# Iniciar aplicação (porta 5173)
npm run dev
```

## 📋 Funcionalidades

### ✅ Implementadas

- **Gestão de Assistidas**: Cadastro completo, histórico médico, internações e drogas
- **Medicamentos**: Controle de estoque com validade e movimentações
- **Doações**: Sistema completo com doadores PF/PJ, validação de documentos
- **Doadores**: CRUD completo com validação de CPF/CNPJ
- **Dashboard**: Visão geral com indicadores e estatísticas
- **Design Responsivo**: Interface otimizada para mobile, tablet e desktop

### 🆕 Atualizações Recentes

- **Modal de Confirmação**: Corrigido comportamento no formulário de assistidas
- **Validação de Dados**: Implementada validação robusta de CPF/CNPJ
- **Interface Padronizada**: Unificação de espaçamento e componentes
- **Documentação**: READMEs atualizados com instruções completas

### 🚧 Em Desenvolvimento

- **Consultas**: Agendamento e acompanhamento médico
- **Despesas**: Controle financeiro e relatórios
- **Usuários**: Sistema de autenticação e permissões
- **Relatórios**: Exportação PDF/Excel e dashboards avançados

## 🔗 Repositórios dos Submódulos

- **Frontend**: https://github.com/fabioaloisio/casa-mais-react
- **Backend**: https://github.com/aldruin/casa-mais-backend

## 📊 Status da Integração

| Módulo       | Frontend              | Backend     | Integração   |
| ------------ | --------------------- | ----------- | ------------ |
| Assistidas   | ✅ UI Completa        | ✅ API REST | ✅ Integrado |
| Medicamentos | ✅ UI Completa        | ✅ API REST | ✅ Integrado |
| Doações      | ✅ UI Completa        | ✅ API REST | ✅ Integrado |
| Doadores     | ✅ UI Completa        | ✅ API REST | ✅ Integrado |
| Consultas    | 🚧 Em desenvolvimento | ❌ Pendente | ❌ Pendente  |
| Despesas     | 🚧 Em desenvolvimento | ❌ Pendente | ❌ Pendente  |
| Usuários     | 🚧 Em desenvolvimento | ❌ Pendente | ❌ Pendente  |

## 🛠️ Tecnologias

### Frontend

- React 19.1.0
- Vite 6.3.5
- React Router DOM 7.6.1
- Bootstrap 5.3.6
- React Bootstrap 2.10.10

### Backend

- Node.js
- Express 5.1.0
- MySQL2 3.14.1
- CORS 2.8.5

## 📖 Documentação

- [Configuração MySQL](./docs/CONFIGURACAO_MYSQL.md)
- [Integração Frontend-API](./docs/INTEGRACAO_FRONTEND_API.md)
- [Gerenciar Submódulos](./docs/REPOSITORIOS_INDEPENDENTES.md)
- [Histórico de Versões](./docs/VERSIONS.md)

## 🤝 Contribuindo

1. Fork o projeto desejado (frontend ou backend)
2. Crie sua feature branch (`git checkout -b feature/NovaFuncionalidade`)
3. Commit suas mudanças (`git commit -m 'Add: nova funcionalidade'`)
4. Push para a branch (`git push origin feature/NovaFuncionalidade`)
5. Abra um Pull Request

## 👥 Equipe

Projeto desenvolvido pelo Grupo 4

## 📝 Licença

ISC License
