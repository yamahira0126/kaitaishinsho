[](scp.md)
# scp 
`scp`（Secure Copy）は、SSH（Secure Shell）を利用してリモート間またはローカルとリモート間でファイルやディレクトリを安全にコピーするコマンド。認証と転送が暗号化されており、安全にファイルを移動できる。

  実行例 [](変更しない)

  ```
  scp file.txt user@example.com:/home/user/
  ```

  実行結果 [](変更しない)

  ```
  file.txt                             100%   20KB 200.0KB/s   00:00
  ```

  上記はローカルの `file.txt` をリモートサーバの `/home/user/` にコピーしている例。

---

### オプション一覧

- **-r**

  ディレクトリを再帰的にコピーする。

  実行例 [](変更しない)

  ```
  scp -r myfolder user@example.com:/home/user/
  ```

  実行結果 [](変更しない)

  ```
  myfolder/file1.txt                    100%  10KB 100.0KB/s   00:00
  myfolder/file2.txt                    100%  15KB 120.0KB/s   00:00
  ```

---

- **-P [ポート番号]**

  SSH接続に使用するポート番号を指定（`-p` ではなく大文字の `-P` に注意）。

  実行例 [](変更しない)

  ```
  scp -P 2222 file.txt user@example.com:/home/user/
  ```

---

- **-i [秘密鍵ファイル]**

  SSH認証に使う秘密鍵ファイルを指定する。

  実行例 [](変更しない)

  ```
  scp -i ~/.ssh/id_rsa file.txt user@example.com:/home/user/
  ```

---

- **-v**

  詳細な通信内容を表示（デバッグ用）。

  実行例 [](変更しない)

  ```
  scp -v file.txt user@example.com:/home/user/
  ```

---

### ローカル → リモート 例

```
scp data.csv user@192.168.1.10:/home/user/
```

### リモート → ローカル 例

```
scp user@192.168.1.10:/home/user/data.csv ./
```

---

このコマンドは、ファイル同期、バックアップ、リモートサーバーとのやり取りなど、日常的なサーバー運用において極めて重要な役割を果たす。
