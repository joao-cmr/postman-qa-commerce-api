# Postman + Newman - QA Commerce API Testing

[![Newman API Tests](https://github.com/joao-cmr/postman-qa-commerce-api/actions/workflows/newman-tests.yml/badge.svg?branch=main)](https://github.com/joao-cmr/postman-qa-commerce-api/actions/workflows/newman-tests.yml)

Automação de testes de API para a aplicação **QA Commerce** utilizando Postman Collections e Newman CLI, com integração contínua via GitHub Actions.

##  Sobre o Projeto

Este repositório contém testes automatizados da API REST do QA Commerce, cobrindo operações CRUD de usuários, autenticação, carrinho de compras e pedidos. Os testes são executados via Newman (CLI do Postman) e geram relatórios HTML detalhados.

**API testada:** [QA Commerce API](https://github.com/joao-cmr/qa-commerce)

##  Tecnologias Utilizadas

- **Postman** - Criação e organização das collections
- **Newman** - Execução de testes via linha de comando
- **newman-reporter-htmlextra** - Geração de relatórios HTML
- **GitHub Actions** - CI/CD para execução automatizada

##  Estrutura do Projeto
```
postman-qa-commerce-api/
├── collections/
│   └── qa-commerce-api.postman_collection.json    # Collection principal
├── environments/
│   └── qa-commerce.postman_environment.json       # Variáveis de ambiente
├── .github/
│   └── workflows/
│       └── newman-tests.yml                       # Pipeline CI/CD
├── reports/                                        # Relatórios gerados (git ignored)
├── package.json
└── README.md
```

##  Como Executar

### Pré-requisitos

- Node.js 18+ instalado
- npm ou yarn

### Instalação
```bash
# Clone o repositório
git clone https://github.com/joao-cmr/postman-qa-commerce-api.git
cd postman-qa-commerce-api

# Instale as dependências
npm install
```

### Executando os Testes
```bash
# Execução simples
npm test

# Execução com relatório HTML
npm run test:report

# Execução verbose (detalhes completos)
npm run test:verbose
```

### Visualizando Relatórios

Após executar `npm run test:report`, abra o arquivo `reports/report.html` no navegador para visualizar o relatório detalhado com:
- Total de testes executados
- Taxa de sucesso/falha
- Tempo de resposta das requisições
- Detalhes de cada endpoint testado

##  CI/CD - GitHub Actions

Os testes são executados automaticamente a cada push ou pull request na branch `main`. O workflow:

1. Configura o ambiente Node.js 20
2. Instala as dependências
3. Executa a collection via Newman
4. Gera relatório HTML
5. Disponibiliza o relatório como artifact

Acesse a aba **Actions** do repositório para visualizar as execuções e baixar os relatórios.

##  Cobertura de Testes

### Endpoints Testados

- **POST** `/login` - Autenticação de usuário
- **POST** `/api/users` - Criação de usuário
- **GET** `/api/users` - Listagem de usuários
- **PUT** `/api/users/{id}` - Atualização de cadastro
- **DELETE** `/api/users/{id}` - Remoção de usuário
- **GET** `/carrinho/{userid}` - Consulta de carrinho
- **POST** `/carrinho` - Adicionar produto ao carrinho
- **DELETE** `/carrinho/{userid}` - Limpar carrinho
- **DELETE** `/carrinho/{userid}/{productid}` - Remover item específico

### Cenários Validados

✅ Criação de usuário com sucesso  
✅ Login com credenciais válidas  
✅ Validação de campos obrigatórios  
✅ Alteração de cadastro  
✅ Exclusão de usuário  
✅ Operações de carrinho (adicionar, listar, remover)  
✅ Tratamento de erros (404, 400, 401)  

##  Próximos Passos

- [ ] Adicionar testes de endpoints de produtos
- [ ] Implementar testes de pedidos (orders)
- [ ] Validações de performance (response time)
- [ ] Testes de segurança (SQL injection, XSS)
- [ ] Integração com ferramentas de monitoring

##  Autor

**João Carlos**  
QA Analyst | Test Automation  

[![LinkedIn](https://img.shields.io/badge/LinkedIn-joaocmr-blue?style=flat-square&logo=linkedin)](https://linkedin.com/in/joaocmr)
[![GitHub](https://img.shields.io/badge/GitHub-joao--cmr-black?style=flat-square&logo=github)](https://github.com/joao-cmr)

---

⭐ Se este repositório foi útil, deixe uma estrela!
