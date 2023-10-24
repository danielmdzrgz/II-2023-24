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

Puedes hacerlo trasladando la esfera a una posición fuera del volumen de vista de la cámara o ajustando el volumen de vista de la cámara para que la esfera quede fuera.

### 5.Como puedes aumentar el ángulo de la cámara. Qué efecto tiene disminuir el ángulo de la cámara

Para aumentar el ángulo de la cámara en Unity, hay que ajustar el campo Field of View (FOV) en el componente de la cámara.

Aumentar el FOV da un efecto de "gran angular" (los objetos cercanos se ven grandes y los lejanos pequeños). Disminuir el FOV da un efecto más "telefoto" (menor ángulo de visión, pero más zoom).

### 6.Es correcta la siguiente afirmación: _Para realizar la proyección al espacio 2D, en el inspector de la cámara, cambiaremos el valor de projection, asignándole el valor de orthographic_

Sí, es correcto. En Unity, si cambias la proyección de la cámara a "Orthographic", obtienes una proyección al espacio 2D.

### 7.Especifica las rotaciones que se han indicado en los ejercicios previos con la utilidad quaternion.

Para rotar 30º alrededor del eje Y usando quaternion:
```csharp
Quaternion.Euler(0, 30, 0);
```

### 8.¿Como puedes averiguar la matriz de proyección en perspectiva que se ha usado para proyectar la escena al último frame renderizado?

```csharp
Matrix4x4 perspectiveProjectionMatrix = camera.projectionMatrix;
```

### 9.¿Como puedes averiguar la matriz de proyección en perspectiva ortográfica que se ha usado para proyectar la escena al último frame renderizado?

Primero hay que asegurarse de que la cámara esté en modo ortográfico, luego:
```csharp
Matrix4x4 orthographicProjectionMatrix = camera.projectionMatrix;
```

### 10.¿Cómo puedes obtener la matriz de transformación entre el sistema de coordenadas local y el mundial?

```csharp
Matrix4x4 localToWorldMatrix = transform.localToWorldMatrix;
```

### 11.Cómo puedes obtener la matriz para cambiar al sistema de referencia de vista

```csharp
Matrix4x4 viewMatrix = camera.worldToCameraMatrix;
```

### 12.Especifica la matriz de la proyección usado en un instante de la ejecución del ejercicio 1 de la práctica 1

La matriz de proyección en un instante de ejecución es:
```text
Matriz de Proyección: 
1.05085	  0.00000	0.00000	  0.00000
0.00000	  2.74748	0.00000	  0.00000
0.00000	  0.00000	-1.00080  -0.40016
0.00000	  0.00000	-1.00000  0.00000
```

### 13.Especifica la matriz de modelo y vista de la escena del ejercicio 1 de la práctica 1

La matriz de modelo y vista de la escena es:
```text
Matriz de Modelo y Vista: 
0.99990	  0.00078	0.01447	  -0.20989
-0.00441  0.96744	0.25307	  -1.36364
0.01380	  0.25311	-0.96734  -4.34724
0.00000	  0.00000	0.00000   1.00000
```

### 14.Aplica una rotación en el start de uno de los objetos de la escena y muestra la matriz de cambio al sistema de referencias mundial

Al aplicar una rotación en el start de la estructura principal de la escena, la matriz de cambio al sistema de referencias mundial es:
```text
Matriz de Cambio al Sistema de Referencias Mundial: 
0.69735	  0.00000	  0.71673   3.39062
-0.01993  0.99961	  0.01940   -0.94589
0.71645   0.02781	  -0.69708  -16.36222
0.00000   0.00000	  0.00000   1.00000
```

### 15.¿Como puedes calcular las coordenadas del sistema de referencia de un objeto con las siguientes propiedades del Transform? Position (3, 1, 1), Rotation (45, 0, 45)

Si tienes un objeto con Position (3, 1, 1) y Rotation (45, 0, 45), la matriz de transformación que representa estas transformaciones en relación al sistema de referencia mundial es simplemente su matriz ```localToWorldMatrix```. La rotación se aplica usando quaterniones, por lo que ```Quaternion.Euler(45, 0, 45)``` te da la rotación deseada.

## Participantes
- Julio Ruzicka Ruzicka
- Daniel Méndez Rodríguez
- José Lozano Armas
- José Gregorio Dorta Luis
