# Esteira CI/CD Automatizada - Projeto DevOps

Este repositório contém uma esteira completa de **Integração Contínua (CI)**, **Automação de Processos** e **Entrega Contínua (CD)**.

## 🏗️ Arquitetura da Esteira

O pipeline está dividido em três fases lógicas para garantir organização e visibilidade:

### 1. 🛡️ Integração Contínua (CI)
*   **Frequência**: Disparado em cada push para `main` ou Pull Requests.
*   **Ações**: Valida estrutura de arquivos, executa Linting de HTML (qualidade de código) e gera artefatos de build.

### 2. 🤖 Automação de PR & Merge
*   **Frequência**: Disparado ao criar branches do tipo `feature/*`, `fix/*` ou `hotfix/*`.
*   **Ações**: Cria automaticamente uma Pull Request para a `main` e ativa o **Auto-Merge**. 
*   **Vantagem**: O desenvolvedor foca no código, e a esteira cuida da burocracia do GitHub.

### 3. 🚀 Entrega Contínua (CD)
*   **Frequência**: Disparado automaticamente após o sucesso da fase de CI.
*   **Ações**: Realiza o deploy automático do site validado para o **GitHub Pages**.

## 📂 Estrutura do Projeto

```text
esteira-ci-cd/
├── site/               # Código fonte do site estático
├── .github/
│   └── workflows/      # Definições dos pipelines
│       ├── ci.yml              # Fase 1: Validação e Build
│       ├── automation-pr.yml   # Fase 2: Automação de PR
│       └── cd.yml              # Fase 3: Deploy para Produção
└── README.md           # Documentação
```

## 🛠️ Configuração Necessária

Para que a automação funcione 100%, verifique:
1.  **Settings > Actions > General**: Habilite *"Allow GitHub Actions to create and approve pull requests"*.
2.  **Settings > Pages**: Mude o *Source* para *"GitHub Actions"*.
3.  **Settings > General**: Habilite *"Allow auto-merge"*.

---
Projeto desenvolvido para fins educacionais em DevOps.
