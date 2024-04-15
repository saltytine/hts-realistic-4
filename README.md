# a silly lil writeup of hts realistic 8  

Ok, here is the lil blurb that tells you what to do  
![image](https://github.com/saltytine/hts-realistic-4/assets/156854448/5ba41e45-4646-442e-a4d1-be1460b8f3d9)

And here is the main page of the site  
![image](https://github.com/saltytine/hts-realistic-4/assets/156854448/bec95660-9455-40c2-816a-3e46e3ada10b)  
Where there are 4 other pages:  
Login  
![image](https://github.com/saltytine/hts-realistic-4/assets/156854448/55f29dba-7f85-45b3-b6b7-46bf10543a5c)  
Signup/Register  
![image](https://github.com/saltytine/hts-realistic-4/assets/156854448/9720d6b2-bb32-4699-92a2-ae7f74da6be8)  
Help  
![image](https://github.com/saltytine/hts-realistic-4/assets/156854448/f9dd3093-8308-4d69-b9ab-0870383afc81)  
And User Info  
![image](https://github.com/saltytine/hts-realistic-4/assets/156854448/325a4bb2-53de-4fcf-9357-d2f43a9b7f53)  

The interesting one is user info, because the first thingie we gotta do is find Gary's user info  
So I immediately start fuckin about with that, and if you put ' into it you get back this fun lil screen  
![image](https://github.com/saltytine/hts-realistic-4/assets/156854448/82d51d8e-ca2f-40ef-9c23-525feaffcf11)  

This is very silly, on the website maker's part, because now we know there's a table with all the users  
Now we can do the pretty popular sql injection: smth' or 1=1 --  
![image](https://github.com/saltytine/hts-realistic-4/assets/156854448/558ee349-4e58-4b39-b92b-ec82015e73d7)  
When we click enter, we get the full list of users:  
![image](https://github.com/saltytine/hts-realistic-4/assets/156854448/0177827e-0ee3-47a4-9bcf-34d6ff5e0c14)  
Among these, you'll notice, is the one and only Gary Hunter  
Now we have his username: GaryWilliamHunter and his password: -- $$$$$ --  
We can try to login as the wonderful Gary  
![image](https://github.com/saltytine/hts-realistic-4/assets/156854448/4ac027f2-0370-4bde-b287-d850364aa9a8)  
But it doesn't work D:  
![image](https://github.com/saltytine/hts-realistic-4/assets/156854448/b43f9a6d-980f-4708-983f-8beaf891c349)  
So I think we're gonna have to fuck around some more  
We're gonna make an acc, so we can better see how this whole website works  
![image](https://github.com/saltytine/hts-realistic-4/assets/156854448/ab5336a5-8bdb-4fd3-bc6f-c81c33b5bf9a)  
I think I chose a pretty good username  
So now I have a new account.  
![image](https://github.com/saltytine/hts-realistic-4/assets/156854448/44834ea7-ed3b-4d64-acbb-2706d8443d91)  
The interesting thing I see here, is the clear personal files button, which we can probably manipulate for our final objective  
But I'm getting ahead of myself  
Now we hop on the wonderful BurpSuite, so I can see how this site sends money  
![image](https://github.com/saltytine/hts-realistic-4/assets/156854448/f3fa5ca3-9032-46a4-95d6-eb074d6a9298)  
This little thing is on, and now we send money to dropCash (despite having no money)  
![image](https://github.com/saltytine/hts-realistic-4/assets/156854448/b037a0a7-af71-4ff9-804a-7eb2a3beacd7)  
The website uses cookies to see whos sending the money  
Now we just need to change the username and password to Gary's  
Like so:  
![image](https://github.com/saltytine/hts-realistic-4/assets/156854448/e615a165-e05a-43ab-8e95-032f739c7a64)  
Now we get this:  
![image](https://github.com/saltytine/hts-realistic-4/assets/156854448/8406bae4-784a-4cf4-ae08-30e37e35e4b2)  
So it worked, and now the money is in the dropCash acc. We just have to cover our tracks  
We log in again, and the clear personal files still looks tempting  
Back to Burp, so we can clear our log files and see what happens  
![image](https://github.com/saltytine/hts-realistic-4/assets/156854448/6a8bc8d2-cd33-4d5d-b01b-6d24896d1695)  
So it tells the website to clear everything in 1337h4x0rSQLFiles  
But we wanna clear 'logFiles'  
So we change 1337h4x0rSQLFiles to logFiles and boom  
![image](https://github.com/saltytine/hts-realistic-4/assets/156854448/fe2e58a3-53c2-4961-85fc-e988e017e221)  
(yours would say you did it)  
