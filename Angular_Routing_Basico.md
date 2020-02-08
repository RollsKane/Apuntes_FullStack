<!--___   ____  _    _ _______ _____ _   _  _____ 
 |  __ \ / __ \| |  | |__   __|_   _| \ | |/ ____|
 | |__) | |  | | |  | |  | |    | | |  \| | |  __ 
 |  _  /| |  | | |  | |  | |    | | | . ` | | |_ |
 | | \ \| |__| | |__| |  | |   _| |_| |\  | |__| |
 |_|  \_\\____/ \____/   |_|  |_____|_| \_|\___-->

<!--ROUTING EN ANGULAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAAR-->

<!--
/******************************  PASOS  ******************************\

1 - crear proyecto con routing, y tantos componentes como links queramos

2 - crear los path a los diferentes componentes en app-routing (dentro del array Routes)
-->

    EJEMPLO:

<script>


const routes: Routes = [
  { path: "", pathMatch: "full", redirectTo: "principal" }, // este path vacío serviría para que siempre redireccione al principal
  { path: "principal", component: MainComponent }, // path normal a otro componente
  { path: "info", component: AboutComponent }, // path normal a otro componente
  { path: "usuario/:usuarioId", component: UsuarioComponent }, // los : representan a las rutas dinámicas
  { path: "**", redirectTo: "principal" }, // este path con ** significa que cualquier texto que pongamos en la URL que no corresponda con alguno de los del array, te redirecciona a main
];

</script>

<!--
IMPORTANTE: Estar seguros de que cuando escribimos el nombre del component, nos lo importe arriba en app-routing

3 - luego nos vamos al HTML de app-component
-->

<script>

    <a [routerLink] ="['/principal']" > Principal </a>

</script>

En caso de estar usando un link <a>, en lugar de usar Href, tenemos que usar siempre [routerLink]="['/urlQueQueramosPoner']"
La razón es que Href recarga la página completa, mientras que [routerLink] tan solo recarga el componente


<!--
4 - en el HTML de app-component tambien añadimos la etiqueta -->
<router-outlet></router-outlet>

<!--
Esta será la etiqueta que representa los diferentes componentes que van cambiando según el link que pulsemos
-->