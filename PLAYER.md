# YassineProject-1
import pygame
class Player(pygame.sprite.Sprite) :
    def __init__(self):
        super().__init__()
        self.Sprit_Sheet = pygame.image.load('player.png')
        self.image = self.get_image(0 , 0)
        self.rect = self.image.get_rect()
    def get_image(self , x, y) :
        image = pygame.Surface([32,32])
        image.blit(self.sprit_sheet , (0,0) , (x , y ,32 , 32)) 
        return image

