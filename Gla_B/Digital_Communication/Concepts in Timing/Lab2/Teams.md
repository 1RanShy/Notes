---
title: Teams
date: 2023-02-07T22:18:49Z
lastmod: 2023-02-08T09:15:25Z
---

# Teams

[16:15](https://web.microsoftstream.com/video/0aa5ac01-698c-4a05-a609-1b039416c3e6?list=user&userId=9eb82978-2982-494d-be3a-23d9b83f21af)

```python
import numpy as np
from numpy import random
from matplotlib import pyplot as plt
from scipy import signal
from PIL import Image

tx_im = Image.open("gulogo.pbm")
Npixels = tx_im.size[1]*tx_im.size[0]
tx_bin = np.array(tx_im)
plt.figure()
plt.imshow(tx_bin)
plt.show()
prelude = np.array(np.random.randint(2,size=16),dtype = "bool")
tx_bin = np.append(prelude,np.ravel(tx_bin))

[[import]] 24bit digital data
[[id_num]] = 3141592
[[tx_bin]] = np.array([id_num//(2**(23-i))%2 for i in range(0,24)],dtype = "u
[[Npixels]] = tx_bin.size

[[initialise]]

mylock = np.array([1.0,0.0])
bit_period = 128
fc = 1/32
fref = fc*(1.+0.02*random.rand()-0.5))
pref = 2*np.pi*random.rand()
volt = 0.0
vout = np.array(volt)
cout = myclock[0]
rout = np.cos(pref)
dout0 = np.empty(0)

# low pass filter
numtaps = 128
b1 = np.flip(signal.firwin(numtaps,0.005))

mixed = np.empty(2)

for i in range(0,bit_period*(period*(prelude.size+Npixels)+numtaps//2);
	mixed[0,:] = np.append(mixed[0,1:],myclock[0]*(2*tx_bin[(i//bit_period)]) [[不全]]
	mixed[0,:] = np.append(mixed[0,1:],myclock[0]*(2*tx_bin[(i//bit_period)]) [[不全]]

	lpmixed = [np.sum(b1*mixed[j,:1]) for j in range(2)]
	volt = lpmixed[0]*lpmixed[1]

	c = np.cos(2*np.pi*fc*(1.+0.25*volt))
	s = np.sin(2*np.pi*fc*(1.+0.25*volt)) 
	myclock = np.matmul(np.array([[c,-s],[s,c]]),mylock)

	vout = np.append(vout,volt)
	cout = np.append(cout,myclock[0])
	rout = np.append(rout,np.cos(pref+2*np.pu*fref*i))
	dout0 = np.append(dout0,lpmixed[0])

plt.figure()
plt.plot(vout,color = 'b;)
plt.show()
plt.figure()
plt.plot(cout,color = 'b')
plt.plot(cout,color = 'r')
plt.show()
plt.figure()
plt.plot(dout0,color = 'b')
plt.show()

rx_bin = np.unit8(np.heaviside(dout0[(2*i+1)*bit_period//2+numtaps//2],0) for i in range(prelength) [[最后一点不全]]
print((rx_bin != tx_bin[prelude.size:]).sum())
rx_bin = rx_bin.reshape(tx_im.size[1],tx/-im.size[0])
plt.figure()
plt.imshowL(rx_bin)
plt.show()
```

‍
