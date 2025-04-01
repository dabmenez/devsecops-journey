# YAML / YML

YAML, também conhecido como YML (YAML Ain't Markup Language), é uma linguagem de serialização de dados legível por humanos, comumente utilizada para arquivos de configuração.

Além disso, é amplamente utilizada em plataformas CI/CD (Integração Contínua / Entrega Contínua) para definir pipelines. Algumas plataformas conhecidas que utilizam YAML incluem GitLab, GitHub Actions e Azure DevOps. Conhecer a sintaxe e estrutura do YAML é essencial para escrever pipelines em diferentes produtos.

## Sintaxe Chave do YAML

- Indentação é vital: arquivos YAML não alinhados corretamente são inválidos.
- Usa espaços, não tabulação.
- Comentários começam com `#`.

### Exemplo de sintaxe YAML:
```yaml
pool:
  vmImage: ubuntu-latest

# exemplo de comentário
stages:
  - stage: example
    jobs:
      - job: example
        steps:
          - script: echo "hello world"
```

## Dicas para uso

- Utilize YAML ao invés de tarefas gráficas (GUI).
- Pipelines utilizam *runners* ou *agents*, dependendo do software, que são os componentes responsáveis por executar as etapas definidas no pipeline.

## YAML no GitLab vs Azure DevOps

### GitLab (`.gitlab-ci.yml`)
```yaml
stages:
  - example

example:
  stage: example
  script: echo "hello world"
```

### Azure DevOps (`azure-pipelines.yml`)
```yaml
stages:
  - stage: example
    jobs:
      - job: example
        steps:
          - script: echo "hello world"
```

Apesar de algumas diferenças, a base da sintaxe é similar. Uma vez dominado o YAML, é possível aplicar o conhecimento em diversas plataformas de CI/CD com pequenas adaptações.