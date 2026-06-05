# Esteira CI/CD Automatizada - Projeto DevOps

Este repositório contém um exemplo prático de uma esteira de **Integração Contínua (CI)** e **Entrega Contínua (CD)** utilizando GitHub Actions para automatizar o deploy de um site estático no GitHub Pages.

## 🚀 Tecnologias Utilizadas

*   **HTML5/CSS3**: Estrutura e estilo do site.
*   **Git/GitHub**: Controle de versão e hospedagem do código.
*   **GitHub Actions**: Automação dos pipelines de CI e CD.
*   **HTMLHint**: Validação de qualidade e sintaxe do código HTML.
*   **GitHub Pages**: Hospedagem automatizada do site.

## 🏗️ Arquitetura do Pipeline

O projeto utiliza dois workflows desacoplados:

1.  **CI Pipeline (`ci.yml`)**:
    *   Disparado em cada `push` ou `pull_request` para a branch `main`.
    *   **Jobs**:
        *   `validate`: Realiza o checkout, verifica a existência dos arquivos, valida a sintaxe HTML (Linting) e gera um artefato (`site-build`).

2.  **CD Pipeline (`cd.yml`)**:
    *   Disparado automaticamente após o sucesso do **CI Pipeline**.
    *   **Jobs**:
        *   `deploy`: Faz o download do artefato validado e realiza o deploy para o GitHub Pages utilizando as APIs oficiais do GitHub.

## 📂 Estrutura do Projeto

```text
esteira-ci-cd/
├── site/               # Arquivos do site estático
│   └── index.html      # Página principal
├── .github/
│   └── workflows/      # Definições dos pipelines
│       ├── ci.yml      # Pipeline de Integração Contínua
│       └── cd.yml      # Pipeline de Entrega Contínua
└── README.md           # Documentação do projeto
```

## 🛠️ Como Utilizar

### 1. Preparação
Certifique-se de que o GitHub Pages está configurado para usar GitHub Actions:
*   Vá em **Settings** > **Pages**.
*   Em **Build and deployment** > **Source**, selecione **GitHub Actions**.

### 2. Executando o Pipeline
Basta realizar um push para a branch `main`:

```bash
git add .
git commit -m "docs: adiciona readme e melhorias no ci"
git push origin main
```

### 3. Monitoramento
*   Acompanhe o progresso na aba **Actions** do seu repositório.
*   O CI validará o código e, se aprovado, o CD fará o deploy.
*   A URL final será exibida nos logs do job de deploy.

## ✅ Melhorias Implementadas

*   **Validação de Sintaxe (Linting)**: Adicionado `htmlhint` ao CI para garantir que o código HTML esteja livre de erros estruturais.
*   **Artefatos Versionados**: Uso de artefatos para garantir que o código testado seja o mesmo código implantado.
*   **Segurança**: Configuração de permissões mínimas (`permissions`) no workflow de CD.

---
Projeto desenvolvido para fins educacionais em DevOps.
