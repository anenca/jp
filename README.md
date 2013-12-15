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
    
Zadanie 5

Poniższy program drukuje wszystkie rzeczywiste wartości zdefiniowanej w nim funkcji funkcja począwszy od rzeczywistej wartości dol_x do rzeczywistej wartości gora_x z rzeczywistym krokiem krok_x. Wpisać do niego taką definicję funkcji funkcja, żeby ten program drukował tablicę wartości funkcji

    a)x3/27 - 2x2/9 + x/3 + 2

    b)ln(x+1) 

Wskazówka do pktu b: żeby mieć dostęp do standardowej funkcji log obliczającej logarytm naturalny, należy

    wpisać na początku programu odwołanie do biblioteki matematycznej: #include<math.h>  oraz
    do wywołania kompilatora dodać parametr: gcc -o ... -lm 
```c
#include<stdio.h>
#include<math.h>

#define dol_x -0.9
#define gora_x 8
#define krok_x 0.1


// miejsce na wpisanie definicji funkcji


int main () {
  double x;
  printf("\nTABLICOWANIE FUNKCJI:\n");
  printf("\n Argument |   Wartosc   ");
  printf("\n----------+-------------");
  for (x=dol_x; x<=gora_x; x=x+krok_x)
    printf("\n %8.4lf | %10.4lf ", x, funkcja(x));
  printf("\n\n");

  return 0;
}
```
Zadanie 6

Program:
```c
#include<stdio.h>
#include<math.h>

#define szer 50
#define wys 40
#define dol_x -0.9
#define gora_x 8
#define dol_y -2.5
#define gora_y 2.5


double  funkcja_b (double x) {
  return  log(x+1);
}


char  rysunek[szer][wys];


void  rysuj(int x, int y, char znak) {
  if (0<=x && x<szer && 0<=y && y<wys)
    rysunek[x][y] = znak;
}


int  interpoluj (double x, double a, double b, int n) {
  return  floor((x-a)*n/(b-a));
}


int  f_b (int x) {
  return
    interpoluj(
	       funkcja_b( ((double)gora_x - (double)dol_x)/szer*x + dol_x),
                 dol_y,  gora_y,  wys
               );
}


int main () {
  int  x,y, poziom, pion;

  printf("\nWYKRES FUNKCJI:\n\n ");

  for (x=0; x<szer; x=x+1)
    for (y=0; y<wys; y=y+1)
      rysuj(x, y, ' ');

  pion = interpoluj(0, dol_x, gora_x, szer);
  for(y=0; y<wys; y=y+1)
    rysuj(pion, y, '|');

  poziom = interpoluj(0, dol_y, gora_y, wys);
  for(x=0; x<szer; x=x+1)
    rysuj(x, poziom, '-');

  rysuj(pion, poziom, '+');

  for (x=0; x<szer; x=x+1) 
    rysuj(x, f_b(x), '*');

  for (y=wys-1; y>=0; y=y-1) {
    for (x=0; x<szer; x=x+1)
      printf("%c", rysunek[x][y]);
    printf("\n ");
  }

  printf("\n\n");

  return 0;
}
```
drukuje gwiazdkami wykres funkcji z pktu 5b powyżej. 
a)Zapoznać się z nim i dobrze zrozumieć jego działanie. Sprawdzić, jak reaguje program na zmianę stałych zdefiniowanych na jego początku.

b)Zmodyfikować program tak , żeby dodatkowo drukował kółeczkami (czyli literami 'o') wykres funkcji z pktu 5a.

c) Użyć tego samego programu do narysowania wykresu funkcji

    f(x) = x * sin x 

Ew. pozmieniać wartości stałych na początku programu, tak żeby wykres wyszedł ,,przekonujący''.

Zadanie 7
<a href="https://inf.ug.edu.pl/~stefan/Dydaktyka/WstepDoProg/Slajdy/lab-zadania3.pdf"> Zadania z funkcji do rozwiązania
</a>
