## 🗺️ Guide to the Odyssey

- [Episode 1: The Question](#episode-1-the-question)
- [Episode 2: The First Step, the Web Browser](#episode-2-the-first-step-the-web-browser)
- [Episode 3: Replacing the Samsung Ecosystem](#episode-3-replacing-the-samsung-ecosystem)
- [Episode 4: The Missing Link](#episode-4-the-missing-link)
- [Episode 5: Conclusions](#episode-5-conclusions)

# Episode 1: The Question

A few months ago I watched a PewDiePie video on YouTube about the risks of trusting Google's digital ecosystem too much, due to privacy violations and the collection of sensitive user data by the American company under the premise of the good Samaritan that makes your digital life easier. In response, PewDiePie decided to radically cut his ties with Google, literally removing any trace of the company from his digital ecosystem, with GrapheneOS as the cornerstone of this process: an alternative operating system to the traditional Android distributions on the market, focused on privacy and giving you back control of your own phone—something that should always have been yours. Since then I have been frankly obsessed with this topic, but I had left it on hold (I had a few very humble attempts at it) given the personal circumstances I faced to carry it out: first, geographical fatalism: living in Cuba (and within it, in a non-central place), my real chances of a stable internet connection to perform all the downloads and modifications seemed remote; and second, limited economic conditions, that is, a low-end phone for which I would have to adapt many of the applications I found during my research due to the processor's slowness. To cut a long story short, I basically set out to degoogle a Samsung A12 in Cuba without GrapheneOS (it is compatible almost exclusively with Google Pixel devices) and without fiber-optic internet to download apps in the blink of an eye. For context, most of the time my download speed did not exceed the 800 kbps threshold. On top of all this, I decided to undertake this odyssey amidst the escalation of economic pressure on the Island by the Trump administration and long periods without electricity. Before starting, I would like to make something very clear: this is not, in any sense, a political pamphlet; therefore, I wish to exclude its content from any discussion in that sphere. This is simply an act of digital sovereignty under complex conditions.

# Episode 2: The First Step, the Web Browser

The first step, obviously, had to be the browser. I couldn't pretend to use Chrome with Google as the search engine so that Google could track and store all the information of my internet searches or sell my personal information to advertising companies. But there is a real problem with this: given the conditions of scarce internet speed in Cuba (whether via mobile data or WiFi), Google is the fastest alternative, and speed in my context was irreplaceable, because subtracting about 2 Mbps for using an alternative search engine from an 800 Mbps connection has no noticeable effect, but for me every kilobyte was necessary. With this explained, my alternatives were reduced even further. If we think of a browser like Brave (heavy on user privacy and a first-rate ad blocker), which would be the best option, we have to discard it, since given the restrictions of the US embargo on Cuba, the Brave virtual domain is not accessible from the Island, and using a VPN is unthinkable, as this also considerably reduces the already diminished available connection. So, faced with the limitations, a savior appeared: Mozilla Firefox, especially its developer version, Nightly, was exactly what I needed—Open Source, lightweight, and, with some extra configurations, extremely private. So, the first step with the browser decided, I had to select the search engine. My first and most lucid choice was DuckDuckGo; in real terms it is the best choice, but we return to fatalism: DDG was frustratingly slower than Google. Again, in my context, these delays, although minimal, were unsustainable. Then the Startpage option appeared: a search engine that returns Google Search results but removes all your personal information (IP, trackers, etc.). Although in 2019 Privacy One Group (a subsidiary of System1, an advertising company) invested in Startpage, the company maintains its stance on privacy. The choice is to believe them or distrust them and sacrifice speed by using DDG (genuinely, if you have patience, it is the best option, although some prefer Startpage because it shows Google results, which DDG does not). Now I had browser + search engine, a good combo for privacy, but that wasn't everything—I needed to squeeze Firefox. What did I do?

## First layer

- **Enhanced tracking protection** (Settings / Privacy and Security) set to **"strict"**, which blocks most visible and hidden trackers, speeding up page loading.
- **Control of data sent to Mozilla** (also in settings)—a company after all. I thank you for your services, but I prefer to use you anonymously.

## Second layer (entering `about:config` in the address bar)

- **Disable telemetry**
  - `toolkit.telemetry.enabled` → `false`
  - `datareporting.healthreport.uploadEnabled` → `false`
- **Disable pre-connections**
  - `network.prefetch-next` → `false`
  - `network.dns.disablePrefetch` → `true`
- **Close IP leaks (WebRTC)**
  - `media.peerconnection.enabled` → `false`
- **Cookie isolation (dFPI)**
  - `network.cookie.cookieBehavior` → `5`
- **Fingerprinting evasion** (this may break some pages, as it is experimental; use with caution)
  - `privacy.resistFingerprinting` → `true`

## Third layer: encryption (DNS and connections)

- **Secure connections only (HTTPS-Only)**
  - Enable it in `Settings > Privacy and Security`.
- **Encrypt DNS queries (DNS over HTTPS)**
  - Go to `Settings > Privacy and Security > DNS over HTTPS`, select **Maximum Protection** and choose a provider (for example, Cloudflare or NextDNS).

## Fourth layer: extensions

- **[uBlock Origin](https://addons.mozilla.org/firefox/addon/ublock-origin/)** – blocks ads and trackers.
- **[Bitwarden](https://addons.mozilla.org/firefox/addon/bitwarden-password-manager/)** – manages passwords securely.

It should be noted that the DNS configurations described here only apply to the Firefox app; therefore, I also set a DNS in the phone's settings: `dns.mullvad.net`.

With all this, bye-bye Google Chrome and Google Search.

# Episode 3: Replacing the Samsung Ecosystem

In the realm of privacy, Open Source applications play a fundamental role, and it is not enough to eliminate Google. I also had to find an alternative to Samsung apps (Phone, Messages, Calculator, Camera, Calendar, Contacts, Voice Recorder, File Manager, Notes, Music Player, and Video Player) and to the other apps that hindered my idyllic Open Source ecosystem (Google Play Store, Google Board or Samsung Keyboard, Microsoft 365, Google Photos or Samsung Gallery).

Faced with this, I needed an Open Source app to download alternative apps and avoid Google Play Store. That is where F-Droid appeared: a massive repository of free apps, to which libraries can be added, and which has strong privacy policies.

I started, therefore, with the Fossify family, an Open Source ecosystem based on privacy that is very well optimized. From it I obtained: Phone, Messages, Calendar, Contacts, Voice Recorder, and Music Player. In Fossify I found a polished, lightweight, discreet, and highly functional digital ecosystem.

Then I wanted to cover the remaining apps. For video playback I chose VLC (well-known enough to spare an introduction). To replace Google Play Store, Aurora Store: an app that allows you to download apps from Google Play with an anonymous login that does not send your data to Google (yes, it is slower and the apps are larger, but it was a sacrifice that had to be made). For the calculator I chose OpenCalc, a lightweight and simple Open Source calculator. For Microsoft 365 I found Collabora Office, a LibreOffice app that does not collect your data, does not need an internet connection to function, and works exactly like Microsoft's tools. For Gboard, HeliBoard: the most functional and lightweight copy of the Google keyboard, comfortable to use and with a simple menu for having multiple languages at the same time, though without swipe typing. For Google Photos, Ente Photos: an open-source app with very robust end-to-end encryption (e2ee) that, minus some non-vital features, works almost like the Google app. Another option is Fossify Gallery; on even more modest phones it is the best choice. For the camera, OpenCamera: a fairly customizable and open-source app, though its interface may not please everyone. For the file explorer, Material Files: the undisputed king in design and functionality, Open Source, of course. For notes, Notally: an exceedingly simple app, open source and with a pleasant interface.

Other necessary apps are a VPN and an email app that is not Gmail. My choices in this case were from the same company: Proton. I selected Proton VPN and Proton Mail. For VPN, the best option is Mullvad VPN, but it is inaccessible in Cuba because it requires payment, and this is difficult on the Island since the necessary infrastructure for that purpose does not exist.

# Episode 4: The Missing Link

With all this we have solid work, but it can be better. One obstacle to overcome is Google Play Services: so to speak, the operating system within the operating system. This app is responsible for push notifications, location, authentication, and compatibility for a large part of the apps (via APIs). The option to replace this service is MicroG, an open-source project that acts in the same way. For my Samsung A12, this option was conflictive, since the best way MicroG could work is with a native operating system with support, like LineageOS, but these ROMs are not compatible with my phone model. There is the option of installing it on my own system without changing anything, but it may be unstable, and given the possibility of crashes or technical conflicts, it is better not to risk it, given the absence of reliable and quality technical support on the Island. Therefore, for now I can only make this concession, aiming to try it in the future under different conditions, or on an alternative phone on which to experiment.

# Episode 5: Conclusions

All things considered, my goals with this series were: first, to demonstrate that with dedication, curiosity, and a lot of patience something like this is possible under complex logistical conditions; second, to bring topics like these (without being an expert at all) to an audience that lacks this type of awareness—the Spanish-speaking, and specifically, the Cuban public. And yes, this may seem like extreme or paranoid behavior, but protecting your privacy and personal information is a universal right, which, whether out of carelessness, laziness, or ignorance, we tend to overlook, but which, as has been shown, is within the reach of anyone who wants to take care of their digital life (increasingly important in our world). Yes, it is not a complete degoogleization job; there are loose ends, whether due to concessions I had to make given my circumstances, or due to technological or geographical abysses that are insurmountable for me for now (self-hosting, the US embargo, the modesty of the hardware).

My goal, I must reiterate, is not to twist my discourse towards political paths, nor, much less, to impose digital behaviors on others. It is simply to educate, to advise, on digital sovereignty and cybersecurity. Another thing: I mention here some apps selected at my discretion through my own research, but that does not make them the best for this process, much less the only ones. I invite you to search by your own means, to inform yourselves, to experiment, and, like me, to overcome the difficulties of the path, something that, from experience, is tremendously satisfying.

---

## 📖 Versión original en español

## 🗺️ Guía de la Odisea

- [Episodio 1: La cuestión](#episodio-1-la-cuestión)
- [Episodio 2: El primer paso, el navegador web](#episodio-2-el-primer-paso-el-navegador-web)
- [Episodio 3: Sustituir el ecosistema de Samsung](#episodio-3-sustituir-el-ecosistema-de-samsung)
- [Episodio 4: El eslabón faltante](#episodio-4-el-eslabón-faltante)
- [Episodio 5: Conclusiones](#episodio-5-conclusiones)
- # Episodio 1, La cuestión:
Hace unos meses vi un vídeo de PewDiePie en Youtube sobre los riesgos de confiar demasiado en el ecosistema digital de Google, por razones de vulneración a la privacidad y obtención por parte de la compañía norteamericana de datos sensibles sobre los usuarios de todo el mundo bajo la premisa del buen samaritano que te facilita la vida digital. Ante esto Pewdiepie decidió eliminar radicalmente sus vínculos con Google, literalmente eliminó cualquier rastro de la compañía en su ecosistema digital, bajo la piedra angular de este proceso: GrapheneOS, un sistema operativo alternativo a las distribuciones tradicionales de los androids del mercado que está enfocado en la privacidad y en devolverte el control de tu propio móvil, algo que siempre debió ser tuyo. Desde entonces he estado francamente obsesionado con este tema, pero lo había dejado en suspenso (tuve algunos intentos bastante humildes al respecto) dadas las condiciones personales que tenía para llevarlo a cabo: primero, el fatalismo geográfico: al vivir en Cuba (y dentro de esta, en un sitio nada medular), mis opciones reales de una conexión estable a internet para realizar todas las descargas y modificaciones parecía alejada; y segundo, las condiciones económicas limitadas, o sea, un móvil de gama baja para el cual tendría que adaptar muchas de las aplicaciones que encontrase investigando dada la lentitud del procesador. Para no aburrir, básicamente me propuse degooglear un Samsung A12 en Cuba sin GrapheneOS (es compatible casi exclusivamente con los Pixel de Google) y sin un internet de fibra óptica para descargar aplicaciones en un pestañazo. Por contextualizar, la mayoría de las veces mi velocidad de descarga no superaba el umbral de los 800kbps, a todo esto, decidí emprender esta odisea en medio de la escalada de presiones económicas hacia la Isla por parte de la administración Trump y los largos períodos de ausencia de electricidad. Antes de comenzar quisiera dejar algo bien claro, esto no es, en ningún sentido un panfleto sobre política, por ende, deseo que se excluya el contenido del mismo de cualquier discusión en ese rubro, esto, solamente, se trata de un acto de soberanía digital bajo condiciones complejas.

# Episodio 2: El primer paso, el navegador web.
El primer paso, evidentemente debía ser el navegador, no podía pretender usar Chrome con Google como motor de búsqueda para que Google rastreara y guardara toda la información de mis consultas en internet o vendiera mi información personal a compañías de publicidad, pero, con esto existe un problema real, dadas las condiciones de escasa velocidad de internet en Cuba (ya sea mediante datos móviles o WiFi), Google es la alternativa más rápida, y la velocidad en mi contexto era insustituible, porque, a una conexión de 800mbps que se le resten unos 2mbps por usar un motor de búsqueda alterno en nada afecta, pero para mí cada kilobyte era necesario. Con esto explicado, mis alternativas se reducían incluso más, si pensamos en un navegador como Brave (pesado en la privacidad del usuario y bloqueador de anuncios de primer orden), que sería la mejor opción, tenemos que descartarlo, ya que dadas las restricciones del embargo norteamericano a Cuba, el dominio virtual de Brave no es accesible desde la Isla, y usar VPN es impensable, ya que esto también reduce considerablemente la ya mermada conexión disponible. Entonces, ante las limitaciones apareció un salvador, Mozilla Firefox, especialmente su versión para desarrolladores, Nightly, era precisamente lo que necesitaba, Open Source, ligero y, con algunas configuraciones extra, extremadamente privado. Entonces, el primer paso con el navegador decidido era seleccionar el motor de búsqueda, mi primera y más lúcida opción fue DuckDuckGo, a efectos reales es la mejor elección, pero volvemos al fatalismo, DDG resultaba frustrantemente más lento que  Google, de nuevo, en mi contexto, estos retrasos, aunque mínimos, resultaban insostenibles. Entonces apareció la opción de Startpage, buscador que arroja los resultados de Google Search pero elimina toda tu información personal (IP, rastreadores, etc.), si bien en 2019 Privacy One Group (subsidiaria de System1, una empresa de publicidad)invirtió en Startpage, estos mantienen su postura en cuanto la privacidad, la elección es, creerles o desconfiar y sacrificar velocidad usando DDG (genuinamente si tienes paciencia es la mejor opción, aunque algunos prefieren Startpage porque muestra los resultados de Google, cosa que DDG no hace). Ya tenía navegador + buscador, un buen combo para la privacidad, pero eso no era todo, necesitaba exprimir firefox.

¿qué hice?:

## Como primera capa

1. **Protección antirrastreo mejorada**  
   (Configuración / Privacidad y Seguridad) marcada como **«estricta»**, lo cual bloquea la mayoría de rastreadores visibles y ocultos, acelerando la carga de páginas.
2. **Control de envío de datos a Mozilla**  
   (también en ajustes), compañía al fin y al cabo, te agradezco por tus servicios, pero prefiero usarte en anonimato.

## Como segunda capa (introduciendo `about:config` en la barra de direcciones)

1. **Desactivación de la telemetría**  
   - `toolkit.telemetry.enabled` → `false`  
   - `datareporting.healthreport.uploadEnabled` → `false`
2. **Desactivación de las preconexiones**  
   - `network.prefetch-next` → `false`  
   - `network.dns.disablePrefetch` → `true`
3. **Clausura de fugas de IP (WebRTC)**  
   - `media.peerconnection.enabled` → `false`
4. **Aislamiento de cookies (dFPI)**  
   - `network.cookie.cookieBehavior` → `5`
5. **Evasión de la huella digital** (esto puede romper algunas páginas, pues es experimental, usar con precaución)  
   - `privacy.resistFingerprinting` → `true`

## Como tercera capa: capa de cifrado (DNS y conexiones)

1. **Solo conexiones seguras (HTTPS-Only)**  
   Habilítalo en `Configuración > Privacidad y Seguridad`.
2. **Cifrar las consultas DNS (DNS sobre HTTPS)**  
   Ve a `Configuración > Privacidad y Seguridad > DNS sobre HTTPS`, selecciona **Protección Máxima** y elige un proveedor (por ejemplo, Cloudflare o NextDNS).

## Como cuarta capa: extensiones

1. **[uBlock Origin](https://addons.mozilla.org/firefox/addon/ublock-origin/)** – bloquea anuncios y rastreadores.
2. **[Bitwarden](https://addons.mozilla.org/firefox/addon/bitwarden-password-manager/)** – gestiona contraseñas de forma segura.

Cabe señalar que las configuraciones de DNS aquí descritas solo aplican a la app de Firefox, ergo, también puse un DNS en los ajustes del móvil: dns.mullvad,net.

Con todo esto, byebye Google Chrome y Google Search.


# Episodio 3: Sustituir el ecosistema de Samsung.

Dentro de la privacidad, las aplicaciones Open Source juegan un papel fundamental, y no basta con eliminar Google, también había que encontrar una alternativa a las apps de Samsung (Teléfono, Mensajes, Calculadora, Cámara, Calendario, Contactos, Grabadora de voz, Gestor de Archivos, Notas, Reproductor de música y Reproductor de vídeo) y a las otras apps que entorpecían mi ecosistema Open Source idílico (Google Play Store, GoogleBoard o Teclado de Samsung, Microsoft 365, Google Fotos o Galería de Samsung).
Ante esto, necesitaba una app Open Source para descargar las apps alternativas y evitar Google Play Store, ahí apareció F-Droid, un repositorio de apps libres masivo, al cual se pueden añadir librerías, y el cual tiene políticas de privacidad elevadas.
Comencé, pues, con la familia de Fossify https://github.com/FossifyOrg, un ecosistema Open Source basado en privacidad que está muy bien optimizado, de esta obtuve: Teléfono, Mensajes, Calendario, Contactos, Grabadora de voz y reproductor de música. En fossify encontré un ecosistema digital pulido, ligero, discreto y altamente funcional.
Luego quise cubrir las apps restantes, para reproducción de video escogí VLC (de sobra conocido), para sustituir a Google Play Store, a Aurora Store, una app que te permite descargar apps de Google Play desde un login anónimo que no envía tus datos a Google (sí, es más lenta y las apps pesan más, pero es un sacrificio que había que tomar). Para la calculadora elegí OpenCalc, calculadora Open Source, ligera y sencilla. Para Microsoft 365 encontré Collabora Office, una app de LibreOffice que no recopila tus datos, no necesita internet para funcionar y funciona exactamente como las herramientas de Microsoft. Para Gboard, HeliBoard, la copia más funcional y ligera del teclado de Google, cómodo de usar y con un menú sencillo para tener varios idiomas a la vez, eso sí, sin el swype typing. Para Google Photos, Ente Photos, app de código abierto con cifrado de extremo a extremo (e2ee) muy robusto, que, quitando algunas funciones no vitales, funciona casi como la app de Google, otra opción es Fossify Gallery, en móviles incluso más modestos es la mejor opción. Para la cámara OpenCamera, app bastante personalizable y de código abierto, su interfaz puede no gustar a todos. Para el explorador de archivos, Material Files, el rey indiscutible en diseño y funcionalidad, Open Source, desde luego. Para las notas, Notally, app excesivamente sencilla, de código abierto y con interfaz agradable. 
Otras apps necesarias son una VPN y una app de Correo que no sea Gmail, desde luego, mis opciones en este caso fueron a una misma empresa: Proton, seleccioné Proton VPN y Proton Mail, para el VPN la mejor opción es Mullvad VPN, pero es inaccesible en Cuba porque requiere pago, y esto se dificulta en la Isla ya que no existe la infraestructura necesaria para ese propósito.

# Episodio 4: El eslabón faltante
Con todo esto tenemos un trabajo sólido, pero puede ser mejor, un obstáculo a sortear es Google Play Services, por así decirlo, el sistema operativo dentro del sistema operativo, esta app se encarga de las notificaciones push, la localización, la autenticación y la compatibilidad de gran parte de las apps (mediante APIs). La opción para reemplazar este servicio es MicroG, un proyecto de código abierto que actúa de la misma forma. Para mi Samsung A12 esta opción era conflictiva, ya que la forma en que mejor podía funcionar MicroG es con un sistema operativo nativo con soporte, tipo LineageOS, pero estos ROM no son compatibles con mi modelo de móvil; existe la opción de instalarlo en mi propio sistema sin cambiar nada, pero puede ser inestable, y ante la posibilidad de bloqueos o conflictos técnicos es mejor no arriesgar, dada la ausencia de un soporte técnico confiable y de calidad en la Isla. Por tanto, por ahora me queda solamente hacer esta concesión, apuntando a probarla en el futuro bajo condiciones distintas, o un móvil alternativo en el cual experimentar.

# Episodio 5: Conclusiones
A todo esto, mis objetivos con esta serie eran, primero, demostrar que con empeño, curiosidad, y mucha paciencia es posible algo como esto bajo condiciones logísticas complejas, dos, llevar temas como estos (sin ser un experto para nada) a un público que carece de este tipo de concientización, el hispanohablante, y, específicamente, el cubano, y sí, es probable que esto parezca una conducta extrema, o paranoica, pero proteger tu privacidad e información personal es un derecho universal, el cual, ya sea por despreocupados, holgazanes, o ignorantes, solemos soslayar, pero que, como se ha visto, esta al alcance de todo aquel que quiera cuidar su vida digital (cada vez más importante en nuestro mundo).
Y sí, no es un trabajo de degoogleización completo, hay cabos sueltos, ya sea por concesiones que tuve que realizar dadas mis condiciones, o por abismos tecnológicos o geográficos insondables para mí por ahora (el selfhosting, el embargo norteamericano, la modestia del hardware).
Mi objetivo, cabe reiterar, no es la tergiversación de mi discurso en torno a derroteros de la política, ni, mucho menos, imponer conductas digitales a los demás, simplemente educar, aconsejar, sobre la soberanía digital y la seguridad cibernética. Otra cosa, yo aquí menciono algunas apps seleccionadas a mi arbitrio mediante investigación propia, pero eso no las hace las mejores para este proceso, ni mucho menos, las únicas, los invito a buscar por sus medios, informarse, experimentar y, como yo, sortear las dificultades del camino, cosa que, por experiencia, resulta tremendamente satisfactoria.

