# ICMP

ICMP（Internet Control Message Protocol）は、IP通信でのエラー通知や診断に使われるプロトコルです。IPパケットが宛先へ届かない場合や、経路上でTTLが尽きた場合などに、関連する情報を返すことがあります。

## よく使う診断コマンド

- **ping**：ICMPエコー要求を送り、応答の有無や往復時間を確認する
- **traceroute / tracert**：TTLを変えながらパケットを送り、途中のルーターから返る応答をもとに経路を推測する

診断結果には限界があります。ICMPがファイアウォールなどで遮断されると、相手が稼働していても応答が返らないことがあります。逆にpingに応答しても、Webやデータベースなどのアプリケーションが正常とは限りません。

たとえば、サーバーへのpingが失敗しても、ICMPだけが遮断されていてHTTPSは利用できる場合があります。pingに応答しても、Webサーバーが停止していればサイトは使えません。必要なポートへの接続とアプリケーションの応答も確認します。

ICMPの結果は、名前解決、ポート接続、アプリケーションログなど、他の確認結果と合わせて判断します。

## 参考資料

- IETF, RFC 792, *Internet Control Message Protocol*（1981年、ICMPv4仕様）および RFC 4443, *Internet Control Message Protocol (ICMPv6) for the Internet Protocol Version 6 (IPv6) Specification*（2006年、ICMPv6仕様）。[RFC 792](https://www.rfc-editor.org/rfc/rfc792)・[RFC 4443](https://www.rfc-editor.org/rfc/rfc4443)
