# Study-with-JPA

42SEOUL Spring JPA Study

### Git 🤿

- 스터디 날에 Pull Rquest
- 각자 닉네임으로 된 branch생성하여 각자 branch에 commit 후 push
- 각 주차 강의를 듣고 강의에서 자세히 다루지 않은 부분을 정리하여 각자 자유롭게 주제선정
- 여러가지 주제를 한 파일에 적지 말고 한 가지의 주제만 정리할 것, 만약 더 정리하고 싶다면 파일을 나눌 것
- 매주마다 1개 이상의 정리글을 commit 할 것
- 가급적 팀원과 중복되는 주제는 피하기 위해 스터디 이틀 전까지 미리 주제를 슬랙에서 예고할 것
- 파일 이름은 자기가 정한 주제를 제목으로 작성, 띄어쓰기는 언더바로 대체

- 커밋 메시지 규칙

  > week해당주차 - 자기가 정한 주제

  > (ex) week1 - 엔티티 설계시 주의점

- **commit 충돌을 피하기 위해 각자 브랜치에 git pull은 하지 말 것**

---

### Rules are rules

- 무단 지각 및 결석 시 벌금 1000원을 부과한다.
- 다음 스터디 진행까지 질문사항 등을 준비한다.

---

**Push 할 때**

1. git checkout 본인브랜치이름
2. git status .
3. git add .
4. git commit -m "커밋메시지"
5. git push origin 본인브랜치이름

---

**Commit 수정법**

- 만약 바로 이전 커밋이 수정사항이 생겼을 때

1. git add .
2. git commit -m "커밋 메시지" --amend
3. 만약 push를 이미 한 상태라면 git push origin 본인브랜치이름 --force

- 훨씬 이전의 커밋을 수정하고 싶다면

1. git log
2. 수정하고자 하는 커밋의 바로 이전 커밋의 해시값을 복사
3. git rebase -i 복사한 해시값
4. 수정하고자 하는 커밋의 pick을 edit으로 수정
5. git add .
6. git commit --amend
7. git rebase --continue
8. git push origin 본인브랜치이름 --force
