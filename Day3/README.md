  # D3 제어문, 조건문, 반복문, 기타제어문
  
  ### 순서도 그리기 
 [diagrams.net](https://app.diagrams.net)
 [codeup.kr]( https://codeup.kr/problem.php?id=1065)
  
 ### 제어문
  * c언어 절차지향, 명령형 프로그램
  * 순차적으로 실행되는 프로그램의 흐름을 제어하기 위해 사용
  * {}중괄호 영역을 블록(block)
  
  
  
  ## C언어에서 사용하는 기본 조건문
  1. if 문
  2. if / else 문
  3. if / else if / else 문
  4. switch 문
  5. 삼향연산자 
  > (조건) ? (조건이 참일 때 수행) : (조건이 거짓일 때 수행)
  
  ## if 문
  
  비교연산자
  num이 0보다 작으면 
  num이 0보다 크면
  num이 0이면 
  
  ### If 문의 기본형태 
  
  if(조건식){
    결과가 참일떄 실행하는 명령문 
  }
  
  ```c 
  #include <stdio.h>
  
  int main(void){
      int num;
      printf("정수 입력: ");
      scanf("%d", &num);
      
      if(num < 0)     // num이 0보다 작으면 
        printf("num 값은 0보다 작다 \n");
      
      if(num > 0)     // num이 0보다 크면
        printf("num 값은 0보다 크다 \n");
      
      if(num == 0)     // num이 0이면 
        printf("num 값은 0이다 \n");
      
      return 0;
  }
  ```
  
  ### if / else 문
  if문과 함께 사용되는 else문은 조건식의 결과가 거짓이면 명령문 수행 
  
  ```c
  #include <stdio.h>
  
  int main(void)
  {
      int num;
      printf("정수 입력: ");
      scanf("%d", &num);
      
      if(num < 0)
        //true
        printf("num 0보다 작다. \n");
      else
        //false
        printf("num 0보다 작지 않다. \n");
      
      return 0;
  }
  ```
  
  ### if / else if / else 문
  
  ```c
  #include <stdio.h>
  
  int main(void)
  {
  int num;
  printf("정수를 입력하세요: ");
  scanf("%d", &num);
  
  if(num<0)
  printf("입력 값은 0보다 작다. \n");
  else if (num==0)
  printf("입력 값은 0이다 \n");
  else
  printf("입력 값은 0보다 작지 않다. \n");
  
  return 0;
  }
  ```
  
  ## switch 문
  switch 문은 if / else 문과 마찬가지로 주어진 조건 값의
  결과에 따라 프로그램이 다른 명령을 수행하도록 하는 조건문입니다.
  가독성이 더 좋으며, 컴파일러가 최적화를 쉽게 할 수 있어 속도 또한 빠른 편
  
  ```c
#include <stdio.h>

int main(void)
{
    int num;
    printf("1이상 5이하의 정수 입력: ");
    scanf("%d", &num);

    switch(num)
    {
        case 1:
            printf("1  \n");
            break;
            
        case 2:
            printf("2 \n");
            break;
            
        case 3:
            printf("3 \n");
            break;
        
        case 4:
            printf("4 \n");
            break;
        
        case 5:
            printf("5 \n");
            break;
        
        default:
            printf(" 1이상 5이하의 정수 \n");
    }
    return 0;
}
  ```
  ```c
  #include <stdio.h>
  
  int main(void)
  {
  char ch = 'a';
  
  switch (ch)
  {
  case 'a':
  case 'A':
  printf(" A입니다.\n");
  break;
  case 'b':
  case 'B':
  printf("B입니다.\n");
  break;
  case 'c':
  case 'C':
  printf(" C입니다.\n");
  break;
  case 'd':
  case 'D':
  printf(" D입니다.\n");
  break;
  case 'f':
  case 'F':
  printf("F입니다.\n");
  break;
  default:
  printf("(A, B, C, D, F)");
  break;
  }
  return 0;
  }
  ```

 ## 반복문 
  1. while 문 : 조건식을 만족할때 까지 명령문을 반속실행 
  2. do / while 문 : 조건에 상관없이 루프를 한번 실행 후에 조건식 검사
  3. for 문 : 조건문 -> 초기값, 조건, 증감값을 모두 포함한 반복문 
  
  ### while 문
  ```c
  #include <stdio.h>
  
  int main(void)
  {
      int num=0;
      
      while(num<5)
      {
        printf("Hello world! %d \n", num);
        num++;
      }
      return 0;
  }
  ```
```c
#include <stdio.h>
int main(void)
{
    int cur=2;
    int is=0;

    while(cur<10)       // 2단부터 9단까지 반복
    {
        is=1;           // 새로운 단의 시작을 위해서
        while(is<10)    // 각 단의 1부터 9의 곱을 표현
        {
            printf("%d×%d＝%d \n", cur, is, cur*is);
            is++;
        }
        cur++;          // 다음 단으로 넘어가기 위한 증가
        printf("\n");
    }
    return 0;
}
```
  
  ### do / while 문
  
  ```c
  #include <stdio.h>
  
  int main(void)
  {
    int total=0, num=0;
  
  do
  {
    printf("정수 입력(0 to quit): ");
    scanf("%d", &num);
    total += num;
  }while(num!=0);
  
  printf("합계: %d \n", total);
  return 0;
  }
  ```
  ```c
#include <stdio.h>

int main(void)
{
    int dan=0, num=1;
    printf("몇 단? ");
    scanf("%d", &dan);

    do 
    {
        printf("%d×%d＝%d \n", dan, num, dan*num);
        num++;
    }while(num<10);

    return 0;
}
```
### for 문
  
  //0부터 num까지의 덧셈, num은 입력받음
  ```c
  #include <stdio.h>
  
  int main(void)
  {
  int total=0;
  int i, num;
  printf("0부터 num까지의 덧셈, num은? ");
  scanf("%d", &num);
  
  for(i=0; i<num+1; i++)
  total+=i;
  
  printf("0부터 %d까지 덧셈결과: %d \n", num, total);
  return 0;
  }
  ```
  ```c
#include <stdio.h>

int main(void)
{
    int cur, is;

    for(cur=2; cur<10; cur++)
    {
        for(is=1; is<10; is++)
            printf("%d×%d＝%d \n", cur, is, cur*is);

        printf("\n");
    }
    
    return 0;
}
  ```
  
  ## 기타제어문
  ### 루프의 제어 
  * continue 문과 break 문은 일반적인 루프의 흐름을 제어 
  
  
  ## continue 문
  continue 문은 루프 내에서 사용하여 해당 루프의 나머지 부분을 건너뛰고, 
  바로 다음 조건식을 체크, 반복문 내에서 특정 조건에 대한 예외 처리할떄 사용 
  
                         
