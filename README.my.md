# CF-Workers & Pages ကိုသုံး၍ Trojan ကို ဆာဗာမဲ့ လွှင့်တင်ပါ။

🇮🇷[ပြင်သစ်](README.fa.md)  
🇹🇷[တူရကီ](README.tr.md)  
🇬🇧[အင်္ဂလိပ်](README.md)  
🇩🇪[ဂျာမနီ](README.de.md)

၎င်းသည် cloudflare Workers ပလက်ဖောင်း ပေါ်တွင်အခြေခံသည်။ မူရင်းဗားရှင်းကို အခြေခံ၍ Trojan စီစဉ်ဖွဲ့စည်းမှု အချက်အလက်များကို ပြသရန် ပြုပြင်ထားပြီး စာရင်းသွင်း ခြင်း လုပ်ဆောင်ချက် အဖြစ် ပြောင်းလဲပေးသည်။ ဤ script ကို အသုံးပြု ကာ အွန်လိုင်း စီစဉ်ဖွဲ့စည်းမှုဖြင့် Clash (သို့) Singbox ကဲ့သို့သော ကိရိယာများသို့ Trojan စီစဉ်ဖွဲ့စည်းမှု အချက်အလက်များကို အလွယ်တကူ ပြောင်းလဲနိုင်ပါသည်။

[tg channel](https://t.me/F_NiREvil)

![rainbow](https://github.com/NiREvil/vless/assets/126243832/1aca7f5d-6495-44b7-aced-072bae52f256)

## မာတိကာ

-   [worker ဖြင့် လွှင့်တင်ခြင်း နည်းလမ်း](#Workers-deployment-method)
-   [Pages ဖြင့် လွှင့်တင်ခြင်း နည်းလမ်း](#Pages-deployment-method)
-   [ပရိုစီအိုင်ပီ](#proxyIP)
-   [ဝန်းကျင် ဆိုင်ရာ ကိန်းရှင် (Enviroment Variable) ဆိုင်ရာ အညွှန်း](#Environment-variables-description)
-   [ဗွီဒီယို သင်ခန်းစာများ](#Video-tutorials)![rainbow](https://github.com/NiREvil/vless/assets/126243832/1aca7f5d-6495-44b7-aced-072bae52f256)

<details>
<summary> အသုံးပြုပါ </summary>

-   ဤစီမံကိန်းကို သင်ယူခြင်း, သုတေသန နှင့် ဘေးကင်းလုံခြုံရေး စစ်ဆေးခြင်း အတွက် သာ ဒီဇိုင်း ပြုလုပ် ထားပါသည်။ ၎င်းသည် လုံခြုံရေး သုတေသီများ, ပညာရှင်များ နှင့် နည်းပညာ စိတ်အားထက်သန်မှုများ ကို ကွန်ယက်ဆက်သွယ်ရေး နည်းပညာကို နားလည်ရန် နှင့် လေ့ကျင့်ရန် ကိရိယာ တစ်ခုအဖြစ်သာ သုံးစွဲရန် ရည်ရွယ်သည်။
    </details>

<details>
<summary> တရားဝင် ပါစေ </summary>
  
  - အသုံးပြု သူ များ သည် ဤ စီမံကိန်း ကို ကူးယူ ပြီး အသုံးပြု သောအခါ ဒေသခံ ဥပဒေ များ နှင့် စည်းမျဉ်း များ ကို လိုက်နာ ရ မည် ။
  - အသုံးပြု သူ များ သည် သူ တို့ ၏ လုပ်ရပ် များ ကို ယင်းတို့ နှင့် ဆိုင်ရာ နိုင်ငံ၊ ဒေသ ၏ ဥပဒေ ၊ စည်းမျဉ်း များ နှင့် အခြား သော ပြဒါန်းထားသည့် လိုပ်အပ်ချက်များ ကို တိကျစွာ လိုက်နာရန် တာဝန် ရှိသည်။

</details>

<details>
<summary> ⚠️ အန္တရာယ် သတိပေးချက် </summary>
  - ကွန်ယက် Node ဖွဲ့စည်းမှု အချက်အလက်များ ပေါက်ကြားခြင်းမှ ကာကွယ်နိုင်စေရန် မယုံကြည်ရသေ အတုအယောင် Node ဖွဲစည်းမှု ပြင်ဆင်ပြောင်လဲ ဝန်ဆောင်သူများ ထံသို့ ဖွဲ့စည်မှု့ အချက်အလက်များ ပေးပို့ ပြင်ဆင်ခြင်း ကိုရှောင်ရှားပါ။
</details>

## worker ဖြင့် လွှင့်တင်ခြင်း နည်းလမ်း

1.  Cloudflare Worker ဖြင့် လွီင့်တင်ရန်

    -   cloudflare worker console တွင် အလုပ်သမား အသစ် တစ်ခုကို ဖန်တီးပါ။

    -   ပြီးလျှင် [worker.js](_worker.js) ရှိ အချက်အလက်များကို worker အယ်ဒီတာ သို့ ကူးထည့်ပါ။

    -   လိုင်းနာပတ် 3 ရှိ `password` ကို သင့်ကိုယ်ပိုင် **စကားဝှက်** ဖြင့် ပြောင်းပါ။

    -    နောက်ထပ် နည်းလမ်း မှာ , သင်တိုက်ရိုက် လွှင့်တင် ရန်အောက်ပါခလုတ်ကိုနှိပ်ပါ။

    [![Deploy to Cloudflare Workers](https://deploy.workers.cloudflare.com/button)](https://deploy.workers.cloudflare.com/?url=https://github.com/NiREvil/Trauma)

2.  နှစ်သက်ရာ ဦးစားပေး ကွန်ယက် လမ်းကြောင်းကို ထည့်ပါ။
    -   အောက်ဖော်ပြပါ `addresses` ဖောမတ် နဲ့အညီ နှစ်သက်ရာ ဒိုမိန်း / သန့်ရှင်းသော IP (အဘန်းမခံထားရသော) ထည့်ပါ။ Port နံပါတ်မရှိပါက ပုံမှန် TLS port သည် 443 ဖြစ်ပြီး # သင်္ကေတက နောက်တွင် alias ကို မှတ်ချက် အနေဖြင့်ပေးနိင်သည်။
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
    -   cloudflare စာမျက်နှာများ console တွင်ရွေးချယ်ပါ`Connected to Git`ထို့နောက်ရွေးပါ`trauma`item ပြီးနောက်ကိုကလစ်နှိပ်ပါ`Start setting up`。
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

2.  Workers.dev တွင်တပ်ဆင်သောအခါသင် proxyip ကို 4 ကြိမ်မြောက်လိုင်းတွင်သတ်မှတ်နိုင်သည်`_worker.js`ဖိုင်။ သို့မဟုတ်ပတ်ဝန်းကျင် variable ကို set ကို set, variable ကိုအမည်ဖြစ်ပါတယ်`proxyIP`

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

[ca110us](https://github.com/ca110us/epeius)\|[ပိုးသတ်](https://github.com/3Kmfi6HP/EDtunnel/tree/trojan)\|[zizifn](https://github.com/zizifn/edgetunnel)\|[ယီမင် 178](https://github.com/emn178/js-sha256)\|[acl4ssr](https://github.com/ACL4SSR/ACL4SSR/tree/master/Clash/config)\|[Shegs1999](https://github.com/SHIJS1999/cloudflare-worker-vless-ip)

![rainbow](https://github.com/NiREvil/vless/assets/126243832/1aca7f5d-6495-44b7-aced-072bae52f256)
