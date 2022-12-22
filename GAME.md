# YassineProject-1
import pygame
import pytmx
import pyscroll
class Game :
    def __init__(self):
        #fenetre du jeux
        self.screen = pygame.display.set_mode((800 ,600))
        pygame.display.set_caption("Yassine Game")
        #charger la carte
        tmx_data = pytmx.util_pygame.load_pygame('main carte.tmx')
        map_data = pyscroll.data.TiledMapData(tmx_data)
        map_layer = pyscroll.orthographic.BufferedRenderer(map_data,self.screen.get_size())
        #genéré un joueur
        self.player = Player()
        #dessiner le group calque
        self.group = pyscroll.PyscrollGroup(map_layer=map_layer, default_layer=1)
        self.group.add(self.player)
        
    def run(self):
        #boucle du jeu
        running = True
        while running :
            self.group.draw(self.screen)
            pygame.display.flip()
            for event in pygame.event.get():
                if event.type == pygame.QUIT :
                    running = False
        pygame.quit()

