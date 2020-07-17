### **Challenge Description: **

`*Man, oracles are weird.*

*nc challenges1.hexionteam.com 5000*`



### **Solving :** 

​	Really Smart Acronym, of course, is RSA. Looking at the code, it uses PyCrypto to generate a RSA key to encrypt the flag. You also get one encryption and 1024 decrypts, but you only get the last bit of the decrypts. At first I thought it could be Franklin-Reiter related-message attack, but there is not enough information for that.

<!--more-->

[	This thread](https://crypto.stackexchange.com/questions/11053/rsa-least-significant-bit-oracle-attack) was one of the resources that I used to solve this problem. From there, the method is given, but we still need to find e and N for the attack to work. e is easy. Since it uses PyCrypto, e = 65537. As for N, that’s what the one encrypt is for. If you realize you can pass negative numbers for the encrypt, then it becomes easy. The encrypted message is m^e mod N, so if you pass -1, it is -1^65537 mod N = N – 1.

### **Solve Script :** 

```
from pwn import *

sh = remote('challenges1.hexionteam.com', 5000)

sh.recvuntil('Flag: ')

cipher = int(sh.recvline().decode().strip())
#print(cipher)

sh.recvuntil('m => ')
sh.sendline('-1')

n = int(sh.recvline().decode().strip()) + 1

mult = pow(2, 65537, n)
#print(mult)

def get_lsb(num):
	sh.recvuntil('> ')
	sh.sendline(str(num))
	return int(sh.recvline().decode().strip())

high = n
low = 0
for i in range(1024):
	cipher *= mult
	cipher %= n
	lsb = get_lsb(cipher)
	if lsb == 0:
		high = (high + low) // 2
	else:
		low = (high + low) // 2

print(high)
```





