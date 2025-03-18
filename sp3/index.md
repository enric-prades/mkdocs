<!DOCTYPE html>
<html lang="ca">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Sprint 3 - Sistemes Informàtics | Walid El Ourfi</title>
    <!-- Enllaç al CSS extern -->
    <link rel="stylesheet" href="../css">
</head>
<body>
    <h1>Sprint 3</h1>

    <h2>Dominis</h2>
    <p>Els dominis són estructures organitzatives emprades per administrar usuaris, recursos i polítiques dins d'una xarxa informàtica.</p>
    <p>Normalment, aquestes estructures es gestionen des d'un servidor central, al qual tots els dispositius de la xarxa estan connectats.</p>
    <p>Els dominis més coneguts són:</p>
    <ul>
        <li>Active Directory Domain Services (AD DS): Windows</li>
        <li>OpenLDAP: Linux i Windows</li>
        <li>Samba: Linux</li>
        <li>Azure Active Directory: Windows i Linux</li>
        <li>Kerberos: Linux i Windows</li>
    </ul>

    <h2>LDAP</h2>

    <h3>Instal·lació i configuració del domini al servidor</h3>

    <h4>Configuració de l'entorn</h4>
    <p>Primer configurarem el SO per a poder fer una instal·lació més agradable de LDAP.</p>
    <p>Configurarem una IP estàtica al servidor i comprovem que tinguem connexió a internet.</p>
    <!-- [Imatge 0: marcador per a la imatge] -->
    <!-- [Imatge 1: marcador per a la imatge] -->
    <p>Seguidament comprovem que al següent fitxer tinguem el nom de l'equip ben configurat. Si es vol canviar, és necessari reiniciar l'equip.</p>
    <pre><code>/etc/hostname</code></pre>
    <!-- [Imatge 2: marcador per a la imatge] -->
    <p>En el següent fitxer, afegirem una línia amb la IP de l'equip, hostname, el nom del domini que es crearà i una altra vegada el hostname.</p>
    <pre><code>/etc/hosts

[IP] [hostname].[nom del domini].[extensió del domini] [hostname]</code></pre>
    <!-- [Imatge 3: marcador per a la imatge] -->

    <h4>Instal·lació LDAP</h4>
    <p>Abans d'instal·lar, actualitzem els repositoris.</p>
    <pre><code>(sudo) apt update</code></pre>
    <p>I instal·larem els següents paquets.</p>
    <pre><code>(sudo) apt install slapd ldap-utils</code></pre>
    <!-- [Imatge 4: marcador per a la imatge] -->
    <p>En instal·lar els paquets, s'obrirà el configurador inicial de LDAP.</p>
    <p>El primer pas és escriure la contrasenya que tindrà l'administrador.</p>
    <!-- [Imatge 5: marcador per a la imatge] -->
    <p>I confirmarem la contrasenya.</p>
    <!-- [Imatge 6: marcador per a la imatge] -->
    <p>Després sortirem del configurador inicial.</p>
    <p>Podrem comprovar amb la següent comanda que s'ha creat el domini de LDAP, només que no està del tot ben configurat.</p>
    <pre><code>(sudo) slapcat</code></pre>
    <!-- [Imatge 7: marcador per a la imatge] -->

    <h4>Configuració LDAP</h4>
    <p>Per acabar de configurar el LDAP, haurem d'utilitzar la següent comanda:</p>
    <pre><code>(sudo) dpkg-reconfigure slapd</code></pre>
    <!-- [Imatge 8: marcador per a la imatge] -->
    <p><strong>Nota:</strong> Es pot repetir aquesta comanda per a reconfigurar el servidor tantes vegades com sigui necessari, encara que no és recomanable utilitzar-lo en grans estructures.</p>
    <p>No omitim la configuració de LDAP.</p>
    <!-- [Imatge 9: marcador per a la imatge] -->
    <p>Introduïm el nom i l'extensió del domini abans afegit en /etc/hosts.</p>
    <!-- [Imatge 10: marcador per a la imatge] -->
    <p>Introduïm el nom de l'organització, que és el nom i l'extensió del domini.</p>
    <!-- [Imatge 11: marcador per a la imatge] -->
    <p>Introduïm la contrasenya de l'administrador, hauria de ser la mateixa abans afegida.</p>
    <!-- [Imatge 12: marcador per a la imatge] -->
    <p>Confirmem la contrasenya.</p>
    <!-- [Imatge 13: marcador per a la imatge] -->
    <p>Acceptem.</p>
    <!-- [Imatge 14: marcador per a la imatge] -->
    <p>I acceptem esborrar la base de dades anterior. En aquest cas no hi ha res en ser la primera configuració.</p>
    <!-- [Imatge 15: marcador per a la imatge] -->
    <p>Ara, si utilitzem la següent comanda, podrem veure que tota la informació està correctament configurada.</p>
    <!-- [Imatge 16: marcador per a la imatge] -->

    <h3>Afegir estructures</h3>
    <p>La forma més comuna d'afegir estructura al nostre domini és mitjançant arxius de configuració .ldif.</p>
    <p>Podrem afegir l'estructura al nostre domini mit ...</p>
</body>
</html>