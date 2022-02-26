# Programacion
#alumno
package edu.ucjc.proyecto.claseviernes25;
//nombre, apellidos, dni y direccion
//calle, numero, localidad, provincia y código postal
public class Alumno {
	private String nombre;
	private String apellidos;
	private String dni;
	private Direccion direccion;
	
	
	
	
	

	public Alumno(String nombre, String apellidos, String dni) {
		super();
		this.nombre = nombre;
		this.apellidos = apellidos;
		this.dni = dni;
	}
	public Alumno(String nombre, String apellidos, String dni, Direccion direccion) {
		
		this.nombre = nombre;
		this.apellidos = apellidos;
		this.dni = dni;
		this.direccion = direccion;
	
	}
	public String getNombre() {
		return this.nombre;
	
	}
	public String getApellidos() {
		return this.apellidos;
	}
	public String getDni() {
		return this.dni;
	}
	public Direccion getDireccion() {
		return this.direccion;
	}
	public void setNombre(String nombre) {
		this.nombre=nombre;
	}
	public void setApellidos(String apellidos) {
		this.apellidos=apellidos;
	}
	public void setDni(String dni) {
		this.dni=dni;
	
	}
	public void setDireccion(Direccion direccion) {
		this.direccion=direccion;
	}

}







#direccion
package edu.ucjc.proyecto.claseviernes25;
//Atributos
public class Direccion {
	private String calle;
	private int numero;
	private String localidad;
	private String provincia;
	private String cp;
//Constructor
	public Direccion(String calle, int numero,String localidad,String provincia, String cp) {
		this.calle=calle;
		this.numero=numero;
		this.localidad=localidad;
		this.provincia=provincia;
		this.cp=cp;
	}
//Acceso a variables
	
	public String getCalle() {
		return this.calle;
	}
	public void setCalle(String calle){
		this.calle=calle;
	}
	public int getNumero() {
		return this.numero;
	}
	public void setNumero(int numero) {
		this.numero=numero;
	}
	public String getLocalidad() {
		return this.localidad;
	}
	public void setLocalidad(String localidad) {
		this.localidad=localidad;
	}
	public String getProvincia() {
		return this.provincia;
	}
	public void setProvincia(String provincia) {
		this.provincia=provincia;
	}
	public String getCp() {
		return this.cp;
	}
	public void setCp(String cp) {
		this.cp=cp;
	}
	
	
	

}



#colegio
package edu.ucjc.proyecto.claseviernes25;
//nombre y aula
public class Colegio {
	private String nombre;
	private Alumno[] aula;
	
	
	
	
	public Colegio(String nombre) {
		
		this.nombre = nombre;
	}
	public Colegio(String nombre, Alumno[] aula) {
		
		this.nombre = nombre;
		this.aula = aula;
	}
	public void setAula(Alumno[] aula) {
		this.aula = aula;
	}
	public String getNombre() {
		return nombre;
	}
	public void setNombre(String nombre) {
		this.nombre = nombre;
	}
	
	
	public Alumno[] getAula() {
		return aula;
	}
	
	
	
}







#main
package edu.ucjc.proyecto.claseviernes25;

import java.util.Scanner;

public class Main {

	public static void main(String[] args) {
		Scanner scan=new Scanner(System.in);
		System.out.println("Introduce el nombre del colegio");
		String nombreColegio=scan.nextLine();
		
		System.out.println("¿Cuántos alumnos tiene el aula?");
		int numeroAlumnos=scan.nextInt();
		
		int opcion=0;
		do {
			System.out.println("1.Rellenar alumno");
			System.out.println("2.Mostrar alumnos");
			System.out.println("3.Buscar alumno");
			System.out.println("4.Borrar alumno");
			System.out.println("5.Salir");
			System.out.println("Seleccione una opcion:");
			
			opcion=scan.nextInt();
			
			switch(opcion) {
			case 1:
				rellenaColegio(nombreColegio,numeroAlumnos);
				break;
			case 2:
				mostrarAlumnos();
				break;
			case 3:
				buscarAlumno();
				break;
			case 4:
				borrarAlumno();
				break;
			case 5:
				System.out.println("adios");
				break;
			default:
				System.out.println("Introduzca un valor válido.");
			}
		}while(opcion!=5);
		
		
	}
	
	private static void rellenaColegio(String nombreColegio,int numeroAlumnos) {
		System.out.println("invocando metodo rellena colegio");
		
		Colegio colegio=new Colegio(nombreColegio);
		Alumno[] alumnos=new Alumno[numeroAlumnos];
		for(int i =0;i<numeroAlumnos;i++) {
			System.out.println("Introduce el nombre del alumno "+(i+1));
			Scanner scan=new Scanner(System.in);
			
			String nombre=scan.nextLine();
			
			System.out.println("Introduce los apellidos del alumno:"+(i+1));
			String apellidos=scan.nextLine();
			
			System.out.println("Introduce el dni del alumno"+(i+1));
			String dni=scan.nextLine();
			Alumno alumnos1=new Alumno(nombre,apellidos,dni);
			alumnos[i]=alumnos1;
			
		}
		colegio.setAula(alumnos); 
		
		
		
		
	}
	private static void mostrarAlumnos() {
		System.out.println("invocando metodo mostrar alumnos");
	}
	private static void buscarAlumno() {
		System.out.println("invocando metodo buscar alumno");
	}
	private static void borrarAlumno() {
		System.out.println("invocando metodo borrar alumno");
	}
}
