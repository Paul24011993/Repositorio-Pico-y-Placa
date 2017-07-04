package predictor_pico_y_placa;

import java.io.BufferedReader;
import java.io.IOException;
import java.io.InputStreamReader;
import java.text.DateFormat;
import java.text.ParseException;
import java.text.SimpleDateFormat;
import java.util.Calendar;
import java.util.Date;
import java.util.GregorianCalendar;
import java.util.Scanner;

public class Predictor_Pico_y_Placa {

    public static void main(String[] args) throws ParseException, IOException {
        Scanner sc = new Scanner(System.in);
// Encabezado
        for (int i = 1; i <= 50; i++) {
            System.out.print("*");
        }
        System.out.print("\n");
        System.out.println("PREDICTOR DE PICO Y PLACA");
        System.out.println("ELABORADO POR : PAUL SANDOVAL");

        for (int j = 1; j <= 50; j++) {
            System.out.print("*");
        }
        System.out.println("\n");
//********************************

        //Inicio del programa
        String[] dioa = {"LUNES", "MARTES", "MIERCOLES", "JUEVES", "VIERNES", "SABADO", "DOMINGO"};
        String[] PicoPlaca = {"1-2", "3-4", "5-6", "7-8", "9-0", "NO APLICA EN PIO Y PLACA", "NO APLICA EN PIO Y PLACA"};
        int numero;
        
        System.out.println("Ingrese el número de placa de su vehículo");
        String nombres = sc.nextLine();
        String nomMay = nombres.toUpperCase();

        char ultimop = nombres.charAt(nombres.length() - 1);
        System.out.println("SU PLACA ES: " + nomMay + " TERMINA EN: " + ultimop);

//Dia de la semana a partir de fecha en Java
        if (ultimop > 0 && ultimop < 366) {
            if (ultimop < 5) {
                
                System.out.println(dioa[ultimop - 1] + " : " + PicoPlaca[ultimop - 1 ]);
                
            } else if (ultimop > 7) {
                System.out.println(dioa[6] + " : " + PicoPlaca[6]);
            } else {
                System.out.println(dioa[(ultimop - 2) % 7] + " : " + PicoPlaca[(ultimop - 2) % 7]);

            }
        } else {
            System.out.println("Ingrese un numero de placa válido");
        }
//Ingreso de la fecha..

        for (int j = 1; j <= 50; j++) {
            System.out.print("*");
        }
        System.out.println("\n");


//      INGRESO DE LA FECHA
        System.out.print("Ingrese una fecha \n ");

        // TODO code application logic here
        InputStreamReader isr = new InputStreamReader(System.in);
        BufferedReader br = new BufferedReader(isr);
        int dia, mes, año, año1, semana, x, y, z, total, u, j;
        System.out.print("  1. Ingrese el día (en número): ");
        dia = Integer.parseInt(br.readLine());
        System.out.print("\n");

        System.out.print("  2. Ingrese el mes (en número): ");
        mes = Integer.parseInt(br.readLine());
        System.out.print("\n");

        System.out.print("  3. Ingrese el año: ");
        año = Integer.parseInt(br.readLine());
        System.out.print("\n");

        semana = 0;
        {
            if ((año / 100) % 4 == 1) {
                x = semana + 5;
            } else if ((año / 100) % 4 == 2) {
                x = semana + 3;
            } else if ((año / 100) % 4 == 3) {
                x = semana + 1;
            } else if ((año / 100) % 4 == 0) {
                x = semana + 0;
            } else {
                x = 0;
            }
            j = 0;
            z = 0;
            año1 = (año % 100) + ((año % 100) / 4);
            y = 0;
            if (año % 400 == 0 && año % 100 != 0 && año % 4 == 0) {
                if (mes == 1 || mes == 2) {
                    j = z - 1;
                } else {
                    j = z + 0;
                }
            }
            if (mes == 8) {
                u = y + 1;
            } else if (mes == 2 || mes == 3 || mes == 11) {
                u = y + 2;
            } else if (mes == 6) {
                u = y + 3;
            } else if (mes == 9 || mes == 12) {
                u = y + 4;
            } else if (mes == 4 || mes == 7) {
                u = y + 5;
            } else if (mes == 1 || mes == 10) {
                u = y + 6;
            } else {
                u = y + 0;
            }
            total = x + y + z + año1 + u + dia + j;
            if (total % 7 == 1) {
                System.out.print("Lunes ");
            } else if (total % 7 == 2) {
                System.out.print("Martes ");
            } else if (total % 7 == 3) {
                System.out.print("Miercoles ");
            } else if (total % 7 == 4) {
                System.out.print("Jueves ");
            } else if (total % 7 == 5) {
                System.out.print("Viernes ");
            } else if (total % 7 == 6) {
                System.out.print("Sabado ");
            } else {
                System.out.print("Domingo ");
            }
            System.out.print("\n");
        }

        
        Date fechaActual = new Date();
        
        System.out.print("Ingrese una hora del día ");
        System.out.print("\n ");
        System.out.print("formato sugerido:(hh:mm)\n");
        
        
                Calendar calendario = Calendar.getInstance();

//Calendar calendario = new GregorianCalendar();
        int hora, minutos, segundos;
        
                int hor, min, seg;
        System.out.print("  1. Ingrese la hora (en número): ");
        hor = Integer.parseInt(br.readLine());

        System.out.print("  2. Ingrese los minutos (en número): ");
        min = Integer.parseInt(br.readLine());

        System.out.print("  3. Ingrese los segundos (en número): ");
        seg = Integer.parseInt(br.readLine());
        
        if(hor > 7 & hor <9 || hor > 16 & hor <19){
            System.out.println("el vehiculo no puede salir");
        } else{
            System.out.println("el vehiculo puede salir !!");
        }
        System.out.println(hor + ":" + min + ":" + seg);

    }

}
