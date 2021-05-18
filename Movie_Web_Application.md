# Movie_Web_Application

- 아직 명세가 나오지 않았다.

# `05.17`

### 4조 : 김재우, 이광교

- 아직 명세가 나오진 않았지만 어떤 framework를 사용할 것인지와 역할 분배에 대해 이야기했다.

#### :orange: Framework : Django, Vue

#### :grapes: 역할 분배 : Front와 Back을 따로 나누지 않고 함께 !

- accounts와 movies를 나눠서 구현하면서 피드백하고 구현 후 서로 설명해주고 디버깅 하기 !
- 처음에는 좀 더 시간이 걸릴 수 있지만 완벽히 `Server`를 구현한 후 `Client`를 구현하면서 후반에 시간을 단축시킨다 !
- 추가적인 기능 생각해보기 !

<br>

#### :melon: 오늘 한 것 !

1. Framework 정하기

2. Front와 Back에 관련하여 역할 정하기

3. Django를 사용하여 community json으로 출력해보기 → 출력 실패,,
   - 생각보다 Django를 많이 잊어버려서 공부가 필요하다는 것을 느꼈다. 
   - html 파일이 아닌 json 파일로 출력해야하기 때문에 `serializers`에 대한 공부 필요 !!

<br>

# `05.18`

### Gitlab 협업

- Server와 Client 두 개의 프로젝트를 만들어서 구현하기로 했다.
- 아직 명세가 나오지 않았기 때문에 기본적인 틀만 만들고 고의적으로 Conflict를 만들어보는 경험을 했다.

#### :bomb: Conflict 만드는 방법

- 각자 master의 branch를 만든다.

- 같은 부분을 수정하고 push한다.

- A와 B branch에서 각각 a와 b를 수정을 했다고 하면 A와 master가 merge할 때는 충돌이 나지 않지만 이렇게 merge한 것을 pull 받아서 B와 merge를 하게 되면 충돌이 일어난다.

- 아래의 에러메세지가 나온다.

  ![image-20210518231941531](Movie_Web_Application.assets/image-20210518231941531.png)

  → 같은 부분을 수정했기 때문에 둘 중 어떤 것을 사용할지 정해야 한다.

#### :bulb: 해결 방법 1(Gitlab merge)

- Gitlab에서 merge를 하게 된다면 a와 b 둘 중 하나를 선택해서 merge할 수 있다.
- merge한 후 뜬 오류에서 옆에 보면 내용을 확인하고 바꿀 수 있는 부분이 있다.

#### :bulb: 해결 방법 2(Local merge)

- 로컬에서 merge 하는 방법으로 이 방법을 사용하면 a, b 둘 중 하나만 선택할 수도 있고 a, b 둘 다 선택할 수 있다 !  → 만약에 둘 다 merge 되는 것을 원한다면 로컬에서 merge !!

- 순서

  ```shell
  # testA branch 생성
  $ git branch testA
  
  # 해당 branch로 이동
  $ git switch testA
  
  # 수정하고 add, commit
  # push 할 때는 해당하는 곳에 push
  $ git push origin testA
  
  # merge할 때는 master branch에서!!
  $ git merge testA
  # -> 충돌이 일어나서 그 부분을 보여줌 -> 두 개를 다 선택하려면 both ~ 선택 !
  
  # merge 성공 ! 다시 git, commit, push
  # 로컬 branch 삭제
  $ git branch -d testA
  # 로컬에서만 삭제된 것이므로 Gitlab에서도 삭제를 해줘야한다.
  ```

#### :bulb: 해결한 후 branch 삭제 !

- branch 삭제는 동기화가 되지 않기 때문에 각각의 위치에서 삭제해줘야한다. Local에서 merge하고 branch를 삭제했다면 Gitlab에서도 branch를 따로 삭제해줘야한다. 반대의 경우도 마찬가지로 로컬과 Gitlab에서 각각 삭제해줘야한다.

<br>

#### :melon: 오늘 한 것

1. `프로젝트를 시작하기 전에 미리 Conflict를 경험`하였다. 어느정도 진행 후에 에러를 보게 되는 것보다는 미리 경험하고 시작하자는 생각이었는데 좋은 선택이었던 것 같다.

2. 명세가 나오지 않아서 구체적으로는 힘들지만 어느정도 예상되는 부분이 있기 때문에 각자 UI를 생각해서 수요일 오후 4시에 보기로 했다 !

<br>

