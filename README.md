# Gantt Visual - API 2° Semestre

API - FATEC Prof. Jessen Vidal - São José dos Campos / 2021

## Resumo do projeto:
A Necto, em parceria com os alunos do 2º semestre do curso de Banco de Dados da Fatec de SJC, nos explicou o problema que tinha em sua empresa.

- "Eu tenho visão estratégica dos projetos, tarefas e horas trabalhadas pelos meus funcionários, porém eu gostaria de um software com mais funcionalidades do que o método que é utilizo atualmente."

Com isso o objetivo proejeto era de desenvolver um software de visão estratégica de projetos e tarefas para o nosso cliente, onde ele poderia ter visão do cronograma dos seus projetos e as tarefas de cada projeto.
Com isso, foi desenvolvido uma API Rest em Java. Esse software contém as seguintes funcionalidades:
- O software exibe uma cronograma que mostra as atividades e projetos criados e schedulados pelo cliente, lembrando que a ferramentas será ultilizada por vários membros do time.
- Login: O usuário, para utilizar as ferramentas, precisa criar um conta baseado nas informações solicitadas. 
- Cadastro de funcionários: Uma página onde o cliente pode cadastrar novos funcionários do seu time.
- Painel de tasks: Foi incluido um botão na página do cronograma onde o cliente poderia usá-lo para criar novas atividades ou projeto e atribuir para os membros do seu time.
- Projetos e Tasks interativas: No cronograma, o cliente tinha o poder de mudar a data de inicio/fim dos projetos ou tasks com um simples drag and drop na página.

## Técnologias utilizadas na solução
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


## Contribuições individuais/pessoais
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


# Score Wizard - API 3° Semestre

API - FATEC Prof. Jessen Vidal - São José dos Campos / 2021

# Resumo do projeto:
O SPC, em parceria com os alunos do 3º semestre do curso de Banco de Dados da Fatec de SJC, necessita de um software para obter uma análise estatística da evolução do consumidor em relação ao histórico de pagamentos e da evolução da nota de score. Esse software é usado por qualquer pessoa física ou jurídica, que possua cadastro positivo e que, ao utilizá-lo, espera melhorar seu score de uma forma melhor do que as alternativas existentes no mercado. Espera também, obter dados de sua evolução financeira, a fim de contribuir para uma melhora de seu score, e, possivelmente, efetuar novas solicitações de crédito para as instituições financeiras.
Com isso, foi desenvolvido uma API Rest em Java. Esse software contém as seguintes funcionalidades:
- Cadastro de usuário e Login: O usuário, para utilizar as ferramentas, precisa criar um conta baseado nas informações solicitados (Nome, CPF, data de nascimento e etc.). Após o cadastro efetuado, o usuário consegue logar na ferramenta para usufruir das demais funcionalidades;
- Análise automática de possíveis motivos de baixo score: O usuário consegue acessar a aplicação e encontrar quais as dívidas e faturas estão diminuindo a sua numeração de score;
- Análise do que seria necessário realizar para melhorar o score: O usuário encontrará na aplicação quais ações podem ajudá-lo a melhorar a pontuação do score;
- Gamificação: Implementamos um estilo de gamificação na aplicação, onde o usuário ganha XP e avança de nível quando quita alguma conta. Esse nível pode ser utilizado para mostrar se o usuário é ou não um bom pagador.


# Técnologias utilizadas na solução
- MySQL:
  - Para a criação do software, foi necessário a criação de um banco de dados para o armazenamento das informações utilizadas (Informações dos clientes, dados de pagamentos e dívidas e etc);
- Java 1.8:
  - O Back-end do projeto foi criado com a linguagem de programação Java; 
- Spring 2.3.0:
  - O Spring foi o framework de Projeto utilizado juntamente com o Java; 
- Gradle:
  - Utilizamos Gradle para gerenciar os importes, dependências e bibliotecas que foram utilizadas no projeto, especificamente no back-end; 
- Hibernate:
  - O Hibernate foi o framework utilizado para a criação das tabelas usando como entidade as classes do back-end (Usuário, Dívida, Pagamento e etc); 
- Bootstrap 4:
   -O Bootstrap 4 foi o framework que nos auxiliou na criação do nosso front-end. Toda a estrutura e modelagem das nossas páginas webs foram desenvolvidas com essa ferramenta; 
- Html5; 
  - O HTML5 foi a linguagem da programação usada para a criação das páginas webs do nosso projeto.
- JavaScript:
  - A linguagem de JavaScript foi utilizada para auxiliar na criação do nosso front-end e na comunicação entre o front e o back.


# Contribuições individuais/pessoais
A minha contribuição para o desenvolvimento do projeto foi mais focada no back-end da nossa aplicação! 

### Criação das classes
Eu fui responsável pela criação das classes no back-end e setar as configuração necessárias para que o Hibernate podesse criar as tabelas no nosso banco de dados. As classes criadas e mapeamentas no back-end foram:
- Fontes;
- Login;
- Modalidade;
- Movimento;
- Operação;
- Pagamento;
- Pessoa fisica e juridica;
- Experiencia do usuário.

### Comunicação entre Front-end e Back-end

Uma das minhas atividades foi criar uma conexão entre o front e o back da nossa API. No projeto, nos tinhamos duas formas de inputs de dados que precisavam ser enviadas para o back-end. 

##### Cadastro de novos usuários
- Formulário front-end para cadastro
```
<div class="card bg-custom mx-5 p-2">
        <div class="card form-style m-3 p-1 mb-5">
            <h1>Cadastro</h1>
        </div>
        <div class="mt-4 mx-4 px-4">
            <form class="row" action="#" th:action="@{/cadastro}" th:object="${cadastro}" method="post">
                <div class="form-group col-4">
                    <label for="InputIdent">CPF ou CNPJ:</label>
                    <input type="text" th:field="*{documento}" class="form-control form-style"  maxlength="11" pattern="[0-9]{11}" title="Este campos só aceita números" required>
                </div>
                <div class="form-group col-4">
                    <label for="InputNome">Nome:</label>
                    <input type="text" th:field="*{nome}" class="form-control form-style mb-5" maxlength="60" pattern="([A-zÀ-ž\s]){2,}" required>
                </div>
                <div class="form-group col-2">
                    <label for="InputSexo">Sexo:</label>
                    <select th:field="*{sexo}" class="form-control form-style mb-5" required>
                        <option th:value="''" th:text="Escolha..."></option>
                        <option th:value="'F'" th:text="Feminino"></option>
                        <option th:value="'M'" th:text="Masculino"></option>
                    </select>
                </div>
                <div class="form-group col-2">
                    <label for="InputNasc">Ano de Nascimento:</label>
                    <input type="number" th:field="*{anoNascimento}" class="form-control form-style" required>
                </div>
                <div class="form-group col-4">
                    <label for="InputCidade">Cidade:</label>
                    <input type="text" th:field="*{cidade}" class="form-control form-style mb-5" required>
                </div>
                <div class="form-group col-4">
                    <label for="InputEstado">Estado:</label>
                    <input type="text" th:field="*{estado}" class="form-control form-style" required>
                </div>
                <div class="form-group col-4">
                    <label for="InputSenha">Senha:</label>
                    <input type="password" th:field="*{senha}" class="form-control form-style" pattern="(?=.*\d)(?=.*[a-z])(?=.*[A-Z]).{8,}"  title="Sua senha precisa conter no mínimo um número, letras maiúsculas e minúsculas, e no mínimo 8 caracteres ou mais" required>
                </div>
                <button type="submit" onclick="window.location.href='/index'" class="btn btn-custom m-3" value="Submit">Cadastrar</button>
            </form>
        </div>
    </div>

```

- Rota Web Server para cadastro
```
  @PostMapping("/cadastro")
	  public String CadastroSubmit(@ModelAttribute PessoaFisica cadastro, Model model) {
		 	
		 	System.out.println("Funcionou!");
		 	
		 	ArrayList<PessoaFisica> pessoaf = new ArrayList<>();
		 	pessoaf.addAll(pf.getAllPessoaFisica());
		 	
		 	int i = 1;
		 	while( i <= pessoaf.size()) {
		 		if(i == pessoaf.size()) {
			  		pf.addpessoaf(cadastro.getDocumento(),
			  				cadastro.getNome(),
							cadastro.getSexo(), 
							cadastro.getAnoNascimento(), 
							cadastro.getCidade(), 
							cadastro.getEstado(),
							cadastro.getSenha());
			  		return "dashboard";
			    	}
			  	  if(cadastro.getDocumento().equals(pessoaf.get(i).getDocumento())) {
			  		  return "index";
			  	  }  
			  	  i++;
			}

	    return null;	  
	  }

```
##### Login dos usuários existentes

- Rota Web Server para login
```
@Autowired
	PessoaFisicaController pf = new PessoaFisicaController();
	
	HelloController cont = new HelloController();
	  
	  @GetMapping("/")
	  public String LoginForm(Model model) {
	    model.addAttribute("index", new Login());
	    return "index";
	  }

	  @PostMapping("/index")
	  public String LoginSubmit(@ModelAttribute Login greeting, Model model) {
		 	
		 	ArrayList<PessoaFisica> pessoaf = new ArrayList<>();
		 	pessoaf.addAll(pf.getAllPessoaFisica());
		 	
		 	int i = 1;
		 	while( i <= pessoaf.size()) {
			  	  if(greeting.getCpf().equals(pessoaf.get(i).getDocumento()) && greeting.getSenha_usu().equals(pessoaf.get(i).getSenha())) {
			  		  System.out.println("User j cadastrado");
			  		  pf.getCalcularXP(pessoaf.get(i).getDocumento());
			  		  return "dashboard";
			  	  }
			  	  i++;
			}

	    return null;	  
	  }

```

### Gerar e calcular o XP dos usuários da API

Como foi mencionado anteriormente, nossa aplicação tinha uma dinâmica de gameficação! Onde os usuários ganhavam XP e avançavam de nível basedo na quantidade de XP...

Eu fui o responsável por implementar essa ideia de gamificação, onde quando o usuário quitasse uma dívida, ele receberia uma quantidade XP. Esse calculo era feito todas as vezes que o usuários se logava na nossa aplicação.

```
    @GetMapping(path="/getXP")
    public @ResponseBody int getCalcularXP(@RequestParam String documento) {
    	PessoaFisica pessoa = pessoafisicarepository.findByDocumento(documento);
        ExperienciaVerificacao experiencia = experienciaVerificacao.findByDocumentoCliente(documento);
        int operacao, movimentos;
        
        operacao = pessoa.getOperacoesCount();
        movimentos = pessoa.getMovimentosCount();
        System.out.println(operacao);
        System.out.println(movimentos);
        
        int oldoperacao = experiencia.getQtd_parcelas_operacoes();
        int oldmovimentos = experiencia.getQtd_parcelas_movimentos();
        
        int XPAdiquirido = 0;
        int XPMovimento = 0;
        int XPOperacao = 0;
        
        if(operacao < oldoperacao){
        	int operacoesToXP = oldoperacao - operacao;
			XPOperacao = operacoesToXP*10;
			System.out.println(XPOperacao);
        }
        
        if(movimentos < oldmovimentos){
			int movimentosToXP = oldmovimentos - movimentos;
			XPMovimento = movimentosToXP*20;
			System.out.println(XPMovimento);
        }
        
        XPAdiquirido = XPOperacao + XPMovimento;
        System.out.println(XPAdiquirido);
        
        ExperienciaVerificacao newexperiencia = new ExperienciaVerificacao(documento,"Pagamento",operacao,movimentos,new Date());
        PessoaFisica pesf = new PessoaFisica(documento, pessoa.getNome(), pessoa.getSexo(), pessoa.getAnoNascimento(), pessoa.getCidade(), pessoa.getEstado(), pessoa.getSenha(), (XPAdiquirido + pessoa.getXP()));

        pessoafisicarepository.save(pesf);
        experienciaVerificacao.save(newexperiencia);
        
        PessoaFisica pessoacont = pessoafisicarepository.findByDocumento(documento);
		int nivelUser = pessoacont.getXP()/100;
		System.out.println(nivelUser);

        return nivelUser;
    }
```


# Aprendizados Efetivos
Com base nas rotinas desenvolvidas, pode-se ser absorvido conhecimento sobre alguns pontos no back-end e front-end:
- Como conectar o front com o back;
- Melhorei muito meu conhecimento com java spring;
- Entendi como funciona o Hibernate e como utiliz-lo.


# Portifolio-API-4-Semestre

### Em 2021-1 JETSOFT - **[Gitlab do projeto](https://gitlab.com/gurst6/projeto-integrador-pythaon)**
O projeto tinha como problema a necessidade de performance em um gerenciador de currículos que contém diversos candidatos e vagas, além de ter uma inteligência que ajuda no cruzamento de vagas e currículos. Diversos novos candidatos e vagas eram inseridos todos os dias e era necessário que esses postos fossem preenchidos das maneiras mais eficiente possível. A inteligência era requisitada nesse momento, onde os requisitos para as vagas, como:
- Salário; 
- Qualificações; 
- Experiência profissional;
- VT0 (onde a distância percorrida pelo trabalhador até o trabalho não pode ser mais do que 1km).

Com isso, deveriam ser analisados de forma com que os possíveis candidatos estivessem o mais próximo possível dos requisitos demandados para a vaga. A solução proposta foi uma api que gerenciasse os currículos e vagas, utilizando de ferramentas do MongoDB para otimizar buscas e cruzamentos de postos de trabalho, além das queries geoespaciais para buscas por VT0.


### Tecnologias Utilizadas
* Python 3.8 - O python foi a liguagem principal para a programação da API.
* FrameWork Django 3 - Foi framework de projeto usado para a criação da aplicação.
* MongoDB - Banco de Dados usado para armazenar as informações de candidatos, vagas e etc.
    * **Pymongo** - interação com nosso Banco de Dados;

# Contribuições individuais/pessoais
A minha contribuição para o desenvolvimento do projeto foi tanto no back-end qunanto no front-end da nossa aplicação! 

### Criação da rota Web-Server para cadastro e atualização de curriculos 
- Eu fui o responsável no time por criar essas duas rotas das inserção de dados no nosso banco atraves das rotas Web Servers.

```
@csrf_exempt
   def cadastrarCurriculo(request):
      client = Vaga.createConnection()         
      db = client["Finder"]
      col = db["Inscrito"]

      result = col.insert_one(json.loads(request.body))
         
         # result
      return JsonResponse({"message":"Curriculo inserido com sucesso."}, status=200)

   @csrf_exempt
   def atualizarCurriculo(request, pk):
      client = Vaga.createConnection()
      db = client["Finder"]
      col = db["Inscrito"]

      result = col.update_one({"InscritoIdExterno" : pk}, json.loads(request.body))
         # result
      return JsonResponse({"message":"Curriculo atualizado com sucesso."}, status=200)
```
### Criação da rota Web-Server para atualizar a lista de curriculos que se aplicam para uma vaga
- Eu fui o responsável no time por criar essa rotas das inserção de dados no nosso banco atraves das rotas Web Servers, onde todas as vagas tinham uma lista com os curriculos que se encaixavam para ela, assim a busca no banco era bem mais rápida.

```
def UpdateListCurriculos(IdCol, pk):
      client = Vaga.createConnection()
      db = client["Finder"]
      col = db["vagas"]

      query = { "$set": { "IncritoIdSelecionado": IdCol }}

      result = col.update_one({"VagaIdExterno" : pk}, query)
      # result
      return JsonResponse({"message":"Lista de curriculos selecionados atualizada com sucesso."}, status=200)

```
### Criação da rota Web-Server para fazer uma busca das vagas no nosso banco
- Eu fui o responsável no time por criar essa rota e mostrar as vagas no banco.

```
@csrf_exempt
   def buscarPorVaga(VagaID):
      # Inicia conexão com o banco
      client = Vaga.createConnection()

      mydb = client["Finder"]
      curriculos = mydb["Inscrito"]
      vagas = mydb["vagas"]

         # Recupera a vaga recebida por parâmetro
      vaga = vagas.find_one({"VagaIdExterno" : VagaID})

      if vaga:
         searchRequisitos = '|'.join([str(requisito['descricao']) for requisito in vaga['competencia']])

         query = {
               "$or" : [ 
                  # { "tipoContratoDesejadoInscrito" : { "$regex": vaga['tipoContratacaoPerfilVaga'] } },
                  { "perfilProfissionalTituloInscrito" : { "$regex":searchRequisitos } },
                  { "perfilProfissionalDescricaoInscrito" : { "$regex": searchRequisitos } },
                  { "experienciaProfissional.descricao": { "$regex": searchRequisitos } },
                  { "formacao.curso": { "$regex": searchRequisitos } },
                  { "competencia.descricao": { "$regex": searchRequisitos } } 
               ] 
         }

         result_curriculos = curriculos.find(query)
         IdCol = [str(result['_id']) for result in result_curriculos]
      
      return IdCol
```
### Implementação do Observer no back-end da API
- Eu fui o responsável no time por implementar o observer na nossa aplicação, para nos ajudar na parte de atualização dos candidatos que se encaixam para uma vaga.

```
class Observer:

	observers = []
	view_func = None

	# def __init__(self): #Construtor da classe.
	# 	self.observers = []
	# 	self.view_func = views.View()
        

	def registerObserver(IdVaga):
		views.View.CurriculosList(IdVaga)
		Observer.observers.append(IdVaga)
		print("Observer added!")

	def removeObserver(self, IDVaga):
		for x in self.observers:
			if(IDVaga == x):
				self.observers.remove(x)

	def notifyObserver(IdVaga):
		results = views.View.CurriculosList(IdVaga)
		Observer.UpdateObserver(IdVaga, results)
		print("Finished!")
 
	def UpdateObserver(IDVaga, results):
		views.View.UpdateListCurriculos(results, IDVaga)
		print("Função para add curriculo a collection")
		print(dumps(results))

```

# Aprendizados Efetivos
Com base nas rotinas desenvolvidas, pode-se ser absorvido conhecimento sobre alguns pontos no back-end:
- Melhorei muito meu conhecimento com django;
- Entendi melhor como utilizar o MongoDB;
- Aprendi o que é o Observe, para que ser e como aplicar/implementar em uma aplicação;
- Entendi como funciona o Pymongo e como utiliz-lo.
