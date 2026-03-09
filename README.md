## Análisis de Violaciones SOLID
| Principio | Método/Sección afectada | Descripción de la violación |
|-----------|-------------------------|-----------------------------|
| SRP       | calculateTotal + applyDiscount + saveOrder + sendEmail + printReport | La clase OrderProcessor concentra responsabilidades de negocio, persistencia, comunicación y presentación. Esto infringe el principio de responsabilidad única, ya que cualquier cambio en impuestos, descuentos, almacenamiento, notificaciones o reportes obliga a modificar la misma clase. |
| OCP | applyDiscount (if/else sobre customerType) |La lógica de descuentos está codificada mediante decisiones condicionales. Cada nueva categoría de cliente o política promocional requiere alterar el código existente, lo cual impide extender el sistema sin modificarlo. |
| DIP | Toda la clase (dependencias internas sin abstracciones) | OrderProcessor depende de implementaciones concretas en lugar de abstracciones, particularmente ArrayList y System.out.println. Esto incrementa el acoplamiento y dificulta pruebas unitarias, mantenimiento y sustitución de componentes. |


## Instructions to execute the project

I used this command cuz i´m poor (i don't have mac professor) --> mvn --% exec:java -Dexec.mainClass=com.patrones.u1.Main

mvn compile && mvn exec:java -Dexec.mainClass="com.patrones.u1.Main"

The first one worked for me. I'm not 100% sure about the second one, but I think it's the one you gave us in class.

## RESULT

![This is my work professor](image.png)
