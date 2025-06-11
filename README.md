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

# Instale as dependências
npm install

# Configure o arquivo .env
cp .env.example .env

# Edite o .env com suas credenciais MySQL
DB_HOST=localhost
DB_USER=root
DB_PASSWORD=sua_senha
DB_NAME=casamais_db
DB_PORT=3306

# Criar banco e tabelas
npm run setup-db

# Popular dados de exemplo
npm run populate-db.js
npm run populate-doadores.js

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

- **Gestão de Assistidas**: Cadastro completo, histórico médico, internações e medicamentos
- **Gestão de Medicamentos**: Controle de estoque com validade e movimentações
- **Gestão de Doações**: Sistema completo com doadores PF/PJ, validação de documentos
- **Gestão de Doadores**: CRUD completo com validação de CPF/CNPJ
- **Gestão de Tipos de Despesas**: Configuração de categorias de despesas
- **Gestão de Despesas**: Controle financeiro completo
- **Dashboard**: Visão geral com indicadores e estatísticas
- **Design Responsivo**: Interface otimizada para mobile, tablet e desktop

### 🆕 Atualizações Recentes

- **Sistema de Despesas**: Implementado gestão completa de tipos de despesas e despesas
- **Validação de Documentos**: Sistema robusto de validação de CPF/CNPJ com dígitos verificadores
- **Interface Modernizada**: Layout responsivo com sidebar reorganizada
- **API Expandida**: Endpoints completos para todos os módulos principais
- **Documentação Técnica**: Guias detalhados com exemplos CURL e configuração

### 🚧 Em Desenvolvimento

- **Consultas**: Agendamento e acompanhamento médico
- **Usuários**: Sistema de autenticação e permissões
- **Relatórios**: Exportação PDF/Excel e dashboards avançados
- **Notificações**: Sistema de alertas e lembretes

## 🔗 Repositórios dos Submódulos

- **Frontend**: https://github.com/fabioaloisio/casa-mais-react
- **Backend**: https://github.com/aldruin/casa-mais-backend

## 📊 Status da Integração

| Módulo           | Frontend              | Backend     | Integração   |
| ---------------- | --------------------- | ----------- | ------------ |
| Assistidas       | ✅ UI Completa        | ✅ API REST | ✅ Integrado |
| Medicamentos     | ✅ UI Completa        | ✅ API REST | ✅ Integrado |
| Unidades Medida  | ✅ UI Completa        | ✅ API REST | ✅ Integrado |
| Doações          | ✅ UI Completa        | ✅ API REST | ✅ Integrado |
| Doadores         | ✅ UI Completa        | ✅ API REST | ✅ Integrado |
| Tipos Despesas   | ✅ UI Completa        | ✅ API REST | ✅ Integrado |
| Despesas         | ✅ UI Completa        | ✅ API REST | ✅ Integrado |
| Consultas        | 🚧 Em desenvolvimento | ❌ Pendente | ❌ Pendente  |
| Usuários         | 🚧 Em desenvolvimento | ❌ Pendente | ❌ Pendente  |

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
- [Compatibilidade Cross-Platform](./docs/COMPATIBILIDADE_CROSS_PLATFORM.md)
- [Histórico de Versões](./docs/VERSIONS.md)

### Documentação dos Módulos

- [Backend - Comandos CURL](./backend/docs/CURL_COMMANDS.md)
- [Backend - Validação de Documentos](./backend/docs/DOCUMENTOS_VALIDOS.md)
- [Frontend - Melhorias de UX](./frontend/frontend-ux.md)

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
