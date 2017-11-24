# Pygame Icons

## Description:
Its a python module use to integrate Icon font, with pygame. It work base on [icon_font_to_png](https://github.com/Pythonity/icon-font-to-png). It can be used with any graphic toolkit that support images. It can handle multiple fonts.

* Works with python 2.7
* Supports multiple fonts
* Works with pygame


## Requirements

    $ sudo pip install -r requirements.txt

## Dependencies
* pillow >=4.3.0
* tinycss >=0.4
* six >=1.10.0

## Usage
Move the icon_font.py file into your working directory then import it into your project. When initializing a IconHandler instance, you will need to pass it the name of the font and also the path of ttf and css files in a dictionary format. In our example below, the ttf and css files are in our working directory.

    import pygame
    from icon_font import  IconHandler

    pygame.init()

    devicons = {'font':'devicons','css':'devicons/devicons.css','ttf':'devicons/devicons.ttf'}

    fonts = [devicons]

    iconHandler = IconHandler(fonts)

    screen = pygame.display.set_mode((400,400))
    screen.fill((255,255,255))

    image = iconHandler.pygame_image('devicons-raspberry_pi',50)
    screen.blit(image, (200,200))

    pygame.display.flip()


The default colour is black, but it can be changed to other colors by passing in the colour when you call the pygame_image method.

    image = iconHandler.pygame_image('devicons-raspberry_pi',50,'red')

You can also get the image in the pillow format, that you will be able to later change to other format such as opencv image format.

    image = iconHandler.pillow_image('devicons-raspberry_pi', 50)

or get it in red

    image = iconHandler.pillow_image('devicons-raspberry_pi',50,'red')
