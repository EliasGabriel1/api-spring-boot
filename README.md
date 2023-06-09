# api-spring-boot

# Aqui vai uma breve documentação sobre o projeto:
<div class="markdown prose w-full break-words dark:prose-invert dark">
    <p>Este é um exemplo de classe Java que utiliza o framework Spring Boot para criar um aplicativo web. A classe é
        chamada de "ApplicationTutorial" e está localizada no pacote "com.company.nomeprojeto". Abaixo segue a
        documentação dos componentes principais da classe:</p>
    <h3><code>@SpringBootApplication</code></h3>
    <p>A anotação <code>@SpringBootApplication</code> é uma combinação de várias outras anotações do Spring, como
        <code>@Configuration</code>, <code>@EnableAutoConfiguration</code> e <code>@ComponentScan</code>. Ela indica que
        a classe é uma classe de configuração do Spring Boot que permite habilitar recursos automáticos, como detecção
        de classes e configuração automática de bancos de dados.</p>
    <h3><code>public static void main(String[] args)</code></h3>
    <p>Este é o método principal da aplicação, responsável por iniciar o aplicativo. Ele recebe um array de argumentos
        em <code>String[] args</code> e chama o método
        <code>SpringApplication.run(ApplicationTutorial.class, args)</code> para iniciar a aplicação.</p>
    <h3><code>SpringApplication.run(ApplicationTutorial.class, args)</code></h3>
    <p>Este método estático é usado para iniciar a aplicação Spring Boot. Ele recebe como parâmetro a classe principal
        da aplicação e os argumentos do método <code>main()</code>. Quando executado, ele inicia um contêiner de
        aplicativos e carrega todos os componentes necessários para a execução da aplicação.</p>
</div>

<div class="markdown prose w-full break-words dark:prose-invert dark">
    <p>O código representa uma classe Java chamada TarefasAPI, que implementa uma API RESTful para gerenciamento de
        tarefas. Esta classe está localizada no pacote <code>com.company.nomeprojeto.tarefas.api</code>. A seguir, serão
        descritos os principais elementos dessa classe:</p>
    <h3><code>@Controller</code></h3>
    <p>A anotação <code>@Controller</code> é uma das anotações do Spring Framework que indica que a classe é um
        controlador. O objetivo desta classe é gerenciar as solicitações HTTP e retornar as respostas adequadas.</p>
    <h3><code>@RequestMapping(value = "/tarefas", produces = MediaType.APPLICATION_JSON_VALUE)</code></h3>
    <p>A anotação <code>@RequestMapping</code> é uma anotação do Spring que mapeia solicitações HTTP para métodos em
        controladores específicos. Neste caso, ela mapeia todas as solicitações para <code>/tarefas</code>. Além disso,
        a anotação <code>produces</code> é usada para indicar o tipo de mídia que o controlador produz, neste caso,
        JSON.</p>
    <h3><code>@Autowired</code></h3>
    <p>A anotação <code>@Autowired</code> é uma anotação do Spring que permite a injeção de dependência automática.
        Neste caso, é usado para injetar uma instância de <code>TarefasFacade</code> no controlador.</p>
    <h3><code>@PostMapping</code></h3>
    <p>A anotação <code>@PostMapping</code> é uma anotação do Spring que indica que o método trata solicitações HTTP
        POST. Neste caso, o método <code>criar</code> é acionado quando uma solicitação POST é feita para
        <code>/tarefas</code>. O parâmetro <code>@RequestBody</code> indica que o método espera um corpo de solicitação
        JSON que pode ser convertido em um objeto TarefaDTO.</p>
    <h3><code>@PutMapping</code></h3>
    <p>A anotação <code>@PutMapping</code> é uma anotação do Spring que indica que o método trata solicitações HTTP PUT.
        Neste caso, o método <code>atualizar</code> é acionado quando uma solicitação PUT é feita para
        <code>/tarefas/{tarefaId}</code>. O parâmetro <code>@PathVariable</code> indica que o valor de
        <code>tarefaId</code> é passado na URL.</p>
    <h3><code>@GetMapping</code></h3>
    <p>A anotação <code>@GetMapping</code> é uma anotação do Spring que indica que o método trata solicitações HTTP GET.
        Neste caso, o método <code>getAll</code> é acionado quando uma solicitação GET é feita para
        <code>/tarefas</code>. Ele retorna uma lista de todas as tarefas existentes.</p>
    <h3><code>@DeleteMapping</code></h3>
    <p>A anotação <code>@DeleteMapping</code> é uma anotação do Spring que indica que o método trata solicitações HTTP
        DELETE. Neste caso, o método <code>deletar</code> é acionado quando uma solicitação DELETE é feita para
        <code>/tarefas/{tarefaId}</code>. O parâmetro <code>@PathVariable</code> indica que o valor de
        <code>tarefaId</code> é passado na URL.</p>
</div>

<div class="markdown prose w-full break-words dark:prose-invert dark">
    <h1>TarefaDTO</h1>
    <p>A classe <code>TarefaDTO</code> é um objeto de transferência de dados (DTO) utilizado para representar as tarefas
        no recurso de tarefas do projeto.</p>
    <h2>Atributos</h2>
    <ul>
        <li><code>id</code> (tipo <code>Long</code>): identificador da tarefa.</li>
        <li><code>titulo</code> (tipo <code>String</code>): título da tarefa.</li>
        <li><code>descricao</code> (tipo <code>String</code>): descrição da tarefa.</li>
    </ul>
    <h2>Métodos</h2>
    <ul>
        <li><code>getId()</code>: retorna o identificador da tarefa.</li>
        <li><code>setId(Long id)</code>: define o identificador da tarefa.</li>
        <li><code>getTitulo()</code>: retorna o título da tarefa.</li>
        <li><code>setTitulo(String titulo)</code>: define o título da tarefa.</li>
        <li><code>getDescricao()</code>: retorna a descrição da tarefa.</li>
        <li><code>setDescricao(String descricao)</code>: define a descrição da tarefa.</li>
    </ul>
    <p>Essa classe é utilizada para transferir informações entre diferentes camadas da aplicação e para representar as
        tarefas no formato JSON durante as operações de criação, atualização e consulta realizadas pela API REST
        implementada no projeto.</p>
</div>

<div class="markdown prose w-full break-words dark:prose-invert dark">
    <h2>TarefasFacade.java</h2>
    <p>Este arquivo está localizado em
        <code>C:\Users\user\Desktop\api-spring-boot\src\main\java\com\company\nomeprojeto\tarefas\facade\TarefasFacade.java</code>
        e contém a classe <code>TarefasFacade</code> que é uma classe de fachada (facade) responsável por fornecer uma
        camada de abstração entre a lógica de negócios e a camada de controle da API de tarefas.</p>
    <p>A classe <code>TarefasFacade</code> contém as seguintes funções:</p>
    <ul>
        <li><code>criar</code>: cria uma nova tarefa a partir de um objeto <code>TarefaDTO</code>, atribui um id único e
            adiciona ao mapa de tarefas;</li>
        <li><code>atualizar</code>: atualiza uma tarefa existente com um objeto <code>TarefaDTO</code> e um id de tarefa
            existente;</li>
        <li><code>getById</code>: recupera uma tarefa existente a partir de um id de tarefa;</li>
        <li><code>getAll</code>: recupera todas as tarefas existentes;</li>
        <li><code>delete</code>: remove uma tarefa existente a partir de um id de tarefa.</li>
    </ul>
    <p>A classe <code>TarefasFacade</code> é marcada com a anotação <code>@Service</code> do Spring Framework, indicando
        que é um componente de serviço que deve ser gerenciado pelo contêiner do Spring. Além disso, a classe contém um
        mapa estático <code>tarefas</code> que é usado para armazenar todas as tarefas gerenciadas pela fachada.</p>
</div>
