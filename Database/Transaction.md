# Transaction(트랜잭션)

## 트랜잭션이란

트랜잭션이란 질의(query)를 하나의 묶음 처리해서 만약 중간에 실행이 중단됐을 경우, 처음부터 다시 실행하는 Rollback을 수행하고, 오류없이 실행을 마치면 commit을 하는 실행 단위를 의미한다.

즉, 한 번 질의가 실행되면 질의가 모두 수행되거나 모두 수행되지 않는 작업수행의 **논리적 단위**이다.

트랜잭션을 작업수행의 논리적 단위라고 이야기를 했는데, 이로인해 DBMS의 성능은 초당 트랜잭션의 실행 수(TPS : Transaction per second)로 측정한다.

## 사용 이유

트랜잭션은 DB 서버에 여러 개의 클라이언트가 동시에 액세스 하거나 응용프로그램이 갱신을 처리하는 과정에서 중단 될 수 있는 경우 등 **데이터 부정합을 방지**하고자 할 때 사용합니다.

부정합이 발생하지 않으려면 프로세스를 병렬로 처리하지 않도록 하여 한 번에 하나의 프로세스만 처리하도록 하면 되는데, 이는 효율이 너무 떨어진다. 즉, 병렬로 처리할 수 밖에 없는 현실적인 상황으로 인해 ㅜ정합을 방지하고자 트랜잭션을 사용하는 것이다.

트랜잭션에서는 스케쥴관리가 중요하다. 스케쥴을 잘못 짜게되면, 데드락에 빠지게 된다(2PL).
