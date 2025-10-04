## EX 10 : IMPLEMENTATION OF DIFFIE HELLMAN ALGORITHM

## AIM :
To implement key exchange between users using Diffie Hellman algorithm.

## ALGORITHM :
1.	Select a large prime number P and a primitive root G of P (publicly known).
2.	Alice selects a private key a and computes her public key x = (G^a) mod P.
3.	Bob selects a private key b and computes his public key y = (G^b) mod P.
4.	Alice and Bob exchange their public keys (x and y).
5.	Alice computes the secret key as ka = (y^a) mod P.
6.	Bob computes the secret key as kb = (x^b) mod P.
7.	Both ka and kb will be the same, forming a shared secret key for secure communication.


## PROGRAM :
```
#include <math.h> 
#include <stdio.h> 
// Power function to return value of a ^ b mod P 
long long int power(long long int a, long long int b, long long int P) 
{ 

if (b == 1)  
return a; 

else 
return (((long long int)pow(a, b)) % P); 
}
// Driver program  
int main() 
{ 
long long int P, G, x, a, y, b, ka, kb; 
// Both the persons will be agreed upon the public keys G and P                                                             
printf("\n*****Diffie-Hellman Key Exchange algorithm*****\n\n"); 
printf("\n\nEnter the value of P: "); 
scanf("%lld",&P); // A prime number P is taken 
printf("The value of P: %lld\n", P); 
printf("Enter the value of G (Primitive root of P): "); 
scanf("%lld",&G); // A primitive root for P, G is taken 
printf("The value of G: %lld\n\n", G); 
// Alice will choose the private key a a = 4; 
// a is the chosen private key 
printf("The private key a for Alice : %lld\n", a);  
x = power(G, a, P); // gets the generated key 
// Bob will choose the private key b 
b = 3; // b is the chosen private key 
printf("The private key b for Bob : %lld\n\n", b); 
y = power(G, b, P); // gets the generated key 
// Generating the secret key after the exchange of keys 
ka = power(y, a, P); // Secret key for Alice 
kb = power(x, b, P); // Secret key for Bob 
printf("Secret key for the Alice is : %lld\n", ka); 
printf("Secret Key for the Bob is : %lld\n", kb); 
return 0; 
}
```

## OUTPUT:
<img width="862" height="609" alt="image" src="https://github.com/user-attachments/assets/4d5ec6a3-677c-4d2a-a2cb-74d867bfd435" />

## RESULT :
The Diffie-Hellman key exchange algorithm has been successfully simulated, with correct execution	of	the	program	and	verification	of	the	results.
