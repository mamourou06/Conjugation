# Conjugation
package projectconjugation;

import java.util.Scanner;

public class Conjugaison {
    public static String saisir_verbe_correct()
    {
    	@SuppressWarnings("resource")
		Scanner clavier=new Scanner(System.in);
		System.out.print("donnez un verbe regulier du premier groupe: ");
		String v=clavier.next();
		while(!(v.substring(v.length()-2).equalsIgnoreCase("er")) || 
				(v.substring(v.length()-3, v.length()-2).equalsIgnoreCase("g")) 
				|| v.equalsIgnoreCase("aller"))
		{
			System.out.print("Incorrect! Veuillez s\'il vous plait saisir un verbe regulier du premier "
					+ "groupe: ");
			 v=clavier.next();
		}
		return v;
    }
    public static void conjugate_verbe()
    { 
    	String[] sujets= {"Je","Tu","Il/Elle","Nous","Vous","Ils/Elles"};
    	String[] terminaisons= {"e","es","e","ons","ez","ent"};
    	@SuppressWarnings("unused")
		String v=saisir_verbe_correct();
    	for(int i=0;i<sujets.length;i++)
    		System.out.println(sujets[i]+" "+v.substring(0, v.length()-2)+terminaisons[i]);
    }
	public static void main(String[] args) 
	{
		 conjugate_verbe();
	}
}
