# Esteira CI/CD Automatizada - Projeto DevOps

Este repositório contém uma esteira completa de **Integração Contínua (CI)**, **Automação de Processos** e **Entrega Contínua (CD)** projetada para garantir qualidade e agilidade no deploy.

## 🏗️ Arquitetura da Esteira

O pipeline está dividido em três fases lógicas e numeradas para máxima visibilidade:

### 1. 🛡️ Integração Contínua (CI)
*   **Frequência**: Disparado em cada `push` para branches de trabalho (`feature/*`, `fix/*`, etc.) e na branch `main`.
*   **Ações**: 
    *   Validação de estrutura de arquivos.
    *   Execução de **Linting (HTMLHint)** para garantir a qualidade do código.
    *   Geração de artefatos de build seguros.

### 2. 🤖 Automação de PR & Merge
*   **Frequência**: Disparado em pushes para branches `feature/*`, `fix/*` ou `hotfix/*`.
*   **Ações**: 
    *   Criação automática de Pull Request (PR) para a branch `main`.
    *   Ativação de **Auto-Merge** (caso habilitado no repositório).
    *   Geração de um **Job Summary** visual na aba Actions com o link da PR.

### 3. 🚀 Entrega Contínua (CD)
*   **Frequência**: Disparado automaticamente após a conclusão bem-sucedida do CI na branch `main`.
*   **Ações**: 
    *   Download do artefato validado.
    *   Deploy automatizado para o **GitHub Pages**.

## 📂 Estrutura do Projeto

```text
esteira-ci-cd-mack/
├── site/               # Código fonte (HTML/CSS)
├── .github/
│   └── workflows/      
│       ├── ci.yml              # Fase 1: Integração Contínua
│       ├── automation-pr.yml   # Fase 2: Automação de PR
│       └── cd.yml              # Fase 3: Deploy (CD)
└── README.md           # Documentação do Projeto
```

## 🛠️ Configurações Necessárias (Checklist)

Para que todas as automações funcionem corretamente, certifique-se de configurar seu repositório no GitHub:

1.  **Habilitar PRs via Actions**:
    *   `Settings > Actions > General` -> Marque *"Allow GitHub Actions to create and approve pull requests"*.
2.  **Habilitar Auto-Merge**:
    *   `Settings > General` -> Na seção Pull Requests, marque *"Allow auto-merge"*.
3.  **Configurar Origem do Pages**:
    *   `Settings > Pages` -> Em *Build and deployment > Source*, selecione **"GitHub Actions"**.

---
Projeto desenvolvido para fins educacionais em DevOps.
