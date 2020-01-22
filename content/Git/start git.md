---
title: "Git 기초"
---

## 로컬 저장소 만들기

```
mkdir [gitfolder]
cd [gitfolder]
git init
```

## 저장소 받아오기

```
git clone [로컬 저장소 경로]
git clone [사용자명]@[호스트]:[원격 저장소 경로]
```

## 작업의 흐름

![](/images/git_workflow.png?classes=shadow)

## 추가와 확정

- 로컬 저장소에만 반영

  git add [파일 이름] git add *

  git commit -m "설명"

## 변경 내용 push

```
git push origin [branch명]
```

- 기존에 있던 원격 저장소를 복제한 것이 아니면, 원격 서버의 주소를 git에게 알려줘야함

  git remote add origin [원격 서버 주소]

## branch

![](/images/git_branch.png?classes=border,shadow)

- branch 생성 후 옮김

  git checkout -b [branch]

- 이동

  git checkout [branch]

- 삭제

  git branch -d [branch]

- push 하기전에는 다른 사람들이 접근할 수 없다.

## pull과 merge

- 로컬 저장소를 원격 저장소에 맞춰 갱신

  git pull

- 다른 branch의 내용을 현재 branch에 병합

  git merge [병합할 branch명]

- 자동으로 받아지고 병합된다.

- 항상 성공하는것은 아니다 변경 후에는 add해야함

  git diff [원래 branch] [비교 대상 branch]

## tag 달기

```
git tag [tag명] [commit번호]
```

- commit 번호 찾기

  git log

## 로컬 변경 내용 되돌리기

- 로컬의 변경 내용을 변경 전 상태(HEAD)로 되돌려줌

- 이미 인덱스에 추가된 변경 내용과 새로 생성한 파일은 남음

  git checkout -- [파일 이름]

- 로컬의 모든 변경 내용과 확정본을 포기

  git fetch origin git reset --hard origin/master

## 그 외

- git의 내장 GUI

  gitk

- 콘솔에서 git output을 컬러로 출력

  git config color.ui true

- log에서 commit 1개를 딱 한 줄로만 표시

  git config format.pretty oneline

- 파일 추가시 대화식으로 추가

  git add -i

참조 : https://rogerdudler.github.io/git-guide/index.ko.html