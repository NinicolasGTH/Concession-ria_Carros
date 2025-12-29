# 🚗 Sistema de Concessionária de Automóveis

Sistema completo para gerenciamento de concessionária de automóveis, desenvolvido com backend em Go, frontend em React e dashboard analítico em Python.

## 📋 Sobre o Projeto

Sistema integrado que permite o gerenciamento completo de uma concessionária de automóveis, incluindo:
- Cadastro e gerenciamento de veículos
- Controle de compras e vendas
- Gestão de funcionários
- Dashboard analítico com visualização de dados

## 🚀 Tecnologias Utilizadas

### Backend
- **Go 1.24.3**
- **Gin** - Framework web
- **GORM** - ORM para manipulação de banco de dados
- **PostgreSQL** - Banco de dados principal
- **Docker** - Containerização da aplicação

### Frontend
- **React 18.3** - Biblioteca JavaScript
- **Vite** - Build tool e dev server
- **React Router DOM** - Roteamento
- **Axios** - Cliente HTTP
- **React Icons** - Ícones

### Dashboard
- **Python**
- **Streamlit** - Framework para dashboards
- **Pandas** - Análise de dados
- **Plotly** - Visualização de dados

## 📁 Estrutura do Projeto

```
.
├── app.go                      # Aplicação principal
├── docker-compose.yml          # Configuração Docker
├── Dockerfile                  # Imagem Docker da API
├── go.mod                      # Dependências Go
│
├── carro/                      # Módulo de Carros
│   ├── carro_controller.go
│   ├── carro_models.go
│   ├── carro_repository.go
│   └── carro_route.go
│
├── compra/                     # Módulo de Compras
│   ├── compra_controller.go
│   ├── compra_models.go
│   ├── compra_repository.go
│   └── compra_route.go
│
├── venda/                      # Módulo de Vendas
│   ├── venda_controller.go
│   ├── venda_models.go
│   ├── venda_repository.go
│   └── venda_route.go
│
├── funcionario/                # Módulo de Funcionários
│   ├── func_controller.go
│   ├── func_models.go
│   ├── func_repository.go
│   └── func_route.go
│
├── config/                     # Configurações
│   └── config.go
│
├── frontend-react/             # Frontend React + Vite
│   ├── src/
│   │   ├── App.jsx
│   │   ├── main.jsx
│   │   ├── lib/
│   │   │   └── api.js
│   │   └── pages/
│   │       ├── HomePage.jsx
│   │       ├── CarrosPage.jsx
│   │       ├── ComprasPage.jsx
│   │       ├── VendasPage.jsx
│   │       └── FuncionariosPage.jsx
│   └── package.json
│
└── dashboard-python/           # Dashboard de Análises
    ├── app.py
    └── requirements.txt
```

## 🛠️ Instalação e Execução

### Usando Docker (Recomendado)

1. Clone o repositório:
```bash
git clone https://github.com/NinicolasGTH/Concession-ria_Carros.git
cd Concession-ria_Carros
```

2. Execute com Docker Compose:
```bash
docker-compose up -d
```

A API estará disponível em: `http://localhost:6000`
O banco de dados MySQL em: `localhost:3307`

### Sem Docker

#### Backend (Go)

1. Instale as dependências:
```bash
go mod download
```

2. Configure as variáveis de ambiente:
```bash
export DB_USER=root
export DB_PASSWORD=minhasenha
export DB_NAME=concessionaria_db
export DB_HOST=localhost
```

3. Execute a aplicação:
```bash
go run app.go
```

#### Frontend (React)

1. Entre na pasta do frontend:
```bash
cd frontend-react
```

2. Instale as dependências:
```bash
npm install
```

3. Execute o servidor de desenvolvimento:
```bash
npm run dev
```

O frontend estará disponível em: `http://localhost:5173`

#### Dashboard (Python)

1. Entre na pasta do dashboard:
```bash
cd dashboard-python
```

2. Instale as dependências:
```bash
pip install -r requirements.txt
```

3. Execute o dashboard:
```bash
streamlit run app.py
```

## 🔌 Endpoints da API

### Carros
- `GET /carros` - Lista todos os carros
- `GET /carros/:placa` - Busca carro por placa
- `POST /carros` - Cadastra novo carro
- `PUT /carros/:placa` - Atualiza dados do carro
- `DELETE /carros/:placa` - Remove carro

### Compras
- `GET /compras` - Lista todas as compras
- `GET /compras/:id` - Busca compra por ID
- `POST /compras` - Registra nova compra
- `PUT /compras/:id` - Atualiza compra
- `DELETE /compras/:id` - Remove compra

### Vendas
- `GET /vendas` - Lista todas as vendas
- `GET /vendas/:id` - Busca venda por ID
- `POST /vendas` - Registra nova venda
- `PUT /vendas/:id` - Atualiza venda
- `DELETE /vendas/:id` - Remove venda

### Funcionários
- `GET /funcionarios` - Lista todos os funcionários
- `GET /funcionarios/:id` - Busca funcionário por ID
- `POST /funcionarios` - Cadastra novo funcionário
- `PUT /funcionarios/:id` - Atualiza funcionário
- `DELETE /funcionarios/:id` - Remove funcionário

## 📊 Funcionalidades

### Gestão de Veículos
- Cadastro completo com foto, placa, marca, modelo, ano, cor, km e valor
- Listagem com filtros e busca
- Atualização de informações
- Exclusão de veículos

### Controle de Compras
- Registro de compras de veículos
- Rastreamento de custos
- Histórico completo de aquisições

### Controle de Vendas
- Registro de vendas
- Controle de receitas
- Histórico de transações

### Gestão de Funcionários
- Cadastro de funcionários
- Controle de equipe
- Atualização de informações

### Dashboard Analítico
- Visualização de métricas de vendas
- Análise de estoque
- Gráficos interativos com Plotly
- Relatórios customizáveis

## 🔧 Configuração do Banco de Dados

O projeto utiliza MySQL 8.0 com as seguintes configurações padrão:

```yaml
Host: localhost
Porta: 3307
Usuário: root
Senha: minhasenha
Database: concessionaria_db
```

As tabelas são criadas automaticamente via GORM AutoMigrate.

## 🌐 CORS

O backend está configurado para aceitar requisições de qualquer origem durante o desenvolvimento. Para produção, ajuste em [app.go](app.go):

```go
AllowOrigins: []string{"https://seu-dominio.com"},
```

## 📝 Licença

Este projeto foi desenvolvido para fins educacionais e de portfólio.

## 👨‍💻 Autor

**Nicolas GTH**
- GitHub: [@NinicolasGTH](https://github.com/NinicolasGTH)

---

⭐ Se este projeto foi útil para você, considere dar uma estrela!
