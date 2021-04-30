import pyautogui, os, logging,time

logging.basicConfig(level=logging.DEBUG,format='%(asctime)s - %(levelname)s - %(message)s')

game_region = (347,163,800,530)
print(os.getcwd())

def main():
    logging.debug('Program Started. Press Ctrl-C to abort at any time.')
    logging.debug('To interrupt mouse movement, move mouse to upper left corner.')
##    getGameRegion()
    startGame()
    startServing()

def imPath(filename):
    return os.path.join('images',filename)

##def getGameRegion():
##    global game_region
##
##    logging.debug('Finding game region...')
##    region = pyautogui.locateOnScreen(imPath('top_left_corner.png'))
##    print(region)
##    if region is None:
##        print('Cannot find game on screen')
##
##    game_region = (region[0],region[1],800,530)
##    logging.debug('Game region found: %s' % (game_region,))


def startGame():
    logging.debug('Looking for Play button...')
    pos = pyautogui.locateCenterOnScreen(imPath('play.png'),region=game_region,confidence=.8)
    pyautogui.click(pos,duration=1)
    logging.debug('Clicked on Play button.')

    time.sleep(2.5)  #resume program after blackscreen

    pos = pyautogui.locateCenterOnScreen(imPath('play2.png'),region=game_region)
    pyautogui.click(pos,duration=0.3)
    logging.debug('Clicked on Play2 button.')

    time.sleep(1)

    pos = pyautogui.locateCenterOnScreen(imPath('Next.png'),region=game_region)
    pyautogui.click(pos,duration=0.3)
    logging.debug('Clicked on Next button.')

    time.sleep(0.5)

    pos = pyautogui.locateCenterOnScreen(imPath('skip.png'),region=game_region)
    pyautogui.click(pos,duration=0.3)
    logging.debug('Clicked on Skip button.')

    time.sleep(0.5)

    pos = pyautogui.locateCenterOnScreen(imPath('Next.png'),region=game_region)
    pyautogui.click(pos,duration=0.3)
    logging.debug('Clicked on Next button.')

def startServing():
        image_list=[imPath('pingu.png'),imPath('pingu2.png')]
        image_list2 = [imPath('pinguw333.png'),imPath('pinguw4.png'),imPath('pinguw5.png')]
        diners = []

        r = None
        while r is None:
            for image in image_list:
                r = pyautogui.locateCenterOnScreen(image, region=game_region,confidence = 0.72)  # find the two types of pingu
                if r:
                    pyautogui.click(r, duration=0.25)
                    logging.debug('Clicked on Pingu2.')

                    pos = pyautogui.locateCenterOnScreen(imPath('table2.png'), region=game_region,confidence = 0.6)
                    pyautogui.click(pos, duration=0.25)
                    print('Getting pingu to table!')
                    logging.debug('Clicked on Table2.')

                    print('out of for loop')

            for image in image_list2:
                r = pyautogui.locateCenterOnScreen(image, region=game_region,confidence = 0.84)
                if r not in diners and r is not None:
                    pyautogui.click(r,duration=0.25)
                    logging.debug('''Took pingu's order''')
                    diners.append(r)
                    print(diners)
                    
            r = None
            print(r)

main()
