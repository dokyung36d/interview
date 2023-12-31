# Backend-Interview


## Contents
- [DataBase](#DataBase)
- [OS](#OS)
- [Network](#Network)
- [Algorithm](#Algorithm)
- [Data Structure](#Data-Structure)
- [Spring(백엔드)](#Spring백엔드)
- [DeepLearning(Option)](#DeepLearning)


## DataBase
<details>
    <summary>Data Definition Language의 예시</summary>
    </br>
    <p>alter : 데이터베이스에 이미 존재하는 object의 구조를 변경할 때 사용</p>
    <p>create : 데이터베이스에 새로운 object를 만들 시 사용</p>
    <p>drop : 데이터베이스에 이미 존재하는 object를 삭제할 때 사용</p>
</details>

<details>
    <summary>Data Manipulation의 예시</summary>
    </br>
    <p>select : 데이터베이스 테이블에서 데이터를 검색할 때 사용</p>
    <p>insert : 데이터베이스 테이블에서 데이터를 새롭게 삽입할 때 사용</p>
    <p>update : 데이터베이스 테이블에 존재하던 데이터를 수정할 때 사용</p>
    <p>delete : 데이터베이스 테이블에 존재하던 데이터를 삭제할 때 사용</p>

</details>

<details>
    <summary>Data Control language의 예시</summary>
    </br>
    <p>commit : 데이터 베이스에 트랜잭션 operation이 정상적으로 종료된 것</p>
    <p>rollback : 트랜잭션 과정에서 문제가 발생하여 트랜잭션 이전 상태로 돌아가는 것</p>
    <p>grant : 특정 유저에게 데이터베이스 object에 대한 권한을 부여하는 것</p>
    <p>revoke : 특정 유저에게 부여했던 권한을 무효화하는 작업</p>
</details>

<details>
    <summary>데이터베이스에서의 index의 장단점</summary>
    </br>
    <p>장점 : 인덱스를 이용하여 더욱 빨리 query 결과를 얻을 수 있다. (정렬된 상태가 유지된다.)</p>
    <p>단점 : insert 연산 등 일부 연산에서는 오히려 성능이 하락할 수 있다.</p>
</details>

<details>
    <summary>데이터베이스에서의 정규화란(총 3단계 존재)</summary>
    </br>
    <p>정규화 : 하나의 릴레이션에서 오직 하나의 의미만이 존재하도록 일레이션을 분해하는 과정</p>
    <p>데이터의 일관성, 최소의 데이터 중복, 최대한의 데이터 유연성 결과를 가져옴</p>
    <p>1. 제 1정규형 : 테이브르이 컬럼이 원자 값(하나의 값)을 가지도록 분해</p>
    <p>2. 제 2정규형 : 제 1 정규형을 만족, 기본키가 아닌 속성이 기본키에 완전 종속이도록 분해</p>
    <p>3. 제 3 정규형 : 제 2 정규형을 만족, 기본키를 제외한 속성들 간의 이행 종속성이 없어야 한다.</p>
</details>

<details>
    <summary>데이터베이스에서 발생하는 이상현상들(3가지)</summary>
    </br>
    <p>이상 현상 : 데이터베이스 테이블을 잘목 설계하여 데이터를 삽입, 삭제, 수정할 때 새익는 논리적 오류</p>
    <p>1. 삽입 이상 : 데이터를 삽입할 때 특정 속성에 해당되는 값이 없어 NULL을 입력해야 하는 현상</p>
    <p>2. 갱신 이상 : 중복된 데이터 중 일부만이 수정되어 중복된 데이터들이 서로 모순을 일으키는 현상</p>
    <p>3. 삭제 이상 : 어떤 데이터를 삭제할 경우, 의도치 않은 다른 정보까지 삭제하는 현상</p>
</details>

<details>
    <summary>scale-up 과 scale-out이란</summary>
    </br>
    <p>scale-up : 하나의 서비의 하드웨어들을 업그레이드</p>
    <p>scale-out : 여러 대의 서버를 추가하는 것</p>
</details>

<details>
    <summary>RDBMS와 NoSQL의 차이점</summary>
    </br>
    <p>RDBMS : 모든 데이터를 2차원으로 표현</p>
    <p>장점 : 스키마에 맞춰 관리, 정합성이 보장됨</p>
    <p>단점 : 시스템이 커질 수록 쿼리 복잡, 성능 저하, scale out이 어려움</p>
    </br>
    <p>NoSQL : 데이터간의 관계를 정의하지 않음, 스키마 존재X - >자유롭게 데이터 관리 가능</p>
    <p>장점 : 스키마없이 Key-Value형태로 데이터 관리 가능, scale-up, scale-out 모두 가능</p>
    <p>단점 : 데이터 중복이 발생할 수 있음.</p>
    </br>
    <p>RDBMS가 유리한 경우 : 데이터 구조 명확, 스키마가 중요한 경우</p>
    <p>NoSQL이 유리한 경우 : 정확한 데이터 구조가 없는 경우, 데이터가 변경/확장될 수 있는 경우</p>
</details>

<details>
    <summary>트랜잭션이란</summary>
    </br>
    <p>한 작업의 완정성을 보장</p>
    <p>작업들을 모두 처리하거나 실패할 경우 실행 이전의 상태로 되돌리는 것</p>
    <p>즉, Commit되거나 Rollback됨</p>
</details>

<details>
    <summary>데이터베이스에서의 락 종류</summary>
    </br>
    <p>1. 공유락(LS, Shared Lock) : 읽기를 진행할 때 사용된는 락, 같은 공유락끼리는 동시에 접근 가능</p>
    <p>2. 배타락(LX, Exclusice Lock) : 데이터를 변경할 때 사용되는 락, 해당 락이 끝나기 전까지는 어떠한 접근도 허용되지 않음.</p>
    <p></p>
</details>

<details>
    <summary>DB 튜닝이란</summary>
    </br>
    <p>1단계 : DB설계 튜닝 (데이터 모델링, 인덱스 설계, 용량 산정)</p>
    <p>2단계 : DBMS 튜닝 (CPU, 메모리, I/O 관점) ex) Buffer크기, Cache 크기</p>
    <p>3단계 : SQL 튜닝 (Join, Indexing, SQL Executing Plan)</p>
    <p></p>
</details>

<details>
    <summary>inner join과 outer join의 차이</summary>
    </br>
    <p>inner join : 서로 연관된 내용만을 검색하는 조인</p>
    <p>outer join : 한쪽에 데이터가 없더라도 데이터가 있는 쪽의 내용을 전부 출력하는 조인</p>
    <p>outer ㅓoin에는 Left, Right, FULL outer join이 존재함</p>
</details>

<details>
    <summary>group by의 역할</summary>
    </br>
    <p>특정 column을 기준으로 연산한 결과를 집계 키로 설정하여 그룹을 지음 </p>
    <p></p>
    <p></p>
</details>

<details>
    <summary>DELETE, TRUNCATE, DROP의 차이점</summary>
    </br>
    <p>DELETE : 데이터는 지우지만 테이블 용량은 줄어들지 않음. 삭제 후 복구 가능</p>
    <p>TRUNCATE : 전체 데이터를 삭제하는 방법. 테이블의 용량은 줄어듦. 인덱스도 삭제됨. 테이블은 삭제되지 않지만 데이터는 복구할 수 없음</p>
    <p>DROP : 테이블 자체를 완전히 삭제하는 방식. 삭제 후 복구 불가</p>
</details>

<details>
    <summary>데이터베이스 클러스터링과 리플리케이션의 차이</summary>
    </br>
    <p>클러스터링 : 여러 개의 DB를 수평적인 구조로 구축, 동기 방식</p>
    <p>장점 : 데이터 동기화 -> 일관성있는 데이터, 높은 가용성(하나의 DB가 죽더라도 에러 X), 로드 밸런싱</p>
    <p>단점 : 저장소 하나를 공유할 경우 병목현상 발생, 운영 비용 상승</p></br>
    <p>리플리케이션 : 여러 개의 DB를 수직적인 구조로 구축, 비동기 방식</p>
    <p>장점 : 대부분의 DB 요청은 읽기 요청, 레플리케이션으로도 충분한 성능, 지연 시간 거의 없음</p>
    <p>단점 : 노드 들간의 데이터 동기화가 보장되지 않음. Master DB가 고장날 경우 복구 및 대처 어려움</p>
</details>

<details>
    <summary>HAVING과 WHERE의 차이</summary>
    </br>
    <p>HAVING : 그룹을 필터링하는데 사용(그룹화 혹은 집계 이후)</p>
    <p>WHERE : 개별 행을 필터링 하는데 사용(그룹화 혹은 집계 이전)</p>
</details>

<details>
    <summary>JOIN에서의 ON과 WHERE의 차이</summary>
    </br>
    <p>ON : JOIN이 시작되지 이전에 필터링을 진행</p>
    <p>WHERE : JOIN이 진행된 이후 해당 조건에 맟춰 필터링을 진행</p>
</details>

## OS

## Network

<details>
    <summary>HTTP프로토콜이란</summary>
    </br>
    <p>서버/클라이언트 모델을 따르는 데이터를 주고받기 위한 프로토콜</p>
    <p>특징 1: stateless(상태 정보를 저장하지 않음)</p>
    <p>특징 2: Connectionless(요청을 전송한 뒤 연결을 끊음.</p>
    </br>
    <p>장점 1: 연결 상태 처리, 상태 정보 관리 필요 X -> 서버 디자인 간단.</p>
    <p>장점 2: 각각의 HTTP 요청에 독립적으로 전송해주면 됨</p>
    </br>
    <p>단점 1: 이전 통신에 대한 정보가 없으므로 매번 인증 필요</p>
    <p>이를 해결하기 위해 쿠기, 세션을 활용</p>
</details>

<details>
    <summary>구글 접속 과정</summary>
    </br>
    <p>1. 사용자가 웹 브라우저에 URL 입력</p>
    <p>2. DNS서버를 이용하여 URL주소에 해당되는 IP 주소를 얻음</p>
    <p>3. 해당 IP 주소로 TCP 연결 설정</p>
    <p>4. 해당 웹 서버로 HTTP 요청 메시지를 보냄.</p>
    <p>5. 웹 서버는 요청에 알맞은 HTTP 응답 메시지를 보냄</p>
    <p>6. 클라이언트에게 도착한 HTTP 응답 메시지는 웹 페이지에 의해 변환, 출력됨.</p>
</details>

<details>
    <summary>OSI 7계층이란?, 각 계층에 대한 설명</summary>
    </br>
    <p>OSI 7계층 : 네트워크에서 데이터가 전송되는 단계를 7단계로 나눈 것.</p>
    <p>1계층(물리 계층) : 데이터를 전기 신호로 변환. 오직 데이터를 전송, 데이터를 전혀 신경쓰지 않음</p>
    <p>2계층(데이터 링크 계층) : 데이터의 물리적인 전송을 담당. 맥주소를 통해 통신함. 에러 검출/재전송/흐름 제어 등을 관리함.</p>
    <p>3계층(네트워크 계층) : 패킷을 목적지까지 빠르게 전송하기 위한 계층, IP주소, 라우터를 통해 라우팅 경로를 search</p>
    <p>4계층(전송 계층) : 최종 수신 프로세스로 데이터를 전송하는 역할, 패킷 생성 및 전송, TCP, UDP가 해당됨.</p>
    <p>5계층(세션 계층) : 양쪽 컴퓨터들이 통신을 하기 위해 세션을 만들기 위한 계층. 양 끝단의 응용 프로세스가 통신을 관리하기 위한 방법을 제공. TCP/IP 세션을 만들고 초기화하는 책임을 진다.</p>
    <p>6계층(표현계층) : 데이터의 형식을 결정하는 계층. 데이터 표현이 상이한 응용 프로세스의 독립성을 제공, 암호화. 코드간의 번역을 담당하는 계층</p>
    <p>7계층(응용 계층) : 사용자에게 통신을 위한 서비스 제공, 인터페이스 역할. 응용 프로세스와 직접 관계하여 일반적인 응용 서비스를 수행.</p>

</details>

## Algorithm

## Spring백엔드

<details>
    <summary>test</summary>
    </br>
    <p>test</p>
</details>

<details>
    <summary>Web Application Server와 Web Server의 차이점</summary>
    </br>
    <P>Web Application Server : 비즈니스 로직을 넣을 수 있음. 주로 동적인 컨텐츠를 담당함(DB 접근, 데이터 처리)</p>
    <P>Web Server : 비즈니스 로직을 담당할 수 없음. 주로 정적인 콘텐츠를 담당함. (HTTP, JavaScript, CSS등)</p>
</details>

<details>
    <summary>Spring Framework의 특징</summary>
    </br>
    <p>1. 컨테이너를 통해 객체를 직접 관리</p>
    <P>2. 제어의 역전(IoC) : 제어권이 개발자가 아닌 프레임워크가 가지고 있어 프레임워크가 개발자의 코드를 호출한다.</p>
    <P>3. 의존성 주입(DI) : 계층, 서비스에서 의존성이 존재할 경우 외부에서 주입해준다.</p>
    <P>4. 관점 지향 프로그래밍(AOP) : 보안 등과 같이 공통적으로 사용하는 기능의 경우 해당 기능을 분리하여 관리한다.</p>
</details>

<details>
    <summary>@RequestBody, @RequestParam, @ModelAttribute의 차이점</summary>
    </br>
    <p>@RequestBody : 클라이언트가 전송한 JSON형태의 HTTP Body 내용을 java 객체로 변환해주는 역할</p>
    <p>@RequestParam : 1개의 HTTP 요청 parameter를 받기 위해 사용</p>
    <p>@ModelAttribute : HTTP내부의 값들을 Getter, Setter, 생성자를 통해 주입하기 위해 사용. (Getter, Setter, 생성자는 미리 정의되어 있어야 함)</p>
</details>

<details>
    <summary>Spring MVC란</summary>
    </br>
    <p>Model : 데이터 관리 및 비즈니스 로직을 처리하는 부분</p>
    <p>View : 비즈니스 로직의 처리 결과를 통해 유저 인터페이스가 표현되는 구간</p>
    <p>Controller : 사용자의 용청을 처리하고 Model과 View사이를 중개하는 역할</p>
</details>

<details>
    <summary>MVC의 추가 구성요소(MVC 제외)</summary>
    </br>
    <p>DispatcherServlet : 클라이언트에게 요청을 받아 응답까지의 MVC 처리 과정을 통제</p>
    <p>HandlerMapping : 클라이언트의 요청 URL을 처리할 Controller를 결정</p>
    <p>HandlerAdapter : HandlerMapping을 통해 결정된 핸들러 정보로 해당 메소드를 직접 호출해주는 역할</p>
    <p>ViewResolver : Controller의 처리 결과를 생성할 View를 결정</p>
</details>

<details>
    <summary>Spring MVC의 전체적인 흐름</summary>
    </br>
    <p>1. 클라언트가 URL을 통해 요청을 전송</p>
    <p>2. Dispatcher Servlet은 해당 요청을 처리할 컨트롤러를 찾는다.</p>
    <p>3. Dispatcher Servlet은 핸들러 어댑터에게 요청의 전달을 맡김</p>
    <p>4. Handler Adpater는 해당 컨트롤러에게 요청을 전달.</p>
    <p>5. 컨트롤러는 비즈니스 로직을 처리한 후 반환할 뷰의 이름을 반환</p>
    <p>6. Dispatcher Sevlet은 ViewResolver를 통해 반환할 뷰를 결정</p>
    <p>7. Dispatcher Servlet은 View에 전달할 데이터를 추가한다.</p>
    <p>8. 데이터가 추가된 View를 반환한다.</p>
</details>

<details>
    <summary>스프링 빈의 라이프사이클</summary>
    </br>
    <p>스프링 IoC 컨테이너 생성 -> 스프링 빈 생성 -> 의존 관계 주입 -> 초기화 콜백 메소드 호출 -> 사용 -> 소멸 전 콜백 메소드 호출 -> 스프링 종료</p>
    <p>빈 생명주기 콜백 방법</p>
    <p>1. 인터페이스(InitilaizingBean, DisposableBean)</p>
    <p>2. 설정 정보에 초기화 메소도, 종료 메소드 지정, @Bean에서 지정</p>
    <p>3. @PostConstruct, @PreDestroy 어노테이션 지원</p>
</details>

<details>
    <summary>Spring Filter와 Interceptor란, 사용예시</summary>
    </br>
    <p>필터 : 요청과 응답을 거른 뒤 정제하는 역할, 톰캣과 같은 웹 컨테이너에 의해 관리, 스프링 범위 밖에서 처리</p>
    <p>사례 : 보안 인증, 인가, 요청 검사, 데이터 압축 및 인코딩, Spring과 분리하고자 하는 기능</p>
    <p>Interceptor : 요청에 대한 작업 전/후로 요청, 참조를 가로채 가공. 스프링 컨텍스트에서 동작함.</p>
    <p>사례 : 세부적인 보안 및 인증, Controller로 넘겨주는 데이터 가공</p>
</details>

<details>
    <summary>AOP프로그래밍이란</summary>
    </br>
    <p>핵심 비즈니스 로직에 존재하는 공통 사랑을 분리하여 각각 모듈화하는 것을 의미.</p>
    <p>주로 인증, 로깅, 트랜잭션 처리에 사용됨</p>
    <p>장점 : 중복 코드 제거, 재활용성 극대화, 변화 수용 용이성</p>
</details>

<details>
    <summary>Lombok 라이브러리란</summary>
    </br>
    <p>메소드를 컴파일 하는 과정에서 개입하여 추가적인 코드를 생성함.(어노테이션 프로세싱)</p>
    <p>EX) Getter, Setter</p>
</details>

<details>
    <summary>서블릿(Servlet)이란?</summary>
    </br>
    <p>클라인언트의 요청을 처리, 결과를 반환하는 Servlet 클래스의 구현 규칙을 지킨 자바 웹 프로그래밍 기술.</p>
</details>

<details>
    <summary>Servlet의 동작 방식</summary>
    </br>
    <p>1. 클라이언트가 URL을 입력한 경우 HTTP Request가 Servlet 콘테이너로 전송된다.</p>
    <p>2. 요청을 받은 Servlet container는  HTTPServletRequest, HTTPServletResponse 객체를 생성</p>
    <p>3. web.xml을 기준으로 요청된 URL에 해당되는 Servlet을 찾는다.</p>
    <p>4. 해당 Servlet에서 service 메소드를 호출, 요청 방식에 따라 doGet(), doPost()를 호출</p>
    <p>5. doGet(), doPost() 메소드는 페이지 생성, 이후 HTTPServletResponse 객체를 통해 응답.</p>
    <p>6. 응답이 종료된 경우 HTTPServletRequest, HTTPServletResponse 객체를 삭제</p>
</details>

<details>
    <summary>Spring의 싱글톤 패턴이란.</summary>
    </br>
    <p>Bean 설정 시 별다른 옵션이 존재하지 않는 경우 default로 설정됨.</p>
    <p>요청이 들어올 때마다 객체를 새로 생성하지 않고, 기존에 존재하던 객체를 활용 -> 효율적인 사용이 가능함.</p>
</details>

<details>
    <summary>Scope 프로토 타입 빈이란.</summary>
    </br>
    <p>기존의 싱글톤과 반대되는 개념.</p>
    <p>요청이 새로 들어롤 때마다 매번 새로운 객체를 반환해줌.</p>
    <p></p>
</details>

<details>
    <summary>@Transactional의 작동원리</summary>
    </br>
    <p>AOP를 통해 Target을 상속한 Proxy 객체가 됨.</p>
    <p>Target 메소드 전후로 Transaction을 수행함.</p>
    <p></p>
</details>

<details>
    <summary>@Transaction에서 ReadOnly 속성을 사용하는 이유</summary>
    </br>
    <p>트랜잭션 내부에서 수정, 삭제 등의 목적이 아닐 때 사용함.</p>
    <p>영속성 콘텍스트에서 엔티티를 관리할 필요 없음 -> readOnly를 통해 메모리 절약 가능(변경 감지를 위한 SnapShot을 보관하지 않음)</p>
    <p>readOnly 옵션을 활성화하지 않는 경우 변경 사항에 대해 쓰기 지연 저장소에 저장함. 그 후 일괄적으로 flush를 함.</p>
</details>

<details>
    <summary>JPA N+1 문제란, 해결방안. </summary>
    </br>
    <p>N + 1 문제 : 하나의 query를 날렸을 때 N개의 추가적인 query가 발생하는 문제.</p>
    <p>해결 방안</p>
    <P>1. Fetch join : 미리 두 테이블을 조인하여 한 번에 모든 데이터를 가져옴</p>
    <P>2. @Entity Graph : attributePaths 속성에 연관 조회할 Entity 명을 적으면 됨.</p>
    <P>주의점 : Catesian Product로 인한 중복값 발생 가능성</p>
    <P>Distinct(SQL) or set(Java)을 통해 해결</p>
</details>

## Data Structure

## DeepLearning