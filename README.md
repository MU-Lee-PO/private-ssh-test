# private-ssh-test
test


eval "$(ssh-agent -s)"

글로벌 키 등록 유지 후 private 키 등록해 test

# SSH Key 설정
## Repository별로 설정
1. ssh-keygen -t ed25519 -C "계정메일주소" -f "ssh키명"
    - ssh키명으로 SSH Key 파일 ~/.ssh에 생성
    - Win 계정명: mulee, Git Nickname: mulee
        - /c/Users/mulee/.ssh/'ssh키명' == ~/.ssh/
    - https://docs.github.com/ko/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent
2. ssh키를 Github 등록
    - 계정 귀속: https://docs.github.com/ko/authentication/connecting-to-github-with-ssh/adding-a-new-ssh-key-to-your-github-account
    - Repostiory 추가: private Repo인 경우 해당 Repo Admin에게 추가 요청
        - Deploy keys에 추가하면 됨
3. 계정별로 세팅
    - ~/.ssh/config 파일 수정, 없는 경우 생성
    - 현재 Repo에 첨부된 config 파일 참고
4. SSH-Agent SSH Key 등록
5. local git Repo에서 불러오기
    - remote 주소 설정: `git remote -set-url origin git@github.com-'계정명':'Repo사용자명'/'Repo명'`
    - `ssh git@github.com -v`
        - Repo로 설정한 경우: `ssh git@github-'계정명' -v`
