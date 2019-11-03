# Crackers
#Beta testing programs to recover lost Bitcoin

from bitcoin import *
import os
import time

print (time.asctime())
counter = 0

# if you wish to test the speed u need to up the counter and remove the # blow at #counter = counter + 1 line at the bottom
while counter < 1:


    priv =  random_key()
    pub = privtopub(priv)
    addr = pubtoaddr(pub)

    # to test cracker remove the # below and put in any address in the MainList.txt file it will hit it every time
    
    #addr =("1DuqqTg2SiYRqYbZrE5KsU3Q7ta5sU3ikn")
    #print(addr)

    #searches file for address match if the priv key generated matchs any address in the MainList.txt it will print it and auto save it
    searchfile = open("MainList.txt","r")

    for line in searchfile:
        if addr in line:
                # Auto saves to Cracked Private Key List.txt
                print("Cracked Priv Key = "+priv+" - Address = " + addr + "\n")
                f = open("Cracked Private Key List.txt", 'a')
                f.write("Cracked Priv Key = " + priv + " - Address = " + addr + "\n")
                f.close()

                
    #counter = counter + 1
print (time.asctime())
