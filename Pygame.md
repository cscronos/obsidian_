
Primeramente verificar si pip esta actulizado para posteriormente instalar pygame
```
python -m pip install -U pip
```

Para instalar pygame es uno de estos para window
```
pip install pygame

py - m pip install - U pygame -- usuario
```
sino ve la documentacion.
https://www.pygame.org/wiki/GettingStarted#Pygame%20Installation

despues de eso 
```python
import pygame

# global ventana
# Inicialización de Pygame
pygame.init()

# VARIABLES
res = (640, 480)

  

# ALL DEF
def dibujar_panel():
    ventana = pygame.display.set_mode(res)
    pygame.display.set_caption("Ejemplo 1")
    return ventana

img = pygame.image.load("img/button.png")
picture = pygame.transform.scale(img, [300, 300])

# Bucle principal del juego

jugando = True
while jugando:
    # Comprobamos los eventos
    #Comprobamos si se ha pulsado el botón de cierre de la ventana
    for event in pygame.event.get():
        if event.type == pygame.QUIT:
            jugando = False

    #___________________________________________
    # click y pos del mouse
    if event.type == pygame.MOUSEBUTTONDOWN:
            x_mouse, y_mouse = pygame.mouse.get_pos()
            if x_mouse > 0 and y_mouse > 0:
                if x_mouse < 100 and y_mouse < 100:
                    print(x_mouse, y_mouse)

    # Se pinta la ventana con un color
    # Esto borra los posibles elementos que teníamos anteriormente
    dibujar_panel().fill((23, 23, 23))
    dibujar_panel().blit(picture, [0, 0])
    # Todos los elementos del juego se vuelven a dibujar
    pygame.display.flip()
    # Controlamos la frecuencia de refresco (FPS)
    pygame.time.Clock().tick(60)
pygame.quit()
```
