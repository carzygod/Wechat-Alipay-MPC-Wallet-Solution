# Wechat/Alipay MPC Multichain Wallet Solutions 

This repo is about a Wechat/Alipay Oauth base MPC solution . To allows users from China to use crypto wallet as sign tools inside Wechat/Alipay mini program . 

本仓库是一个基于微信、支付宝小程序的多链MPC解决方案，作为毕业设计，将会使用上海树图链CONFLUX作为样例example进行wallet系统及附属SDK构建。



## About Wechat/Alipay MPC solution

目前MPC行业已发展蓬勃近十年，以龙头WEB3AUTH为例，率先的推出了WAAS (wallet as a service)的Dapp为单位的Dapp自托管MPC钱包方案。MPC方案也从TSS卷到了ZKP。 随着OKX WEB3 MPC Wallet的出现，标志着传统中心化交易所入局MPC wallet赛道，同时各家卷的方向也从原有的技术方案比拼转向用户服务型用户体验竞争。

但是传统MPC服务体验是远不如中心化托管钱包的，而安全性与泄露风险又高于插件钱包、离线热钱包或冷钱包等客户端私钥托管方案。故而在过往数年中MPC钱包都与非原生账户抽象（AA）一样处于上不足以改善体验至用户无门槛准入，下不足以安全到让Web3 OG愿意把资产拿进来。

直到2023年中下旬，这个情况由Telegram Team有关联的TON Fundation wallet team提出的 [Wallet_Bot](https://t.me/wallet)方案出现，与Telegram Webapp生态的完善，逐步打破了上述MPC wallet的尴尬平衡。随着后续2024年上半年越来越多的Telegram Webapp MPC 解决方案的出现，包括但不限于 [Tonspack wallet](http://t.me/tonspack_bot/app)(颇有王婆卖瓜之嫌疑XD) 、[UXUY ](https://t.me/UXUYbot)、[OKX TG Wallet](https://t.me/OKX_WALLET_BOT) 等钱包通过Telegram webapp的形式配合MPC作为私钥保管，依靠Telegram webapp auth 作为鉴权校验作JWT鉴权。兼顾了原生中心化钱包的便捷性，同时又降低了中心化托管钱包的私钥存储风险。

同理，Telegram BOT 体系虽然是自成一派的独立交互模式，但是Telegram Webapp 本质则是 微信小程序、支付宝小程序的低配版本，之所以称之为“低配”并不是指其技术能力或性能优化上的“不如”，而是在审核、校验、边界限制问题处理上的“低配”。周知的微信支付宝小程序的申请流程繁琐，要求实名，并且域名请求要求备案并强制HTTPS，这些边界都要求微信、支付宝在内置小程序时需要重构底层浏览器内核并加限制，好处是实现了多端浏览器内核一致性。但Telegram Webapp则没有除HTTPS外的任何限制，故而“自由度”高很多，同时由于使用的是OS默认browser core，故而适配时常一塌糊涂。

基于这样的背景，构建微信、支付宝小程序为基础的JWT OAUTH 鉴权 MPC 方案显然并不是技术力问题，更显著的显而易见，是监管与法规限制问题。受限于大陆模糊的加密货币管制相关法律，没有多少企业或个人愿意做这种吃力不讨好可能还要蹲局子的事情。故而本仓库要实现的微信、支付宝MPC小程序仅作为“签名器”实现，并不承载加密钱包的资产管理等职能（意味着你不会在微信、支付宝小程序内直接查看加密资产，而是在外部的某个网页实现，但是所有的签名流程及操作将会走到该小程序实现）。并且将会以大陆合规化程度较高的CONFLUX上海树图链为基础进行构建。

鉴于当今加密圈日益合规化的大趋势，以及边缘化XMR RVN等真正意义上“去中心化”资产的情况看，Web3已然从当初混沌去中心化的犯罪洗钱温床向多中心化，以性能和金融噱头为核心的“多中心化”又或可以直言“不完全中心化”的方向发展，Solana生态的爆火正是这套方向落地的产物。随着Tornado cash创始人的入狱，一棍打碎了EVM“去中心化”的神话，意味着Web3的去中心化属性彻底沦为为金融属性服务的噱头。在这种大趋势下，是否真的有用户关心技术意义上的“去中心化”？我想我还是悲观的。



## Repo Index

This project including follow repo : 

- MPC Core system with JWT auth 
  - MPC Core using TSS
  - Keypair generate and storage
  -  JWT auth system & Mini-Program auth system
- Network bridge service
  - Cache Token
  - Cache Sign Data
  - Url Redirect With Deeplink support
- Mini program wallet
  - Mini-Program
  - BIP39 Keypair management 
  - Multi-signature support
  - Network bridge support
- Self-Generate wallet
  - Generate & Recover private key by JWT Auth
- Developer SDK
  - Wallet-SDK
  - Self-Generator-SDK
- Dapp Demo
  - Example sign
  - Example send transaction
  - Example multichain support 

