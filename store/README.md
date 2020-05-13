# 

Comando útiles al usar **nuxtjs/auth**

<img src="./readme_img/img01.png" height="100">

Comprobar si el *login* está activo
~~~console
$nuxt.$auth.loggedIn
~~~

Obtener datos del usuario *leagueado*
~~~console
$nuxt.$auth.user
~~~

Cerrar la sesión de usuario iniciada
~~~console
$nuxt.$auth.logout()
~~~