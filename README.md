<div align="center">

# 🌸🎀 Práctica: Pruebas Unitarias con JUnit 5 en VS Code 🎀🌸

![Java](https://img.shields.io/badge/Java-ff69b4?style=for-the-badge&logo=java&logoColor=white)
![VS Code](https://img.shields.io/badge/VS_Code-db7093?style=for-the-badge&logo=visual%20studio%20code&logoColor=white)
![JUnit5](https://img.shields.io/badge/JUnit_5-ffb6c1?style=for-the-badge&logo=junit5&logoColor=white)
![Maven](https://img.shields.io/badge/Maven-ff1493?style=for-the-badge&logo=apachemaven&logoColor=white)

💖 **¡Bienvenidos a mi repositorio!** 💖
Aquí exploramos la magia de los tests unitarios con un toque súper colorido. 🦄✨

</div>

---

## 🎯 🩷 Objetivo del Proyecto 🩷

El propósito principal de esta actividad es aprender a **configurar un entorno de desarrollo para Java fuera de IntelliJ**, utilizando **Visual Studio Code** y **Maven** para la gestión de nuestras dependencias y la ejecución de *tests unitarios* con JUnit 5. 🚀🌈

🔗 **Enlace del Repositorio Git:** [Tarea_Evaluacion_Modulo_15](https://github.com/mgg06/Tarea_Evaluacion_Modulo_15.git)

---

## 🛠️ 🌺 1. Configuración del Proyecto 🌺

Para no tener que crear las carpetas a mano (¡qué aburrido! 🥱), hemos utilizado el asistente mágico de VS Code siguiendo estos pasitos:

1. 🌸 Abrimos VS Code y pulsamos `F1` (o `Ctrl+Shift+P`).
2. 🌸 Buscamos la opción: **`Java: Create Java Project`**.
3. 🌸 Elegimos **Maven** y luego la varita mágica de **`maven-archetype-quickstart`**.
4. 🌸 En la versión, siempre vamos a por la última disponible. ✨
5. 🌸 **GroupId**: `com.entornos` | **ArtifactId**: `test-vscode`.
6. 🌸 Tras darle a *Enter* y elegir dónde guardarlo, la terminal hace todo el trabajo. ¡Y listo! 🎉

---

## 📦 🌷 2. El archivo de configuración (`pom.xml`) 🌷

Para que nuestro querido VS Code se haga muy amigo de **JUnit 5**, tuvimos que hacerle unos ajustes al archivo `pom.xml`. Nos aseguramos de incluir la siguiente dependencia súper importante en el apartado `<dependencies>`:

```xml
<dependency>
    <groupId>org.junit.jupiter</groupId>
    <artifactId>junit-jupiter-api</artifactId>
    <version>5.10.0</version>
    <scope>test</scope>
</dependency>
```
*(¡Adiós JUnit 4, hola JUnit 5! 👋💖)*

---

## 💻 🍧 3. Código a probar (`CalculadoraRiesgo.java`) 🍧

Dentro de la ruta mágica `src/main/java/com/entornos`, creamos nuestra lógica de seguros. ¡Es pequeñita pero muy poderosa! 💪✨

```java
package com.entornos;

public class CalculadoraRiesgo {
    public String evaluarEdad(int edad) {
        if (edad < 0 || edad > 120) return "Error";
        if (edad < 18) return "Joven";
        if (edad <= 65) return "Adulto";
        return "Senior";
    }
}
```

---

## 🧪 🎀 4. Creación de los Tests (`CalculadoraRiesgoTest.java`) 🎀

¡Aquí viene la mejor parte! 🥳 En `src/test/java/com/entornos` pusimos a prueba nuestro código. Además de los tests básicos, resolvimos el "TODO" añadiendo los casos para **"Senior"** y para el límite súper estricto de **18 años**. 📏

```java
package com.entornos;

import static org.junit.jupiter.api.Assertions.assertEquals;
import org.junit.jupiter.api.Test;

class CalculadoraRiesgoTest {

    CalculadoraRiesgo calc = new CalculadoraRiesgo();

    @Test
    void testEdadNegativa() {
        assertEquals("Error", calc.evaluarEdad(-5)); // 🚫 Caso de error
    }

    @Test
    void testAdulto() {
        assertEquals("Adulto", calc.evaluarEdad(25)); // 👩 Caso normal adulto
    }

    @Test
    void testSenior() {
        assertEquals("Senior", calc.evaluarEdad(70)); // 👵 Caso añadido: Senior
    }

    @Test
    void testJoven() {
        assertEquals("Joven", calc.evaluarEdad(18)); // 🎂 Caso añadido: Límite 18
    }
}
```

---

## 🔎 💖 5. Cómo manejar los tests en VS Code (¡Lo que se evalúa!) 💖

Para triunfar en esta práctica, aprendimos a dominar estas tres herramientas maravillosas de VS Code:

### 🧪 El Matraz (Testing Explorer)
En la barrita lateral izquierda hay un icono de un **matraz de laboratorio**. Al hacer clic ahí, podemos ver todos nuestros tests y ejecutarlos todos de golpe. ¡Es súper satisfactorio ver cómo todo funciona a la perfección! 💚✅

### 🔍 CodeLens
Encima de cada `@Test` en nuestro código, VS Code nos pone un texto pequeñito y mágico que dice `Run | Debug`. Si solo queremos probar un test en concreto sin molestar a los demás, ¡pulsamos `Run` ahí mismo! 🏃‍♀️💨

### 🐞 Depuración (Debugging)
Si algo sale mal (¡que no cunda el pánico! 😱), ponemos un puntito rojo (*breakpoint*) a la izquierda del número de línea en nuestra `CalculadoraRiesgo`. Luego, usamos el botón `Debug` desde el test y VS Code nos permite ver paso a paso cómo viaja la información por nuestro código. ¡Como usar una lupa para encontrar el bug! 🔎✨

---

### 📸 🖼️ Captura de Pantalla Requerida 🖼️

*(A continuación se muestra la evidencia de la ejecución exitosa de los tests 💖)*

<img width="1475" height="1227" alt="image" src="https://github.com/user-attachments/assets/f4dca6db-76e0-4584-962a-efd96f85417e" />
<img width="602" height="392" alt="image" src="https://github.com/user-attachments/assets/eafef870-0b19-477a-bbfa-690ca4f8f77a" />
<img width="126" height="119" alt="image" src="https://github.com/user-attachments/assets/2cc7e526-8c32-49de-ab04-f9a0be0a154d" />

---
<div align="center">
Hecho con mucho 💖, por Marta González González y con código Java. ☕
</div>
