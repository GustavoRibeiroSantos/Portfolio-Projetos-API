# Gantt Visual - API 2° Semestre

API - FATEC Prof. Jessen Vidal - São José dos Campos / 2021

# Resumo do projeto:
A Necto, em parceria com os alunos do 2º semestre do curso de Banco de Dados da Fatec de SJC, nos explicou o problema que tinha em sua empresa.

- "Eu tenho visão estratégica dos projetos, tarefas e horas trabalhadas pelos meus funcionários, porém eu gostaria de um software com mais funcionalidades do que o método que é utilizo atualmente."

Com isso o objetivo proejeto era de desenvolver um software de visão estratégica de projetos e tarefas para o nosso cliente, onde ele poderia ter visão do cronograma dos seus projetos e as tarefas de cada projeto.
Com isso, foi desenvolvido uma API Rest em Java. Esse software contém as seguintes funcionalidades:
- O software exibe uma cronograma que mostra as atividades e projetos criados e schedulados pelo cliente, lembrando que a ferramentas será ultilizada por vários membros do time.
- Login: O usuário, para utilizar as ferramentas, precisa criar um conta baseado nas informações solicitadas. 
- Cadastro de funcionários: Uma página onde o cliente pode cadastrar novos funcionários do seu time.
- Painel de tasks: Foi incluido um botão na página do cronograma onde o cliente poderia usá-lo para criar novas atividades ou projeto e atribuir para os membros do seu time.
- Projetos e Tasks interativas: No cronograma, o cliente tinha o poder de mudar a data de inicio/fim dos projetos ou tasks com um simples drag and drop na página.

# Técnologias utilizadas na solução
- MySQL:
  - Para a criação do software, foi necessário a criação de um banco de dados para o armazenamento das informações utilizadas (Informações dos clientes, dados de pagamentos e dívidas e etc);
- Java 1.8: O Back-end do projeto foi criado com a linguagem de programação Java:
-- DHTMLX: Foi a biblioteca usadas para a criação de gráficos interativos de task e projetos;
-- Spring Web: Foi o framework usado para a criação do projeto em Java;
- Gradle:
  - Utilizamos Gradle para gerenciar os importes, dependências e bibliotecas que foram utilizadas no projeto, especificamente no back-end; 
- Hibernate:
  - O Hibernate foi o framework utilizado para a criação das tabelas usando como entidade as classes do back-end (Usuário, Dívida, Pagamento e etc); 
- Html5; 
  - O HTML5 foi a linguagem da programação usada para a criação das páginas webs do nosso projeto.
- JavaScript:
  - A linguagem de JavaScript foi utilizada para auxiliar na criação do nosso front-end e na comunicação entre o front e o back.


# Contribuições individuais/pessoais
A minha contribuição para o desenvolvimento do projeto foi tanto no back-end qunanto no front-end da nossa aplicação! 

### Criação das classes
Eu fui responsável pela criação das classes no back-end e setar as configuração necessárias para que o Hibernate podesse criar as tabelas no nosso banco de dados. As classes criadas e mapeamentas no back-end foram:
- Projeto (Classe, Controller e Repository);
- Task (Classe, Controller e Repository);
- e Funcionário (Classe, Controller e Repository).

### Criação das páginas Web

Eu fui o responsável pela criação de todas as páginas Webs da aplicação, desde a página Home até a página do cronograma.

### Criação do cronograma 

Para a criação do cronograma foi usada a biblioteca DHTMLX, e eu fui o responsável por explorar esse recurso e entender quais eram as limitações delas?, como usar? e como ela poderia nos ajudar?. Isso foi muito importante, pois esse conhecimento nos ajudou muito em algumas partes do nosso back-end.

![alt text](https://dhtmlx.com/docs/products/dhtmlxGantt/images/gantt-demo.png)


### Comunicação entre Front-end e Back-end

Uma das minhas atividades foi criar uma conexão entre o front e o back da nossa API. No projeto, nos tinhamos duas formas de inputs de dados que precisavam ser enviadas para o back-end. 

##### Cadastro de novos usuários
- Formulário front-end para o cronograma
```
$("#save").click(function(event) {
					
				// PREPARE FORM DATA
					var formData = JSON.stringify(gantt.serialize());

					alert(formData);
					
					// DO POST
					jQuery.ajax({
								url : "/salvar",
								type : "POST",
								data : formData,
								dataType : "json",
								contentType : "application/json; charset=utf-8",
								success : function() {
									alert("Save Success!")
								}
							});
				});


```

# Aprendizados Efetivos
Com base nas rotinas desenvolvidas, pode-se ser absorvido conhecimento sobre alguns pontos no back-end e front-end:
- Como conectar o front com o back;
- Melhorei muito meu conhecimento com java spring;
- Melhorei muito meu conhecimento na parte de fron-end(HTML, css e etc.).
- Descobri uma biblioteca(DHTMLX) muito util e apliquei ela em nosso projeto.
- Entendi como funciona o Hibernate e como utiliz-lo.
