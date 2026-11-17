# Sistema de Ventas e Inventario – Game Store (Unidad 3 Version ACTUALIZADA)
* **Materia:** Lenguajes de Interfaz
* **Horario:** 10:00-11:00
* **Alumno:** Yahir Luna Beltrán
* **Docente:** Dr. José Luis Medina Jiménez


- **Unidad 2:** versión original (`GameStore_U2.asm`).
- **Unidad 3:** versión modularizada con procedimientos, macros y `USES` (`GameStore_U3.asm`). Conserva las funciones, validaciones y la regla de negocio de la Unidad 2.

## Funciones

- Registrar productos, mostrar el inventario y buscar por código (`ABC-123`).
- Recibir mercancía (máximo 100 unidades por producto).
- Vender, con validación de existencias, cálculo del importe en MXN e ingresos de la sesión.
- Resumen: unidades disponibles, valor del inventario e ingresos.
- Guardar y cargar el catálogo en `inventario.txt`, con validación antes de reemplazar el catálogo y aviso de cambios sin guardar al salir.
- Regla del negocio: descuento por cantidad (10 % desde 3 unidades del mismo juego).

## Archivos

| Archivo | Descripción |
|---|---|
| `GameStore_U3.asm` | Código fuente de la versión de la Unidad 3 |
| `GameStore_U2.asm` | Código fuente de la versión de la Unidad 2 (para comparar) |
| `inventario.txt` | Archivo de inventario de prueba con 4 juegos |
| `inventario_invalido.txt` | Archivo dañado para probar el rechazo (renómbralo a `inventario.txt` para usarlo) |

## Requisitos

- Windows con **Visual Studio** (con las herramientas de C++ / MASM).
- Biblioteca **Irvine32** instalada (por defecto en `C:\Irvine`).
- Plataforma **x86 (Win32)**.

## Compilación y ejecución (Visual Studio)

1. Crea un proyecto vacío de C++ (o usa la plantilla de Irvine32 de tu curso).
2. Activa MASM: clic derecho en el proyecto, *Build Dependencies*, *Build Customizations*, marca **masm**.
3. Agrega `GameStore_U3.asm` al proyecto (*Add > Existing Item*) y verifica que su tipo de elemento sea **Microsoft Macro Assembler**.
4. Configura la plataforma en **x86**.
5. En *Project Properties*:
   - *Microsoft Macro Assembler > General > Include Paths*: `C:\Irvine`
   - *Linker > General > Additional Library Directories*: `C:\Irvine`
   - *Linker > Input > Additional Dependencies*: `Irvine32.lib;kernel32.lib;user32.lib`
   - *Linker > System > SubSystem*: **Console**
6. Compila con **Build > Build Solution** y ejecuta con **Ctrl+F5**.
7. Copia `inventario.txt` a la carpeta de trabajo: la del proyecto si ejecutas desde Visual Studio, o la del `.exe` si lo abres directamente.


## Formato de `inventario.txt`

```
GSV1
ZLD-001|Zelda TOTK|129950|15
MAR-002|Mario Kart 8 Deluxe|109900|10
```

La primera línea es la marca `GSV1`. Cada línea siguiente es `CODIGO|NOMBRE|CENTAVOS|EXISTENCIA`. Los precios se guardan en centavos enteros.

## Menú

1. Registrar y consultar (registrar, mostrar inventario, buscar)
2. Recibir mercancía
3. Vender
4. Resumen
5. Regla del negocio (cotizador de descuento por cantidad)
6. Guardar y cargar
0. Salir
