class Main{
	class Main{

  public static void main(String args[]){
    int dato1=leggiDouble("inserisci 1^ numero");
    int dato2=leggiDouble("inserisci 2^ numero");
    System.out.println(sottrai(dato1,dato2));
    System.out.println(addizione(dato1,dato2));
    System.out.println(dividi(dato1,dato2));
  }
public static void addizione(double a, double b){
	return a+b;
}
public static int sottrai(int a, int b) {
        return a - b;
}

public double dividi(double dividendo, double divisore) {
	
		try{
			if(divisore==0) {
				if(dividendo>0) return Double.POSITIVE_INFINITY;
				else return Double.NEGATIVE_INFINITY;
			} else {
				double risultato = dividendo/divisore;
				return risultato;
			}
		} catch (Exception e) {
			return 0;
		}
		
	}

/**
   * Legge un valore di tipo double da input.
   *
   * @param domanda La domanda da visualizzare.
   * @return Il valore di tipo double inserito.
   */
  public static double leggiDouble(String domanda){//leggi intero POSITIVO
    double numeroInserito = 0;
    boolean conversione=false;//flag che controlla che la conversione sia corretta
    do{
      try{
        numeroInserito=Double.parseDouble(leggiStringa(domanda));
        conversione=true;
      }catch(ArithmeticException e){
        Colori.rosso("devi inserire un numero! "+e+"\n");
      }catch(Exception e){
        Colori.rosso("errore nella conversione "+e+"\n");
      }
    }while(!conversione);
    return numeroInserito;
  }

/**
   * Legge una stringa da input.
   *
   * @param domanda La domanda da visualizzare.
   * @return La stringa inserita.
   */
  public static String leggiStringa(String domanda) {//leggi STRINGA
    BufferedReader k=new BufferedReader (new InputStreamReader(System.in));
    boolean corretto=false; //flag che controlla che l'input sia corretto
    String risposta = "";
    do{
      try{
        System.out.println(domanda);
        risposta = k.readLine();
        corretto=true;
      }catch(IOException e){
        Colori.rosso("errore nell'acquisizione del dato!\n");
      }catch(Exception e){
        Colori.rosso("errore "+e+"\n");
      }
    }while(!corretto);
    return risposta;
  }  
}

}
