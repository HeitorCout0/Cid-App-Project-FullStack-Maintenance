# CID APP — Manutenção de Software e Métricas de Qualidade

![Java](https://skillicons.dev/icons?i=java)
![Spring](https://skillicons.dev/icons?i=spring)
![PostgreSQL](https://skillicons.dev/icons?i=postgres)
![React](https://skillicons.dev/icons?i=react)
![Vite](https://skillicons.dev/icons?i=vite)
![Bootstrap](https://skillicons.dev/icons?i=bootstrap)

Plataforma full-stack de gestão de serviços municipais — projeto acadêmico desenvolvido para a govtech fictícia **ObservaAção**, alinhada às ODS 10, 11 e 16 da ONU.

Este repositório é a contribuição de **Heitor Couto** ao projeto, com foco em **Manutenção de Software** e aplicação de ferramentas de análise estática de código.

---

## Sobre o Projeto

Cidadãos enfrentam dificuldades para solicitar serviços públicos, acompanhar protocolos e ter retorno efetivo. O CidApp resolve isso oferecendo:

- Registro de solicitações com categoria, localização, prioridade e opção de anonimato
- Acompanhamento de status com histórico de movimentações
- Painel para atendentes e gestores com rastreabilidade
- Controle de acesso por roles: Cidadão, Servidor, Gestor

---

## Stack

**Backend:** Java 21 · Spring Boot · Spring Security · JWT · Spring Data JPA · PostgreSQL · Lombok

**Frontend:** React · Vite · React Router · Axios · Bootstrap

---

## Métricas de Qualidade de Código

Esta branch inclui integração com ferramentas de análise estática para medir e discutir a qualidade e manutenibilidade do código.

### Ferramentas utilizadas

| Ferramenta | O que analisa |
|---|---|
| **SonarCloud** | Bugs, Code Smells, vulnerabilidades, duplicações, maintainability index |
| **Checkstyle** | Conformidade com padrões de estilo (Google Java Style Guide) |
| **PMD** | Más práticas, código morto, CPD (Copy-Paste Detection) |
| **SpotBugs** | Bugs potenciais em tempo de execução (análise bytecode) |

### Como rodar os relatórios localmente

**Pré-requisito:** Java 21 e Maven instalados.

```bash
cd backend/Back-End

# Compila e gera todos os relatórios HTML
mvn site -DskipTests
```

Relatórios gerados em `backend/Back-End/target/site/`:
- `checkstyle.html` — violações de estilo
- `pmd.html` — más práticas e código duplicado
- `spotbugs.html` — bugs potenciais

### Como rodar o SonarCloud

```bash
cd backend/Back-End

mvn sonar:sonar \
  -Dsonar.projectKey=SEU_PROJECT_KEY \
  -Dsonar.organization=SEU_ORG_KEY \
  -Dsonar.host.url=https://sonarcloud.io \
  -Dsonar.token=SEU_TOKEN \
  -DskipTests
```

Dashboard: [sonarcloud.io](https://sonarcloud.io)

---

## Arquitetura

```
Frontend (React + Vite)
         │
         ▼
  REST API (Spring Boot)
         │
         ▼
Spring Security + JWT
         │
         ▼
      PostgreSQL
```

---

## Configuração do Ambiente

### Backend

```bash
cd backend/Back-End
```

Configure o `src/main/resources/application.properties`:
```properties
spring.datasource.url=jdbc:postgresql://localhost:5432/bd_api
spring.datasource.username=postgres
spring.datasource.password=SUA_SENHA
```

```bash
mvn spring-boot:run
```

API disponível em: `http://localhost:8080`

### Frontend

```bash
cd cid-app-front
npm install
npm run dev
```

Frontend disponível em: `http://localhost:5173`

---

## Controle de Acesso

| Role | Permissões |
|---|---|
| **Gestor** | Acesso total, gestão de usuários e demandas, dashboard admin |
| **Servidor** | Atualização de status, gerenciamento de solicitações |
| **Cidadão** | Abertura de solicitações, acompanhamento por protocolo |

---

## Contribuidores

- [SouzaRenann](https://github.com/SouzaRenann) — Desenvolvimento full-stack (backend + frontend)
- [HeitorCout0](https://github.com/HeitorCout0) — Manutenção de Software e métricas de qualidade
