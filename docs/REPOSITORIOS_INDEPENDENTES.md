# REPOSITÓRIOS INDEPENDENTES

Este projeto utiliza uma estrutura de **3 repositórios Git independentes** para flexibilidade no desenvolvimento e deploy.

## Estrutura dos Repositórios

```
casa_mais/                      # Repositório Principal
├── .git/                       # Git do projeto completo
├── frontend/                   # Submódulo Frontend (casa-mais-react)
│   └── .git/                   # Git independente do React
└── backend/                    # Submódulo Backend (casa-mais-backend)
    └── .git/                   # Git independente do Node.js/Express
```

## ⚠️ IMPORTANTE: Como Funcionam os Submódulos

### Submódulos Git

Este projeto usa **submódulos Git**, que são repositórios Git independentes referenciados pelo repositório principal.

**ATENÇÃO:** Cada submódulo é um repositório completo. Commits em um NÃO afetam os outros.

#### ❌ O que NÃO funciona:

```bash
# Alterar arquivos no frontend e backend
# Depois tentar commitar tudo pelo principal
cd /casa_mais
git add .
git commit -m "nova feature"  # NÃO commitará as alterações dos subdiretórios!
```

#### ✅ Como fazer corretamente:

1. **Commitar no Frontend:**

```bash
cd frontend
git add .
git commit -m "feat: implementa nova funcionalidade no frontend"
git push origin main
```

2. **Commitar no Backend:**

```bash
cd ../backend
git add .
git commit -m "feat: implementa API para nova funcionalidade"
git push origin main
```

3. **Atualizar referências no Principal:**

```bash
cd ..
git add frontend backend    # Atualiza referências dos submódulos
git commit -m "chore: atualiza submódulos para últimas versões"
git push origin main
```

## Comportamento dos Submódulos

Quando o Git detecta submódulos:

- **Trackeia apenas a referência** (commit específico) de cada submódulo
- **Não inclui** o conteúdo dos arquivos dos submódulos
- **Gerencia** arquivos no nível raiz e as referências dos submódulos

## Fluxo de Trabalho Recomendado

### Para Features Completas (Front + Back):

1. **Criar branch em cada submódulo:**

```bash
# Frontend
cd frontend
git checkout -b feature/nova-funcionalidade

# Backend
cd ../backend
git checkout -b feature/nova-funcionalidade
```

2. **Desenvolver e commitar separadamente**

3. **Fazer PRs/merges independentes**

4. **Documentar no principal** (se necessário)

### Para Alterações Específicas:

- **Só Frontend:** Trabalhe apenas em `frontend/`
- **Só Backend:** Trabalhe apenas em `backend/`
- **Só Docs/Config:** Trabalhe no repositório principal

## Vantagens desta Estrutura

1. **Deploy Independente:** Frontend e backend podem ter ciclos diferentes
2. **Equipes Separadas:** Times podem trabalhar sem interferência
3. **Histórico Limpo:** Commits focados em cada área
4. **CI/CD Específico:** Pipelines otimizados para cada stack

## Coordenação de Versões

Mantemos um arquivo `VERSIONS.md` no repositório principal documentando:

- Versão atual do frontend: **v0.2.0** (02/06/2025)
- Versão atual do backend: **v0.1.1** (02/06/2025)
- Compatibilidade entre versões: ✅ Compatíveis
- Histórico detalhado de mudanças

## Comandos Úteis para Submódulos

```bash
# Atualizar todos os submódulos para latest
git submodule update --remote --merge

# Ver status dos submódulos
git submodule status

# Clonar projeto com submódulos
git clone --recurse-submodules https://github.com/julianocamposcode/casa_mais

# Adicionar submódulo (exemplo)
git submodule add https://github.com/user/repo.git nome-pasta
```

## Resumo

- **3 repositórios Git: 1 principal + 2 submódulos**
- **Commits devem ser feitos em cada repositório separadamente**
- **Repositório principal trackeia referências dos submódulos**
- **Cada submódulo é um repositório Git completo e independente**
