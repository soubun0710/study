# シングルサインオンと特権アクセス

シングルサインオン（SSO）は、利用者が一つの認証基盤を通じて複数のサービスを利用できるようにする仕組みです。管理者権限などの特権アクセスは、通常の利用者権限より大きな影響を持つため、別途厳格に管理します。

## SSOと認証連携

SSOでは、認証を担うIdP（Identity Provider）と、利用者が使うサービスが認証情報を連携します。代表的な方式にはSAMLとOpenID Connect（OIDC）があります。

SSOは利用者の利便性とアカウント管理を改善できますが、IdPのアカウントが侵害されると複数のサービスに影響する可能性があります。IdPの多要素認証、管理者権限の制限、認証ログの監視、サービス側の連携設定の確認が必要です。

## 特権IDの管理

特権IDは、システムの設定変更、アカウント管理、データの読み書きなど強い操作権限を持つIDです。悪用や誤操作が起きると、サービス停止、情報漏えい、証跡の消去につながる可能性があります。

特権IDは、施設のマスターキーにたとえられます。広い範囲の操作ができるため、紛失や不正利用の影響も大きくなります。誰が、どの作業で、いつ使ったかを追えるようにし、管理者権限を共用せず個人ごとのIDで管理します。

- 管理者権限を個人ごとのIDに付与し、共用アカウントを避ける
- 日常業務用のIDと管理作業用のIDを分ける
- 必要な作業に必要な期間だけ権限を付与する
- 多要素認証を適用し、利用記録を確認する
- 特権アクセス管理（PAM）などは、組織のリスクと運用要件に応じて利用する

## アカウントのライフサイクル

アカウントと権限は、発行して終わりではありません。入社、異動、退職、委託終了、業務変更のタイミングで、発行、変更、停止、削除を行います。サービスアカウントについても、所有者、用途、接続先、権限、認証情報の更新方法を明確にし、使われていないIDを残さないようにします。

## 参考資料

- OASIS, *Assertions and Protocols for the OASIS Security Assertion Markup Language (SAML) V2.0*（2005年、標準仕様）および OpenID Foundation, *OpenID Connect Core 1.0*（2014年初版、2023年Errata Set 2反映版、認証連携仕様）。SSOで用いる認証連携の一次資料です。[OASIS SAML](https://docs.oasis-open.org/security/saml/v2.0/) / [OpenID Connect](https://openid.net/specs/openid-connect-core-1_0.html)
- NIST, *Digital Identity Guidelines: Authentication and Authenticator Management*, NIST SP 800-63B-4（2025年、デジタル認証ガイドライン）。認証器と多要素認証の要件を参照できます。[NIST公式ページ](https://pages.nist.gov/800-63-4/sp800-63b.html)
- NIST, *Security and Privacy Controls for Information Systems and Organizations*, NIST SP 800-53 Rev. 5（管理策カタログ）。アカウント管理、特権アクセス、認証などの管理策を確認できます。[NIST管理策カタログ](https://csrc.nist.gov/projects/cprt/catalog)
