Exercício 1: Cadastro de Produto
public class ProdutoDTO {
    private String nome;
    private double preco;
    private int quantidade;

    // Construtor
    public ProdutoDTO(String nome, double preco, int quantidade) {
        this.nome = nome;
        this.preco = preco;
        this.quantidade = quantidade;
    }

    // Getters e Setters
    public String getNome() {
        return nome;
    }

    public void setNome(String nome) {
        this.nome = nome;
    }

    public double getPreco() {
        return preco;
    }

    public void setPreco(double preco) {
        this.preco = preco;
    }

    public int getQuantidade() {
        return quantidade;
    }

    public void setQuantidade(int quantidade) {
        this.quantidade = quantidade;
    }

    @Override
    public String toString() {
        return "Produto: " + nome + ", Preço: R$" + preco + ", Quantidade: " + quantidade;
    }
}
import javax.swing.*;
import java.util.ArrayList;
import java.util.List;

public class ProdutoDAO {
    private List<ProdutoDTO> produtos;

    // Construtor
    public ProdutoDAO() {
        this.produtos = new ArrayList<>();
    }

    // Método para adicionar produto à lista
    public void adicionarProduto(ProdutoDTO produto) {
        produtos.add(produto);
        JOptionPane.showMessageDialog(null, "Produto cadastrado com sucesso!");
    }

    // Método para exibir todos os produtos cadastrados
    public void exibirProdutos() {
        if (produtos.isEmpty()) {
            JOptionPane.showMessageDialog(null, "Não há produtos cadastrados.");
        } else {
            StringBuilder sb = new StringBuilder();
            for (ProdutoDTO produto : produtos) {
                sb.append(produto.toString()).append("\n");
            }
            JOptionPane.showMessageDialog(null, sb.toString());
        }
    }
}
Exercício 2: Sistema de Gerenciamento de Funcionários
public class FuncionarioDTO {
    private String nome;
    private String cargo;
    private double salario;

    // Construtor
    public FuncionarioDTO(String nome, String cargo, double salario) {
        this.nome = nome;
        this.cargo = cargo;
        this.salario = salario;
    }

    // Getters e Setters
    public String getNome() {
        return nome;
    }

    public void setNome(String nome) {
        this.nome = nome;
    }

    public String getCargo() {
        return cargo;
    }

    public void setCargo(String cargo) {
        this.cargo = cargo;
    }

    public double getSalario() {
        return salario;
    }

    public void setSalario(double salario) {
        this.salario = salario;
    }

    @Override
    public String toString() {
        return "Nome: " + nome + ", Cargo: " + cargo + ", Salário: R$" + salario;
    }
}
import javax.swing.*;
import java.util.ArrayList;
import java.util.List;

public class FuncionarioDAO {
    private List<FuncionarioDTO> funcionarios;

    // Construtor
    public FuncionarioDAO() {
        this.funcionarios = new ArrayList<>();
    }

    // Método para adicionar funcionário
    public void adicionarFuncionario(FuncionarioDTO funcionario) {
        funcionarios.add(funcionario);
        JOptionPane.showMessageDialog(null, "Funcionário cadastrado com sucesso!");
    }

    // Método para exibir todos os funcionários cadastrados
    public void exibirFuncionarios() {
        if (funcionarios.isEmpty()) {
            JOptionPane.showMessageDialog(null, "Não há funcionários cadastrados.");
        } else {
            StringBuilder sb = new StringBuilder();
            for (FuncionarioDTO funcionario : funcionarios) {
                sb.append(funcionario.toString()).append("\n");
            }
            JOptionPane.showMessageDialog(null, sb.toString());
        }
    }
}
Exercício 3: Gerenciamento de Biblioteca
public class LivroDTO {
    private String titulo;
    private String autor;
    private int anoPublicacao;

    // Construtor
    public LivroDTO(String titulo, String autor, int anoPublicacao) {
        this.titulo = titulo;
        this.autor = autor;
        this.anoPublicacao = anoPublicacao;
    }

    // Getters e Setters
    public String getTitulo() {
        return titulo;
    }

    public void setTitulo(String titulo) {
        this.titulo = titulo;
    }

    public String getAutor() {
        return autor;
    }

    public void setAutor(String autor) {
        this.autor = autor;
    }

    public int getAnoPublicacao() {
        return anoPublicacao;
    }

    public void setAnoPublicacao(int anoPublicacao) {
        this.anoPublicacao = anoPublicacao;
    }

    @Override
    public String toString() {
        return "Título: " + titulo + ", Autor: " + autor + ", Ano de Publicação: " + anoPublicacao;
    }
}
import java.util.ArrayList;
import java.util.List;
import javax.swing.JOptionPane;

public class LivroDAO {
    private List<LivroDTO> livros;

    // Construtor
    public LivroDAO() {
        this.livros = new ArrayList<>();
    }

    // Método para adicionar livro
    public void adicionarLivro(LivroDTO livro) {
        livros.add(livro);
        JOptionPane.showMessageDialog(null, "Livro cadastrado com sucesso!");
    }

    // Método para remover livro
    public void removerLivro(String titulo) {
        boolean removido = false;
        for (LivroDTO livro : livros) {
            if (livro.getTitulo().equalsIgnoreCase(titulo)) {
                livros.remove(livro);
                removido = true;
                JOptionPane.showMessageDialog(null, "Livro removido com sucesso!");
                break;
            }
        }
        if (!removido) {
            JOptionPane.showMessageDialog(null, "Livro não encontrado!");
        }
    }

    // Método para exibir todos os livros cadastrados
    public void listarLivros() {
        if (livros.isEmpty()) {
            JOptionPane.showMessageDialog(null, "Não há livros cadastrados.");
        } else {
            StringBuilder sb = new StringBuilder();
            for (LivroDTO livro : livros) {
                sb.append(livro.toString()).append("\n");
            }
            JOptionPane.showMessageDialog(null, sb.toString());
        }
    }
}
Exercício 4: Sistema de Reserva de Quartos de Hotel
import java.util.Date;

public class ReservaDTO {
    private String cliente;
    private int numeroDoQuarto;
    private Date dataEntrada;
    private Date dataSaida;

    // Construtor
    public ReservaDTO(String cliente, int numeroDoQuarto, Date dataEntrada, Date dataSaida) {
        this.cliente = cliente;
        this.numeroDoQuarto = numeroDoQuarto;
        this.dataEntrada = dataEntrada;
        this.dataSaida = dataSaida;
    }

    // Getters e Setters
    public String getCliente() {
        return cliente;
    }

    public void setCliente(String cliente) {
        this.cliente = cliente;
    }

    public int getNumeroDoQuarto() {
        return numeroDoQuarto;
    }

    public void setNumeroDoQuarto(int numeroDoQuarto) {
        this.numeroDoQuarto = numeroDoQuarto;
    }

    public Date getDataEntrada() {
        return dataEntrada;
    }

    public void setDataEntrada(Date dataEntrada) {
        this.dataEntrada = dataEntrada;
    }

    public Date getDataSaida() {
        return dataSaida;
    }

    public void setDataSaida(Date dataSaida) {
        this.dataSaida = dataSaida;
    }

    @Override
    public String toString() {
        return "Cliente: " + cliente + ", Quarto: " + numeroDoQuarto +
               ", Entrada: " + dataEntrada.toString() + ", Saída: " + dataSaida.toString();
    }
}
import java.util.Date;

public class ReservaDTO {
    private String cliente;
    private int numeroDoQuarto;
    private Date dataEntrada;
    private Date dataSaida;

    // Construtor
    public ReservaDTO(String cliente, int numeroDoQuarto, Date dataEntrada, Date dataSaida) {
        this.cliente = cliente;
        this.numeroDoQuarto = numeroDoQuarto;
        this.dataEntrada = dataEntrada;
        this.dataSaida = dataSaida;
    }

    // Getters e Setters
    public String getCliente() {
        return cliente;
    }

    public void setCliente(String cliente) {
        this.cliente = cliente;
    }

    public int getNumeroDoQuarto() {
        return numeroDoQuarto;
    }

    public void setNumeroDoQuarto(int numeroDoQuarto) {
        this.numeroDoQuarto = numeroDoQuarto;
    }

    public Date getDataEntrada() {
        return dataEntrada;
    }

    public void setDataEntrada(Date dataEntrada) {
        this.dataEntrada = dataEntrada;
    }

    public Date getDataSaida() {
        return dataSaida;
    }

    public void setDataSaida(Date dataSaida) {
        this.dataSaida = dataSaida;
    }

    @Override
    public String toString() {
        return "Cliente: " + cliente + ", Quarto: " + numeroDoQuarto +
               ", Entrada: " + dataEntrada.toString() + ", Saída: " + dataSaida.toString();
    }
}
Exercício 5: Sistema de Controle de Pedidos de Restaurantes
import java.util.List;

public class PedidoDTO {

    private int numeroDoPedido;
    private String cliente;
    private List<String> itens;
    private double total;

    // Construtor
    public PedidoDTO(int numeroDoPedido, String cliente, List<String> itens, double total) {
        this.numeroDoPedido = numeroDoPedido;
        this.cliente = cliente;
        this.itens = itens;
        this.total = total;
    }

    // Getters e Setters
    public int getNumeroDoPedido() {
        return numeroDoPedido;
    }

    public void setNumeroDoPedido(int numeroDoPedido) {
        this.numeroDoPedido = numeroDoPedido;
    }

    public String getCliente() {
        return cliente;
    }

    public void setCliente(String cliente) {
        this.cliente = cliente;
    }

    public List<String> getItens() {
        return itens;
    }

    public void setItens(List<String> itens) {
        this.itens = itens;
    }

    public double getTotal() {
        return total;
    }

    public void setTotal(double total) {
        this.total = total;
    }

    @Override
    public String toString() {
        return "Pedido nº " + numeroDoPedido + " - Cliente: " + cliente + "\nItens: " + itens + "\nTotal: R$ " + total;
    }
}
import java.util.ArrayList;
import java.util.List;

public class PedidoDAO {

    private List<PedidoDTO> pedidos;

    // Construtor
    public PedidoDAO() {
        this.pedidos = new ArrayList<>();
    }

    // Adicionar um novo pedido
    public void adicionarPedido(PedidoDTO pedido) {
        pedidos.add(pedido);
    }

    // Remover um pedido pelo número do pedido
    public boolean removerPedido(int numeroDoPedido) {
        for (PedidoDTO pedido : pedidos) {
            if (pedido.getNumeroDoPedido() == numeroDoPedido) {
                pedidos.remove(pedido);
                return true;
            }
        }
        return false; // Retorna false se o pedido não for encontrado
    }

    // Listar todos os pedidos
    public List<PedidoDTO> listarPedidos() {
        return pedidos;
    }

    // Buscar um pedido pelo número do pedido
    public PedidoDTO buscarPedido(int numeroDoPedido) {
        for (PedidoDTO pedido : pedidos) {
            if (pedido.getNumeroDoPedido() == numeroDoPedido) {
                return pedido;
            }
        }
        return null; // Retorna null se o pedido não for encontrado
    }
}
Exercício 6: Sistema de Vendas de Carros
public class CarroDTO {

    private String modelo;
    private String marca;
    private int ano;
    private double preco;

    // Construtor
    public CarroDTO(String modelo, String marca, int ano, double preco) {
        this.modelo = modelo;
        this.marca = marca;
        this.ano = ano;
        this.preco = preco;
    }

    // Getters e Setters
    public String getModelo() {
        return modelo;
    }

    public void setModelo(String modelo) {
        this.modelo = modelo;
    }

    public String getMarca() {
        return marca;
    }

    public void setMarca(String marca) {
        this.marca = marca;
    }

    public int getAno() {
        return ano;
    }

    public void setAno(int ano) {
        this.ano = ano;
    }

    public double getPreco() {
        return preco;
    }

    public void setPreco(double preco) {
        this.preco = preco;
    }

    @Override
    public String toString() {
        return "Modelo: " + modelo + ", Marca: " + marca + ", Ano: " + ano + ", Preço: R$ " + preco;
    }
}
import java.util.ArrayList;
import java.util.List;

public class CarroDAO {

    private List<CarroDTO> vendas;

    // Construtor
    public CarroDAO() {
        this.vendas = new ArrayList<>();
    }

    // Adicionar um novo carro vendido
    public void adicionarVenda(CarroDTO carro) {
        vendas.add(carro);
    }

    // Listar todos os carros vendidos
    public List<CarroDTO> listarVendas() {
        return vendas;
    }

    // Calcular o total de vendas
    public double calcularTotalVendas() {
        double total = 0;
        for (CarroDTO carro : vendas) {
            total += carro.getPreco();
        }
        return total;
    }
}
Exercício 7: Sistema de Controle de Alunos
public class AlunoDTO {

    private String nome;
    private String matricula;
    private String curso;

    // Construtor
    public AlunoDTO(String nome, String matricula, String curso) {
        this.nome = nome;
        this.matricula = matricula;
        this.curso = curso;
    }

    // Getters e Setters
    public String getNome() {
        return nome;
    }

    public void setNome(String nome) {
        this.nome = nome;
    }

    public String getMatricula() {
        return matricula;
    }

    public void setMatricula(String matricula) {
        this.matricula = matricula;
    }

    public String getCurso() {
        return curso;
    }

    public void setCurso(String curso) {
        this.curso = curso;
    }

    @Override
    public String toString() {
        return "Nome: " + nome + ", Matrícula: " + matricula + ", Curso: " + curso;
    }
}
import java.util.ArrayList;
import java.util.List;

public class AlunoDAO {

    private List<AlunoDTO> alunos;

    // Construtor
    public AlunoDAO() {
        this.alunos = new ArrayList<>();
    }

    // Adicionar um novo aluno
    public void adicionarAluno(AlunoDTO aluno) {
        alunos.add(aluno);
    }

    // Remover um aluno pela matrícula
    public boolean removerAluno(String matricula) {
        for (AlunoDTO aluno : alunos) {
            if (aluno.getMatricula().equals(matricula)) {
                alunos.remove(aluno);
                return true; // Retorna true se o aluno for removido com sucesso
            }
        }
        return false; // Retorna false se o aluno não for encontrado
    }

    // Listar todos os alunos
    public List<AlunoDTO> listarAlunos() {
        return alunos;
    }

    // Buscar aluno pela matrícula
    public AlunoDTO buscarAluno(String matricula) {
        for (AlunoDTO aluno : alunos) {
            if (aluno.getMatricula().equals(matricula)) {
                return aluno;
            }
        }
        return null; // Retorna null se o aluno não for encontrado
    }
}

Exercício 8: Sistema de Controle de Veículos
public class VeiculoDTO {

    private String placa;
    private String modelo;
    private int ano;
    private String tipo;

    // Construtor
    public VeiculoDTO(String placa, String modelo, int ano, String tipo) {
        this.placa = placa;
        this.modelo = modelo;
        this.ano = ano;
        this.tipo = tipo;
    }

    // Getters e Setters
    public String getPlaca() {
        return placa;
    }

    public void setPlaca(String placa) {
        this.placa = placa;
    }

    public String getModelo() {
        return modelo;
    }

    public void setModelo(String modelo) {
        this.modelo = modelo;
    }

    public int getAno() {
        return ano;
    }

    public void setAno(int ano) {
        this.ano = ano;
    }

    public String getTipo() {
        return tipo;
    }

    public void setTipo(String tipo) {
        this.tipo = tipo;
    }

    @Override
    public String toString() {
        return "Placa: " + placa + ", Modelo: " + modelo + ", Ano: " + ano + ", Tipo: " + tipo;
    }
}
import java.util.ArrayList;
import java.util.List;

public class VeiculoDAO {

    private List<VeiculoDTO> veiculos;

    // Construtor
    public VeiculoDAO() {
        this.veiculos = new ArrayList<>();
    }

    // Adicionar um novo veículo
    public void adicionarVeiculo(VeiculoDTO veiculo) {
        veiculos.add(veiculo);
    }

    // Listar todos os veículos cadastrados
    public List<VeiculoDTO> listarVeiculos() {
        return veiculos;
    }

    // Buscar veículo pela placa
    public VeiculoDTO buscarVeiculo(String placa) {
        for (VeiculoDTO veiculo : veiculos) {
            if (veiculo.getPlaca().equals(placa)) {
                return veiculo;
            }
        }
        return null; // Retorna null se o veículo não for encontrado
    }
}

Exercício 9: Sistema de Gerenciamento de Tarefas
import java.time.LocalDate;

public class TarefaDTO {

    private String titulo;
    private String descricao;
    private LocalDate prazo;

    // Construtor
    public TarefaDTO(String titulo, String descricao, LocalDate prazo) {
        this.titulo = titulo;
        this.descricao = descricao;
        this.prazo = prazo;
    }

    // Getters e Setters
    public String getTitulo() {
        return titulo;
    }

    public void setTitulo(String titulo) {
        this.titulo = titulo;
    }

    public String getDescricao() {
        return descricao;
    }

    public void setDescricao(String descricao) {
        this.descricao = descricao;
    }

    public LocalDate getPrazo() {
        return prazo;
    }

    public void setPrazo(LocalDate prazo) {
        this.prazo = prazo;
    }

    @Override
    public String toString() {
        return "Título: " + titulo + ", Descrição: " + descricao + ", Prazo: " + prazo;
    }
}
import java.util.ArrayList;
import java.util.List;

public class TarefaDAO {

    private List<TarefaDTO> tarefas;

    // Construtor
    public TarefaDAO() {
        this.tarefas = new ArrayList<>();
    }

    // Adicionar uma nova tarefa
    public void adicionarTarefa(TarefaDTO tarefa) {
        tarefas.add(tarefa);
    }

    // Listar todas as tarefas cadastradas
    public List<TarefaDTO> listarTarefas() {
        return tarefas;
    }
}
Exercício 10: Sistema de Controle de Contas a Pagar
import java.time.LocalDate;

public class ContaDTO {

    private String descricao;
    private double valor;
    private LocalDate dataVencimento;
    private boolean pago;

    // Construtor
    public ContaDTO(String descricao, double valor, LocalDate dataVencimento) {
        this.descricao = descricao;
        this.valor = valor;
        this.dataVencimento = dataVencimento;
        this.pago = false;  // Inicialmente a conta não é paga
    }

    // Getters e Setters
    public String getDescricao() {
        return descricao;
    }

    public void setDescricao(String descricao) {
        this.descricao = descricao;
    }

    public double getValor() {
        return valor;
    }

    public void setValor(double valor) {
        this.valor = valor;
    }

    public LocalDate getDataVencimento() {
        return dataVencimento;
    }

    public void setDataVencimento(LocalDate dataVencimento) {
        this.dataVencimento = dataVencimento;
    }

    public boolean isPago() {
        return pago;
    }

    public void setPago(boolean pago) {
        this.pago = pago;
    }

    @Override
    public String toString() {
        return "Descrição: " + descricao + ", Valor: R$" + valor + ", Vencimento: " + dataVencimento + ", Pago: " + (pago ? "Sim" : "Não");
    }
}
import java.util.ArrayList;
import java.util.List;

public class ContaDAO {

    private List<ContaDTO> contas;

    // Construtor
    public ContaDAO() {
        this.contas = new ArrayList<>();
    }

    // Adicionar uma nova conta
    public void adicionarConta(ContaDTO conta) {
        contas.add(conta);
    }

    // Remover uma conta
    public void removerConta(ContaDTO conta) {
        contas.remove(conta);
    }

    // Listar todas as contas pendentes (não pagas)
    public List<ContaDTO> listarContasPendentes() {
        List<ContaDTO> pendentes = new ArrayList<>();
        for (ContaDTO conta : contas) {
            if (!conta.isPago()) {
                pendentes.add(conta);
            }
        }
        return pendentes;
    }

    // Marcar uma conta como paga
    public void pagarConta(ContaDTO conta) {
        conta.setPago(true);
    }
}
