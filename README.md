### Documento de Projeto de Testes - OS-Tracker para Gestão de Ordens de Serviço

---

#### Histórico de Revisões
- **Data**: 05/10/2024  
- **Versão**: 1.0  
- **Descrição**: Primeira versão do documento de testes para OS-Tracker com foco em operações CRUD.  
- **Autores**: Thialy Sthéfany Medeiros de Lima, Larissa dos Santos Oliveira.

#### Índice
1. Introdução
2. Recursos
3. Riscos
4. Cronograma
5. Estratégia de Testes
6. Níveis de Testes
7. Casos de Teste

---

### 1. Introdução

#### 1.1 Propósito do Documento
Este documento visa estabelecer e descrever os testes para o sistema **OS-Tracker**, desenvolvido para gerenciamento de ordens de serviço em manutenção de equipamentos, garantindo que as funcionalidades de cadastro, leitura, atualização e exclusão (CRUD) funcionem conforme esperado. O objetivo é assegurar que todos os processos críticos do sistema estejam operacionais e alinhados aos requisitos.

#### 1.2 Interessados
| Perfil       | Nome                            | Contato                           |
|--------------|---------------------------------|-----------------------------------|
| Desenvolvedor| Thialy Sthéfany Medeiros de Lima| thialys.lima@unifacol.edu.br      |
| Desenvolvedor| Larissa dos Santos Oliveira     | larissas.oliveira@unifacol.edu.br |

---

### 2. Recursos

#### 2.1 Ambiente de Testes
Para a execução dos testes do OS-Tracker, foram definidos os seguintes requisitos e configurações:
- **Ambiente Backend**: Aplicação em Java com Spring Boot.
- **Frontend**: Aplicação Angular utilizando TypeScript.
- **Banco de Dados**: PostgreSQL hospedado na nuvem pelo Supabase.
- **Outras Dependências**:
   - *JUnit* para testes de unidade.
   - *Postman* para testes de API.

#### 2.2 Pessoas Envolvidas
| Nome         | Função                         | Contato                           |
|--------------|--------------------------------|-----------------------------------|
| Thialy       | Backend e Integração           | thialys.lima@unifacol.edu.br      |
| Larissa      | Frontend e Testes de Interface | larissas.oliveira@unifacol.edu.br |

---

### 3. Riscos

| Risco                    | Responsável | Estratégia             | Ação                                         |
|--------------------------|-------------|------------------------|----------------------------------------------|
| Falha de integração      | Thialy      | Teste de Integração    | Validar as comunicações entre componentes    |
| Inconsistência de dados  | Larissa     | Teste de Sistema       | Verificar atualizações no PostgreSQL         |
| Tempo de resposta lento  | Thialy      | Teste de Desempenho    | Monitorar o desempenho                       |

---

### 4. Cronograma

| Fase                        | Data Início | Data Fim   |
|-----------------------------|-------------|------------|
| Construção dos Testes       | 05/10/2024  | 05/11/2024 |
| Execução dos Testes         | 10/10/2024  | 10/11/2024 |
| Análise dos Resultados      | 20/10/2024  | 20/11/2024 |

---

### 5. Estratégia de Testes

#### 5.1 Estratégias
- **Teste de Unidade**: Foco em métodos individuais usando JUnit.
- **Teste de Integração**: Verificação das operações CRUD com troca de dados entre backend e frontend.
- **Teste de Validação**: Confirmação da conformidade com requisitos.
- **Teste de Sistema**: Validação do sistema OS-Tracker de ponta a ponta.

#### 5.2 Técnicas de Teste
- **Manuais**: Teste de usabilidade e verificação de interface.
- **Semi-automatizados**: Casos que exigem entrada de dados no sistema.
- **Automatizados**: Testes CRUD automatizados usando scripts JUnit.

#### 5.3 Cobertura de Código
Definida como 80% de cobertura desejável para o projeto OS-Tracker, com a meta mínima de 50%.

---

### 6. Níveis de Testes

| Dimensão de Qualidade | Tipo de Teste         | Descrição                                                                                  |
|-----------------------|-----------------------|--------------------------------------------------------------------------------------------|
| Funcionalidade        | Teste de função       | Testa CRUD para as entidades Client, Employee, Equipment e ServiceOrder                    |
| Confiabilidade        | Teste de Integridade  | Verifica a robustez das operações, como consulta e atualização no banco de dados           |
| Desempenho            | Teste de Carga        | Avaliação de desempenho com aumento da carga de ordens de serviço                          |
| Suportabilidade       | Teste de Configuração | Testa o sistema em diferentes configurações e valida a integração com o banco de dados     |

---

### 7. Casos de Testes

#### 7.1 Client CRUD
| ID do Teste | Descrição                          | Entrada                | Resultado Esperado                 |
|-------------|------------------------------------|------------------------|------------------------------------|
| T-CLI-01    | Criar novo cliente                 | Nome, email, telefone  | Cliente criado com sucesso         |
| T-CLI-02    | Consultar cliente                  | ID do cliente          | Retorna informações do cliente     |
| T-CLI-03    | Atualizar dados do cliente         | Nome, telefone         | Dados atualizados com sucesso      |
| T-CLI-04    | Excluir cliente                    | ID do cliente          | Cliente removido do sistema        |

#### 7.2 Employee CRUD
| ID do Teste | Descrição                          | Entrada                | Resultado Esperado                 |
|-------------|------------------------------------|------------------------|------------------------------------|
| T-EMP-01    | Criar novo funcionário             | Nome, cargo            | Funcionário criado com sucesso     |
| T-EMP-02    | Consultar funcionário              | ID do funcionário      | Retorna informações do funcionário |
| T-EMP-03    | Atualizar dados do funcionário     | Nome, cargo            | Dados atualizados com sucesso      |
| T-EMP-04    | Excluir funcionário                | ID do funcionário      | Funcionário removido do sistema    |

#### 7.3 Equipment CRUD
| ID do Teste | Descrição                          | Entrada                       | Resultado Esperado                 |
|-------------|------------------------------------|-------------------------------|------------------------------------|
| T-EQP-01    | Registrar novo equipamento         | Nome, modelo, número de série | Equipamento registrado             |
| T-EQP-02    | Consultar equipamento              | Número de série               | Retorna informações do equipamento |
| T-EQP-03    | Atualizar dados do equipamento     | Nome, modelo                  | Dados atualizados com sucesso      |
| T-EQP-04    | Excluir equipamento                | Número de série               | Equipamento removido do sistema    |

#### 7.4 ServiceOrder CRUD
| ID do Teste | Descrição                          | Entrada                           | Resultado Esperado                 |
|-------------|------------------------------------|-----------------------------------|------------------------------------|
| T-SO-01     | Criar nova ordem de serviço        | Cliente, equipamento, responsável | OS criada com sucesso              |
| T-SO-02     | Consultar ordem de serviço         | Número da OS                      | Retorna informações da OS          |
| T-SO-03     | Atualizar dados da ordem de serviço| Status, responsável               | Dados da OS atualizados            |
| T-SO-04     | Excluir ordem de serviço           | Número da OS                      | OS removida do sistema             |

---
