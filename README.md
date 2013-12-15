# zadania  do rozwiazania



zadanie 1
Jakie wyniki otrzyma się po wykonaniu następującego programu?
```c
#include <stdio.h>
main(){
int n=10, p=5,q=10,r;
r=n==(p=q);
printf("A:n=%d p=%d q=%d r=%d\n",n,p,q,r);
n=p=q=r=5;
n+=p+=q;
printf("B:n=%d p=%d q=%d \n",n,p,q);
q=n<p ? n++ : p++;
printf("C:n=%d p=%d q=%d \n",n,p,q);
q=n>p ? n++:p++;
printf("D:n=%d p=%d q=%d \n",n,p,q);
}
```
Zadanie 2
```c
#include <stdio.h>
main(){
 int n;
 scanf("%d",&n);
 switch (n){
  case 0 : printf("Zero\n");
  case 1 :
  case 2 : printf("Mala\n");
           break;
  case 3 : 
  case 4 :
  case 5 : printf("Srednia\n");
  case 6 : printf("Duza\n");
  }
}
```
Jaki będzie wynik działania programu, gdy poda mu się jako dane:
a) 0
b) 1
c) 4
d) 10
e) -5


Zadanie 3

Przeanalizować program sortowania bąbelkowego z przyśpieszeniem.
```c
#include<stdio.h>
#define ILE 15

int main () {
  double tab[ILE], x;  int k, n, m;
  printf("\nSORTOWANIE BABELKOWE Z PRZYSPIESZENIEM");
  printf("\nPodaj %i liczb rzeczywistych: ", ILE);
  for (k=0; k<ILE; k=k+1)
    scanf("%lf", &tab[k]);

  n=ILE;
  while (n>1) {
    m=1;
    for (k=1; k<n; k=k+1)
      if (tab[k-1] > tab[k]) {
        x=tab[k-1]; tab[k-1]=tab[k]; tab[k]=x;
        m=k;
      }
    n=m;
  }
  
  printf("\nWynik sortowania:\n");
  for (k=0; k<ILE; k=k+1)
    printf("  %lf\n", tab[k]);
  printf("\n");

  return 0;
}
```
Zadanie 4
Napisać program, który wczyta

  -  liczbę rzeczywistą r>0,
  -  liczbę naturalną n,
  -  ciąg długości n liczb rzeczywistych dodatnich (to jest ważne założenie) a0,a1,...,an−1 

i znajdzie taki spójny fragment ciągu, którego suma wynosi r:

    ap + ap+1 + ... + aq−1  =  r 
    

