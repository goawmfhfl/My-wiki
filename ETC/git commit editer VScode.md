# 💡git command editor VScode로 변경하기

> 코드 실행 명령어

git commit을 할때 vscode에서 commit명을 작성하려고함
아래와 같은 명령어를 작성하면 실행한다고해서 실행

```jsx
git config --global core.editor "code --wait"
```

<br/>

> 에러 발생

```jsx
code --wait: code: command not found
error: There was a problem with the editor 'code --wait'.
메시지를 -m 또는 -F 옵션으로 입력하십시오.
```

<br/>

> 문제 해결

1. shift + command + p
2. code 설치 `Shell Command: Install 'code' command in PATH`
3. 다시 실행 `git config --global core.editor "code --wait"`

<br/>

> 다른 문제 발생

재부팅 할 때마다 code설치를 다시해줘야함

<br/>

> 문제 해결

아래 명령어로 application에 파일 설치

```jsx
sudo ln -fs "/Applications/Visual Studio Code.app/Contents/Resources/app/bin/code" /usr/local/bin/
```

<br/>

# 🔗 Reference

- [https://codechacha.com/ko/git-commit-msg-editor/](https://codechacha.com/ko/git-commit-msg-editor/)
- [https://stackoverflow.com/questions/53847777/associating-visual-studio-code-with-git-in-mac](https://stackoverflow.com/questions/53847777/associating-visual-studio-code-with-git-in-mac)
- [https://apple.stackexchange.com/questions/294176/how-to-install-visual-studio-codes-code-command-permanently](https://apple.stackexchange.com/questions/294176/how-to-install-visual-studio-codes-code-command-permanently)
