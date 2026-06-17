DevUp - Productivity with health | GCS Project
> **Projeto de Gestão de Configuração de Software (GCS)**
> 
> Ano Letivo: 2026 | Localização: UTFPR - Dois Vizinhos, PR
> 
> Autores e Equipe: Ana L. Weber Cattani e Letícia Ceron Hass

## Visão Geral do Projeto
O **DevUp** é uma plataforma de software corporativo desenvolvida para unir o bem-estar dos colaboradores à produtividade diária no ambiente de trabalho. Ao integrar o gerenciamento de tarefas com o monitoramento de hábitos saudáveis, o aplicativo auxilia empresas a combaterem o esgotamento profissional (burnout), reduzir o absenteísmo e fortalecer o engajamento da cultura organizacional.

---

## Definição do Problema
Muitas empresas enfrentam dificuldades em engajar colaboradores na adoção de hábitos saudáveis e produtivos. As iniciativas tradicionais de bem-estar sofrem com baixa adesão, falta de constância e ausência de resultados mensuráveis. Além disso, os gestores não possuem ferramentas claras baseadas em dados para acompanhar o impacto direto dessas ações na produtividade e na saúde da equipe, dificultando a justificativa de investimentos na área.

### Público-Alvo
* **Colaboradores**: Profissionais que desejam otimizar seu desempenho diário sem abrir mão da saúde física e mental.
* **Gestores e Líderes**: Supervisores e coordenadores que buscam métricas confiáveis de engajamento e alta performance das equipes.
* **Empresas**: Organizações de pequeno a grande porte focadas em impulsionar resultados de negócios através do desenvolvimento pessoal dos funcionários.

---

## Regras do Grupo (Gestão de Configuração)
Para garantir que ninguém apague ou estrague o código do outro, o grupo seguirá as seguintes regras no GitHub:

### 1. Organização das Branches (Ambientes de Código)
Ninguém mexe direto no código oficial. O trabalho será dividido de acordo com os ambientes:
*   `main` (Produção): Guarda a versão final do software, aquela que está funcionando perfeitamente e pronta para apresentar ao professor.
*   `develop` (Staging): É o ambiente de testes. O grupo junta as partes do trabalho aqui para testar se tudo funciona bem junto antes de enviar para a produção.
*   `feature/nome-da-tarefa`: Cada integrante cria a sua própria ramificação para trabalhar em uma função isolada (ex: `feature/registro-agua`) e não atrapalhar o outro.

### 2. Padrão de Nomes nos Commits (Mensagens de Envio)
Para o histórico do projeto ficar organizado, os envios devem começar com:
*   `feat:` Se você adicionou algo novo (ex: `feat: nome da feat`).
*   `fix:` Se você consertou um erro (ex: `fix: nome do fix`).
*   `docs:` Se você mexeu em textos ou explicações (ex: `docs: atualiza o readme`).

### 3. Revisão de Código (Pull Requests)
*   Quando terminar sua tarefa na sua branch, você deve abrir um **Pull Request** para enviar as mudanças para a branch de Staging (`develop`).
*   O outro membro do grupo precisa dar uma olhada e **aprovar** no GitHub antes do código ser juntado oficialmente.
