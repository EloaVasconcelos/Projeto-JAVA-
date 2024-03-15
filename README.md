# Projeto-JAVA-

#eclipse 

PROJETO DA AULA DE QTS - PROGRAMANDO EM JAVA
package bg_etim_projeto1_turmaAeB;

public class ContaCorrente {

	//DEFINIR ATRIBUTOS 
	
	public String nomeTitular;
	
	public double saldo;
	
	public int agConta;
	
	//MÉTODOS 
	
	//AÇÃO DA CLASSE CONTA CORRENTE 
	//VOID - SEM RETORNO 
	// (this) INDICA A SALDO QUE É ATRIBUTO/ REGISTRO COM OS MESMO NOMES 
	// += IRÁ SOMAR 
	
	public void depositar(double valor) {
		this.saldo += valor;
		
	}
	
	//RETORNAR VERDADEIRA OU FALSO 
	
	public boolean sacar(double valor) {
		if (this.saldo >= valor) {
			this.saldo -= valor;
			return true;
		}
		
		// NÃO PRECISA DO ELSE, VAI DIRETO PRO RETURN 

			return false;  // SE NÃO FOR VERDADEIDO IRÁ CAIR NO RETURN ABAIXO 
		
	
}
 
	
	//O VALOR VAI PRA CONTADESTINO 
	public boolean transferir(double valor, ContaCorrente ContaDestino ) {
		if (this.saldo >= valor) {
			this.saldo -= valor;
			ContaDestino.saldo+=valor;
			return true;
		}
		
		// NÃO PRECISA DO ELSE, VAI DIRETO PRO RETURN 
		// SE NÃO FOR VERDADEIDO IRÁ CAIR NO RETURN ABAIXO 

			return false;  
		
		
	}
	}
	

// LETRA MAIÚSCULA INDICA QUE É UMA CLASSE 

// clase principal 


package bg_etim_projeto1_turmaAeB;

public class Principal {

	public static void main(String[] args) {
		// TODO Auto-generated method stub
		
		ContaCorrente cc1 = new ContaCorrente();
		ContaCorrente cc2 = new ContaCorrente();
		
		cc1.nomeTitular ="Aline";
		cc2.nomeTitular ="Cidade";

		
		System.out.println( "Teste 1");
		cc1.depositar(200);
		// ATALHO DE IMPRIMIR 
		System.out.println("Saldo de "+ cc1.nomeTitular + "Deve ser: 200");
		System.out.println("Saldo de "+ cc1.nomeTitular + "É:" + cc1.saldo);

		
		System.out.println( "Teste 2");
		cc1.depositar(300);
		// ATALHO DE IMPRIMIR 
		System.out.println("Saldo de "+ cc1.nomeTitular + "Deve ser: 500");
		System.out.println("Saldo de "+ cc1.nomeTitular + "É:" + cc1.saldo);
		
	
		
		System.out.println( "Teste 3");
		boolean sucesso = cc1.sacar(400);
		// ATALHO DE IMPRIMIR 
		System.out.println("Saldo de "+ cc1.nomeTitular + " Deve ser: 100");
		System.out.println("Saldo de "+ cc1.nomeTitular + " É:" + cc1.saldo);
		System.out.println(" Sucesso da op. deve ser: true");
		System.out.println(" Sucesso da op. é" + sucesso );
		
		
		// SE ELA NÃO TIVER DINHEIRO NÃO VAI PODER FAZER A TRANSFERNECIA, O SALDO CONTINUA IGUAL  
		
		System.out.println( "Teste 3");
		boolean falha = cc1.sacar(500);
		// ATALHO DE IMPRIMIR 
		System.out.println("Saldo de "+ cc1.nomeTitular + " Deve ser: 100");
		System.out.println("Saldo de "+ cc1.nomeTitular + " É:" + cc1.saldo);
		System.out.println(" Sucesso da op. deve ser: false");
		System.out.println(" Sucesso da op. é: " + falha);
		
		
		System.out.println( "Teste 5");
		
		// PRA QUEM VAI TRANSFERIR
		 cc1.transferir(104, cc2);
		// ATALHO DE IMPRIMIR 
		System.out.println("Saldo de "+ cc1.nomeTitular + " Deve ser: 100");
		System.out.println("Saldo de "+ cc1.nomeTitular + " É:" + cc1.saldo);
		System.out.println("Saldo de "+ cc2.nomeTitular + " Deve ser: 200");
		System.out.println("Saldo de "+ cc2.nomeTitular + " É:" + cc2.saldo);
		System.out.println(" Sucesso da op. deve ser: TRUE");
		System.out.println(" Sucesso da op. é: " + sucesso);
		
		

	}

}

