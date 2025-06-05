# VERSIONS.md

## Versões Atuais

| Componente | Versão | Data | Status |
|------------|--------|------|--------|
| Frontend (React) | 0.3.0 | 05/06/2025 | Desenvolvimento |
| Backend (Node.js/Express) | 0.2.0 | 05/06/2025 | Desenvolvimento |

## Compatibilidade

| Frontend | Backend | Compatível | Notas |
|----------|---------|------------|-------|
| 0.3.0 | 0.2.0 | ✅ | Documentação atualizada, estrutura completa |
| 0.2.0 | 0.1.1 | ✅ | Frontend melhorado, backend com correções |
| 0.1.0 | 0.1.0 | ✅ | Versão inicial de desenvolvimento |

## Histórico de Versões

### v0.3.0 Frontend / v0.2.0 Backend (05/06/2025)
- **Frontend (v0.3.0):**
  - README completamente atualizado com estrutura real
  - Documentação de todos os componentes e serviços
  - Correção de caminhos e comandos
  - Adição de componentes faltantes na documentação
  - Integração com API de medicamentos e doações
  
- **Backend (v0.2.0):**
  - README atualizado com estrutura completa
  - Documentação do módulo de assistidas
  - Comandos corrigidos (node ao invés de npm scripts)
  - Schema completo do banco de dados documentado
  - Todas as tabelas e endpoints documentados

### v0.2.0 Frontend / v0.1.1 Backend (02/06/2025)
- **Frontend (v0.2.0):**
  - Formulário de assistidas completamente reformulado
  - Campos dinâmicos para medicamentos e internações
  - Correção de gênero (masculino → feminino) para casa de assistência feminina
  - Headers com design consistente (azul com texto branco)
  - Melhorias de UX: indicadores visuais, validações aprimoradas
  - Layout otimizado para Contato/Endereço e Internações
  
- **Backend (v0.1.1):**
  - Correção no setup_database.sql: adicionado USE casamais_db
  - API de doações implementada e funcional
  - Estrutura preparada para novas entidades

### v0.1.0 (01/06/2025)
- **Frontend:**
  - Estrutura inicial com React + Vite
  - Páginas básicas criadas
  - Sistema de roteamento configurado
  - Serviços usando localStorage
  
- **Backend:**
  - API REST com Express
  - CRUD de medicamentos implementado
  - Conexão MySQL configurada
  - Estrutura MVC + Repository

## Estado Atual da Integração

### ✅ Integrado
- **Assistidas**: CRUD completo funcionando com API
- **Medicamentos**: CRUD completo funcionando com API
- **Doações**: CRUD completo funcionando com API

### ❌ Pendente
- **Consultas**: Módulo não implementado
- **Despesas**: Módulo não implementado
- **Usuários**: Sistema de autenticação não implementado

## Estrutura dos Submódulos

| Submódulo | Repositório | Branch Atual |
|-----------|-------------|--------------|
| frontend/ | https://github.com/fabioaloisio/casa-mais-react | update-frontend-readme |
| backend/ | https://github.com/aldruin/casa-mais-backend | update-backend-readme |

## Próximas Versões Planejadas

### v0.4.0 (Planejado)
- **Frontend:**
  - Conectar módulo de assistidas com API
  - Implementar paginação nas listagens
  - Adicionar filtros avançados
  
- **Backend:**
  - Implementar autenticação JWT
  - Adicionar endpoints de relatórios
  - Implementar soft delete

### v1.0.0 (Release)
- **Geral:**
  - Todos os módulos integrados
  - Sistema de autenticação completo
  - Testes automatizados
  - Documentação completa
  - Deploy em produção

## Notas de Desenvolvimento

- **Ambiente:** Desenvolvimento local
- **Banco de Dados:** MySQL 8.0 (casamais_db)
- **Node.js:** Versão 16+ requerida
- **Portas:** Backend (3003), Frontend (5173)
- **Submódulos:** Usar `git clone --recurse-submodules` para clonar projeto completo