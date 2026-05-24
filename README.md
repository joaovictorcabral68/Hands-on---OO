# 1.
```java

import java.util.ArrayList;

class Compras{
String produto;

public Compras(String produto){
this.produto=produto;
}
public String getproduto(){
return produto;
}
public static void main(String[] args) {
    ArrayList<Compras>lista=new ArrayList<>();

    lista.add(new Compras("Arroz"));
    lista.add(new Compras("Feijão"));
     lista.add(new Compras("Oleo"));
      lista.add(new Compras("Biscoito"));
       lista.add(new Compras("Iorgute"));
       System.out.println("Os produtos da lista são:");
       for(int i=0;i<lista.size();i++){
       System.out.println(lista.get(i).getproduto());
       }
       System.out.println("A lista possui: "+lista.size()+" Itens");
}
 }


```

# 2.

```java

import java.util.ArrayList;
import java.util.Scanner;

class Notas2{
    double notas;
    double media;
    public double media(){
        return media;
    }
public static void main(String[] args) {
    Scanner sc=new Scanner(System.in);

    ArrayList<Notas2>calculo=new ArrayList<>();

    System.out.println("Escreva 4 notas:");

    for(int i=0;i<4;i++){
    Notas2 n=new Notas2();
    n.notas=sc.nextDouble();
    calculo.add(n);
    }
    double soma=0;
    for(int i=0;i<calculo.size();i++){
        soma=+calculo.get(i).notas;
    }
     
    double media=soma/calculo.size();

    if(media>=7){
        System.out.println("A media da turma foi:"+media);
    }else{
        System.out.println("A turma ficou com média abaixo de 7");
    }
}
    
}

```

# 3.

```java

import java.util.HashSet;

public class PresencaAlunos {
    public static void main(String[] args) {

        HashSet<String> presentes = new HashSet<>();

        presentes.add("Ana");
        presentes.add("Bruno");
        presentes.add("Carlos");
        presentes.add("Ana");
        presentes.add("Bruno");
        presentes.add("Daniela");
        presentes.add("Eduardo");
        presentes.add("Carlos");

        System.out.println("Alunos presentes (sem repetição):");
        for (String aluno : presentes) {
            System.out.println(aluno);
        }

        System.out.println("\nTotal de alunos presentes: " + presentes.size());
    }
}

```
# 4.

```java
import java.util.HashMap;

public class CadastroAlunos {
    public static void main(String[] args) {

        HashMap<Integer, String> alunos = new HashMap<>();

        alunos.put(1001, "Ana");
        alunos.put(1002, "Bruno");
        alunos.put(1003, "Carlos");
        alunos.put(1004, "Daniela");

        int matriculaBusca = 1002;
        System.out.println("Aluno encontrado: " + alunos.get(matriculaBusca));

        int matriculaRemover = 1003;
        alunos.remove(matriculaRemover);

        System.out.println("\nAlunos cadastrados:");
        for (Integer matricula : alunos.keySet()) {
            System.out.println(matricula + " - " + alunos.get(matricula));
        }
    }
}

```

# 5.
```java
import java.util.LinkedList;
import java.util.Queue;

public class FilaClientes {
    public static void main(String[] args) {

        Queue<String> fila = new LinkedList<>();

        fila.add("Cliente 1");
        fila.add("Cliente 2");
        fila.add("Cliente 3");
        fila.add("Cliente 4");
        fila.add("Cliente 5");

        System.out.println("Próximo a ser atendido: " + fila.peek());

        fila.poll();
        fila.poll();

        System.out.println("\nFila atualizada:");
        for (String cliente : fila) {
            System.out.println(cliente);
        }
    }
}

```

# 6.

```java

import java.util.ArrayList;
import java.util.Scanner;

class Livro {
    int codigo;
    String titulo;
    String autor;
    boolean disponivel = true;

    public Livro(int codigo, String titulo, String autor) {
        this.codigo = codigo;
        this.titulo = titulo;
        this.autor = autor;
    }
}

public class SistemaBiblioteca {
    public static void main(String[] args) {

        ArrayList<Livro> livros = new ArrayList<>();
        Scanner sc = new Scanner(System.in);

        int opcao;

        do {
            System.out.println("\n1 - Cadastrar livro");
            System.out.println("2 - Listar livros");
            System.out.println("3 - Emprestar livro");
            System.out.println("4 - Devolver livro");
            System.out.println("0 - Sair");
            opcao = sc.nextInt();
            sc.nextLine();

            if (opcao == 1) {
                System.out.print("Código: ");
                int codigo = sc.nextInt();
                sc.nextLine();

                System.out.print("Título: ");
                String titulo = sc.nextLine();

                System.out.print("Autor: ");
                String autor = sc.nextLine();

                livros.add(new Livro(codigo, titulo, autor));
            }

            else if (opcao == 2) {
                for (Livro l : livros) {
                    System.out.println(
                        l.codigo + " - " +
                        l.titulo + " - " +
                        l.autor + " - " +
                        (l.disponivel ? "Disponível" : "Emprestado")
                    );
                }
            }

            else if (opcao == 3) {
                System.out.print("Código do livro: ");
                int codigo = sc.nextInt();

                for (Livro l : livros) {
                    if (l.codigo == codigo && l.disponivel) {
                        l.disponivel = false;
                        System.out.println("Livro emprestado.");
                        break;
                    }
                }
            }

            else if (opcao == 4) {
                System.out.print("Código do livro: ");
                int codigo = sc.nextInt();

                for (Livro l : livros) {
                    if (l.codigo == codigo && !l.disponivel) {
                        l.disponivel = true;
                        System.out.println("Livro devolvido.");
                        break;
                    }
                }
            }

        } while (opcao != 0);

        sc.close();
    }
}

```

# 7.

```java

import java.util.ArrayList;
import java.util.Scanner;

class Pedido {
    int numero;
    String cliente;
    String item;
    double valor;
    String status;

    public Pedido(int numero, String cliente, String item, double valor) {
        this.numero = numero;
        this.cliente = cliente;
        this.item = item;
        this.valor = valor;
        this.status = "PENDENTE";
    }
}

public class SistemaLanchonete {
    public static void main(String[] args) {

        ArrayList<Pedido> pedidos = new ArrayList<>();
        Scanner sc = new Scanner(System.in);

        int opcao;

        do {
            System.out.println("\n1 - Cadastrar pedido");
            System.out.println("2 - Listar pedidos");
            System.out.println("3 - Atualizar status de um pedido");
            System.out.println("4 - Buscar pedido pelo número");
            System.out.println("5 - Mostrar valor total dos pedidos");
            System.out.println("0 - Sair");
            opcao = sc.nextInt();
            sc.nextLine();

            if (opcao == 1) {
                System.out.print("Número do pedido: ");
                int numero = sc.nextInt();
                sc.nextLine();

                System.out.print("Nome do cliente: ");
                String cliente = sc.nextLine();

                System.out.print("Item pedido: ");
                String item = sc.nextLine();

                System.out.print("Valor: ");
                double valor = sc.nextDouble();

                pedidos.add(new Pedido(numero, cliente, item, valor));
            }

            else if (opcao == 2) {
                for (Pedido p : pedidos) {
                    System.out.println(
                        p.numero + " - " +
                        p.cliente + " - " +
                        p.item + " - R$ " +
                        p.valor + " - " +
                        p.status
                    );
                }
            }

            else if (opcao == 3) {
                System.out.print("Número do pedido: ");
                int numero = sc.nextInt();
                sc.nextLine();

                System.out.print("Novo status (PENDENTE / PREPARANDO / FINALIZADO): ");
                String status = sc.nextLine();

                for (Pedido p : pedidos) {
                    if (p.numero == numero) {
                        p.status = status;
                        System.out.println("Status atualizado.");
                        break;
                    }
                }
            }

            else if (opcao == 4) {
                System.out.print("Número do pedido: ");
                int numero = sc.nextInt();

                for (Pedido p : pedidos) {
                    if (p.numero == numero) {
                        System.out.println(
                            p.numero + " - " +
                            p.cliente + " - " +
                            p.item + " - R$ " +
                            p.valor + " - " +
                            p.status
                        );
                        break;
                    }
                }
            }

            else if (opcao == 5) {
                double total = 0;
                for (Pedido p : pedidos) {
                    total += p.valor;
                }
                System.out.println("Valor total dos pedidos: R$ " + total);
            }

        } while (opcao != 0);

        sc.close();
    }
}
```
