import pyautogui
import time
import math
import keyboard

# Centralizar o cursor no meio da tela
screen_width, screen_height = pyautogui.size()
pyautogui.moveTo(screen_width / 2, screen_height / 2)

# Configurações do círculo
radius = 2  # Raio do círculo
speed = 0.1   # Velocidade do movimento do mouse
angle = 0    # Ângulo inicial

teclas_para_parar = ["F", "A", "S", "D", "Z", "X", "C"]

while True:
    x_position = radius * math.cos(math.radians(angle))
    y_position = radius * math.sin(math.radians(angle))

    pyautogui.moveTo(screen_width / 2 + x_position, screen_height / 2 + y_position, duration=speed)

    angle += 10

    for tecla in teclas_para_parar:
        if keyboard.is_pressed(tecla):
            print("Tecla pressionada. Parando o programa.")
            break
    else:
        continue
    break

    time.sleep(0.1)
