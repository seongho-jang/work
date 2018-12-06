# Cache

- Redis(Remote-Dictionary Server)
  - 09년 살바토르 산필리포(Salvatore Sanfilippo)가 개발
  - 15년 부터 Redis Labs에서 지원
  - Key-value구조의 비정형 데이터
    - 말 그대로 일정 Key값에 해당하는 Value가 존재
  - 읽기 성능 증대를 위한 서버 측에서의 복제를 지원한다.
  - 쓰기 성능 증대를 위한 샤딩 지원
    - 샤딩이란
      - 하나로 모아져 있는 데이터베이스를 같은 타입의 데이터를 다수의 데이터베이스로 쪼개서 저장하는것
      - 하나로 모으기에는 큰 데이터베이스를 샤딩을 통해 여러 데이터베이스로 나누어준다.
  - 스냅샷(기억장치) 기능을 이용해서 *.rdb파일로 저장해 해당 시점으로 복구가 가능
  - Redis Server는 1개의 싱글 쓰래드만 사용하기 때문에 한개의 서버에 여러 서버를 띄울 수 있다.
  - Master-slave방식으로 데이터 분실 위험을 없애준다.
    - 즉, 한개의 서버에 Master-server가 있고 여러개의 Slave-server가 있는데 이 중 Master-server가 down되도 slave서버를 이용하면 이어서 서비스도 가능하고 데이터 분실 또한 없다.
  - 