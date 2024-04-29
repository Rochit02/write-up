# Donations
The following was the challange:

![image](https://github.com/Rochit02/write-up/assets/150697578/3f1a6d2b-c761-4af5-ab27-f2cf46e14240) 

From the given challange, after loging into the challange, this is how it looks:
![image](https://github.com/Rochit02/write-up/assets/150697578/1ac93e9f-2b84-4eec-8f52-4cf86f140d07)
By clicking any of the Jeff Bezos, it would ask for donations.
![image](https://github.com/Rochit02/write-up/assets/150697578/133d5d90-775a-470c-bea4-0197bcbaf5f0)
Now, the catch is, if we donate the money interms of -ve, we can get the flag.
So I opened bursuip, and opened it in proxy with same username and password and sent it to repeater. (or you could inspect and remove -ve element in html source)
![image](https://github.com/Rochit02/write-up/assets/150697578/ff1c75d0-ebd3-4631-921c-cbd7f838e589)
![image](https://github.com/Rochit02/write-up/assets/150697578/7945fb8c-4414-400f-88b3-63b596d11689)
From the above image we can identify that the server has responded with 200.
Since there is still no sight of flag, lets check our profile.
![image](https://github.com/Rochit02/write-up/assets/150697578/3ff2ae52-45ab-43fa-bded-b0907e041e29)
There you go! We have got the flag!

```UMDCTF{BE20$_1s_7h3_T0N6U3_OF_Th3_uN5e3N}```
