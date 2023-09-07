Para iniciar se tiene que instalar git bash, las mas antigua

Para ver la version local de su git.
```bash
git --version
```

Ahora configuramos de manera global con "--global" y así configuramos git con nuestro nombre.
```bash
git config --global user.name "NOMBRE USUARIO"
```

Ahora configuramos git con nuestro correo electrónico.
```bash
git config --global user.email CORREOELECTRONICO
```

AHORA NOSE QUE PASA ACA
```bash
git config --global core.editor "code --wait"
git config --global -e
git config --global core.autocrlf true/input #window/mac o lunux
```

Para ver mas configuraciones de git
```bash
git -h
```


Luego ya esto configurado para empezar con los repositorios 
```bash
git init
git add . #subimos el archivo que modificamos
git commit -m "descrip"
git status #para subir los cambios
```

fin?