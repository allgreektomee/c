# day8 포인터 심화

기본 포인터, 배열 day5,6 복습 
배열 포인터 
문자열 포인터
포인터 함수 

## 포인터 
```c
#include <stdio.h>

void printStrP( char *ptext );
void printStrA( char text[] );

int main(void)
{
    //1.포인터 자료형 출력 
    printf( "1.포인터 자료형 출력 " );
    //문자형
    char   *p_char;

    //정수형
    short  *p_short;
    int    *p_int;
    long   *p_long;

    //실수형
    float  *p_float;
    double *p_double;

    printf( "char 크기 : %d 바이트 \n", sizeof(char) );
    printf( "short 크기 : %d 바이트 \n", sizeof(short) );
    printf( "int 크기 : %d 바이트 \n", sizeof(int) );
    printf( "long 크기 : %d 바이트 \n", sizeof(long) );
    printf( "float 크기 : %d 바이트 \n", sizeof(float) );
    printf( "double 크기 : %d 바이트 \n", sizeof(double) );

    printf( "char 포인터의 크기 : %d 바이트 \n", sizeof(p_char) );
    printf( "short 포인터의 크기 : %d 바이트 \n", sizeof(p_short) );
    printf( "int 포인터의 크기 : %d 바이트 \n", sizeof(p_int) );
    printf( "long 포인터의 크기 : %d 바이트 \n", sizeof(p_long) );
    printf( "float 포인터의 크기 : %d 바이트 \n", sizeof(p_float) );
    printf( "double 포인터의 크기 : %d 바이트 \n", sizeof(p_double) );


    // char 크기 : 1 바이트 
    // short 크기 : 2 바이트 
    // int 크기 : 4 바이트 
    // long 크기 : 8 바이트 
    // float 크기 : 4 바이트 
    // double 크기 : 8 바이트 

    // char 포인터의 크기 : 8 바이트 
    // short 포인터의 크기 : 8 바이트 
    // int 포인터의 크기 : 8 바이트 
    // long 포인터의 크기 : 8 바이트 
    // float 포인터의 크기 : 8 바이트 
    // double 포인터의 크기 : 8 바이트 


    //2.포인터 사용
    printf( "\n 2.포인터 사용 \n" );
    int n1 = 0;
    int n2 = 0;
    int* pointer1;
    int* pointer2;

    pointer1 = &n1;
    *pointer1 = 1;
    printf( "%d, %d \n", n1, *pointer1 );        

    pointer2 = &n1;
    *pointer2 = 2;
    printf( "%d, %d, %d \n", n1, *pointer1, *pointer2 );    

    pointer1 = &n2;
    *pointer1 = 3;
    printf( "%d, %d, %d \n", n1, n2, *pointer1 );

    pointer2 = &n2;
    *pointer2 = 4;                                        
    printf( "%d, %d, %d, %d\n", n1, n2, *pointer1, *pointer2 );



    return 0;
}
```

## 포인터 함수
```c
#include <stdio.h>

void change_x1( int x1 );
void change_x2( int *x2 );

void main( void ) {
    int x;

    x = 5;
    printf( "함수를 호출하기 전 x 값 : %d \n", x );

    change_x1( x );
    printf( "change_x1() 함수를 호출한 후의 x 값 : %d \n", x );

    change_x2( &x );
    printf( "change_x2() 함수를 호출한 후의 x 값 : %d \n", x );
}

void change_x1( int x1 ){
    x1 = 50;
}

void change_x2( int *x2 ){
    *x2 = 100;
}
```

## 포인터 배열 함수

```c
#include <stdio.h>

void print_pxy( int* pxy[2] );

void main( void ) {
    int x = 0, y = 0;
    int *pxy[2];

    pxy[0] = &x;
    pxy[1] = &y;

    *pxy[0] = 5;
    *pxy[1] = 10;

    print_pxy( pxy );
}

void print_pxy( int* pxy[2] ){
    printf( "pxy[0] = %d \n", *pxy[0] );
    printf( "pxy[1] = %d \n", *pxy[1] );
}
```


------- 
```c


#include <stdio.h>
#include <string.h>

void printStrP( char *ptext );
void printStrA( char text[] );

int main(void){
    //1.포인터 자료형 출력 
    printf( "1.포인터 자료형 출력 " );
    //문자형
    char   *p_char;

    //정수형
    short  *p_short;
    int    *p_int;
    long   *p_long;

    //실수형
    float  *p_float;
    double *p_double;

    printf( "char 크기 : %d 바이트 \n", sizeof(char) );
    printf( "short 크기 : %d 바이트 \n", sizeof(short) );
    printf( "int 크기 : %d 바이트 \n", sizeof(int) );
    printf( "long 크기 : %d 바이트 \n", sizeof(long) );
    printf( "float 크기 : %d 바이트 \n", sizeof(float) );
    printf( "double 크기 : %d 바이트 \n", sizeof(double) );

    printf( "char 포인터의 크기 : %d 바이트 \n", sizeof(p_char) );
    printf( "short 포인터의 크기 : %d 바이트 \n", sizeof(p_short) );
    printf( "int 포인터의 크기 : %d 바이트 \n", sizeof(p_int) );
    printf( "long 포인터의 크기 : %d 바이트 \n", sizeof(p_long) );
    printf( "float 포인터의 크기 : %d 바이트 \n", sizeof(p_float) );
    printf( "double 포인터의 크기 : %d 바이트 \n", sizeof(p_double) );


    // char 크기 : 1 바이트 
    // short 크기 : 2 바이트 
    // int 크기 : 4 바이트 
    // long 크기 : 8 바이트 
    // float 크기 : 4 바이트 
    // double 크기 : 8 바이트 

    // char 포인터의 크기 : 8 바이트 
    // short 포인터의 크기 : 8 바이트 
    // int 포인터의 크기 : 8 바이트 
    // long 포인터의 크기 : 8 바이트 
    // float 포인터의 크기 : 8 바이트 
    // double 포인터의 크기 : 8 바이트 


    //2.포인터 사용
    printf( "\n 2.포인터 사용 \n" );
    int n1 = 0;
    int n2 = 0;
    int* pointer1;
    int* pointer2;

    pointer1 = &n1;
    *pointer1 = 1;
    printf( "%d, %d \n", n1, *pointer1 );        

    pointer2 = &n1;
    *pointer2 = 2;
    printf( "%d, %d, %d \n", n1, *pointer1, *pointer2 );    

    pointer1 = &n2;
    *pointer1 = 3;
    printf( "%d, %d, %d \n", n1, n2, *pointer1 );

    pointer2 = &n2;
    *pointer2 = 4;                                        
    printf( "%d, %d, %d, %d\n", n1, n2, *pointer1, *pointer2 );


    //3.포인터 배열
    printf( "\n 3.포인터 배열" );
    int x = 0, y = 0;
    int *pArray[2];

    pArray[0] = &x;
    pArray[1] = &y;

    *pArray[0] = 5;
    *pArray[1] = 10;

    printf( "x = %d, pArray[0] = %d \n", x, *pArray[0] );
    printf( "y = %d, pArray[1] = %d \n", y, *pArray[1] );

    printf( "x + y = %d \n", x + y );
    printf( "x + y = %d \n", *pArray[0] + *pArray[1] );

    //4.1차원 배열
    printf( "\n 4. 1차원 배열" );
    char txtArray[10] = "Koxea IT";

    puts( txtArray );
    txtArray[2] = 'r';
    puts( txtArray );

    printf( "txtArray[0] = ASCII %3d, %c \n", txtArray[0], txtArray[0] );
    printf( "txtArray[1] = ASCII %3d, %c \n", txtArray[1], txtArray[1] );
    printf( "txtArray[2] = ASCII %3d, %c \n", txtArray[2], txtArray[2] );
    printf( "txtArray[3] = ASCII %3d, %c \n", txtArray[3], txtArray[3] );
    printf( "txtArray[4] = ASCII %3d, %c \n", txtArray[4], txtArray[4] );
    printf( "txtArray[5] = ASCII %3d, %c \n", txtArray[5], txtArray[5] );
    printf( "txtArray[6] = ASCII %3d, %c \n", txtArray[6], txtArray[6] );
    printf( "txtArray[7] = ASCII %3d, %c \n", txtArray[7], txtArray[7] );
    printf( "txtArray[8] = ASCII %3d, %c \n", txtArray[8], txtArray[8] );


    //5. 1차원 배열 포인트
    printf( "\n 6. 1차원 배열 포인트 \n" );
    char textArr[] = "Korea";
    char *ptext;

    ptext = textArr;

    puts( textArr );        
    puts( ptext );        

    strcpy( ptext, "IT" ); //#include <string.h>

    puts( textArr );        
    puts( ptext );        


    //6. 1차원 배열 포인트 함수
    printf( "\n 6. 1차원 배열 포인트 함수" );
    char charArray[] = "\nKorea IT";

    printStrP( charArray );
    printStrA( charArray );

    return 0;
}

void printStrP( char *ptxt )
{
    puts( ptxt );
}

void printStrA( char text[] )
{
    puts( text );
}
```
