# V2Ray Heroku

**若需部署 V2Ray VLESS，请转到 [vless](https://github.com/googluck9012/vless-1.git) 分支。**
**若需部署 V2Ray VMESS，请转到 [vmess](https://github.com/googluck9012/vmess-1.git) 分支。**
**若需部署 V2Ray XRAY，请转到 [xray](https://github.com/googluck9012/xray-1.git) 分支。**



> [![Deploy](https://www.herokucdn.com/deploy/button.png)](https://dashboard.heroku.com/new?template=https://github.com/pheuihsd213/qin889)

 

反向代理：
<details>
<summary>cloudflare workers example</summary>

```js
const SingleDay = 'appname.herokuapp.com'
const DoubleDay = 'appname.herokuapp.com'
addEventListener(
    "fetch",event => {
    
        let nd = new Date();
        if (nd.getDate()%2) {
            host = SingleDay
        } else {
            host = DoubleDay
        }
        
        let url=new URL(event.request.url);
        url.hostname=host;
        let request=new Request(url,event.request);
        event. respondWith(
            fetch(request)
        )
    }
)
```
</details>

<details>
<summary>cloudflare workers example</summary>

```js
addEventListener(
  "fetch",event => {
     let url=new URL(event.request.url);
     url.hostname="应用名称.herokuapp.com";
     let request=new Request(url,event.request);
     event. respondWith(
       fetch(request)
     )
  }
)
```
</details>