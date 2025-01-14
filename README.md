# Projeto Inicial
Site com o objetivo de ajudar os estudantes a planejar seus estudos com o objetivo de passar no ENEM 2025.
Com o auxilio do Chat GPT conseguir a explicaçao da ideia inicial para criar um projeto completo e bem estruturado.  

---

### **BRVest: Estrutura do Projeto**

#### **1. Objetivo Geral**
Criar um site e um programa que ofereçam uma plataforma educativa completa para estudantes se prepararem para o ENEM, com foco em conteúdos organizados por áreas de conhecimento, suporte personalizado através de inteligência artificial e ferramentas para planejamento de estudos.

---

### **2. Funcionalidades Principais**

#### **2.1. Organização das Matérias**
- **Divisão por Áreas do Conhecimento**:
  - Ciências Humanas: História, Geografia, Filosofia, Sociologia.
  - Ciências da Natureza: Biologia, Física, Química.
  - Ciências Exatas: Matemática.
  - Linguagens e Códigos: Português, Literatura, Inglês ou Espanhol, Artes.
  - Redação: Técnicas e temas recorrentes.
  
- **Banco de Dados**:
  - Criar um banco de dados relacional (ex.: MySQL) contendo todas as matérias, subtemas e recursos associados (vídeos, e-books, exercícios).
  - Tabela exemplo:
    ```sql
    CREATE TABLE materias (
        id INT AUTO_INCREMENT PRIMARY KEY,
        area VARCHAR(50),
        materia VARCHAR(50),
        subtema VARCHAR(100),
        recurso VARCHAR(255)
    );
    ```

#### **2.2. Chat com IA**
- **Descrição**: Um assistente virtual no canto inferior direito do site que pode:
  1. Responder perguntas sobre conteúdos do ENEM.
  2. Propor pelo menos 3 soluções, como:
     - Indicar e-books na biblioteca do site.
     - Recomendar vídeos confiáveis no YouTube (curadoria).
     - Sugerir sites confiáveis ou canais de professores parceiros.
  
- **Ferramentas**:
  - Integração com GPT (como o OpenAI API) para fornecer respostas contextuais.
  - Respostas personalizadas com links para recursos no site.

#### **2.3. Biblioteca de Recursos**
- **E-books**:
  - Disponibilizar materiais gratuitos e pagos.
  - Categorizar por área e tema.
  
- **Canais e Sites Confiáveis**:
  - Listar parceiros educacionais.
  - Oferecer busca integrada para facilitar o acesso.

#### **2.4. Roadmap de Estudos**
- **Mapa de Estudo Personalizado**:
  - Planejamento semanal ou mensal com base no tempo disponível até a prova.
  - Recursos vinculados aos temas da semana.
  
- **Funcionalidade de Rastreamento**:
  - Progresso do aluno em temas estudados.
  - Recomendação de ajustes no planejamento com base no desempenho.

---

### **3. Design do Site**

#### **3.1. Estrutura Visual**
- **Topo do Site**:
  - Menu com as áreas do conhecimento.
  - Opções de login/cadastro.
  
- **Seção Principal**:
  - Banner com informações sobre o ENEM.
  - Atalhos para as áreas de estudo e roadmap.

- **Rodapé**:
  - Links rápidos para biblioteca, canais confiáveis e FAQ.

#### **3.2. Chat no Canto Direito Inferior**
- Ícone de chatbot que expande para uma janela interativa.
- Mensagens amigáveis e personalizáveis.

---

### **4. Desenvolvimento Técnico**

#### **4.1. Tecnologias para o Site**
- **Frontend**:
  - Framework: React, Vue.js ou Angular.
  - Design responsivo com Tailwind CSS ou Bootstrap.
  
- **Backend**:
  - Node.js, Python (Django/Flask), ou Java (Spring Boot).
  - Integração com APIs, como OpenAI para IA e Google Books para e-books.

- **Banco de Dados**:
  - MySQL ou PostgreSQL para armazenar dados das matérias, recursos e usuários.

#### **4.2. Implementação do Chatbot**
- **Backend do Chat**:
  - Configurar API GPT para processar perguntas e sugerir soluções.
  
- **Frontend do Chat**:
  - Biblioteca como Chat UI Kit para criar a interface.

#### **4.3. Roadmap de Estudos**
- Gerador de planos com base no tempo restante até a prova.
- Sistema de recomendação baseado em temas mais recorrentes no ENEM.
- É uma ótima ideia alinhar o roadmap com o conteúdo programático oficial do ENEM! Isso garante que os estudantes estejam estudando exatamente o que é necessário e seguindo a orientação oficial do exame. Vamos detalhar como estruturar essa parte do projeto:

---

### **1. Estrutura do Roadmap Baseado no Conteúdo Programático do ENEM**

#### **1.1. Conteúdo Programático Oficial**
- Utilize o **Edital Oficial do ENEM** (atualizado anualmente) como base para:
  - Identificar as **áreas de conhecimento** e suas competências.
  - Organizar os conteúdos em tópicos detalhados.

- **Exemplo** de tópicos extraídos do edital:
  - **Ciências Humanas**:
    - História: Brasil Colônia, República, Globalização.
    - Geografia: Cartografia, Recursos Naturais, Urbanização.
  - **Ciências da Natureza**:
    - Física: Cinemática, Termodinâmica, Ondas.
    - Biologia: Ecologia, Citologia, Genética.
  - **Matemática**:
    - Geometria Plana, Estatística, Análise Combinatória.
  - **Linguagens e Redação**:
    - Leitura e Interpretação de Textos, Gramática, Produção Textual.

#### **1.2. Banco de Dados do Conteúdo Programático**
- Crie tabelas específicas para armazenar as informações extraídas do edital.

**Exemplo de estrutura para o banco de dados:**
```sql
CREATE TABLE conteudo_programatico (
    id INT AUTO_INCREMENT PRIMARY KEY,
    area VARCHAR(50), -- Ex: Ciências Humanas
    materia VARCHAR(50), -- Ex: História
    topico VARCHAR(100), -- Ex: Brasil Colônia
    descricao TEXT -- Ex: Principais eventos da colonização portuguesa
);
```

---

### **2. Funcionalidade do Roadmap de Estudo**

#### **2.1. Geração do Roadmap**
- **Entrada do Usuário**:
  - Data de início e fim (exemplo: início do ano letivo e data do ENEM).
  - Disponibilidade semanal de estudo (horas por dia ou dias da semana).
  - Áreas onde o aluno deseja focar mais (baseado em autoavaliação).

- **Distribuição dos Tópicos**:
  - Divida os tópicos de cada área igualmente no tempo disponível.
  - Dê prioridade para temas mais cobrados no ENEM.
  - Inclua períodos de revisão ao final de cada etapa.

**Exemplo de Algoritmo para Divisão:**
1. Calcule o total de semanas disponíveis.
2. Divida o conteúdo programático em blocos semanais.
3. Ajuste com base na disponibilidade semanal do aluno.
4. Insira lembretes para revisões antes do ENEM.

#### **2.2. Exemplo de Roadmap Gerado**
Se o aluno tem 6 meses e 2 horas por dia:
- Semana 1:
  - Matemática: Geometria Plana.
  - Ciências Humanas: Brasil Colônia.
- Semana 2:
  - Biologia: Ecologia.
  - Física: Cinemática.

#### **2.3. Feedback no Roadmap**
- Permita que o aluno marque temas como "concluídos" ou "em revisão".
- Mostre progresso visual (ex.: 70% do cronograma concluído).

---

### **3. Integração com o Site**

#### **3.1. Seção de Planejamento**
- Página dedicada ao **Planejamento de Estudos**.
- Formulário para o aluno configurar:
  - Horas/dias disponíveis.
  - Foco por área de conhecimento.

#### **3.2. Exibição do Roadmap**
- Mostre um calendário interativo com:
  - Tópicos por dia/semana.
  - Links para recursos relacionados (e-books, vídeos, exercícios).
  - Opção de arrastar e soltar (drag-and-drop) para reorganizar o plano.

#### **3.3. Recursos Vinculados**
- Cada tema no roadmap pode ter um botão que leva a:
  - Resumos teóricos.
  - Exercícios práticos.
  - Aulas em vídeo (via YouTube ou conteúdo próprio).

---

### **4. Atualização Anual**
- Sempre atualize o conteúdo com base no edital mais recente do ENEM.
- Crie uma funcionalidade para os administradores do site adicionarem ou editarem tópicos no banco de dados.

---

### **5. Chat de IA e o Roadmap**
- Integre o chat de IA para sugerir ajustes no roadmap.
- Exemplo de interação:
  - Pergunta do aluno: *"Não consegui estudar Geometria Plana esta semana. O que faço?"*
  - Resposta da IA: 
    1. **Reorganize o cronograma** para incluir Geometria na próxima semana.
    2. **Acesse este vídeo curto** para recuperar o conteúdo rapidamente.
    3. **Resolva esta lista de exercícios** para consolidar o aprendizado.

---

### **6. Benefícios**
- Planejamento eficiente baseado no edital oficial.
- Redução da ansiedade com metas claras.
- Integração de recursos confiáveis para otimizar o estudo.

---

### **Próximos Passos**
1. Coletar o conteúdo programático oficial do ENEM mais recente.
2. Criar o banco de dados para armazenar os tópicos.
3. Desenvolver o algoritmo para gerar roadmaps personalizados.
4. Implementar a interface visual para o aluno interagir com o roadmap.

---

### **6. Monetização**
- Planos Premium para acesso a materiais exclusivos.
- Parcerias com professores para cursos pagos.
- Publicidade de cursos e livros parceiros.

---

Criar um **espaço para o aluno ter seu próprio perfil no site** permitirá personalizar o roadmap e acompanhar o progresso individual. Aqui está um plano detalhado para implementar essa funcionalidade:

---

### **1. Funcionalidade: Perfil do Aluno**

#### **1.1. Cadastro e Login**
- **Campos de Cadastro**:
  - Nome completo.
  - E-mail (usado como login).
  - Senha (armazenada com hash para segurança).
  - Data de nascimento (opcional, para personalizar ainda mais a experiência).
  - Áreas de interesse ou matérias que o aluno sente mais dificuldade (opcional).

- **Banco de Dados do Usuário**:
```sql
CREATE TABLE usuarios (
    id INT AUTO_INCREMENT PRIMARY KEY,
    nome VARCHAR(100),
    email VARCHAR(100) UNIQUE,
    senha_hash VARCHAR(255), -- Armazenar a senha com hash
    data_nascimento DATE,
    interesses TEXT, -- Armazenar áreas de interesse como JSON
    criado_em TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

#### **1.2. Login**
- O aluno faz login usando o e-mail e a senha cadastrados.
- **Autenticação Segura**:
  - Use **bcrypt** ou uma biblioteca de hashing segura para proteger as senhas.
  - Implemente autenticação baseada em tokens (ex.: JWT) para sessões seguras.

---

### **2. Painel de Controle do Aluno**

#### **2.1. Informações no Painel**
- **Resumo do Progresso**:
  - Percentual de conclusão do roadmap.
  - Número de tópicos estudados.
  - Áreas ainda pendentes.

- **Acesso ao Roadmap**:
  - Exibição do roadmap personalizado.
  - Botões para marcar como "Concluído", "Revisar", ou "Pular".

- **Histórico de Estudo**:
  - Tópicos revisados e desempenho (se possível, com notas em quizzes).

---

### **3. Personalização do Roadmap**

#### **3.1. Configuração Inicial**
- No momento do cadastro ou na primeira vez que acessar o roadmap, o aluno preenche:
  - Tempo disponível para estudar.
  - Áreas ou matérias com maior dificuldade.
  - Data do ENEM ou da prova desejada.

#### **3.2. Ajustes no Roadmap**
- O aluno pode:
  - Reorganizar as tarefas no calendário (drag-and-drop).
  - Adicionar tópicos extras manualmente.
  - Alterar a prioridade de temas.
  
---

### **4. Tecnologias Recomendadas**

#### **4.1. Backend**
- **Framework**: Node.js (Express), Python (Django ou Flask), ou Java (Spring Boot).
- **Autenticação**:
  - **JWT** (JSON Web Token) para gerenciar sessões do usuário.
  - Criptografia para senhas com bibliotecas como bcrypt.

#### **4.2. Banco de Dados**
- **Relacional**: MySQL ou PostgreSQL para armazenar usuários e seus dados.
- **Estruturado para Progresso**:
```sql
CREATE TABLE progresso_roadmap (
    id INT AUTO_INCREMENT PRIMARY KEY,
    usuario_id INT,
    topico_id INT,
    status ENUM('pendente', 'concluido', 'revisar') DEFAULT 'pendente',
    atualizado_em TIMESTAMP DEFAULT CURRENT_TIMESTAMP,
    FOREIGN KEY (usuario_id) REFERENCES usuarios(id),
    FOREIGN KEY (topico_id) REFERENCES conteudo_programatico(id)
);
```

#### **4.3. Frontend**
- **Framework**: React, Vue.js ou Angular para criar uma interface dinâmica.
- **Painel de Controle**:
  - Use gráficos (ex.: Chart.js ou D3.js) para mostrar o progresso visual.
  - Integre calendários interativos para o roadmap.

---

### **5. Experiência do Aluno**

#### **5.1. Após o Cadastro**
1. **Configuração Inicial**:
   - O site guia o aluno para preencher dados sobre disponibilidade e áreas de foco.
   - Gera um roadmap inicial automaticamente.

2. **Interação Diária**:
   - O aluno faz login para acessar seu roadmap.
   - Pode marcar tarefas como "Concluído", revisar, ou reorganizar tópicos.

#### **5.2. Benefícios Extras**
- Notificações (e-mail ou push) para lembrar de estudar.
- Recomendações personalizadas baseadas no progresso (ex.: *"Você concluiu Matemática Básica! Agora é hora de avançar para Geometria."*).

---

### **6. Segurança e Privacidade**
- **Proteção de Dados**:
  - Garanta que os dados pessoais sejam protegidos por criptografia (ex.: TLS para conexões HTTPS).
  - Forneça uma política de privacidade clara para os usuários.

- **Recuperação de Senha**:
  - Permita que o aluno redefina a senha através de um link enviado ao e-mail.

---

### **Próximos Passos**
1. **Estruturar o Banco de Dados**:
   - Crie as tabelas para usuários, progresso no roadmap, e conteúdos programáticos.
2. **Desenvolver o Sistema de Login/Cadastro**:
   - Configure autenticação com hashing de senhas e sessões seguras.
3. **Desenvolver o Painel de Controle**:
   - Crie um frontend básico com o resumo do progresso e acesso ao roadmap.


### **7. Próximos Passos**
1. Especificar o escopo inicial.
2. Definir as tecnologias para cada parte.
3. Criar um MVP com foco nas funcionalidades principais (ex.: chat e roadmap).
4. Testar com usuários reais.

