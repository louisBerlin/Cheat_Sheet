# OAuth with GitHub 

## 1. In backend

1. Add a new dependency to your `pom.xml` file
 ```
<dependency>
   <groupId>org.springframework.boot</groupId>
   <artifactId>spring-boot-starter-oauth2-client</artifactId>
  </dependency>
```
2. Add the following properties to the `application.properties` file:
```
spring.security.oauth2.client.registration.github.client-id=${GITHUB_ID}
spring.security.oauth2.client.registration.github.client-secret=${GITHUB_SECRET}
spring.security.oauth2.client.registration.github.scope=none
app.url=${APP_URL}
```

3. Add the GitHub OAuth ID and Secret as environment variables to your run configuration and deployment.
4. Create a `SecurityConfig` class and configure authentication.
```java
@Configuration
@EnableWebSecurity
public class SecurityConfig {

    @Value("${app.url}")
    private String appUrl;

    @Bean
    public SecurityFilterChain securityFilterChain(HttpSecurity http) throws Exception {
        http
            .csrf(AbstractHttpConfigurer::disable)
            .authorizeHttpRequests(a -> a
                .requestMatchers("/api/auth/me").authenticated()
                .requestMatchers("/api/secured").authenticated()
                .anyRequest().permitAll()
            )
            .sessionManagement(s -> s.sessionCreationPolicy(SessionCreationPolicy.ALWAYS))
            .exceptionHandling(e -> e
                .authenticationEntryPoint(new HttpStatusEntryPoint(HttpStatus.UNAUTHORIZED)))
            .oauth2Login(o -> o.defaultSuccessUrl(appUrl));
        return http.build();
    }

}
```

> 💡 Spring automatically generates a login page at `/login` and a logout page at `/logout`.

> 💡 We can determine whether we are in a local or production environment based on the environment variable and set the appropriate URL for successful login.

> 💡 `@Value` is an annotation used to inject the value of an environment variable into a variable.

5. The `AuthController` class is used to fetch the currently logged-in user.
```java
@RestController
@RequestMapping("/api/auth")
public class AuthController {

    @GetMapping("/me")
    public String getMe(@AuthenticationPrincipal OAuth2User user) {
       return defaultOAuth2User.getAttributes().get("login").toString();
    }

   // or
    @GetMapping("/me")
    public String getMe(@AuthenticationPrincipal OAuth2User user){
        return user.getName();
    }

  // or
    @GetMapping("/me")
    public String getMe(){
        return SecurityContextHolder.getContext().getAuthentication().getName();
    }

}



```
## 2. In github

1. Go in Settings > Developer Settings > OAuth apps

<img width="818" alt="Screenshot 2024-05-02 at 11 17 25" src="https://github.com/louisBerlin/Cheat_Sheet/assets/80892116/a407eb90-c192-4416-b27d-88b21d53378a">


## 3. In frontend

1. change vite.config.ts

```ts
import { defineConfig } from 'vite'
import react from '@vitejs/plugin-react'

// https://vitejs.dev/config/
export default defineConfig({
  plugins: [react()],
  server: {
    proxy: {
      "/api": {
        target: "http://localhost:8080",
      },
    },
  },
})

```

2. Install axios ``` $ npm install axios ```

3. App.tsx



```ts
   
import './App.css'
import axios from "axios";
import {useState} from "react";

function App() {

    const[user, setUser] = useState<string>("")
    function login(){
        const host = window.location.host === 'localhost:5173' ? 'http://localhost:8080': window.location.origin;

        window.open(host + '/oauth2/authorization/github', '_self')
    }

    function getMe(){
        axios.get("/api/user/me")
            .then(response => {
                setUser(response.data)
            })
    }

  return (
    <>
     <h2>{user}</h2>
     <button onClick={login}>Login</button>
     <button onClick={getMe}>GetMe</button>
    </>
  )
}

export default App

```



## Resources

- [GitHub OAuth Documentation](https://docs.github.com/en/developers/apps/building-oauth-apps)
- [OAuth 2.0 Specification](https://oauth.net/2/)
- [Spring Security OAuth](https://spring.io/projects/spring-security-oauth)
