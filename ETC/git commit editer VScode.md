# ๐กgit command editor VScode๋ก ๋ณ๊ฒฝํ๊ธฐ

> ์ฝ๋ ์คํ ๋ช๋ น์ด

git commit์ ํ ๋ vscode์์ commit๋ช์ ์์ฑํ๋ ค๊ณ ํจ
์๋์ ๊ฐ์ ๋ช๋ น์ด๋ฅผ ์์ฑํ๋ฉด ์คํํ๋ค๊ณ ํด์ ์คํ

```jsx
git config --global core.editor "code --wait"
```

<br/>

> ์๋ฌ ๋ฐ์

```jsx
code --wait: code: command not found
error: There was a problem with the editor 'code --wait'.
๋ฉ์์ง๋ฅผ -m ๋๋ -F ์ต์์ผ๋ก ์๋ ฅํ์ญ์์ค.
```

<br/>

> ๋ฌธ์  ํด๊ฒฐ

1. shift + command + p
2. code ์ค์น `Shell Command: Install 'code' command in PATH`
3. ๋ค์ ์คํ `git config --global core.editor "code --wait"`

<br/>

> ๋ค๋ฅธ ๋ฌธ์  ๋ฐ์

์ฌ๋ถํ ํ  ๋๋ง๋ค code์ค์น๋ฅผ ๋ค์ํด์ค์ผํจ

<br/>

> ๋ฌธ์  ํด๊ฒฐ

์๋ ๋ช๋ น์ด๋ก application์ ํ์ผ ์ค์น

```jsx
sudo ln -fs "/Applications/Visual Studio Code.app/Contents/Resources/app/bin/code" /usr/local/bin/
```

<br/>

# ๐ย Reference

- [https://codechacha.com/ko/git-commit-msg-editor/](https://codechacha.com/ko/git-commit-msg-editor/)
- [https://stackoverflow.com/questions/53847777/associating-visual-studio-code-with-git-in-mac](https://stackoverflow.com/questions/53847777/associating-visual-studio-code-with-git-in-mac)
- [https://apple.stackexchange.com/questions/294176/how-to-install-visual-studio-codes-code-command-permanently](https://apple.stackexchange.com/questions/294176/how-to-install-visual-studio-codes-code-command-permanently)
