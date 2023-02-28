# next-js-error-fix-note

## for route.push used to async function if need to return , have to return null or self calling async funtion

```
  async function handleNavigation() {
    if (userInfo?.role === "admin") {
      await router.push("/admin/dashboard");
    } else if (userInfo.role === "user") {
      await router.push("/user/dashboard");
    }
  }
  if (userInfo?.email) {
    handleNavigation();
    return null;
  }

```

## self calling async funtion 

```

(async()=>{
await router.push("/")
})()

```

## localstorage not defiend error fix


if(window !=="undifiend"){
//statement
}

```

  if (typeof window !== "undefined") {
      const userInfoString = localStorage.getItem("user_info");
      const user_info = JSON.parse(userInfoString);
      return user_info;
    }
 
 ```
