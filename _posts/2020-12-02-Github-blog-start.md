---
title:  "Github 블로그 시작하기"
excerpt: "GitHub Blog 서비스인 github.io 블로그를 시작하기로 했다."

categories: 
  - Jekyll
tags:
  - update
toc: true
toc_label: "Github 블로그 시작하기"
---

## Step 1: 윈도우 루비설치

로컬에서 지킬(Jekyll)로 작업하기 위해 루비를 설치해야 합니다. 

[공식홈페이지](https://rubyinstaller.org/downloads/){: target="_blank"}에서 `=>` 화살표(추천)가 있는 `Ruby+Devkit 2.7.2-1 (x64)`를 다운받습니다.
저는 오른쪽에 we recommend that you use the **Ruby+Devkit 2.7.X (x64)** installer 를 보고 64비트 버전을 다운 받았습니다.

설치 중 체크 박스는 모두 체크하였습니다. 찾아보니 환경변수등록, UTF-8 인코딩, cmd창에서 Ruby 명령어를 쓰기 위해 MSYS2 설치 등 모두 체크해야 하는 항목들이었습니다.

설치가 끝나면 cmd창이 자동으로 켜지는데 여기서 3을 입력후 Enter 를 눌러 `development toolchain`을 설치하였습니다.

깃허브 블로그 로컬작업을 위한 환경세팅이 끝났습니다.

## Step 2: Jekyll 로컬 실행

저의 경우, 미리 받아 놓은 테마폴더 위치에서 다음을 입력했습니다.

다음 명령어는 Gemfile 이 있는 곳에서 입력해야 합니다.

```bash
gem install bundler
bundle 
jekyll serve
```

블로그를 시작을 위한 모든 준비가 끝났습니다. 