## Exceptions

En Java cuando se produce un error en un metodo se lanza un objeto Throwable.
Cualquier metodo que haya llamado al metodo puede capturar la excepcion y tomar las medidas que estime oportunas,
tras capturar la excepcion, el control no vuelve al metodo en el que se produjo la excepcion, si no que la ejecucion
del programa continua en el punto donde se haya capturado la excepcion.

#### Jerarquia

Tenemos la clase Throwable y de ella heredan Exception y Error, pero de la clase Exeption heredan dos clases mas que son
la clase RuntimeException y IOException
                
Throwable <--- Exception
Throwable <--- Error

Exception <--- RuntimeException
Exception <--- IOException

##### Throwable
Throwable contiene una instantánea de la pila de ejecución de su hilo en el momento de su creación. También puede contener 
una string de mensaje que brinda más información sobre el error. También puede evitar que se propaguen otros objetos arrojadizos.

Si un usuario quiere crear su propio elemento arrojadizo personalizado, puede extender la clase Throwable.

```

// Como podemos ver aqui vamos a extender de Throwable
public Class MyThrowable extends Throwable{
 // aqui es donde vamos a poner nuestra propia excepcion
}

```

Contamos con la [API](https://docs.oracle.com/javase/8/docs/api/java/lang/Throwable.html) de java (Oracle) para ver mas de sus constructores 

Como breve explicacion pondremos los constructores y un par de metodos

Contrusctores
---

- Throwable(): Es un constructor no parametrizado que construye un nuevo Throwable con null como su mensaje detallado.
- Throwable (mensaje de string): Es un constructor parametrizado que construye un nuevo Throwable con el mensaje detallado específico.
- Throwable (mensaje de string, causa Throwable): es un constructor parametrizado que construye un nuevo Throwable con el mensaje detallado específico y una causa.
- Throwable (causa Throwable): Es un constructor parametrizado que construye un nuevo Throwable con la causa específica y un mensaje detallado de la causa convirtiendo el caso al String usando el método toString().

Metodos
---
1. addSuppressed (excepción Throwable) : este método agrega la excepción especificada a las excepciones que fueron suprimidas para entregar esta excepción.
Syntax:
Public final void addSuppressed(Throwable exception)
Returns: This method does not returns anything.

2. fillInStackTrace() : completa el seguimiento de la pila de ejecución. Este método registra información sobre el estado actual de los marcos de pila para el subproceso actual dentro del objeto Throwable actual.
Syntax:
public Throwable fillInStackTrace()
Returns: a reference to the current Throwable instance.

3. getLocalizedMessage() : este método crea una descripción localizada del Throwable actual.
Syntax:
public String getLocalizedMessage()
Returns: The localized description of current Throwable

4. getMessage() : Devuelve la string del mensaje de detalle del actual arrojable.
Syntax:
public String getMessage()
Returns: the detailed message string of current Throwable instance( may also return null)