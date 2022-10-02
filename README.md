# Pi-hole_list
El proyecto Pi-hole_list es un proyecto en el cual bloqueamos y protegemos en toda la red a través de su propio hardware con docker®. Pi-hole® y Adguard Home® es un sumidero de DNS que protege sus dispositivos de contenidos no deseados sin necesidad de instalar ningún software del lado del cliente.


<p align="center">
        <img src="https://github.com/JuanRodenas/Pi-hole_list/blob/main/pihole.png" alt="Pi-hole" width="320"/>
        <img src="https://github.com/JuanRodenas/Pi-hole_list/blob/main/AdGuard_Logo.png" alt="AdGuard Home" width="280"/>
    </a>
    <br>
    <strong>Bloqueo de anuncios en toda la red a través de su propio hardware</strong>
</p>
<!-- markdownlint-enable MD033 -->

## Enlaces a instalación o desarrollador
| PROYECTO | LINK INSTALACIÓN | LINK DESARROLLADOR |
| :-- | :--: | :--: |
| <img src="https://github.com/JuanRodenas/Pi-hole_list/blob/main/AdGuard_Logo.png" alt="AdGuard Home" width="32"/> Adguard Home® | [INSTALACIÓN](https://github.com/JuanRodenas/AdGuardHome) | [DESARROLLADOR](https://adguard.com/es/adguard-home/overview.html) |
| <img src="https://github.com/JuanRodenas/Pi-hole_list/blob/main/pihole.png" alt="Pi-Hole" width="40"/> Pi-hole® | [INSTALACIÓN](https://github.com/JuanRodenas/Pihole) | [DESARROLLADOR](https://pi-hole.net/) |


## Detalles
Estas listas se crearon porque quería algo con un poco más de control sobre lo que se bloquea. Muchas listas son de todo o nada. Nos propusimos crear listas con más control sobre lo que se bloquea.

### Versiones:

<details>
<summary>Versión original:</summary>

<Original>&nbsp;Todas las urls de esta versión **van** precedidas de una dirección IP en el archivo txt o host:</Original>

<p>  &nbsp;&nbsp;<code>0.0.0.0 example.com</code> – Enviará el dominio example.com a la dirección 0.0.0.0 (pero no para sus subdominios)</p>
<p>  &nbsp;&nbsp;<code>127.0.0.1 example.com</code> – devolverá la dirección 127.0.0.1 para el dominio example.com (pero no para sus subdominios).</p>

</details>
&nbsp;
<details>
<summary>Versión sin IP a la izquierda:</summary>

<Original>&nbsp;Todas las urls de esta versión **no** van precedidas de una dirección IP en el archivo txt o host:</Original>

<p>  &nbsp;&nbsp;<code>example.com</code></p>

<sup>Nuestros usuarios nos han comunicado que algunos dispositivos dan error si la url va precedida de una dirección IP.</sup>
</details>
&nbsp;
<details>
<summary>Adguard Version:</summary>

<p>&nbsp;Todas las urls de esta versión de la lista **AdGuard** aparecen en el archivo de hosts de la siguiente manera:</p>

<p>  &nbsp;&nbsp;<code>||example.org^</code> – bloquea el acceso al dominio <code>example.org</code> y a todos sus subdominios</p>
<p>  &nbsp;&nbsp;<code>@@||example.org^</code> – desbloquea el acceso al dominio <code>example.org</code> y a todos sus subdominios</p>
<p>  &nbsp;&nbsp;<code>/REGEX/</code> – bloquea el acceso a los dominios que coincidan con la expresión regular especificada. Por ejemplo, la regla <code>/example.*/</code> bloqueará los hosts que coincidan con el <code>example.*</code></p>
<p>  &nbsp;&nbsp;<code>$</code> – Es el delimitador, que indica que el resto de la regla son modificadores. Los modificadores deben ubicarse al final de la regla después del carácter y estar separados por comas. Por ejemplo <code>||example.org^$important</code>.</p>
<p>  &nbsp;&nbsp;<code>$important</code> – El modificador aplicado a una regla aumenta su prioridad sobre cualquier otra regla sin el modificador. Incluso por encima de las reglas básicas de excepción.</p>
<p>  &nbsp;&nbsp;<code>*</code> – el carácter comodín. Se utiliza para representar cualquier conjunto de caracteres. También puede ser una cadena vacía o una cadena de cualquier longitud.</p>
<p>  &nbsp;&nbsp;<code>^</code> – el carácter separador. A diferencia del bloqueo de anuncios del navegador, no hay nada que separar en un nombre de host, por lo que el único propósito de este carácter es marcar el final del nombre de host.</p>
<p>  &nbsp;&nbsp;<code>|</code> – un puntero al principio o al final del nombre de host. El valor depende de la ubicación del carácter en la máscara. Por ejemplo, la regla <code>ample.org|</code> corresponde a <code>example.org</code>, pero no a <code>example.org.com</code>. <code>|example</code> corresponde a <code>example.org</code> pero no a <code>test.example.org</code></p>
    
<sup>Las instrucciones son actuales a partir de [AdGuard Home](https://github.com/AdguardTeam/AdGuardHome/wiki/Hosts-Blocklists#special-characters) v0.107.2. AdGuard admite las versiones anteriores.</sup>
<sup>Las instrucciones que admite [AdGuard Home](https://kb.adguard.com/en/general/how-to-create-your-own-ad-filters).</sup>
</details>
&nbsp;
<details>
<summary>Comentarios en las listas:</summary>

<p>&nbsp;Todas las urls de esta versión de la lista aparecen en el archivo de hosts de la siguiente manera</p>

<p>  &nbsp;&nbsp;<code># comentario</code> – solo un comentario</p>
<p>  &nbsp;&nbsp;<code>! comentario</code> – solo un comentario</p>

</details>
&nbsp;

### Uso:
<details>
    <summary>Utilizar con Pi-Hole <img src="https://github.com/JuanRodenas/Pi-hole_list/blob/main/pihole.png" alt="Pi-Hole" width="40"/>:</summary>

## Instrucciones de uso con Pi-Hole:

1. Copie el enlace al formato Pi-hole de la lista deseada (de la tabla correspondiente que aparece a continuación).
2. Añade la URL a las listas de bloqueo de tu Pi-hole (**Inicio de sesión** > **Gestión de grupos** > **Listas** > **Pega la URL de la lista en el campo "Dirección", añade un comentario** > **Haz clic en "Añadir "**)
3. Actualizar Gravity (**Herramientas** > **Actualizar Gravity** > **Hacer clic en "Actualizar "** )

&nbsp;
<sup>Instrucciones actuales a partir de Pi-hole 5.2.4. Las instrucciones pueden ser ligeramente diferentes en la actualidad. Las instrucciones se actualizarán cuando se publique la versión 6.</sup>
</details>
&nbsp;

<details>
    <summary>Utilizar con AdGuard Home <img src="https://github.com/JuanRodenas/Pi-hole_list/blob/main/AdGuard_Logo.png" alt="AdGuard Home" width="32"/>:</summary>

## Instrucciones de uso con AdGuard Home:

1. Copie el enlace al formato de AdGuard correspondiente a la lista deseada (de la tabla correspondiente a continuación).
2. Añada la URL a su lista de bloqueo de AdGuard (**Inicio de sesión** > **Filtros** > **Listas de bloqueo DNS** > **Añadir lista de bloqueo** > **Añadir una lista personalizada** > **Introducir nombre** > **Pegar la URL del enlace copiado**)
3. La lista se activa automáticamente y está lista para empezar a bloquear.

&nbsp;
<sup>Las instrucciones son actuales a partir de AdGuard Home v0.107.2</sup>
</details>
&nbsp;

# Listas para Pihole <img src="https://github.com/JuanRodenas/Pi-hole_list/blob/main/pihole.png" alt="Pi-Hole" width="40"/> y AdGuard Home <img src="https://github.com/JuanRodenas/Pi-hole_list/blob/main/AdGuard_Logo.png" alt="AdGuard Home" width="32"/>

## Main White Lists

| List | Link | AdGuard | Description |
| -- | :--: | :--: | -- |
| Whitelist | [Link](https://raw.githubusercontent.com/JuanRodenas/Pi-hole_list/main/Listas/whitelist.txt) | - | Lista blanca a permitir |


## Main Black Lists


#### Host
| List Host | Link | AdGuard | Description |
| -- | :--: | :--: | -- |
| Listas oisd | [Link](https://dbl.oisd.nl) | [Link](https://abp.oisd.nl) | To Block host Adguard and domains [dbl.oisd](https://oisd.nl/) |
| urlhaus-filter-domains | [Link](https://raw.githubusercontent.com/AzagraMac/PiHoleDocker/master/list/urlhaus-filter-domains.txt) | - | - |
| everything | [Link](https://blocklistproject.github.io/Lists/everything.txt) | [Link](https://raw.githubusercontent.com/blocklistproject/Lists/master/adguard/everything-ags.txt) | To Block everything |
| energized pro | [Link](https://energized.pro/unified/formats/hosts.txt) | - | To Block [energized](https://energized.pro/) |
| d3host | [Link](https://raw.githubusercontent.com/d3ward/toolz/master/src/d3host.txt) | - | [d3ward](https://github.com/d3ward) popular list |


#### Malware
| List Malware | Link | AdGuard | Description |
| -- | :--: | :--: | -- |
| Gambling-porn | [Link](https://raw.githubusercontent.com/JuanRodenas/Pi-hole_list/main/List/Gambling.txt) | [Link](https://github.com/blocklistproject/Lists/blob/master/adguard/gambling-ags.txt) | To Block Gambling and porn |
| Malware | [Link](https://blocklistproject.github.io/Lists/malware.txt) | [Link](https://raw.githubusercontent.com/blocklistproject/Lists/master/adguard/malware-ags.txt) | To Block malware |
| Ransomware | [Link](https://raw.githubusercontent.com/blocklistproject/Lists/master/ransomware.txt) | [Link](https://raw.githubusercontent.com/blocklistproject/Lists/master/adguard/ransomware-ags.txt) | To Block ransomware |
| phishing | [Link](https://phishing.army/download/phishing_army_blocklist_extended.txt) | - | To Block phishing |


#### Tracking/Ads
| List Tracking/Ads | Link | AdGuard | Description |
| -- | :--: | :--: | -- |
| SmartTV | [Link](https://raw.githubusercontent.com/Perflyst/PiHoleBlocklist/master/SmartTV.txt) | [Link](https://raw.githubusercontent.com/blocklistproject/Lists/master/adguard/smart-tv-ags.txt) | To Block SmartTV |
| WindowsSpyBlocker | [Link](https://raw.githubusercontent.com/crazy-max/WindowsSpyBlocker/master/data/hosts/spy.txt) | - | To Block WindowsSpyBlocker |
| GoodbyeAds-Ultra | [Link](https://raw.githubusercontent.com/jerryn70/GoodbyeAds/master/Hosts/GoodbyeAds-Ultra.txt) | [Link](https://raw.githubusercontent.com/hagezi/dns-blocklists/main/adblock/pro.plus.txt) | To Block [hagezi](https://github.com/hagezi/dns-blocklists) and [jerryn70](https://github.com/jerryn70/GoodbyeAds) |
| GoodbyeAds-d3host | - | [Link](https://raw.githubusercontent.com/d3ward/toolz/master/src/d3host.txt) | To Block GoodbyeAds-d3host |
| ads-and-tracking-extended | [Link](https://www.github.developerdan.com/hosts/lists/ads-and-tracking-extended.txt) | - | To Block ads-and-tracking-extended |
| Adblock_Plus | [Link](https://raw.githubusercontent.com/notracking/hosts-blocklists/master/adblock/adblock.txt) | [Link](https://raw.githubusercontent.com/JuanRodenas/Pi-hole_list/main/List/Adblock_Plus_Ads.txt) | To Block Tracking AdBlock |

#### Adguard team filters
| List Tracking/Ads | Link | Description |
| -- | :--: | -- |
| AdGuardSDNSFilter | [Link](https://adguardteam.github.io/AdGuardSDNSFilter/Filters/filter.txt) | AdGuard team DNS filter |
| AdAway | [Link](https://adaway.org/hosts.txt) | AdAway default blocklist |
| Game Console Adblock List | [Link](https://raw.githubusercontent.com/DandelionSprout/adfilt/master/GameConsoleAdblockList.txt) | Game Console Adblock List |
| SmartTV-AGH | [Link](https://raw.githubusercontent.com/Perflyst/PiHoleBlocklist/master/SmartTV-AGH.txt) | Smart-TV Blocklist for AdGuard Home |
| Android tracking | [Link](https://perflyst.github.io/PiHoleBlocklist/android-tracking.txt) | Android tracking for AdGuard Home |
| Peter Lowe's List | [Link](https://pgl.yoyo.org/adservers/serverlist.php?hostformat=adblockplus&showintro=1&mimetype=plaintext) | Blocklist for use with Adblock Plus |

#### Services
| List Services | Link | AdGuard | Description |
| -- | :--: | :--: | -- |
| Youtube | [Link](https://raw.githubusercontent.com/blocklistproject/Lists/master/youtube.txt) | [Link](https://raw.githubusercontent.com/blocklistproject/Lists/master/adguard/youtube-ags.txt) | To Block youtube |
| Facebook | [Link](https://github.com/jmdugan/blocklists/blob/master/corporations/facebook/all) | - | To Block Facebook/Instagram/Whatsapp |
| Whatsapp open | [Link](https://raw.githubusercontent.com/jmdugan/blocklists/master/corporations/facebook/all-but-whatsapp) | - | To Block Facebook/Instagram but leave Whatsapp open |
| Google | [Link](https://raw.githubusercontent.com/jmdugan/blocklists/master/corporations/google/all) | - | To Block Google |
| Mozilla | [Link](https://raw.githubusercontent.com/JuanRodenas/Pi-hole_list/main/List/mozilla.txt) | [Link](https://raw.githubusercontent.com/JuanRodenas/Pi-hole_list/main/List/mozilla_adguard.txt) | To Block Mozilla tracking |
| Microsoft | [Link](https://raw.githubusercontent.com/jmdugan/blocklists/master/corporations/microsoft/all) | - | To Block Microsoft |
| VideoGamesAdiction | [Link](https://raw.githubusercontent.com/JuanRodenas/Pi-hole_list/main/List/VideoGamesAdiction.txt) | - | To Block VideoGames Adiction |


#### uBlock Origin uAssets
| List Services | Link | Link dev | Description |
| -- | :--: | :--: | -- |
| uBlock filters | [Link](https://raw.githubusercontent.com/uBlockOrigin/uAssets/master/filters/filters.txt) | [Link DEV](https://github.com/uBlockOrigin/uAssets/tree/master/filters) | uBlock filters |
| Badware risks | [Link](https://raw.githubusercontent.com/uBlockOrigin/uAssets/master/filters/badware.txt) | [Link DEV](https://github.com/uBlockOrigin/uAssets/tree/master/filters) | uBlock filters – Badware risks |
| Privacy | [Link](https://raw.githubusercontent.com/uBlockOrigin/uAssets/master/filters/privacy.txt) | [Link DEV](https://github.com/uBlockOrigin/uAssets/tree/master/filters) | uBlock filters – Privacy |
| Quick fixes list | [Link](https://raw.githubusercontent.com/uBlockOrigin/uAssets/master/filters/quick-fixes.txt) | [Link DEV](https://github.com/uBlockOrigin/uAssets/tree/master/filters) | Quick fixes list |
| Resource abuse | [Link](https://raw.githubusercontent.com/uBlockOrigin/uAssets/master/filters/resource-abuse.txt) | [Link DEV](https://github.com/uBlockOrigin/uAssets/tree/master/filters) | uBlock filters – Resource abuse |
| Unbreak | [Link](https://raw.githubusercontent.com/uBlockOrigin/uAssets/master/filters/unbreak.txt) | [Link DEV](https://github.com/uBlockOrigin/uAssets/tree/master/filters) | uBlock filters – Unbreak |
| i-dont-care-about-cookies | [Link](https://raw.githubusercontent.com/uBlockOrigin/uAssets/master/filters/unbreak.txt) | [Link DEV](https://www.i-dont-care-about-cookies.eu/) | i-dont-care-about-cookies | 


<sup>Se ha añadido una pestaña para AdGuard con listas adaptadas a su formato.</sup>


### Comprobar tu SelfHosted:

<details>
<summary>fivefilters:</summary>

<Original>&nbsp;Pagina para comprobar tu selfhosted de fivefilters</Original>

<p>  &nbsp;&nbsp;https://blockads.fivefilters.org/</p>
</details>
&nbsp;

<details>
<summary>d3ward:</summary>

<Original>&nbsp;Pagina para comprobar tu selfhosted de [d3ward](https://d3ward.github.io/toolz/)</Original>

<p>  &nbsp;&nbsp;https://d3ward.github.io/toolz/adblock.html</p>
</details>
&nbsp;

<details>
<summary>canyoublockit:</summary>

<Original>&nbsp;Pagina para comprobar tu selfhosted de canyoublockit</Original>

<p>  &nbsp;&nbsp;https://canyoublockit.com/</p>
</details>
&nbsp;

<details>
<summary>No more ads:</summary>

<Original>&nbsp;Pagina para comprobar tu selfhosted de No more ads</Original>

<p>  &nbsp;&nbsp;https://ads-blocker.com/es/pruebas/</p>
</details>
&nbsp;


<details>
<summary>AdBlock Tester:</summary>

<Original>&nbsp;Pagina para comprobar tu selfhosted de AdBlock Tester</Original>

<p>  &nbsp;&nbsp;https://adblock-tester.com/</p>
</details>
&nbsp;

### Comprobar DoH, DoT y DDNSSEC:

<details>
<summary>1.1.1.1 de Cloudflare:</summary>

<Original>&nbsp;Pagina para comprobar cifrado de 1.1.1.1 de Cloudflare</Original>

<p>  &nbsp;&nbsp;https://1.1.1.1/help</p>
</details>
&nbsp;

<details>
<summary>Tenta VPN Browser:</summary>

<Original>&nbsp;Pagina para comprobar cifrado de Tenta VPN Browser</Original>

<p>  &nbsp;&nbsp;https://tenta.com/test/</p>
</details>
&nbsp;

<details>
<summary>Cloudflare:</summary>

<Original>&nbsp;Pagina para comprobar cifrado de Cloudflare</Original>

<p>  &nbsp;&nbsp;https://www.cloudflare.com/es-es/ssl/encrypted-sni/</p>
</details>
&nbsp;

<details>
<summary>DNSSEC Resolver Test:</summary>

<Original>&nbsp;Pagina para comprobar cifrado DNSSEC por Matthäus Wander</Original>

<p>  &nbsp;&nbsp;http://dnssec.vs.uni-due.de/</p>
<p>  &nbsp;&nbsp;http://www.dnssec-or-not.com/</p>
<p>  &nbsp;&nbsp;http://en.conn.internet.nl/connection/</p>
</details>
&nbsp;

## COPIAS DE SEGURIDAD
Si queremos realizar una copias de seguridad de la configuración o recuperar el backup, Pulsa en la imagen para visitar el repositorio de copias de seguridad.
<p align="center">
    <a href="https://github.com/JuanRodenas/Backup/blob/main/README.md">
        <img src="https://github.com/JuanRodenas/Pi-hole_list/blob/main/cloud-backup.png" width="400" height="200">
    </a>
    <br>
    <strong>Pulsa en la imagen para visitar el repositorio de copias de seguridad.</strong>
</p>

### HELP ME
<p> &nbsp;If you want to contribute to improve the lists, open a <code>issue</code> here:  <A HREF="https://github.com/JuanRodenas/Pi-hole_list/issues"> ISSUE </A></p>
<sup>Si deseas contribuir a mejorar las listas, ábreme un problema aquí.</sup>

## Ready!

### Credits
Buy me a coffee so I can continue creating content. Invítame a un café para que pueda seguir creando contenidos.
#
<a href="https://www.paypal.com/donate/?hosted_button_id=HVJT2YDSHRZY2" target="_blank"><img src="https://cdn.buymeacoffee.com/buttons/v2/default-yellow.png" alt="Buy Me A Coffee" style="height: 60px !important;width: 217px !important;" ></a>
