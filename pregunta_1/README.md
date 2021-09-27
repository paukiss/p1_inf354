## 1. Seleccione dos dataset de los propuestos por su persona en una anterior tarea. Realice lo siguiente:
  ### Trabajamos con los datos del dataset de Netflix, para ello abrimos el archivo csv, con Pandas
  ![datos](https://user-images.githubusercontent.com/39333761/134872926-d92baf66-31c2-4852-b6a8-ddf5fa4b0a60.png)

  ### a. La media, moda y la desviación estándar por columna; explique qué significa en cada caso mediante Python sin uso de librerías
 #### MEDIA
  ```python
  def media(mat):
      med, n = [], len(mat)
      for i in range(len(mat[0])):
          s = 0
          for j in range(n):
              s += mat[j][i]
          med.append(s / n)
      return med
  ```
  ![media_sa](https://user-images.githubusercontent.com/39333761/134872664-e8b7c0cd-8b4e-4927-9a72-7618f0761ccd.png)

 #### MODA
  ```python
  def moda(mat):
      mod, n = [], len(mat)
      for i in range(len(mat[0])):
          s = 0
          occ = {}
          for j in range(n):
              occ[mat[j][i]] = occ.get(mat[j][i], 0) + 1
          most_frequent = max(occ.values())
          mod.append([key for key, value in occ.items() if value == most_frequent] )
      return mod
  ```
  ![moda_sa](https://user-images.githubusercontent.com/39333761/134872728-46810a3f-2e0c-4de5-a568-086f29a2cf36.png)

 #### DESVIACION ESTANDAR
  ```python
  import math
  def desviacion_estandar(mat):
      d_s, n = [], len(mat)
      mod = media(mat)
      for i in range(len(mat[0])):
          s = 0
          for j in range(n):
              s += (mat[j][i] - mod[i])*(mat[j][i] - mod[i])
          d_s.append(math.sqrt(s / n ))
      return d_s
  
  ```
  ![de_sa](https://user-images.githubusercontent.com/39333761/134872757-4cc09705-aaf8-40ef-8e0d-9e72b7088556.png)

   ### b. La media, la moda, la desviación estándar con el uso de numpy y pandas
   #### Media
  ![media_with](https://user-images.githubusercontent.com/39333761/134873386-1d7e29c8-cada-4771-8151-19d05539c6ee.png)
  #### Moda
  ![moda_with](https://user-images.githubusercontent.com/39333761/134873375-a5cdcc9f-d6e0-4745-b1a2-01114d832302.png)
 #### Desviacion Estandar
  ![de_with](https://user-images.githubusercontent.com/39333761/134873388-8937848a-c84b-4233-82cd-f64f1f359b54.png)

   ### c. Grafique los datos y explique su comportamiento (PYTHON)
   #### Graficamos los datos de la columna Rating 
   ![image](https://user-images.githubusercontent.com/39333761/134873678-f17d0b43-cf94-4a68-9dcb-e2c898c27759.png)
   #### En la grafica se observa como el valor de Rating es el valor que mas se repite, si se compara con la MODA podemos observar que es correcto
   ![image](https://user-images.githubusercontent.com/39333761/134873837-6e1ecfd4-b980-48ed-982f-52ef0a2cafef.png)
   #### En la grafica vemos que el valor que mas se repite se encuentra en el intervalo 20- 40, si comparamos con la Moda de la columna Movie_ID vemos que la moda es "30"
  ![image](https://user-images.githubusercontent.com/39333761/134873946-010398d5-7916-4b71-95e2-2aca3edd5c10.png)
