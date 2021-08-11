# Day7 .문자와 문자열

## 입출력 / Stream 
스트림에 일련의 바이트 문자열을 기록하여 데이터를 입력 받거나 출력한다. 
즉, 스트림으로 부터 데이터를 읽고 출력한다.

## c언어가 제공하는 표준 입출력 스트림
스트림     설명              장치
stdin      표준 입력       키보드 //scanf
stdout    표준 출력       화면  //printf
stderr     표준 에러       화면
stdprn    표준 프린터    프린터
stdaux    표준 보조       직렬포트


## EOF End of File 
c언어 파일에 끝에 도달할때 EOF를 리턴
컨트롤 z로 EOF 발생 


## 문자형
```c
char ch;
unsigned char j;
char k;

ch = 2;
j = 200;
k = 'a';

printf( "문자형 변수 ch = %d \n", ch );
printf( "문자형 변수 i = %u \n", j );
printf( "문자형 변수 k = %d \n", k );
printf( "문자형 변수 k = %c \n", k );
```

## 문자열 상수 & 변수
```c
char str[] = "코리아 아이티 C언어";   //상수
char *j = "I love CC";           //변수

//char *j ; // 다른 문자열을 가르킬수있다
// j = "코리아";
// j = "아이티";

printf( "문자열형 변수 str의 값은 %s \n", str );
printf( "문자열형 상수 j의 값은 %s \n", j );
```

## 문자열 배열
```c
char * pClass[] ={"코리아아 아이티","시언어특강","문자열배열"};

printf(" %d \n",sizeof(pClass)/sizeof(pClass[0]));
printf("* pClass[] %d \n",sizeof(pClass));
printf("pClass[0] %d \n",sizeof(pClass[0]));

for (int i = 0 ; i < sizeof(pClass)/sizeof(pClass[0]); i++) {
    puts( pClass[i] );
}    
```


## 문자관련 레퍼런스 살펴보기




