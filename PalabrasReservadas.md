```java
    ```java
    package ProyectoFinal;
    
    import biblioteca.LE;
    import javax.swing.JOptionPane;
    
    public class Hamburguesas {
    
        // Atributos
        String nombre[];
        String codigo[];
        String tipo[];
        double precio[];
        int unidades[];
        int numHam;
    
        //Constructor
        public Hamburguesas() {
            numHam = 0;
            nombre = new String[10000];
            codigo = new String[10000];
            tipo = new String[10000];
            precio = new double[10000];
            unidades = new int[10000];
        }
    
        //Metodos
        void menus() {
            String menu;
            String menu1 = "----------------MADAMS BURGUER----------------\n"
                    + "[1] Ingresar hamburguesas\n"
                    + "[9] Finalizar\n"
                    + "Ingrese una opción:";
            String menu2 = "----------------MADAMS BURGUER----------------\n"
                    + "[1] Ingresar hamburguesas\n"
                    + "[2] Mostrar codigos\n"
                    + "[3] Mostrar codigos-precio\n"
                    + "[4] Buscar hamburguesas\n"
                    + "[5] Ordenar hamburguesas\n"
                    + "[9] Finalizar\n"
                    + "Ingrese una opción:";
            menu = menu1;
            int opc = 0;
            boolean sw = false;
            do {
                opc = LE.leerInt(menu);
                switch (opc) {
                    case 1: // Ingresar
                        ingresarHam();
                        sw = true;
                        menu = menu2;
                        break;
                    case 2: // Mostrar Codigos
                        if (sw) {
                            mostrarCodigos();
                        } else {
                            LE.mostrarError("Ingrese una opcion valida");
                        }
                        break;
                    case 3: // Mostrar codigos-precios
                        if (sw) {
                            codigosPrecio();
                        } else {
                            LE.mostrarError("Ingrese una opcion valida");
                        }
                        break;
                    case 4: // Buscar hamburguesas
                        if (sw) {
                            buscarHamburguesas();
                        } else {
                            LE.mostrarError("Ingrese una opcion valida");
                        }
                        break;
                    case 5: // Ordenar hamburguesas
                        if (sw) {
                            ordenar();
                            LE.mostrarInformacion("Hamburguesas ordenadas correctamente.");
                        } else {
                            LE.mostrarError("Ingrese una opcion valida");
                        }
                        break;
                    case 9: // Finalizar
                        LE.mostrarInformacion("Programa Finalizado");
                        break;
                    default:
                        LE.mostrarError("Ingrese una opcion valida");
                        break;
                }
            } while (opc != 9);
        }
    
        public void ingresarHam() {
            int rpta = 0;
            String buscar;
            boolean tip;
            do {
                nombre[numHam] = LE.leerString("Ingrese el nombre de la hamburguesa: ");
                buscar = codigo[numHam] = nombre[numHam].substring(0, 2) + "-" + nombre[numHam];
                boolean encontrado = evitarCod(buscar);
                if (!encontrado) {
                    codigo[numHam] = buscar;
                    do {
                        tip = tipoHam();
                    } while (tip);
                    do {
                        precio[numHam] = LE.leerDouble("Ingrese el precio de la hamburguesa [ " + nombre[numHam] + " ]:");
                        if (precio[numHam] <= 0 || precio[numHam] > 20) {
                            LE.mostrarError("Precio no valido, precio de S/0-S/20");
                        }
                    } while (precio[numHam] <= 0 || precio[numHam] > 20);
                    unidades[numHam] = LE.leerInt("Ingrese el stock de la hamburguesa [ " + nombre[numHam] + " ]:");
                    numHam++;
                    rpta = LE.mostrarPreguntaOpcion2("¿Deseas continuar?");
                } else {
                    LE.mostrarInformacion("Esta hamburguesa ya ha sido registrada");
                }
    
            } while (rpta == 0);
        }
    
        public boolean evitarCod(String buscar) {
            boolean encontrado = false;
            for (int i = 0; i < numHam; i++) {
                if (codigo[i].equalsIgnoreCase(buscar)) {
                    encontrado = true;
                    return encontrado;
                }
            }
            return encontrado;
        }
    
        public boolean tipoHam() {
            boolean tip = true;
            tipo[numHam] = LE.leerString("Ingrese el tipo de hambuguesa: " + "\nTIPOS: A, B, C y D");
            switch (tipo[numHam]) {
                case "A":
                    tip = false;
                    break;
                case "B":
                    tip = false;
                    break;
                case "C":
                    tip = false;
                    break;
                case "D":
                    tip = false;
                    break;
                default:
                    LE.mostrarError("Ingrese un tipo valido");
                    break;
            }
            return tip;
        }
    
        public void mostrarCodigos() {
            String datos = "---------------Codigos Hamburguesas---------------\n";
            for (int i = 0; i < numHam; i++) {
                datos = datos + "Codigo [" + (i + 1) + "] : " + codigo[i] + "\n";
            }
            datos = datos + "-------------------------------------------------------";
            LE.mostrarInformacion(datos);
        }
    
        public void codigosPrecio() {
            String datos = "---------------Codigos Hamburguesas---------------\n";
            for (int i = 0; i < numHam; i++) {
                datos = datos + "Codigo [" + (i + 1) + "] : " + codigo[i] + "\n";
                datos = datos + "Precio -------- : S/" + precio[i] + "\n";
                datos = datos + "-------------------------------------------------------\n";
            }
            LE.mostrarInformacion(datos);
        }
    
        public void buscarHamburguesas() {
            String botones[] = {"Codigos", "Nombre", "Tipo"};
            int resul = JOptionPane.showOptionDialog(null, "Buscar por: ", "BUSQUEDA DE HAMBURGUESAS", 
            JOptionPane.DEFAULT_OPTION, JOptionPane.INFORMATION_MESSAGE, null, botones, botones[0]);
            switch (resul) {
                case 0:
                    int codEncdo;
                    String busCod = LE.leerString("Ingrese el codigo de la hamburguesa: ");
                    codEncdo = busquedaCoNom(codigo, busCod);
                    if (codEncdo == -1) {
                        LE.mostrarInformacion("El codigo no ha sido encontrado.");
                    } else {
                        LE.mostrarInformacion("El codigo: " + busCod + " encontrado con exito.\n"
                                + "El nombre: " + nombre[codEncdo] + "\n"
                                + "El tipo: " + tipo[codEncdo] + "\n"
                                + "El precio: " + precio[codEncdo] + "\n"
                                + "Unidades disponibles: " + unidades[codEncdo] + "\n");
                    }
                    break;
                case 1:
                    String codNom = LE.leerString("Ingrese el nombre de la hamburguesa: ");
                    codEncdo = busquedaCoNom(nombre, codNom);
                    if (codEncdo == -1) {
                        LE.mostrarInformacion("El nombre no ha sido encontrado.");
                    } else {
                        LE.mostrarInformacion("El nombre: " + codNom + " encontrado con exito.\n"
                                + "El codigo: " + codigo[codEncdo] + "\n"
                                + "El tipo: " + tipo[codEncdo] + "\n"
                                + "El precio: " + precio[codEncdo] + "\n"
                                + "Unidades disponibles: " + unidades[codEncdo] + "\n");
                    }
                    break;
                case 2:
                    String tpos = LE.leerString("Ingrese el tipo de hamburguesas: ");
                    busquedaTipo(tpos);
                    break;
            }
        }
    
        public int busquedaCoNom(String[] arreglo, String cod) {
            for (int i = 0; i < numHam; i++) {
                if (arreglo[i].equalsIgnoreCase(cod)) {
                    return i;
                }
            }
            return -1;
        }
    	public void busquedaTipo(String tip) {
            String tiposInfo = "-------------------Tipos Hamburguesas-------------------\n";
            String aux = tiposInfo;
            for (int i = 0; i < numHam; i++) {
                if (tipo[i].equalsIgnoreCase(tip)) {
                    tiposInfo = tiposInfo + "El tipo: " + tipo[i] + "\n";
                    tiposInfo = tiposInfo + "El codigo: " + codigo[i] + "\n";
                    tiposInfo = tiposInfo + "El nombre: " + nombre[i] + "\n";
                    tiposInfo = tiposInfo + "El precio: " + precio[i] + "\n";
                    tiposInfo = tiposInfo + "Unidades disponibles: " + unidades[i] + "\n";
                    tiposInfo = tiposInfo + "-----------------------------------------------------------------\n";
                }
            }
            if (tiposInfo.equalsIgnoreCase(aux)) {
                LE.mostrarInformacion("No hay hamburguesas de ese tipo disponible");
            } else {
                LE.mostrarInformacion(tiposInfo);
            }
    
        }
    
        public void ordenar() {
            String nom;
            String codig;
            String tip;
            double pre;
            int unid;
            for (int i = 0; i < numHam - 1; i++) {
                for (int j = 0 + i; j < numHam; j++) {
                    if (nombre[i].compareToIgnoreCase(nombre[j]) > 0) {
                        nom = nombre[j];
                        nombre[j] = nombre[i];
                        nombre[i] = nom;
    
                        codig = codigo[j];
                        codigo[j] = codigo[i];
                        codigo[i] = codig;
    
                        tip = tipo[j];
                        tipo[j] = tipo[i];
                        tipo[i] = tip;
    
                        pre = precio[j];
                        precio[j] = precio[i];
                        precio[i] = pre;
    
                        unid = unidades[j];
                        unidades[j] = unidades[i];
                        unidades[i] = unid;
                    }
                }
            }
        }
    }
    ```
```
