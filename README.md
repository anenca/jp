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
Napisz program, który będzie obliczał pierwiastki kwadratowe z odczytanych liczb. Program powinien odrzucać wartości ujemne i zatrzymać się, gdy otrzyma wartość 0. (Funkcja sqrt z biblioteki math.h oblicza pierwiastek kwadratowy)

Zadanie 4
Napisz funkcję, która będzie otrzymywać jako argumenty dwie liczby naturalne, i będzie zwracać ich sumę.

