# Backend-Interview


## Contents
- [DataBase](#DataBase)
- [OS](#OS)
- [Network](#Network)
- [Algorithm](#Algorithm)
- [Data Structure](#ata-Structure)
- [Spring(백엔드)](#Spring(백엔드))
- [DeepLearning(Option)](#DeepLearning(Option))


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

## Algorithm

## Spring(백앤드)

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

## Data Structure

## DeepLearning(Option)