# OSI参照モデル

OSI参照モデルは、ネットワーク通信の役割を七つの層に分けて理解するための概念モデルです。実際の製品やプロトコルが常に一つの層だけで動くという意味ではありません。

## 七つの層

1. **物理層**：電気、光、電波などでビットを伝送する
2. **データリンク層**：同じリンク上でフレームを届ける
3. **ネットワーク層**：IPアドレスを使って異なるネットワーク間を中継する
4. **トランスポート層**：アプリケーション間の通信を制御する
5. **セッション層**：通信する相手との会話や接続状態を扱う考え方
6. **プレゼンテーション層**：データの形式や表現を扱う考え方
7. **アプリケーション層**：Webやメールなど、アプリケーション向けの通信を扱う

会社の組織にたとえると、物理層からネットワーク層は現場で荷物を運ぶ部門、トランスポート層は配送の追跡や再送を担う品質管理部門、セッション層からアプリケーション層は顧客との商談や契約を担当する部門のように、役割を分けて考えられます。これは役割分担を理解するためのたとえです。

送信時は、上位のデータに下位層の情報を付けて送ります。受信側は各層の情報を確認しながら、上位の処理へ渡します。この処理をカプセル化とデカプセル化と呼びます。

荷物を小箱（トランスポート層）、中箱（ネットワーク層）、大箱（データリンク層）で順に包み、宛先で外側から開けていくイメージです。箱に付ける宛先情報が各層のヘッダーに相当します。

たとえば、Web要求はアプリケーション層のデータとして作られ、TCPのポート情報、IPの送信元・宛先情報、イーサネットのMACアドレスなどが順に付加されて送信されます。途中のルーターは通常、イーサネットのフレームを次のリンク向けに作り直しながら、IPパケットを転送します。

障害調査では、ケーブルや信号、IP経路、ポート、アプリケーションの順に観点を整理できます。ただし、層の番号だけで原因を断定せず、実際の通信とログを確認します。

## 参考資料

- International Telecommunication Union Telecommunication Standardization Sector (ITU-T), Recommendation X.200, *Information technology — Open Systems Interconnection — Basic Reference Model: The basic model*（1994年、国際勧告）。OSI基本参照モデルの7層を定めています。[ITU-T公式資料](https://www.itu.int/rec/T-REC-X.200/en)
- International Organization for Standardization (ISO) and International Electrotechnical Commission (IEC), ISO/IEC 7498-1:1994, *Information technology — Open Systems Interconnection — Basic Reference Model: The Basic Model*（国際規格）。ITU-T X.200と対応する規格です。[ISO公式カタログ](https://www.iso.org/standard/20269.html)
