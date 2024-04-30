# Donations (I have fixed it):
The following is the challenge name and its description:

![image](https://github.com/Rochit02/write-up/assets/150697578/d9e73b55-0f47-4643-bd63-0b68c81a1758)

After clicking on the link given in the challenge, we get to see this site:

![image](https://github.com/Rochit02/write-up/assets/150697578/47a2fbc5-a9fa-4ce1-98bd-11275aa2be05)

Now login and create one main account, and login the same when opening it in a proxy of Burpsuit.

When trying to send -ve money like in the previous challenge, it returns with a 403 status code.

![image](https://github.com/Rochit02/write-up/assets/150697578/199be1b9-b9c1-4023-88b8-032c94c3ad8a)

Sending money in -ve amount is not possible.
So, when we try sending money to some other account only and not to Jeff Bezos, it returns a 403 status code with a message that "you may only donate to Jeff Bezos".

![image](https://github.com/Rochit02/write-up/assets/150697578/e4d05c7d-4158-4034-aa6f-f970fc3fe02e)

Since money can't be sent to other accounts, let's try sending it to Jeff Bezos and to our own account to see if we can bypass the condition of only donating money to Jeff Bezos.

![image](https://github.com/Rochit02/write-up/assets/150697578/aad39a8f-cffa-4231-9124-e853ee12a989)

Now we have found the vulnerability from which we can bypass the server-side condition, and sending money to our own account from our account will not help increase our money.
So, let's make more accounts and send money to our main account.
To get the flag, we need to have a minimum of $5,000 in our main account for the challenge.
Once we get more than $5,000 in our main account,

![image](https://github.com/Rochit02/write-up/assets/150697578/7c857633-3c96-4748-8454-09e5359db7cd)

we get the flag!!

```UMDCTF{TeS7_your_CHAL1En93S 6UyS}```
