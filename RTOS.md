# RTOS

리눅스 커널, 드라이버, 안드로이드 프레임웤 개발하셨다.



MCU SoC. 32bit



우리가 쓰는 폰보다는 성능이 떨어져도, 8bit에 비해 비약적으로 높아짐. 



1기가헤르츠 m7코어, m4코어를 듀얼코어 형태로 장착.

요새는 성능이 좋아져서 외부에 SD램을 달 수 있다.(?)



### ARM

우리가 쓰는 스마트폰의 AP가 다 암. 퀄컴은 암꺼를 써서 모디파이했다.

CPU를 물리적인 CPU를 팔지 않고, 설계도를 만들어 판다. 



윈도우를 만들 때 x86을 모르고 만들 수 있겠니? ㄴㄴ



암코어 A(애플리케이션), R(리얼타임), M(마이크로)

A가 보통 스마트폰, r은 오토모티브, M은 마이크로 컨트롤러



모든지 추세를 알자.

#### Cortex-M

M7

하버드 아키텍쳐!! 캐시에 대한 얘기. 제품을 만들 때 가격을 배제하고 만들 순 없다. 

기타 이펙터 오픈소스!! 앰프에서 만들어주는 것.

#### 암 trustzone

트러스트 존이라는 특정 메모리 영역

도어락. 해커가 뚫나??

이 전에는 퍼포먼스가 되었다. 트러스트존으로 보안도 해결했다.

그럼 다음 세대는? maybe AI.

내가 코어를 고를 때, 뭐는 뭐가 되고 안되고를 알고 고르자. 내가 타겟으로 하는 녀석의 뭘 써야 하는가!



#### 스타트업 코드

주로 어셈블리를 쓴다. C를 쓰면 좀 더 빠르게 쓰기 위해서 C 안에 inline을 쓰기도 하지만,



암에서는 설계도를 팔고, 많은 회사들이 코어를 만든다.

ST. 우리나라 사람들이 여기서 만든 걸 쓴다. 한글 자료가 제일 많아서. STM 코어를 쓰면 그 안에 기능 뭐 아냐?? 몰라~

내가 주력으로 쓰는 vendor에서 어떤걸 쓰고, 어떤 특징이 있는지 잘 알자.

임베디드를 하고자 한다면(임베디드 하지 마세요!), vendor에서 칩을 만드는 걸 주시하자. 우리보다 앞서 생각하고 계속해서 만들어진다.



#### 툴

이클립스 같은 곳에서 만든 통합 툴.

벤더사에서 배포하는 툴. 유료 툴은 없다?

- **공짜라서**
- 안되는 거 없고
- 업데이트가 가장 빨리 반영되지

툴에 대한 제약은 없으니, 알아서 쓰라. printf() 쓰는 건 똑같지만, 이를 구성하기 위한 각각의 툴과 컴파일러 옵션은 다르다.

링킹. 여러 소스 파일들을 합칠 때 번지수를 재정렬 해준다.

부트 로더를 만들 때가 있다면, 꼭 신경 쓰자



STM을 써서 라이브러리를 받고 example을 찾아 갈 때, 디렉토리 밑에 들어가서 example을 찾자.

이 업계에서는 용어가 절반. 위의 예제들은 이 보드 안에 있는 각각의 기능들을 사용하기 위한 것. 코드에 있는 내용들은 직접 분석하자! 프로잖아?

#### 에코시스템

벤더에서 보드, 예제, 툴 등 개발을 위한 환경.

- discovery : 이것저것들 다 넣어주어 
- nucleo : 
- eval : 풀 피쳐. 얘가 가장 많은 예제들을 갖고 있다! eval 이니까!

내가 STM 말고 다른 걸 쓰게 됐다. 그럼 그녀석의 에코시스템을 보면 된다.



#### 프로젝트 실행

- MCU/MPU 셀렉터로 고르는 방법

- 보드 셀렉터로 고르는 방법

차이가 있다. 보드 셀렉터로 고르면, mpu에 연결된 설정값이 보이는데, mcu/mpu 셀렉터로 보면 설정값이 안 보인다.



만약 커스터마이징한 보드를 만들고 싶다면, mpu는 천 단위, ap는 억 단위; 10개 20개 만들걸로 뭘 쓴다면 있는 보드 사서 써라.



#### 동적/정적 라이브러리

DLL



#### 드라이버



#### CMSIS

cpu를 arm사의 cpu를 쓴다. cpu에 관련된 코드들이 cmsis에 있다. cortex 마이크로 소프트웨어 인터페이스 스탠다드의 약자. cpu는 우리꺼기 때문에, cpu를 다루는 코드들이 파편화 되는 것을 원치 않아! 그래서 표준을 만들었다.



#### 링커

ld 파일.



### Core

#### Startup 디렉토리 하위의~

시작하는 코드. 어셈블리어 ㅎㄷㄷ



main.c가 우리가 작업할 파일.



#### Firmware

단일 어플리케이션 하나만 짠다고 보면 된다.

펌웨어 업데이트



#### 팁

보드를 만들 때, 보드의 신호를 확인하는 LED나 삡 하는 애들을 넣어준다. 가장 간단한 방법!



하나의 핀(다리)이 하는 가장 간단한 일.

- 아웃풋일 때전기를 주거나, 받거나. 
- 인풋일 때 들어오는 전기를 확인하거나.



MCU의 플래시에 우리 프로그램을 다운로드. 이걸 시커먼거 큰거 옆에 시커먼거 작은거. 이게 프로그램을 다운로드 해준다. 그래서 디버거를 시리얼와이어로 살려준다. 기본적으로 serial wire를 많이 쓴다.



클럭을 설정. 내가 돈 주고 샀는데 80메가를 꼭 쓸꺼야 우이씨1

근데 클럭을 많이 쓴다는 것은, 전력을 많이 소모한다는 말.



#### 디버깅을 가능하게 하는 칩 아까 위에서 프로그램을 다운로드 받아준다는 거

이게 너무 옛날거면 안 된다~



#### 실습1 두 개의 LED를 500ms, 700ms로 깜빡이게 하라.



# Day 2

### RTOS 종류

대기업에서 RTOS에 돈을 많이 쓴다. 왜일까?

aws에서 freeRTOS를 인수한 이유.

azure mbed-OS에 돈을 많이 쓴 이유.

IoT를 위해서. 마이크로컨트롤러의 성능을 극대화 해야 하다보니~



메모리가 많이 증가했다고 봐야 256k 512k?

제품을 만들 때 남들보다 더 싸게 만드는 것이 중요.

어떤 세세한 기능들이 예전의 제품보다 지금의 제품이 더 많은 것을 지원해준다.



임베디드 리눅스도 하시고,



RTOS는 **실시간 OS**. time. 실시간성이란? 시계로 잰다. mcu 안에 timer 혹은 시계가 존재. clock. time에 관련돼서 실시간성. timer가 필요. 시간을 재야 되는 timer가 있어요. freeRTOS를 안 쓰고, ST사에서 제공해주는 라이브러리를 쓸 때는, HAL_Delay(ms 단위)를 썼다. 뭘 기준으로 ms? 시간을 재는 시계가 있어야 한다. 기준 타이머. **Systick** freeRTOS를 추가할 때 뜨는 워닝 : timer가 뭉칠 수도 있으니, 왠만하면 timer를 분간해서 써주세요.?



Timebase Source의 타이머들

각각의 타이머들은 특징이 있다. 간단한 것, 그보다 많은 기능, 그보다 많은 기능.



freeRTOS의 펑션은, osKernelStart()의 vTaskScheduler()에 의해 실행되고, 이 때 Main의 while()문은 실행되지 않는다. 실행이 될 수가 없다. why?

Main()부와 RTOS부. 

vTaskScheduler()에 의해 freeRTOS의 커널이 실행이 된다. 그래서 main의 while 부분이 돌지 않는다.

내 코드는 StartDefaultTask(void const * argument)에 넣는다.



ARM사가 CMSIS _os라는 펑션 리스트들을 제공해준다.

cmsis_os.c를 제공해주지 않는다. 내가 필요한 것만 포팅해서 직접 쓰면 된다. 그러기를 소스를 지원하지 않는 벤더사가 원한다. 단 ST만 지원해준다. 여기서 지원해주기 때문에! 우리는 cmsis_os를 하지 않는다~



FreeRTOS 함수를 통해 예제를 제공해주고,  ST는 해주지만.

freeRTOS.org에 나오는 함수 리스트들로 뭔가를 만들지 않는다.



Project Manager - Code Generator  - Generate peripheral  initialization ..

제너레이트로 만들어내는 코드를 .c, .h로 구분해서 제너레이팅 해주는 것.

이렇게 하면 필요한 코드들끼리 모여서 전체 소스 그림을 알아보기가 쉽다.

freeRTOS TaskManager

오늘의 목표 Task



## UART

uart 핀이 날라가서 deburger가 뭘 해준다. usb to com ? com port로 text가 달리는걸 볼 수 있다.



uart 1번이라는 포트가 저 핀만 쓰는 게 아니라, 다른 핀으로도 연결이 가능하다. 다른 핀으로 쓸 수 있는 핀이 정해져있는 게 있다. 핀을 바꾸는 이유가 뭐죠?

stdio.h에 printf가 있지.

우리가 쓰던 printf()는 lib에 잘 바디가 구성이 돼 있기 때문에 쓸 수 있었다. edge에서 제공해주는 라이브러리c나 펌웨어에서 제공해주는 libc는 풀피쳐는 아니지만, printf 정도는 있다. _write

stdout, stdin. 바꿀 수 있다는 말이 무슨 의미일까? uart로 출력하기 위해, __io_putchar()를 수정하였다.



#### 아무 것도 없는 보드위에 UART를 써서 helloworld 띄우기.

이거 해보셈. 쉬운가.



푸티를 이용해 통신하기. 

보드에서 지원하는 유아트1의 통신속도가 115200bps



### 우선순위

```c++
void MX_FREERTOS_Init(void)
{
	/* Create the thread(s) */
	xTaskCreate(vTaskFunction, "Task 1", 128, (void*)pcTextForTask1, 3, NULL );
	xTaskCreate(vTaskFunction, "Task 2", 128, (void*)pcTextForTask2, 4, NULL );
}
```



### Task

어떤 os에서는 thread. 뭐가 됐건~

RTOS라는 시스템이 돌 때, 

RTOS에서 안 짜고 firmware에서 짜면~ 일단 무조건 우리가 **짠 순서대로** 실행된다. 우리가 태스크를 나눠놓으면 kernel. kernel 객체가 여러 개. 여러 개가 돌면서 쓰는 하나의 작업 단위가 Task. 시간을 기준으로 동작한다. 내가 어떻게 작업 단위를 나눌 것이냐? 언제 실행될지를 구조화 해야 한다.

라운드 로빈. 시간을 일정하게 나누어 놓은 스케줄링.

우선순위를 위해 실시간성을 반영하여 선점형. 멀티태스크를 위해 시분할.



가상메모리. 프로세스. 프로세스가 하나인가?

태스크 변환할 때의 컨텍스트 스위칭, 암차원에서 뭘 안 해줌. 우리가 코딩해야 함.



#### 운영체제의 스케줄링

printf 글자를 찍는다. 서로 다른 태스크. 글자를 찍는 동안

```c++
/* Delay for a period. */
for( ul = 0; ul < mainDELAY_LOOP_COUNT; ul++ )
{
}
```

cpu는 쉬지 않았다. 증가 연산, 비교 연산. cpu가 딜레이 되지 않는다. 시간 타이밍이 아다리가 안 맞아서 printf가 핑퐁하지 않는다. busywait. 



#### block State

어떤 태스크가 이벤트를 대기하도록 만들면 block 상태가 된다.

1. 타임에 의해
2. 다른 task나 interrupt에 의해



RTOS에서 하고자 하는 건, 내가 하는 일을 작업단위로 나누고 싶고, 원하는대로 동작하게 하고, 

실시간성을 위해 우선순위. 필요에 따라 우선순위를 바꿀 수도 있을 것.



freeRTOS의 설정값들을 보고 싶다면

Inc 하위에 FreeRTOSConfig.h값을 본다.

FreeRTOS.h, FreeRTOSConfig.h에 RTOS에 필요한 것들이 작성돼 있다.

정의, 함수.

자원 자체가 제한적. 타겟이 되는 아이들이 작은 자원일 뿐만 아니라 상당히 다양한 곳에서 동작. 되게 작은 곳에서도 동작하도록 해야 한다.



#### vTaskPrioritySet()

#### uxTaskPriorityGet()

#### vTaskDelete()

주의해야할 점.

태스크가 무한루프를 도는 코드가 아니라 동작 후에 종료되는 코드라면? 그럼에도 명시적으로 태스크를 삭제 해주어야 한다. 이렇게 명시적으로 지워줘야 커널 객체에서 자원을 회수할 수 있다.

태스크 안에서 태스크를 만들어 수행할 수 있다. 

