# sacerless Cf-Works & Pages ကို အသုံးပြု. Trojan ကိုဖြန့်ဖြူးပါ

🇮🇷[ပါရှန်းပစ္စည်းများ](README.fa.md)  
🇹🇷[တာယာတူ](README.tr.md)  
🇬🇧[အင်္ဂလိပ်](README.md)  
🇩🇪[ဂျာမနီ](README.de.md)  
🇲🇲[မြန်မာ](README.my.md)

၎င်းသည် cloudflare အလုပ်သမားပလက်ဖောင်းပေါ်တွင်အခြေခံသည်။ မူရင်းဗားရှင်းအပေါ် အခြေခံ. ၎င်းကို Trojan Configuration Information ကိုပြသရန်နှင့် subscription content အဖြစ်ပြောင်းလဲရန်ပြင်ဆင်ထားသည်။ ဤ script ကို အသုံးပြု. Trojan Configuration Information ကိုအွန်လိုင်း configuration သုံး. Singbox ကဲ့သို့သောကိရိယာများသို့အလွယ်တကူပြောင်းလဲနိုင်သည်။

[tg channel](https://t.me/F_NiREvil)

![rainbow](https://github.com/NiREvil/vless/assets/126243832/1aca7f5d-6495-44b7-aced-072bae52f256)

## မာတိကာ

-   [အလုပ်သမားများဖြန့်ကျက်နည်းလမ်း](#Workers-deployment-method)
-   [စာမျက်နှာများဖြန့်ကျက်နည်းလမ်း](#Pages-deployment-method)
-   [proxyip](#proxyIP)
-   [ပတ်ဝန်းကျင် variable ကိုဖော်ပြချက်](#Environment-variables-description)
-   [ဗွီဒီယိုသင်ခန်းစာများ](#Video-tutorials)![rainbow](https://github.com/NiREvil/vless/assets/126243832/1aca7f5d-6495-44b7-aced-072bae52f256)

<details>
<summary> Use </summary>

-   ဤစီမံကိန်းကိုသင်ယူခြင်း, သုတေသနနှင့်ဘေးကင်းလုံခြုံရေးစစ်ဆေးခြင်းအတွက်ဒီဇိုင်းပြုလုပ်ထားသည်။ ၎င်းသည်လုံခြုံရေးသုတေသီများ, ပညာရှင်များနှင့်နည်းပညာစိတ်အားထက်သန်မှုများကိုကွန်ယက်ဆက်သွယ်ရေးနည်းပညာကိုနားလည်ရန်နှင့်လေ့ကျင့်ရန်ကိရိယာတစ်ခုပါ 0 င်ရန်ရည်ရွယ်သည်။
    </details>

<details>
<summary> Legality </summary>
  
  - Users must comply with local laws and regulations when downloading and using this project.
  - Users are responsible for ensuring that their actions comply with the laws, regulations and other applicable requirements of their region

</details>

<details>
<summary> Risk warning </summary>
  - Avoid leaking node configuration information by submitting false node configurations to the subscription service 
</details>

## အလုပ်သမားများဖြန့်ကျက်နည်းလမ်း

1.  Cloudflare Worker ကိုဖြန့်ကျက်ပါ။

    -   cloudflare လုပ်သား console တွင်အလုပ်သမားအသစ်တစ်ခုကိုဖန်တီးပါ။

    -   သေတမ်းစာ[အလုပ်သမား .JJs](_worker.js)ပါ 0 င်သောအရာများကိုအလုပ်သမားအယ်ဒီတာသို့ကူးထည့်ပါ။

    -   လိုင်း 3 ကိုပြောင်းပါ`password`သင့်ကိုယ်ပိုင်ကိုပြုပြင်မွမ်းမံပါ**လှျို့ဝှက်စကား**

    -   တနည်းအားဖြင့်, သင်တိုက်ရိုက်ဖြန့်ကျက်ရန်အောက်ပါခလုတ်ကိုနှိပ်ပါ။

    [![Deploy to Cloudflare Workers](https://deploy.workers.cloudflare.com/button)](https://deploy.workers.cloudflare.com/?url=https://github.com/NiREvil/Trauma)

2.  ဦး စားပေးလမ်းကြောင်းကိုထည့်ပါ။
    -   ပေး`addresses`format နဲ့အညီ ဦး စားစက်နာမည် / ပိုနှစ်သက်သော IP ထည့်ပါ။ Port နံပါတ်မရှိပါကပုံမှန် TLS port သည် 443 ဖြစ်ပြီး # နိမိတ်လက်ခဏာမှာ alias ကိုမှတ်ချက်ပေးသည်။
        ```js
        let addresses = [
        // any Domain or clean IPv4/IPv6 addresses from cloudflare is usable, no sweat.
        'cdnjs.com:443#N1',
        'www.wto.org:2053#N2',
        'sky.rethinkdns.com#N3',
        'creativecommons.org#N4',
        '[2606:4700:310c::ac42:2c39]#N5 √IPv6',
        ];
        ```

3.  subscription အကြောင်းအရာများရယူပါ:
    -   ဝင်ရောက်ခွင့်`https://[YOUR-WORKERS-URL]/[password]`subscription အကြောင်းအရာရယူပါ။
    -   ဥပမာအားဖြင့်`https://vless.trauma.workers.dev/auto`ဤသည်သင်၏ Universal advelive subscription လိပ်စာဖြစ်သည်။
    -   ဥပမာအားဖြင့်`https://vless.trauma.workers.dev/auto?sub`SSR +, SSR + စသည်တို့အတွက်သင့်လျော်သော base64 subscription format ကို
    -   ဥပမာအားဖြင့်`https://vless.trauma.workers.dev/auto?clash`openclash များအတွက်သင့်လျော်သော subscription format ကိုတိုက်ပွဲဖြစ်ပါ။
    -   ဥပမာအားဖြင့်`https://vless.trauma.workers.dev/auto?sb`Singbox Subscription format, Singbox အတွက်သင့်တော်သော Singbox Subsion format ကို

4.  အလုပ်သမားများအားစိတ်ကြိုက်ဒိုမိန်းကိုချည်နှောင်ခြင်း -
    -   အလုပ်သမား console ၌တည်၏`trigger`tab ကို, အောက်တွင်ကိုနှိပ်ပါ`Add a custom domain`。
    -   ဥပမာ - cloudflare domain namin name resolution resolution service သို့သင်လွှဲပြောင်းထားသောဒုတိယဒိုမိန်းအမည်ကိုဖြည့်ပါ။`vless.trauma.com`ကလစ်နှိပ်ပါ`Add a custom domain`လက်မှတ်ကိုအကျိုးသက်ရောက်ရန်စောင့်ဆိုင်းပါ။

![rainbow](https://github.com/NiREvil/vless/assets/126243832/1aca7f5d-6495-44b7-aced-072bae52f256)

## စာမျက်နှာများဖြန့်ကျက်နည်းလမ်း

1.  cloudflare စာမျက်နှာများဖြည်ချခြင်း:
    -   ခက်ရင်း[GitHub ရှိဤစီမံကိန်း](https://github.com/NiREvil/Trauma/fork)
    -   cloudflare စာမျက်နှာများ console တွင်ရွေးချယ်ပါ`Connected to Git`ထို့နောက်ရွေးချယ်ပါ`trauma`item ပြီးနောက်ကိုကလစ်နှိပ်ပါ`Start setting up`。
    -   တည်နေ`Setting up build and deployment`စာမျက်နှာ၏အောက်ခြေတွင် Select လုပ်ပါ`Environment variables (advanced)`နောက်ပိုင်းတွင်ပေါင်းစည်း[variable တွေကိုထည့်ပါ](#Environment-variables-description),
    -   variable ကို name ကိုဖြည့်ပါ**လှျို့ဝှက်စကား**တန်ဖိုးသည်သင်၏စကားဝှက်ဖြစ်သည်, ပြီးနောက်ကိုနှိပ်ပါ`Save and deploy`ဒါပဲ။

2.  ဦး စားပေးလမ်းကြောင်းကိုထည့်ပါ။
    -   variable တွေကိုထည့်ပါ`ADD`ဒေသဆိုင်ရာငြိမ်ဝပ်စွာ ဦး စားပေးသည့်လိုင်းတွင် port နံပါတ်မရှိလျှင်ပုံမှန် TLS port သည် 443 ခုဖြစ်ပြီးနံပါတ်ကိုမှတ်ချက်ပေးသည်။
        ```js
        discord.com#You can just put the domain name as follows
        www.speedtest.net:443#N1
        speed.cloudflare.com#N2
        zula.ir#N3
        creativecommons.org:2053#N4
        sky.rethinkdns.com#N5
        104.17.152.41#IPv4 is available
        [2606:4700:310c::ac42:2c39]#also IPv6
        ```

3.  subscription အကြောင်းအရာများရယူပါ:
    -   ဝင်ရောက်ခွင့်`https://[YOUR-PAGES-URL]/[password]`subscription အကြောင်းအရာရရှိနိုင်ပါသည်။
    -   ဥပမာအားဖြင့်`https://trauma.pages.dev/auto`ဤသည်သင်၏ Universal advelive subscription လိပ်စာဖြစ်သည်။
    -   ဥပမာအားဖြင့်`https://trauma.pages.dev/auto?sub`SSR +, SSR + စသည်တို့အတွက်သင့်လျော်သော base64 subscription format ကို
    -   ဥပမာအားဖြင့်`https://trauma.pages.dev/auto?clash`openclash များအတွက်သင့်လျော်သော subscription format ကိုတိုက်ပွဲဖြစ်ပါ။
    -   ဥပမာအားဖြင့်`https://trauma.pages.dev/auto?sb`Singbox Subscription format, Singbox အတွက်သင့်တော်သော Singbox Subsion format ကို

4.  CNAME စိတ်ကြိုက်ဒိုမိန်းကိုစာမျက်နှာများသို့ချည်နှောင်ခြင်း -
    -   စာမျက်နှာ console ၌တည်၏`Custom domains`tab ကို, အောက်တွင်ကိုနှိပ်ပါ`Set up a custom domain`.
    -   သင်၏အကာအကွယ်အလယ်ပိုင်းဒိုမိန်းအမည်ကိုဖြည့်ပါ, သင်၏ root domain name ကိုမသုံးရန်သတိထားပါ။
    -   သင်သတ်မှတ်ထားသောဒိုမိန်းအမည်ဖြစ်သည်`fuck.cloudns.biz`, ထို့နောက်ဖြည့်ရန်စိတ်ကြိုက်လယ်ပြင်ထည့်ပါ`iran.fuck.cloudns.biz`ဒါပဲ;
    -   Cloudflare ၏လိုအပ်ချက်အရသင်၏ domain name dns service provider ကိုပြန်ပို့ပေးပြီးစိတ်ကြိုက်ဒိုမိန်းကိုထည့်သွင်းလိမ့်မည်။`trauma`၏ CNAME စံချိန်`trauma.pages.dev`ထို့နောက်ကလစ်နှိပ်ပါ`Activate Domain`ဒါပဲ။

![rainbow](https://github.com/NiREvil/vless/assets/126243832/1aca7f5d-6495-44b7-aced-072bae52f256)

## proxyip

1.  cloudflare စာမျက်နှာများတွင်ဖြန့်ချိသောအခါ, သင် proxyip ကို 4 ကြိမ်မြောက်လိုင်းတွင်သတ်မှတ်နိုင်သည်`_worker.js`ဖိုင်။ သို့မဟုတ်ပတ်ဝန်းကျင် variable ကို set ကို set, variable ကိုအမည်ဖြစ်ပါတယ်`PROXYIP`

2.  When deploy in worker.dev, you can set proxyIP in 4th line of `_worker.js`ဖိုင်။ သို့မဟုတ်ပတ်ဝန်းကျင် variable ကို set ကို set, variable ကိုအမည်ဖြစ်ပါတယ်`proxyIP`

### Proxyip ကိုဘယ်လိုရှာရမလဲ

[ဒီမှာကြည့်ပါ](https://github.com/NiREvil/vless/edit/main/sub/ProxyIP.md)

## ပတ်ဝန်းကျင် variable တွေကိုဖော်ပြချက်

> [!မှတ်ချက်]၎င်းတို့ထဲမှနှစ်ခုသာရှိသည်, ပထမ ဦး ဆုံး variable ကိုလုံလောက်ပါတယ်`PASSWORD`နှင့်ဒုတိယ`PROXYIP`အောက်ဖော်ပြပါဇယားတွင်ဖော်ပြထားသော variable များကိုပညာရေးရည်ရွယ်ချက်များနှင့်ထပ်ဆင့်ရှင်းလင်းချက်များအတွက်သာဖြစ်သည်။![rainbow](https://github.com/NiREvil/vless/assets/126243832/1aca7f5d-6495-44b7-aced-072bae52f256)

| variable ကိုအမည်                                                                                   | နမူနာ                                                                                                                           | ပေြာဆို                                                                                                                   |
| -------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------- |
| လှျို့ဝှက်စကား                                                                                     | အကြီးဆုံး                                                                                                                       | မည်သည့်တန်ဖိုးကိုယူနိုင်ပါတယ်                                                                                             |
| proxyip                                                                                            | `bpb.radically.pro`သို့မဟုတ်သင်လိုချင်သောအခြားအရာတစ်ခု[ဒီမှာကြည့်ပါ](https://github.com/NiREvil/vless/edit/main/sub/ProxyIP.md) | CFCDN ဆိုဒ်များကိုရယူရန်အတွက်အခြား proxy node (proxyips များနှင့်အတူ proxyips မျိုးစုံ, 1 သို့မဟုတ် 2 လိုင်းအားလပ်ချိန်)) |
| ပေါင်း                                                                                             | `zula.ir,www.wto.org:2053`                                                                                                      | ဒေသခံနှစ်သက်သောဒိုမိန်းအမည် / ပိုမိုနှစ်သက်သော IP (ဒြပ်စင်များစွာကိုထောက်ပံ့သည်`,`သို့မဟုတ်လိုင်းအနေဖြင့်အစာကျွေးခြင်း)   |
| ပေါင်းထည့်သည်                                                                                      | <https://raw.githubusercontent.com/NiREvil/Trauma/main/cleanIPs.txt>                                                            | ရှင်းပြစရာမလိုပါ, လူတိုင်းနားလည်တယ်                                                                                       |
| နောက်ဖြစ်သော                                                                                       | SUBAPI.fxxk.dedyn.io                                                                                                            | Clad, Singbox စသည်တို့ကိုစသည်တို့                                                                                         |
| မျက်နှာပနုတ်                                                                                       | နာကေြာင်း                                                                                                                       | စာရင်းပေးသွင်းမှုအမည်                                                                                                     |
| ![rainbow](https://github.com/NiREvil/vless/assets/126243832/1aca7f5d-6495-44b7-aced-072bae52f256) | ![rainbow](https://github.com/NiREvil/vless/assets/126243832/1aca7f5d-6495-44b7-aced-072bae52f256)                              | ![rainbow](https://github.com/NiREvil/vless/assets/126243832/1aca7f5d-6495-44b7-aced-072bae52f256)                        |

* * *

## ဗွီဒီယိုသင်ခန်းစာများ

<https://github.com/NiREvil/Trauma/assets/126243832/92a430c3-4884-4831-bf8c-e328cfd78af8>

![rainbow](https://github.com/NiREvil/vless/assets/126243832/1aca7f5d-6495-44b7-aced-072bae52f256)

<https://github.com/NiREvil/Trauma/assets/126243832/f20a0215-bd75-4302-89dd-90a5bdd75cbc>

![rainbow](https://github.com/NiREvil/vless/assets/126243832/1aca7f5d-6495-44b7-aced-072bae52f256)

<https://github.com/NiREvil/Trauma/assets/126243832/f63c74c9-0e86-40a2-8894-e027c06776f5>

![rainbow](https://github.com/NiREvil/vless/assets/126243832/1aca7f5d-6495-44b7-aced-072bae52f256)

<https://github.com/NiREvil/Trauma/assets/126243832/61ce0b14-2c26-4325-a6c0-6f12cfc608d7>

![rainbow](https://github.com/NiREvil/vless/assets/126243832/1aca7f5d-6495-44b7-aced-072bae52f256)

# ကေျးဇူးတင်တတ်သော

[ca110us](https://github.com/ca110us/epeius)\|[ပိုးသတ်](https://github.com/3Kmfi6HP/EDtunnel/tree/trojan)\|[zizizefn](https://github.com/zizifn/edgetunnel)\|[ယီမင် 178](https://github.com/emn178/js-sha256)\|[acl4ssr](https://github.com/ACL4SSR/ACL4SSR/tree/master/Clash/config)\|[Shegs1999](https://github.com/SHIJS1999/cloudflare-worker-vless-ip)

![rainbow](https://github.com/NiREvil/vless/assets/126243832/1aca7f5d-6495-44b7-aced-072bae52f256)
