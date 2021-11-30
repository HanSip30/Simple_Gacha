# Simple_Gacha
Hello, this is my first Repository
i hope this code can be your reference


# PROGRAM GACHA, PENGURANGAN DIAMOND, PITY
# ORIGINAL MILIK FARHAN ADITYA
from random import *

koleksi = {}
#choices(["kucing","anjing","monyet","ayam","burung","sapi","kambing","bebek","kelinci","ampas","rijal","kuda","jerapah","kodok"],[10,10,10,10,10,10,10,10,10,10,20,10,10,10],k=10)
diamond = 10040
jumlah_gacha = 0
    
def judul(): #
    print("\n[ %i ]" % diamond)
    print("="*16)
    print("= PULL RATE UP =")
    print("=","***".center(12),"=")
    print("="*16,"\n")
    print(" [1]".ljust(10),"[10] ".rjust(0),)
    input_data()
    
def input_data():
    global jumlah_pull
    jumlah_pull = int(input("\nJumlah Pull: "))
    
    if (jumlah_pull != 1) and (jumlah_pull != 10):
        print("Invalid\n")
        input_data()
        
    else:
        print("Diproses...".center(16),("\n"))
        proses()
        
def proses():
    global diamond
    diamond = diamond
    global jumlah_gacha
    jumlah_gacha = jumlah_gacha
    
    if (jumlah_pull == 1) and (diamond >= 100):
        hasil = choices(
            ["kucing","anjing","monyet","ayam","burung","sapi","kambing","bebek","kelinci","ampas","RIJAL ***","kuda","jerapah","kodok"],
            [18,50,50,50,25,50,50,50,20,90,5,50,50,50],
            k=1)
        diamond = diamond - 100
        jumlah_gacha = jumlah_gacha + 1
        print(hasil)
        print("sisa diamond[%i]" % diamond)
        
    elif (jumlah_pull == 10) and (diamond >= 1000):
        hasil = choices(
            ["kucing","anjing","monyet","ayam","burung","sapi","kambing","bebek","kelinci","ampas","RIJAL ***","kuda","jerapah","kodok"],
            [18,50,50,50,25,50,50,50,20,90,5,50,50,50],
            k=10)
        diamond = diamond - 1000
        jumlah_gacha = jumlah_gacha + 10
        print(hasil)
        print("\sisa diamond[%i]" % diamond)
        
    elif (jumlah_pull == 10) and (diamond < 1000):
        print("Diamond anda kurang")
        input_data()
        
    else:
        print("Diamond kurang! TOP UP DULU SONO!!")
        print("program berhenti karena anda miskin")
        exit()
        

if __name__ == "__main__":
    judul()
    while(diamond >= 0):
        input_data()
