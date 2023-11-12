Para convertir un script de Python en un archivo binario que pueda ejecutarse en cualquier lugar, puedes usar una herramienta como PyInstaller o cx_Freeze. Estas herramientas empacan tu script de Python y todas sus dependencias en un archivo ejecutable independiente. Aquí tienes un ejemplo usando PyInstaller:

1. Asegúrate de tener PyInstaller instalado en tu sistema. Y ldd Puedes instalarlo con pip:
```
pkg install binutils
```

```
pip install pyinstaller
```

```
pkg install ldd
```

2. Luego, crea una versión ejecutable de tu script de Python utilizando PyInstaller:

```
pyinstaller --onefile nombre_de_tu_script.py
```

Esto generará un directorio "dist" en la ubicación actual con un archivo ejecutable que puedes mover y ejecutar en cualquier lugar. Por ejemplo, si tu script se llama "mi_script.py", encontrarás un archivo ejecutable llamado "mi_script" dentro del directorio "dist".

3. Copia el archivo ejecutable a tu dispositivo Android en la ubicación que desees.

4. Abre Termux en tu dispositivo Android.

5. Navega hasta el directorio donde copiaste el archivo ejecutable. Puedes usar el comando `cd` para cambiar de directorio.

6. Ejecuta el archivo binario:

```
./nombre_de_tu_script
```

Esto ejecutará tu script de Python en Termux en tu dispositivo Android.

Recuerda que para ejecutar scripts en Termux, debes asegurarte de que Termux tenga los permisos adecuados para acceder al almacenamiento y ejecutar archivos. Puedes configurar estos permisos en la configuración de la aplicación Termux si es necesario.

El comando "pyinstaller --onefile encryp_files.py" se utiliza para crear un archivo ejecutable a partir de tu script de Python "encryp_files.py". La opción "--onefile" indica que deseas generar un solo archivo ejecutable en lugar de múltiples archivos. 

Cuando ejecutas ese comando, PyInstaller empacará tu script de Python y todas sus dependencias en un solo archivo ejecutable que puede ser ejecutado en cualquier lugar sin necesidad de tener Python instalado. Esto es útil si deseas compartir tu script con otros usuarios que no tengan Python instalado en sus sistemas.

Una vez que hayas creado el archivo ejecutable, puedes ejecutarlo en Termux o en cualquier otro lugar donde desees utilizarlo, y realizará la funcionalidad definida en tu script "encryp_files.py".
## Para ejecutar tu script de Python como una herramienta binaria personalizada en Termux, debes seguir estos pasos:

1. Asegúrate de que tu script de Python "encryp_files.py" tenga el shebang adecuado en la parte superior del archivo. El shebang le indicará a Termux que debe usar Python para ejecutar el script. El shebang debe ser algo como:

```python
#!/data/data/com.termux/files/usr/bin/python
```

Asegúrate de que la ruta al intérprete de Python de Termux sea correcta.

2. Dale permisos de ejecución a tu script:

```bash
chmod +x encryp_files.py
```

3. Crea un directorio bin en tu directorio de inicio de Termux si aún no existe:

```bash
mkdir -p ~/bin
```

4. Mueve tu script al directorio bin:

```bash
mv encryp_files.py ~/bin/
```

5. Asegúrate de que el directorio bin esté en tu variable de entorno PATH. Puedes agregarlo al archivo .bashrc o .zshrc (según la shell que utilices) si aún no está configurado:

```bash
echo 'export PATH="$HOME/bin:$PATH"' >> ~/.bashrc  # O ~/.zshrc si usas zsh
```

6. Recarga la configuración de la shell:

```bash
source ~/.bashrc  # O source ~/.zshrc si usas zsh
```

Ahora, podrás ejecutar tu script "encryp_files.py" desde cualquier lugar en Termux como una herramienta binaria personalizada simplemente escribiendo el nombre del archivo sin la extensión, por ejemplo:

```bash
encryp_files.py
```

Esto hará que el script se ejecute como si fuera una herramienta binaria en Termux. Asegúrate de que el script tenga permisos de ejecución y que la variable de entorno PATH esté configurada correctamente para que Termux pueda encontrarlo.
