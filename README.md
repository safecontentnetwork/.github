# Safe Content Platform

Uma plataforma robusta para detectar conteúdo gerado por Inteligência Artificial, plágio, imagens manipuladas e vídeos deepfake. 

O objetivo é fornecer uma ferramenta simples e confiável para usuários validarem a autenticidade de conteúdos digitais.

## 🎯 Sobre o Projeto
Este projeto consiste em uma aplicação multiplataforma (Mobile, Web e Desktop) construída com Flutter, que se comunica com um middleware em .NET 8. Este backend, por sua vez, integra-se com diversas APIs de terceiros especializadas na análise e validação de textos, imagens e vídeos.A arquitetura foi desenhada para ser modular, escalável e fácil de manter, utilizando containers Docker para o ambiente de desenvolvimento e com um plano claro para migração para a nuvem.

## ✨ Principais Funcionalidades (MVP)
- **Análise de Texto:** Detecção de plágio e conteúdo gerado por IA.
- **Análise de Imagem:** Detecção de manipulações, montagens e conteúdo gerado por IA.
- **Análise de Vídeo:** Detecção de deepfakes com um score de confiança simplificado.

## 🚀 Começando
Siga estas instruções para configurar e executar o ambiente de desenvolvimento em sua máquina local.📋 Pré-requisitosAntes de começar, garanta que você tenha as seguintes ferramentas instaladas:
- **Docker e Docker Compose** - Para orquestração dos containers.
- **.NET 8 SDK** - Para o desenvolvimento do backend.
- **Flutter 3.x+ SDK** - Para o desenvolvimento do frontend.
- **Git** - Para controle de versão.Um editor de código de sua preferência (recomendamos o VS Code com as extensões para Docker, C# e Dart/Flutter).

## ⚙️ Executando o Ambiente Localmente

Clone os Repositórios: Este projeto utiliza uma abordagem multi-repo. Clone todos os repositórios necessários para a sua máquina.

### Exemplo (execute para cada repositório)

```
git clone https://github.com/sua-organizacao/api-csharp.git
git clone https://github.com/sua-organizacao/app-flutter.git
git clone https://github.com/sua-organizacao/db-postgres.git
git clone https://github.com/sua-organizacao/ops.git
```

### Configure as Variáveis de Ambiente:

Navegue até a pasta do repositório de operações: `cd ops/docker`.
Copie o arquivo de exemplo .env.example para um novo arquivo chamado .env.
```
cp .env.example .env
```
Abra o arquivo .env e preencha as variáveis, incluindo as credenciais do banco de dados e as chaves das APIs de terceiros.

### Suba os Containers: 
Com o Docker em execução, execute o seguinte comando na pasta ops/docker para construir as imagens e iniciar todos os serviços.

```
docker compose up -d --build
```

### Verifique se está tudo funcionando: 
Após alguns instantes, todos os serviços estarão disponíveis.Use docker compose ps para ver o status dos containers.

A API estará acessível em `http://localhost:8080` (ou no endereço configurado no seu reverse proxy, como `http://api.validacao.localhost`).O banco de dados PostgreSQL estará acessível na porta 5432.

# 🏗️ Estrutura do Projeto

O projeto é dividido em múltiplos repositórios, cada um com uma responsabilidade clara:
**app-flutter/:** Código-fonte do aplicativo frontend para Android, iOS, Web e Desktop.
**api-csharp/:** Middleware em .NET 8 que expõe uma API REST e orquestra as chamadas para os serviços de validação.
**db-postgres/:** Scripts de migração e configuração inicial do banco de dados PostgreSQL.
**integrations/:** SDKs e clientes C# para facilitar a comunicação com as APIs de terceiros.
**ops/:** Configurações de infraestrutura, incluindo os arquivos do Docker Compose, pipelines de CI/CD e documentação operacional.

#📄 Licença

Este projeto está licenciado sob a Licença MIT. Veja o arquivo LICENSE para mais detalhes.
