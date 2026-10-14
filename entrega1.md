# TRABALHO PRÁTICO - ENGENHARIA DE SOFTWARE
## ETAPA 1: ESCOPO, BENCHMARKING, REQUISITOS, UML E TESTES

---

### 1. PROBLEMA E ESCOPO

* **Domínio Universitário Escolhido:**
  *Radar acadêmico*
* **Problema Identificado:**
  *Alunos não sabem quando vai ter eventos, e se vai haver docinho ou não nos eventos*
  *Professores só conseguem validar a demanda real por um evento após a execução*
* **Público-Alvo / Atores Principais:**
  *Alunos no geral, Professores organizadores*
* **As Duas Novas Funcionalidades Escolhidas:**
  1. **Disque-Docinho: um informe público de quando o próximo evento com docinhos vai ocorrer no INF**
  2. **Let's talk?: uma ferramenta de validação de interesses da comunidade acadêmica**
---

### 2. BENCHMARKING

#### 2.1. Referência Interna (Sistema da Própria Universidade)
* **Nome do Sistema: Mural de Notícias UFRGS**
* **Link: [https://www.ufrgs.br/prorext/eventos](https://www.ufrgs.br/prorext/eventos)**
* **Funcionalidade / Problema observado:** O sistema lista palestras, defesas de TCC e mestrado e seminários acadêmicos em formato puramente textual. Não há nada específico para docinhos.
* **Fluxos, regras ou informações relevantes identificadas:** Categorização por data, horário e título do palestrante/evento.
* **O que será aproveitado como referência no projeto:** A estrutura básica de exibição do cardápio de eventos
* **O que NÃO será aproveitado e por quê:** A ausência de informações especificas do INF correlações com filtro de data e informações de docinhos.

#### 2.2. Referência Externa (Pelo menos um sistema/plataforma real de fora)
* **Nome do Sistema / Plataforma:** meetup
* **Link de acesso:** https://www.meetup.com
* **Funcionalidade / Problema observado:** Gestão de comunidades de tecnologia e eventos presenciais/híbridos.
O organizador consegue lançar temas em discussão, medir o número de confirmados (RSVP)
* **Fluxos, regras ou informações relevantes identificadas:** Mecanismo de confirmação de presença prévia para dimensionamento de espaço e alimentação.
* **O que será aproveitado como referência no projeto:** O uso de tags visuais em destaque para conveniências (como a tag de docinhos/coffee break).
A lógica de quórum prévio: usar enquetes e votos de interesse para apoiar a decisão de viabilidade de alocação de recursos (auditório, orçamento de recepção).
* **O que NÃO será aproveitado e por quê:** Venda de ingressos, cobranças ou regras de check-in complexas com QR Code comercial: os eventos universitários são gratuitos e voltados ao engajamento comunitário.

---

### 3. REQUISITOS E HISTÓRIAS DE USUÁRIO (USER STORIES)

#### 3.1. Funcionalidade 1: [Nome da Funcionalidade 1]
* **User Story:**
  > *Como aluno faminto, eu quero consultar o próximo evento com docinhos, para que eu participe do próximo evento acadêmico, enquanto como docinhos.*
* **Critérios de Aceitação:**
  - **Se há evento sem docinho: não entra na lista**
  - **Se há docinho sem evento: não entra na lista**
  - **Se há docinho e evento: entra na lista**

#### 3.2. Funcionalidade 2: [Nome da Funcionalidade 2]
* **User Story:**
  > *Como professor, eu quero decidir se organizo um evento sobre Blockchain para a comunidade, para que eu desloque os recursos do INF de modo a maximizar o proveito acadêmico.*
* **Critérios de Aceitação:**
  - **Se há uma enquete: todos os alunos do INF devem poder votar**
  - **Se houve uma enquete: os dados devem ser visíveis por toda a comunidade**
  - **Se um professor quer fazer um evento: ele pode criar a enquete**

---

### 4. ESPECIFICAÇÃO DE CASOS DE USO

#### 4.1. Caso de Uso 01: Consultar próximo Coffe-break
* **Atores Envolvidos: Aluno**
* **Pré-condições: Disque-docinho operacional e atualizado**
* **Pós-condições: Aluno ciente da data e detalhes do proximo evento**
* **Fluxo Principal (Caminho Feliz):**
  1. O aluno acessa a tela Disque-docinho
  2. O sistema busca a lista de eventos cadastrados por ordem cronologica, apartir da data atual
  3. O sistema apresenta o próximo evento mais recente
* **Fluxos Alternativos:**
  * **2a.** Consultar lista completa
  * **2a.** Consultar lista filtrada com inicio e fim
* **Fluxos de Exceção (Erros e Falhas):**
  * **3e.** Não há eventos com docinhos programados: a comunidade fica triste

#### 4.2. Caso de Uso 02: [Título do Caso de Uso - Funcionalidade 2]
* **Atores Envolvidos: Professor e Aluno**
* **Pré-condições: Professor tem evento idealizado**
* **Pós-condições: Professor descobre se evento vale a pena**
* **Fluxo Principal (Caminho Feliz):**
  1. O Professor acessa a tela Lets Talk e eleciona "Propor nova enquete"
  2. O apresenta o formulario de proposta com os detalhes a preencher
  3. O professor preenche os dados do evento e clica em Publicar Enquete
  4. O sistema valida, registra a enquete como aberta e disponibiliza pra comunidade
  5. Os alunos votam na enquete
  6. O professor fecha a enquete e obtém o resultado.
* **Fluxos Alternativos:**
  * **3a. O professor decide salvar como rascunho ao inves de terminar**
* **Fluxos de Exceção:**
  * **4e. há erro no preenchimento**

---

### 5. MODELAGEM UML
*(Cole aqui as imagens, exportações de ferramentas visuais ou códigos PlantUML/Mermaid)*

1. **Diagrama de Casos de Uso:**
   * *Objetivo explicável:* Apresentar os atores, fronteiras do sistema e o escopo das duas funcionalidades.
   * *[Inserir Diagrama]*
2. **Diagrama de Atividades:**
   * *Objetivo explicável:* Detalhar a lógica de fluxo e decisões da [Funcionalidade X].
   * *[Inserir Diagrama]*
3. **Diagrama de Sequência:**
   * *Objetivo explicável:* Mapear a troca de mensagens entre ator, interface, controlador e banco na interação [especificar interação].
   * *[Inserir Diagrama]*
4. **Diagrama de Classes:**
   * *Objetivo explicável:* Estruturar as entidades de domínio, atributos e relações essenciais.
   * *[Inserir Diagrama]*
5. **Diagrama de Pacotes:**
   * *Objetivo explicável:* Demonstrar a organização lógica em módulos/camadas da solução.
   * *[Inserir Diagrama]*

---

### 6. CASOS DE TESTE

#### 6.1. Casos de Teste - Funcionalidade 1: [Nome]
* **CT 1.1 - Cenário de Sucesso:**
  * *Entrada / Ação:*
  * *Resultado Esperado:*
* **CT 1.2 - Cenário de Erro / Rejeição:**
  * *Entrada / Ação:*
  * *Resultado Esperado:*
* **CT 1.3 - Cenário de Exceção / Situação-Limite (Boundary / Timeout / etc.):**
  * *Entrada / Ação:*
  * *Resultado Esperado:*

#### 6.2. Casos de Teste - Funcionalidade 2: [Nome]
* **CT 2.1 - Cenário de Sucesso:**
  * *Entrada / Ação:*
  * *Resultado Esperado:*
* **CT 2.2 - Cenário de Erro / Rejeição:**
  * *Entrada / Ação:*
  * *Resultado Esperado:*
* **CT 2.3 - Cenário de Exceção / Situação-Limite:**
  * *Entrada / Ação:*
  * *Resultado Esperado:*

---

### 7. REGISTRO DE EXPERIMENTOS COM GENAI (Rascunho / Evidências da Etapa 1)
*(Mantenha esta seção para documentar a interação com pelo menos duas ferramentas de IA e alimentar a Etapa 2)*

* **Experimento 01:**
  * **Ferramenta/Modelo:** *(ex.: ChatGPT-4o, Claude 3.5 Sonnet, Gemini Pro)*
  * **Artefato submetido:** *(ex.: Rascunho inicial dos Critérios de Aceitação da Funcionalidade 1)*
  * **Prompt utilizado:**
  * **Retorno da IA:** *(resumo ou trecho do resultado)*
  * **Decisão do Grupo:** *(O que foi aceito, o que foi rejeitado e justificativa crítica)*
  * **Problemas notados:** *(alucinação, excesso de complexidade, omissão de regra de negócio acadêmica, etc.)*

* **Experimento 02:**
  * **Ferramenta/Modelo:**
  * **Artefato submetido:** *(ex.: Rascunho do Diagrama de Sequência ou Casos de Teste)*
  * **Prompt utilizado:**
  * **Retorno da IA:**
  * **Decisão do Grupo:**
  * **Problemas notados:**
