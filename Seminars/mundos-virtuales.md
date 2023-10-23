# Seminario: Mundos virtuales. Introducción a la programación de gráficos 3D.

### 1.Qué funciones se pueden usar en los scripts de Unity para llevar a cabo traslaciones, rotaciones y escalados

las funciones para realizar las operaciones del enunciado en Unity son:

- Traslaciones: 
```csharp
transform.Translate(Vector3);
```
- Rotaciones:
```csharp
transform.Rotate(Vector3);
```
- Escalados:
```csharp
transform.localScale = new Vector3(x, y, z);
```

### 2.Como trasladarías la cámara 2 metros en cada uno de los ejes y luego la rotas 30º alrededor del eje Y? Rota la cámara alrededor del eje Y 30ª y desplázala 2 metros en cada uno de los ejes. ¿Obtendrías el mismo resultado en ambos casos? Justifica el resultado

Para trasladar la cámara 2 metros en cada eje:

```csharp
camera.transform.Translate(new Vector3(2, 2, 2));
```
Y para rotar la cámara 30º alrededor del eje Y:

```csharp
Copy code
camera.transform.Rotate(new Vector3(0, 30, 0));
```

Si rotas primero y luego trasladas, la dirección de la traslación estará afectada por la rotación previa. En el caso contrario, solo afectará la posición final, no la orientación. Por lo tanto, no obtendrías el mismo resultado en ambos casos

### 3.Sitúa la esfera de radio 1 en el campo de visión de la cámara y configura un volumen de vista que la recorte parcialmente

Simplemente traslada la esfera a una posición donde la cámara la pueda ver y ajusta el volumen de vista de la cámara (frustum) para que solo la recorte parcialmente

### 4.Sitúa la esfera de radio 1 en el campo de visión de la cámara y configura el volumen de vista para que la deje fuera de la vista

### 5.Como puedes aumentar el ángulo de la cámara. Qué efecto tiene disminuir el ángulo de la cámara

### 6.Es correcta la siguiente afirmación: _Para realizar la proyección al espacio 2D, en el inspector de la cámara, cambiaremos el valor de projection, asignándole el valor de orthographic_

### 7.Especifica las rotaciones que se han indicado en los ejercicios previos con la utilidad quaternion.

### 8.¿Como puedes averiguar la matriz de proyección en perspectiva que se ha usado para proyectar la escena al último frame renderizado?

### 9.¿Como puedes averiguar la matriz de proyección en perspectiva ortográfica que se ha usado para proyectar la escena al último frame renderizado?

### 10.¿Cómo puedes obtener la matriz de transformación entre el sistema de coordenadas local y el mundial?

### 11.Cómo puedes obtener la matriz para cambiar al sistema de referencia de vista

### 12.Especifica la matriz de la proyección usado en un instante de la ejecución del ejercicio 1 de la práctica 1

### 13.Especifica la matriz de modelo y vista de la escena del ejercicio 1 de la práctica 1

### 14. Aplica una rotación en el start de uno de los objetos de la escena y muestra la matriz de cambio al sistema de referencias mundial

### 15.¿Como puedes calcular las coordenadas del sistema de referencia de un objeto con las siguientes propiedades del Transform? Position (3, 1, 1), Rotation (45, 0, 45)
