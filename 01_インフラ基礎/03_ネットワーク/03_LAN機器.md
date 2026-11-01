# LAN機器

LANを構成する機器は、端末をネットワークへ接続したり、データを転送したりします。機器ごとの役割を知ると、ネットワーク構成や障害箇所を理解しやすくなります。

| 機器 | 主な役割 |
|---|---|
| NIC | PCやサーバーをネットワークへ接続する |
| スイッチ | MACアドレスを学習し、LAN内のフレームを転送する |
| ルーター | IPアドレスと経路情報をもとに、異なるネットワーク間でパケットを転送する |
| 無線LANアクセスポイント | Wi-Fi端末を有線LANなどへ接続する |
| ハブ | 受信した信号を複数のポートへ中継する。現在のLANではスイッチが主流 |

機器同士は、ツイストペアケーブルや光ファイバー、無線などで接続します。ケーブルの種類や長さ、電波環境、接続規格によって、通信できる距離や速度が異なります。

オフィスのPCはNICからスイッチへ接続し、別ネットワークやインターネット上の宛先へはルーターを経由します。無線LANを使う場合、端末はアクセスポイントへ無線接続し、その先は有線LANへつながる構成が一般的です。機器の電源やリンク状態、接続先ポートをたどると、物理接続の問題を調査できます。

家庭用ルーターのように、ルーター、スイッチ、無線LAN、DHCPなどの機能を一台にまとめた製品もあります。製品の形だけで役割を判断せず、構成上どの機能を担っているか確認します。

## 参考資料

- IEEE Standards Association, IEEE/ISO/IEC 8802-3:2021, *Telecommunications and exchange between information technology systems — Requirements for local and metropolitan area networks — Part 3: Ethernet*（2021年、LAN規格）。イーサネットのMAC層と物理層の仕様です。[IEEE Standards Catalog](https://standards.ieee.org/standard/) / [IEEE 802.3 Working Group](https://www.ieee802.org/3/)
- IEEE Standards Association, IEEE 802.11-2024, *Wireless LAN Medium Access Control (MAC) and Physical Layer (PHY) Specifications*（2024年、無線LAN規格）。無線LANのMAC層と物理層の仕様です。[IEEE Standards Catalog](https://standards.ieee.org/standard/) / [IEEE 802.11 Working Group](https://www.ieee802.org/11/)
