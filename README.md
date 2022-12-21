# food tracker
def getdate():
    import datetime
    return datetime.datetime.now()


def tracker(d, f):
    x = str(getdate())
    with open(f"{d}.txt", "a") as file:
        file.write(x)
        file.write(" ")
        file.write(f)
        file.write("\n")


def retrieve(d):
    with open(f"{d}.txt") as file:
        text = file.read()
        print(text)


while True:
    name = str(input("enter your name accordingly:"))
    while True:
        r = int(input("enter 0 for tracking and 1 for retrieve and 2 to close:"))
        if r == 0:
            food = str(input("enter the food you ate:"))
            tracker(name, food)
        elif r == 1:
            retrieve(name)
        elif r == 2:
            break
    break
