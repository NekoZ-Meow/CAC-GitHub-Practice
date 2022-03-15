# CAC-GitHub-Practice

C.A.C. GitHub勉強会用のリポジトリです。

勉強会が終わった後も自由に使ってもらって大丈夫です。

## Step1 リポジトリをクローンしよう

リモートにあるリポジトリをローカル環境に持ってきましょう。

ターミナル（コマンドライン）から次のコマンドを実行すると、現在いるディレクトリにリポジトリがダウンロードされます。

```shell
git clone "https://github.com/NekoZ-Meow/CAC-GitHub-Practice.git"
```

これ以下のステップは全てダウンロードしたリポジトリの中で行うので、移動しましょう。

```shell
cd CAC-GitHub-Practice
```

## Step2 ブランチを作って切り替えよう

変更を行う前に新しいブランチを作成しましょう。

ブランチ名は被ってはいけないので、今回は学生証番号を使用しましょう。

**<注意>** ```${ブランチ名}```は変数を表し、文字列が入ります。ブランチ名を"123456"とすると、実行するコマンドは```git branch 123456```になります。

```shell
git branch ${ブランチ名}
```

作成したブランチに切り替えましょう。

```shell
git switch ${作成したブランチ名}
```

正しく移動できているか確かめましょう
```shell
$ git branch
* 123456
  main
```

## Step3 ローカルリポジトリに変更を加えよう

### 3.1 テキストファイルを作成する

まず、ローカルリポジトリに何かしらの変更を加えてみましょう。

今回は自分の自己紹介を書いたテキストファイルを作成します。
以下のコマンドを実行して、テキストファイルを作成しましょう。

```shell
touch ${自分の学生証番号}.txt
```

次に、好きなテキストエディタ（メモ帳、VSCodeなどなんでもOK）で作成したテキストファイルに自己紹介を書き、保存しましょう。

### 3.2 変更をコミット対象にする

先ほど加えた変更をコミットの対象にします。

まずは、以下のコマンドを実行して、コミット対象とするファイルを追加しましょう。

```shell
git add ${自分の学生証番号}.txt
```

その後、ちゃんと対象として選択されているか確認しましょう。

```shell
git status
```

```shell
$ git status
On branch main
Your branch is up to date with 'origin/main'.

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
	new file:   123456.txt
```

### 3.3 コミットする
最後に、変更をコミットし、ローカルリポジトリに変更を反映しましょう。

```${コミットの詳細}```には、どのような変更を加えたのかを軽く記述しましょう。今回の例だと、「自己紹介テキストの追加」などです。

```shell
git commit -m  ${コミットの詳細}
```

これでローカルリポジトリに変更が反映できました！！

## Step4 ローカルリポジトリの変更をリモートリポジトリに反映しよう

次に、先ほどローカルリポジトリに反映した変更をリモートリポジトリに反映しましょう。

```shell
git push origin ${現在のブランチ名}
```

現在のブランチ名は以下のコマンドで確認できます。
```shell
$ git branch
```

おめでとう！！これでGitHub上のリポジトリを更新することが出来ました。

## Step5 プルリクエストを出そう

作成したブランチをマージしてもらうためにプルリクエストを出してみましょう。

まずは下の図のように、メニューの`Pull Requests`を選択し、`New pull request`を選択しましょう

<img width="1308" alt="Screen Shot 2022-03-15 at 12 31 23" src="https://user-images.githubusercontent.com/51152638/158300942-11b555db-682f-40d0-81ad-3b706ff91d75.png">

次にプルリクエストの内容を編集します。

<img width="923" alt="Screen Shot 2022-03-15 at 12 36 49" src="https://user-images.githubusercontent.com/51152638/158301551-443925e9-9637-4529-864b-ae4745240db8.png">

まず、①のようにきちんとマージ元のブランチが設定されていることを確認しましょう。
上の画像では、`123456`というブランチを`main`ブランチにマージするという意味になります。

次に、②の場所にマージ元のブランチで行ったことを簡単に記述しましょう。

③の場所にはさらに詳細に行ったことを記述できます。
これは書かなくてもプルリクエストを送信できますが、変更の確認がしやすいように、きちんと記述しましょう。

最後に④のボタンを押して、プルリクエストを送信します。

## Step6 プルリクエストを確認しよう

再びプルリクエストのメニューを確認すると、項目が増えていることが分かります。これを選択してプルリクエストを確認してみましょう。

<img width="1240" alt="Screen Shot 2022-03-15 at 12 48 18" src="https://user-images.githubusercontent.com/51152638/158302673-f55465a4-9d66-4be4-a732-ae2d8484af9f.png">

選択すると、このようなページへ移動します。

<img width="828" alt="Screen Shot 2022-03-15 at 12 52 49" src="https://user-images.githubusercontent.com/51152638/158302973-090a6f66-9f06-4c4b-afef-b71badf3dba2.png">

①を選択すると、プルリクエストを承認し、ブランチをマージします。

②の部分ではコメントを書くことができます。修正して欲しいことがあればここに書きましょう。

## Step7 ブランチの削除

マージ後必要無くなったブランチは削除しましょう。これを行わないと、量が増えてブランチがどんどん汚くなっていきます。

<img width="971" alt="Screen Shot 2022-03-15 at 12 58 39" src="https://user-images.githubusercontent.com/51152638/158303633-f4a37986-888a-4deb-884c-5fcec401cf73.png">

①を選択して、ホームへ移動し、②の`Branches`を選択しましょう。


<img width="1130" alt="Screen Shot 2022-03-15 at 13 01 29" src="https://user-images.githubusercontent.com/51152638/158304042-e8830349-506d-4ae4-94a3-93bcc9a06882.png">

①のゴミ箱マークを選択してブランチを削除できます。

