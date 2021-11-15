# Gantt Visual - API 2° Semestre

API - FATEC Prof. Jessen Vidal - São José dos Campos / 2021


Problema:
Nosso cliente da Necto (Empresa desenvolvedora de software) nos contatou e explicou o problema que tinha em sua empresa.

"Eu tenho visão estratégica dos projetos, tarefas e horas trabalhadas pelos meus funcionários, porém eu gostaria de um software com mais funcionalidades do que o método que é utilizo atualmente."

# Resumo do projeto:
A Necto, em parceria com os alunos do 2º semestre do curso de Banco de Dados da Fatec de SJC, com o objetivo de desenvolver um software de visão estratégica de projetos e tarefas para o nosso cliente, onde ele poderia ter visão do cronograma dos seus projetos e as tarefas de cada projeto.
Com isso, foi desenvolvido uma API Rest em Java. Esse software contém as seguintes funcionalidades:
- O software exibe uma cronograma que mostra as atividades e projetos criados e schedulados pelo cliente, lembrando que a ferramentas será ultilizada por vários membros do time.
- Login: O usuário, para utilizar as ferramentas, precisa criar um conta baseado nas informações solicitadas. 

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
