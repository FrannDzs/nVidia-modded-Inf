Geforce Experience Login Remover
---------------------------------

Geforce Experience is forcing  the user to login in order to use it, with the modified app.js version you#re able to bypass it.



HowTo
-----

Copy the script into the following dir (and override or backup the current app.js) C:\Program Files\NVIDIA Corporation\NVIDIA GeForce Experience\www\


Manually Method
---------------

Find the following line:
```bash
if (e.domains.list.indexOf(n) > -1) return !0
```

... and replace it with:
```bash
if (e.domains.list.indexOf(n) > -1) return w.handleLoggedIn(e), !0
```


Find:
```bash
return !("choose" === w.nvActiveAuthView && C)
            }, b()
```


... and replace it with the fake login:
```bash
w.handleLoggedIn({
                sessionToken: "dummySessionToken",
                userToken: "dummyUserToken",
                user: {
                    core: {
                        displayName: "Anonymous",
                        primaryEmailVerified: true
                    }
                }
            });
```


Enable ShadowPlay Share-Button
-------------------------------

This works only until [GFE <3.13](https://www.filehorse.com/download-nvidia-geforce-experience/34291/).

```bash
K.isShareSupported = !1, K.isShareButtonClicked = !1

or

if(e.domains.list.indexOf(n)>-1)return!0}return!1},A.isLeftPaneVisible=function(){return!("choose"===A.nvActiveAuthView&&T)},E()
```


```bash
K.isShareSupported = !0, K.isShareButtonClicked = !0
```
