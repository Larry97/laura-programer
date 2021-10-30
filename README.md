package domaci6;

import java.util.ArrayList;
import java.util.Scanner;

public class Biblioteka {

	public static void main(String[] args) {
		
		
		ArrayList<String> idClanova = new ArrayList<String>();
		ArrayList<String> imena = new ArrayList<String>();
		ArrayList<String> prezimena = new ArrayList<String>();
		
		ArrayList<String> idKnjiga = new ArrayList<String>();
		ArrayList<String> naslovi = new ArrayList<String>();
		ArrayList<String> autori = new ArrayList<String>();
		
		//za clanove
		idClanova.add("C1");
		idClanova.add("C2");
		idClanova.add("C3");
		idClanova.add("C4");
		idClanova.add("C5");
		
		imena.add("Marko");
		imena.add("Milan");
		imena.add("Petar");
		imena.add("Zoran");
		imena.add("Dejan");
		
		prezimena.add("Novakovic");
		prezimena.add("Popov");
		prezimena.add("Jokic");
		prezimena.add("Markov");
		prezimena.add("Drljaca");
		
		
		//za knjige
		idKnjiga.add("K1");
		idKnjiga.add("K2");
		idKnjiga.add("K3");
		
		naslovi.add("Antigona");
		naslovi.add("Tvrdica");
		naslovi.add("Karenjina");
		
		autori.add("Sofokle");
		autori.add("Molijer");
		autori.add("Tolstoj");
		
		Scanner sc = new Scanner(System.in);
		
		String opcija;
		
		do {
			System.out.println("********************** MENI ************************");
			System.out.println("--------------------ZA CLANOVE----------------------");
			
			System.out.println("1. Unos clana"); //1. Unos vec postojeceg clana
			System.out.println("2. Prikaz svih clanova");
			System.out.println("3. Brisanje clana na osnovu clanskog broja");
			System.out.println("4. Izmena clana na osnovu clanskog broja");
			System.out.println("5. Pretraga clana po clanskom broju");
			
			System.out.println("--------------------ZA KNJIGE----------------------");
			
			System.out.println("6. Unos knjige"); //2. Unos vec postojece knjige
			System.out.println("7. Prikaz svih knjiga");
			System.out.println("8. Brisanje knjiga na osnovu broja knjige");
			System.out.println("9. Izmena knjige po poziciji knjige u listi broja knjiga");
			
			System.out.println("10. Pretraga knjiga po autoru");
			System.out.println("11. Pretraga knjiga po naslovu");
			
			System.out.println("x. Izlaz");
			System.out.print("Unesite opciju: ");
			
			opcija = sc.nextLine();
			
			switch (opcija) {
			
			//-----------------------ZA CLANOVE--------------------------
			case "1": //Unos clana
			System.out.println("Unesite clanski broj: ");
			String brojClana = sc.nextLine();
			int pozicija = idClanova.indexOf(brojClana);
			//ako postoji sa tim brojem clana, ispisemo podatke
			if(pozicija != -1 ) {
				System.out.printf("%10s %10s %10s \n", idClanova.get(pozicija), 
				imena.get(pozicija), prezimena.get(pozicija));
			}
			else
				System.out.println("Osoba sa unetim clanskim brojem ne postoji.");
			break;
				
			case "2": //Prikaz svih clanova
				for (int i = 0; i < idClanova.size(); i++) {
					//10 mesta za imena i 5 mesta prosek odvojimo da bi podaci bili poravnati
					System.out.printf("%10s %10s %10s \n", idClanova.get(i), 
					imena.get(i), prezimena.get(i));
				}
			break;
			
			case "3":
				//brisanje clana
				System.out.println("Unesite clanski broj: ");
				brojClana = sc.nextLine();
				
				//trazimo poziciju clana u listi
				pozicija = idClanova.indexOf(brojClana);
				//ako postoji osoba sa tim brojem clana
				if(pozicija != -1) {
					idClanova.remove(pozicija);
					imena.remove(pozicija);
					prezimena.remove(pozicija);
					System.out.println("Clan je uspesno obrisan.");
				}
				else
					System.out.println("Osoba sa unetim clanskim brojem ne postoji.");
				
			break;
			
			case "4":
				//izmena podataka o clanu
				System.out.print("Unesite clanski broj: ");
				brojClana = sc.nextLine();
				
				//trazimo poziciju clana u listi
				pozicija = idClanova.indexOf(brojClana);
				//ako postoji osoba sa tim brojem clana
				//onda unosimo novo ime i prezime
				if(pozicija != -1) {
					System.out.print("Unesite novo ime studenta: ");
					String novoIme = sc.nextLine();
					System.out.print("Unesite novo prezime studenta: ");
					String novoPrezime = sc.nextLine();
					
					//azuriramo podatke na odgovovarajucoj poziciji u nizu
					imena.set(pozicija, novoIme);
					prezimena.set(pozicija, novoPrezime);
					
					System.out.println("Clan je uspesno promenjen.");
				}
				else
					System.out.println("Osoba sa unetim clanskim brojem ne postoji.");
				
			break;
				
			case "5": //pretraga clanova po clanskom broju
				System.out.print("Unesite clanski broj: ");
				brojClana = sc.nextLine();
				pozicija = idClanova.indexOf(brojClana);
				//ako postoji student sa tim brojem indeksa, prikazemo njegove podatke
				if(pozicija != -1)  {
					System.out.printf("%10s %10s %10s \n", idClanova.get(pozicija), 
										imena.get(pozicija), prezimena.get(pozicija));
				}
				else
					System.out.println("Osoba sa unetim clanskim brojem ne postoji.");
					
				break;
				
			//------------------------ZA KNJIGE-----------------------
			case "6": //Unos knjige
				System.out.println("Unesite broj knjige: ");
				String brojKnjige = sc.nextLine();
				pozicija = idKnjiga.indexOf(brojKnjige);
				//ako postoji sa tim brojem knjige, ispisemo podatke
				if(pozicija != -1 ) {
					System.out.printf("%10s %10s %10s \n", idKnjiga.get(pozicija), 
					naslovi.get(pozicija), autori.get(pozicija));
			}
			else
				System.out.println("Knjiga sa unetim brojem knjige ne postoji.");
			break;
			
			case "7": //Prikaz svih knjiga
				for (int i = 0; i < idKnjiga.size(); i++) {
					//10 mesta za imena i 5 mesta prosek odvojimo da bi podaci bili poravnati
					System.out.printf("%10s %10s %10s \n", idKnjiga.get(i), 
					naslovi.get(i), autori.get(i));
				}
			break;
			
			case "8":
				//brisanje knjige
				System.out.println("Unesite broj knjige: ");
				brojKnjige = sc.nextLine();
				
				//trazimo poziciju clana u listi
				pozicija = idKnjiga.indexOf(brojKnjige);
				//ako postoji osoba sa tim brojem clana
				if(pozicija != -1) {
					idKnjiga.remove(pozicija);
					naslovi.remove(pozicija);
					autori.remove(pozicija);
					System.out.println("Knjiga je uspesno obrisana.");
				}
				else
					System.out.println("Knjiga sa unetim brojem knjige ne postoji.");
				
			break;
			
			case "9":
				//izmena knjige
				System.out.print("Unesite broj knjige: ");
				brojKnjige = sc.nextLine();
				
				//trazimo poziciju knjige u listi
				pozicija = idKnjiga.indexOf(brojKnjige);
				//ako postoji knjiga sa tim brojem knjige
				//onda unosimo novi naslov i autora
				if(pozicija != -1) {
					System.out.print("Unesite novi naslov: ");
					String noviNaslov = sc.nextLine();
					System.out.print("Unesite novi naziv autora: ");
					String noviAutor = sc.nextLine();
					
					//azuriramo podatke na odgovovarajucoj poziciji u nizu
					naslovi.set(pozicija, noviNaslov);
					autori.set(pozicija, noviAutor);
					
					System.out.println("Knjiga je uspesno promenjena.");
				}
				else
					System.out.println("Knjiga sa unesenim brojem knjige ne postoji.");
				
			break;
			
			case "10":
				
			break;
			
			case "11":
				
			break;
			
			//----------------------KRAJ------------------------
			
			//AKO TREBA unos novog clana
			
			//case "1.1": //unos novog clana
			//prvo trazimo od korisnika da unese podatke
				//	System.out.println("Unesite clanski broj: ");
			 	//String brojClana = sc.nextLine();
				//	System.out.println("Unesite ime studenta: ");
				//	String ime = sc.nextLine();
				//	System.out.println("Unesite prezime studenta: ");
				//	String prezime = sc.nextLine();
			
				//unete podetke dodajemo u odgovarajuce liste (na kraj liste)
				//	idClanova.add(brojClana);
				//	imena.add(ime);
				//	prezimena.add(prezime);
			
				//	System.out.println("Clan je uspesno upisan.");
				//	break;
			
			
			
			} 
		
		} while (!opcija.equals("x"));
		
		sc.close();
		

	}

}
