# SORTEIO CARVALHO
[![NPM](https://img.shields.io/npm/l/react)](https://github.com/devsuperior/sds1-wmazoni/blob/master/LICENSE) 

# Sobre o projeto

O sistema foi desenvolvido para realizar sorteios de brindes entre colaboradores da Carvalho Cargo, uma empresa voltada para o seguimento de frete de transportes. A aplicação possui uma interface web dinâmica, com integração ao Supabase para armazenamento de dados.

A aplicação permite cadastrar prêmios e colaboradores (vinculados a filiais). Além disso, possui um modo de apresentação que exibe, de forma sequencial, as filiais e seus respectivos colaboradores.

## Layout web
![Web 1](https://github.com/acenelio/assets/raw/main/sds1/web1.png)

## Funcionalidades
Cadastro de Prêmios: Permite cadastrar prêmios com uma ordem de sorteio

Sorteio Dinâmico: Realiza sorteios com animação de caminhão trazendo o resultado

Modo Apresentação: Exibe automaticamente todas as filiais e seus colaboradores

Integração com Supabase: Todos os dados são armazenados e gerenciados no Supabase

Interface Moderna: Design responsivo com tema de transporte nas cores laranja e branco

## Modelo de dados
O sistema utiliza três tabelas no Supabase:

filiais: Armazena as filiais da empresa

colaboradores: Armazena os colaboradores, cada um vinculado a uma filial

premios: Armazena os prêmios a serem sorteados, com uma ordem de sorteio

# Tecnologias utilizadas
## Back end
- Supabase - Backend as a Service (BaaS)
- PostgreSQL - Banco de dados
## Front end
- HTML5
- CSS3
- JavaScript (ES6+)
- Tailwind CSS - Framework CSS
- Supabase JS - Cliente JavaScript para Supabase
## Implantação em produção
- Front end: Hospedagem estática
- Back end: Supabase (gerenciamento automático)
- Banco de dados: PostgreSQL (através do Supabase)

# Como executar o projeto

## Pré-requisitos
- Conta no Supabase
- Navegador web moderno

## Configuração do Supabase
1. Crie um projeto no Supabase
2. Execute os seguintes comandos SQL para criar as tabelas:
   
```bash
-- Tabela de filiais
CREATE TABLE filiais (
  id SERIAL PRIMARY KEY,
  nome VARCHAR(255) NOT NULL,
  created_at TIMESTAMP DEFAULT NOW()
);

-- Tabela de colaboradores
CREATE TABLE colaboradores (
  id SERIAL PRIMARY KEY,
  nome VARCHAR(255) NOT NULL,
  filial_id INTEGER REFERENCES filiais(id),
  created_at TIMESTAMP DEFAULT NOW()
);

-- Tabela de prêmios
CREATE TABLE premios (
  id SERIAL PRIMARY KEY,
  nome VARCHAR(255) NOT NULL,
  ordem INTEGER NOT NULL,
  created_at TIMESTAMP DEFAULT NOW()
);
```

# Uso do sitema

## Cadastro de Prêmios
1. Acesse a aba "Cadastrar Prêmios"
2. Preencha o nome do prêmio e a ordem de sorteio
3. Clique em "Adicionar"

## Realizar Sorteio
1. Acesse a aba "Sorteio"
2. Clique no botão "Sortear"
3. Aguarde a animação do caminhão e o resultado

## Modo Apresentação
1. Clique no botão "Apresentação" no cabeçalho
2. O sistema mostrará automaticamente todas as filiais e seus colaboradores
3. Cada filial é exibida por 5 segundos antes de passar para a próxima

