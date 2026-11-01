# DHCP

DHCP（Dynamic Host Configuration Protocol）は、端末にIPアドレスやネットワーク設定を自動で割り当てるプロトコルです。端末ごとに手入力する負担や設定ミスを減らせます。

DHCPサーバーは、利用可能なIPアドレスの範囲を管理し、端末へ一定期間利用できる設定を貸し出します。一般的な配布情報には、IPアドレス、サブネットマスク、デフォルトゲートウェイ、DNSサーバーがあります。サーバーやプリンターなど、固定アドレスが必要な機器には予約や静的設定を使うことがあります。

会社に入社したときに人事や総務がデスクの場所や内線番号を割り当てるように、DHCPは接続してきた端末へネットワーク上の住所（IPアドレス）や通信に必要な設定を割り当てます。

IPv4のDHCPでは、端末が利用可能なサーバーを探し、サーバーから提示された設定を選んで利用を要求し、サーバーからの応答を受け取る流れが一般にDORA（Discover、Offer、Request、Acknowledge）と呼ばれます。端末が設定を取得できない場合は、DHCPサーバーの稼働、アドレスの残数、VLANや中継設定を確認します。

## DHCP以外の関連機能

- **ARP**：同じIPv4リンク上で、相手のIPアドレスに対応するMACアドレスを調べる。IPv6ではNeighbor Discoveryを使う
- **DNS**：`example.com`のような名前をIPアドレスへ対応付ける。人名から電話番号を調べる電話帳のような役割

ARPやDNSはDHCPとは別の仕組みですが、端末がネットワーク上の相手と通信するために関係します。DHCPでIPアドレスを取得できても、DNSや経路の設定が正しくなければ目的のサービスへ接続できません。

## 参考資料

- IETF, RFC 2131, *Dynamic Host Configuration Protocol*（1997年、DHCP仕様）および RFC 2132, *DHCP Options and BOOTP Vendor Extensions*（1997年、DHCPオプション仕様）。[RFC 2131](https://www.rfc-editor.org/rfc/rfc2131)・[RFC 2132](https://www.rfc-editor.org/rfc/rfc2132)
- IETF, RFC 826, *An Ethernet Address Resolution Protocol*（1982年、ARP仕様）および RFC 4861, *Neighbor Discovery for IP version 6 (IPv6)*（2007年、IPv6 Neighbor Discovery仕様）。[RFC 826](https://www.rfc-editor.org/rfc/rfc826)・[RFC 4861](https://www.rfc-editor.org/rfc/rfc4861)
- IETF, RFC 1034, *Domain Names — Concepts and Facilities*（1987年）および RFC 1035, *Domain Names — Implementation and Specification*（1987年）。DNSの基本仕様です。[RFC 1034](https://www.rfc-editor.org/rfc/rfc1034)・[RFC 1035](https://www.rfc-editor.org/rfc/rfc1035)
