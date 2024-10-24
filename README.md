import pygame
from jeu import Game
from joueur import Player
pygame.init()




#la fenetre du jeu tree kill zombie
pygame.display.set_caption("tree kill zombies")
ecran=pygame.display.set_mode((1000, 500))


#charger l'image
arriere_plan = pygame.image.load("images et sons/bg.jpg")
#charger le joueur
player= Player()
#charger les parametres du jeu
game=Game()
on = True

#boucle tant que on est vrai
while on:

    ecran.blit(arriere_plan, (0, -400))

    ecran.blit(game.player.image, game.player.rect)

    pygame.display.flip()

    for event in pygame.event.get():
        if event.type== pygame.QUIT:
            on = False
            pygame.quit()
        elif event.type == pygame.KEYDOWN:
            if event.key==pygame.K_RIGHT:
                game.player.move_right()
            if event.key==pygame.K_LEFT:
                game.player.move_left() 

            
