---
title: 'Lync Server 2013 : Rapport de périphérique'
TOCTitle: Rapport de périphérique
ms:assetid: f42e4d60-699b-4870-8bb5-13b51bb6eb2b
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg615049(v=OCS.15)
ms:contentKeyID: 49299359
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Rapport de périphérique dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

Le Rapport de périphérique devrait plutôt s’appeler le Rapport de microphone et de haut-parleurs : en effet, le Rapport de périphérique récupère toutes les mesures de l’appel (comme le pourcentage d’appels médiocres, les échos et la durée du basculement vocal) regroupées par les microphones et les haut-parleurs utilisés pendant l’appel. Si les téléphones IP (connus sous le nom de « périphériques ») vous intéressent, utilisez plutôt le [Rapport d’inventaire de téléphonie IP dans Lync Server 2013](lync-server-2013-ip-phone-inventory-report.md).

Le rapport de périphérique est très utile pour les administrateurs souhaitant déterminer si un type d’appareil spécifique rencontre un plus grand nombre d’appels médiocres que d’autres appareils. Ce rapport pourrait, à son tour, influencer les décisions que vous devez prendre au moment de l’achat de nouveaux périphériques ou du remplacement des périphériques existants.

Par défaut, les informations affichées dans le rapport de périphérique sont également basées sur le microphone (le périphérique de capture) et les haut-parleurs/casques (le périphérique de sortie) utilisés pour l’appel. Par exemple, supposons que vous ayez différents utilisateurs utilisant les périphériques de capture et de sortie suivants :

  - Périphérique de capture : microphone (SoundMAX Integrated Digital HD Audio)

  - Périphérique de rendu : casque pour téléphone (Microsoft LifeChat LX-3000)

Si ces utilisateurs passent 254 appels, une entrée semblable à celle-ci sera affichée dans le rapport :


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Périphérique de capture</th>
<th>Périphérique de rendu</th>
<th>Volume d’appels</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Microphone (SoundMAX Integrated Digital HD Audio)</p></td>
<td><p>Casque pour téléphone (Microsoft LifeChat LX-3000)</p></td>
<td><p>254</p></td>
</tr>
</tbody>
</table>


À présent, supposons que vous ayez un nombre d’utilisateurs utilisant le même périphérique de capture, mais avec un autre périphérique de rendu. Dans ce cas, une deuxième entrée sera affichée dans le rapport, pour cette combinaison de périphériques de capture et de rendu :


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Périphérique de capture</th>
<th>Périphérique de rendu</th>
<th>Volume d’appels</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Microphone (SoundMAX Integrated Digital HD Audio)</p></td>
<td><p>Casque pour téléphone (Microsoft LifeChat LX-3000)</p></td>
<td><p>254</p></td>
</tr>
<tr class="even">
<td><p>Microphone (SoundMAX Integrated Digital HD Audio)</p></td>
<td><p>Haut-parleurs (SoundMAX Integrated Digital HD Audio)</p></td>
<td><p>319</p></td>
</tr>
</tbody>
</table>


Si vous préférez consulter les totaux combinés d’un périphérique donné (par exemple, pour le périphérique de capture SoundMAX, indépendamment du périphérique de rendu utilisé), sélectionnez l’option adéquate dans la liste déroulante Typé de périphérique (que ce soit pour le périphérique de capture ou celui de rendu). Si vous sélectionnez le périphérique de capture dans cet exemple, l’entrée sera semblable à celle-ci :


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Périphérique de capture</th>
<th>Volume d’appels</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Microphone (SoundMAX Integrated Digital HD Audio)</p></td>
<td><p>573</p></td>
</tr>
</tbody>
</table>


## Accès au rapport de périphérique

Normalement, vous pouvez accéder au rapport de périphérique à partir de la page d’accueil Rapports de surveillance. Cependant, si vous affichez le [Rapport détaillé des appels dans Lync Server 2013](lync-server-2013-call-detail-report.md) vous pouvez afficher les détails du rapport de périphérique pour un périphérique spécifique en cliquant sur l’une des mesures suivantes :

  - Périphérique de capture

  - Périphérique de rendu

Depuis le rapport de périphérique, vous pouvez accéder au [Rapport de la liste d’appels dans Lync Server 2013](lync-server-2013-call-list-report.md) en cliquant sur l’une des mesures suivantes :

  - Volume d’appels

  - Pourcentage d’appels médiocres

## Utilisation optimale du rapport de périphériques

Pour ce qui est des noms de périphériques, le rapport de périphérique est extrêmement détaillé : par exemple, supposons que vous ayez les périphériques de capture suivants :

  - Microphone Aastra 3002 (2- Aastra 3002)

  - Microphone Aastra 3002 (3- Aastra 3002)

  - Microphone Aastra 3002 (Aastra 3002)

  - Aastra 6725ip

  - Microphone Aastra 6725ip (10- Aastra 6725ip)

  - Microphone Aastra 6725ip (10- Aastra 6725ip)-V0

  - Microphone Aastra 6725ip (2- Aastra 6725ip)

  - Microphone Aastra 6725ip (3- Aastra 6725ip)

  - Microphone Aastra 6725ip (4- Aastra 6725ip)

  - Microphone Aastra 6725ip (5- Aastra 6725ip)

  - Microphone Aastra 6725ip (6- Aastra 6725ip)

  - Microphone Aastra 6725ip (7- Aastra 6725ip)

  - Microphone Aastra 6725ip (9- Aastra 6725ip)

  - Microphone Aastra 6725ip (9- Aastra 6725ip)-V0

  - Microphone Aastra 6725ip (Aastra 6725ip)

  - Microphone Aastra 6725ip (Aastra 6725ip)-V0

  - Microphone Aastra 6725ip (périphérique audio USB)

  - Microphone Aastra 6725ip (périphérique audio USB)-V0

> [!NOTE]  
> N’oubliez pas que les noms de périphériques de capture peuvent différer si vous exécutez des versions localisées de Lync Server 2013. Un périphérique nommé Microphone Aastra 6725ip (Aastra 6725ip)-V0 en FR français peut être nommé différemment en français ou en espagnol.

Il est possible que vous souhaitiez ce niveau de détail à plusieurs reprises ; cependant, la plupart du temps, vous serez probablement uniquement intéressé par le nombre d’appels utilisant n’importe quel microphone Aastra, indépendamment du numéro du modèle. Pour obtenir ce genre d’informations, exportez les données du Rapport de périphérique dans Microsoft Excel et enregistrez ces données sous la forme d’une chaîne de valeurs séparées par des virgules (par exemple, C:\\Data\\Rapport\_périphériques.csv). Vous pouvez ensuite utiliser un ensemble de commandes similaires à celles-ci pour importer le fichier .CSV dans Windows PowerShell et renvoyer le nombre d’appels effectués en utilisant un périphérique de capture Aastra :

    $devices = Import-Csv "C:\Data\Device_Report.csv
    $sum = $devices | Where-Object {$_."Capture device" -match "Aastra"}
    $sum | foreach-object {[Int]$x = [Int]$x + [Int]$_."call volume"}
    $x

Cela va renvoyer une valeur unique représentant le nombre d’appels effectués en utilisant un périphérique de capture Aastra. Par exemple :

    384

## Filtres

Les filtres vous offrent la possibilité de renvoyer un ensemble de données mieux ciblées ou de visualiser les données renvoyées de différentes manières. Par exemple, le rapport de périphérique vous permet de filtrer des éléments comme le type d’appel, c’est-à-dire s’il s’agissait d’un appel client, d’une téléconférence ou d’un appel du réseau téléphonique commuté (RTC). Vous pouvez également choisir le mode de groupement des données. Dans ce cas, les périphériques sont groupés par heure, jour, semaine ou mois.

Le tableau qui suit dresse la liste des filtres que vous pouvez utiliser avec le rapport de périphérique.

### Filtres du rapport de périphérique

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Nom</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>De</strong></p></td>
<td><p>Date/heure de début de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de début comme suit :</p>
<p>07/07/2012 13:00</p>
<p>Si vous ne précisez aucune heure de début, le rapport commence automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :</p>
<p>07/07/2012</p>
<p>Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :</p>
<p>7/3/2012</p>
<p>Les semaines s’étalent toujours du dimanche au samedi.</p></td>
</tr>
<tr class="even">
<td><p><strong>À</strong></p></td>
<td><p>Date/heure de fin de la période. Pour afficher les données par heures, entrez à la fois la date et l’heure de fin comme suit :</p>
<p>07/07/2012 13:00</p>
<p>Si vous ne précisez aucune heure de fin, le rapport se termine automatiquement à midi (12:00 AM) à la date du jour défini. Pour afficher les données par jour, entrez simplement la date :</p>
<p>07/07/2012</p>
<p>Pour afficher les données par semaine ou mois, entrez une date tombant un jour quelconque de la semaine ou du mois que vous souhaitez visualiser (nul besoin d’entrer le premier jour de la semaine ou du mois) :</p>
<p>7/3/2012</p>
<p>Les semaines s’étalent toujours du dimanche au samedi.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Cause du basculement vocal</strong></p></td>
<td><p>Raison pour laquelle un appel a dû être émis en mode semi-duplex afin d’empêcher l’écho. En mode semi-duplex, la communication peut voyager dans un seul sens à la fois, de la même façon que les utilisateurs attendent leur tour pour communiquer à l’aide d’un talkie-walkie. Sélectionnez l’une des options suivantes :</p>
<dl>
<dt><span></span></dt>
<dd><p>[Tous]</p>
</dd>
<dt><span></span></dt>
<dd><p>Aucune</p>
</dd>
<dt><span></span></dt>
<dd><p>Horodateur incorrect</p>
</dd>
<dt><span></span></dt>
<dd><p>Écho</p>
</dd>
<dt><span></span></dt>
<dd><p>DNLP (Dynamic Nonlinear Processor, processeur non linéaire dynamique)</p>
</dd>
<dt><span></span></dt>
<dd><p>Faible complexité</p>
</dd>
<dt><span></span></dt>
<dd><p>État de périphérique incorrect</p>
</dd>
<dt><span></span></dt>
<dd><p>Écho post-AEC (Acoustic Echo Cancellation, annulation de l’écho acoustique)</p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><strong>Cause de l’écho</strong></p></td>
<td><p>Raison pour laquelle un écho au-dessus du niveau acceptable a été détecté dans un appel. (Dans le domaine des télécommunications, un écho est la réflexion d’un son, il s’agit du même phénomène que vous entendez lorsque vous hélez en direction du fond d’un puits.) Sélectionnez l’une des options suivantes :</p>
<dl>
<dt><span></span></dt>
<dd><p>[Tous]</p>
</dd>
<dt><span></span></dt>
<dd><p>Aucune</p>
</dd>
<dt><span></span></dt>
<dd><p>Horodateur incorrect</p>
</dd>
<dt><span></span></dt>
<dd><p>Écho post-AEC (Acoustic Echo Cancellation, annulation de l’écho acoustique)</p>
</dd>
<dt><span></span></dt>
<dd><p>ANLP (Adaptive Nonlinear Processor, processeur non linéaire adaptatif)</p>
</dd>
<dt><span></span></dt>
<dd><p>DNLP (Dynamic Nonlinear Processor, processeur non linéaire dynamique)</p>
</dd>
<dt><span></span></dt>
<dd><p>Écrêtage du microphone</p>
</dd>
</dl></td>
</tr>
<tr class="odd">
<td><p><strong>Type d’appel</strong></p></td>
<td><p>Indique le type d’appel émis. Sélectionnez l’une des options suivantes :</p>
<dl>
<dt><span></span></dt>
<dd><p>[Tous]</p>
</dd>
<dt><span></span></dt>
<dd><p>Appel client</p>
</dd>
<dt><span></span></dt>
<dd><p>Appel RTC</p>
</dd>
<dt><span></span></dt>
<dd><p>Téléconférence</p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><strong>Type d’accès</strong></p></td>
<td><p>Indique si le client était connecté au réseau interne ou au réseau externe au moment de passer l’appel. Sélectionnez l’une des options suivantes :</p>
<dl>
<dt><span></span></dt>
<dd><p>[Tous]</p>
</dd>
<dt><span></span></dt>
<dd><p>Interne</p>
</dd>
<dt><span></span></dt>
<dd><p>Externe</p>
</dd>
</dl></td>
</tr>
<tr class="odd">
<td><p><strong>Type de réseau</strong></p></td>
<td><p>Indique le type de réseau auquel le client était connecté au moment où l’appel a été émis. Sélectionnez l’une des options suivantes :</p>
<dl>
<dt><span></span></dt>
<dd><p>[Tous]</p>
</dd>
<dt><span></span></dt>
<dd><p>Câblé</p>
</dd>
<dt><span></span></dt>
<dd><p>Sans fil</p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><strong>VPN</strong></p></td>
<td><p>Indique si un client externe utilisait une connexion de réseau privé virtuel (VPN) au moment d’effectuer l’appel. Sélectionnez l’une des options suivantes :</p>
<dl>
<dt><span></span></dt>
<dd><p>[Tous]</p>
</dd>
<dt><span></span></dt>
<dd><p>VPN</p>
</dd>
<dt><span></span></dt>
<dd><p>Non-VPN</p>
</dd>
</dl></td>
</tr>
<tr class="odd">
<td><p><strong>Type de périphérique</strong></p></td>
<td><p>Indique le type du périphérique. Sélectionnez l’une des options suivantes :</p>
<dl>
<dt><span></span></dt>
<dd><p>Périphérique de capture</p>
</dd>
<dt><span></span></dt>
<dd><p>Périphérique de rendu</p>
</dd>
<dt><span></span></dt>
<dd><p>Périphérique de capture/périphérique de rendu</p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><strong>Nom du périphérique</strong></p></td>
<td><p>Nom du périphérique de capture ou de rendu. Vous pouvez entrez le nom complet du périphérique ou seulement une partie. Par exemple, pour trouver le périphérique Microphone (Microsoft LifeCam VX-1000), vous pouvez entrer la totalité du nom du périphérique comme suit :</p>
<p>Microphone (Microsoft LifeCam VX-1000)</p>
<p>Ou, vous pouvez entrer uniquement une partie du nom. Par exemple :</p>
<p>LifeCam</p>
<p>Notez que le filtre précédant permet de renvoyer tous les périphériques qui contiennent la chaîne « LifeCam » dans leur nom.</p></td>
</tr>
</tbody>
</table>


## Mesures

Le tableau qui suit répertorie les informations fournies dans le rapport de périphérique.

### Mesures du rapport de périphérique

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Nom</th>
<th>Est-il possible d’effectuer un tri sur cet élément ?</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Périphérique de capture</strong></p></td>
<td><p>Oui</p></td>
<td><p>Périphérique (par exemple, un microphone ou une webcam) utilisé pour transmettre de l’audio.</p></td>
</tr>
<tr class="even">
<td><p><strong>Périphérique de rendu</strong></p></td>
<td><p>Oui</p></td>
<td><p>Périphérique (par exemple, un casque ou des haut-parleurs) utilisé pour recevoir de l’audio.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Volume d’appels</strong></p></td>
<td><p>Oui</p></td>
<td><p>Nombre total d’appels émis.</p></td>
</tr>
<tr class="even">
<td><p><strong>Pourcentage d’appels médiocres</strong></p></td>
<td><p>Oui</p></td>
<td><p>Pourcentage d’appels jugés et classés comme étant médiocres. Un appel médiocre désigne un appel dont l’une des valeurs mesurées est supérieure à la valeur autorisée (par exemple, un appel soumis à un phénomène de gigue excessive).</p></td>
</tr>
<tr class="odd">
<td><p><strong>Utilisateurs uniques</strong></p></td>
<td><p>Oui</p></td>
<td><p>Utilisateurs uniques qui ont utilisé le périphérique. Si un utilisateur a utilisé le périphérique 13 fois, il compte comme un seul utilisateur, à l’instar d’un utilisateur qui l’a utilisé une seule fois.</p></td>
</tr>
<tr class="even">
<td><p><strong>Ratio de la durée du basculement vocal</strong></p></td>
<td><p>Oui</p></td>
<td><p>Pourcentage de l’appel qui a dû être effectué en mode semi-duplex afin d’empêcher l’écho. En mode semi-duplex, la communication peut voyager dans un seul sens à la fois, de la même façon que les utilisateurs attendent leur tour pour communiquer à l’aide d’un talkie-walkie.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Ratio du microphone ne fonctionnant pas</strong></p></td>
<td><p>Oui</p></td>
<td><p>Pourcentage de l’appel pendant lequel le périphérique de capture ne fonctionnait pas à un niveau acceptable. Une valeur élevée suggère que les problèmes de qualité de l’appel étaient principalement dus au fonctionnement incorrect du périphérique de capture.</p></td>
</tr>
<tr class="even">
<td><p><strong>Ratio du haut-parleur ne fonctionnant pas</strong></p></td>
<td><p>Oui</p></td>
<td><p>Pourcentage de l’appel pendant lequel le périphérique de rendu ne fonctionnait pas à un niveau acceptable. Une valeur élevée suggère que les problèmes de qualité de l’appel étaient principalement dus au fonctionnement incorrect du périphérique de rendu.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Appels avec basculement vocal (%)</strong></p></td>
<td><p>Oui</p></td>
<td><p>Pourcentage du nombre total d’appels qui ont dû être émis en mode semi-duplex. En mode semi-duplex, la communication peut voyager dans un seul sens à la fois, de la même façon que les utilisateurs attendent leur tour pour communiquer à l’aide d’un talkie-walkie.</p></td>
</tr>
<tr class="even">
<td><p><strong>Écho en entrée du microphone (%)</strong></p></td>
<td><p>Oui</p></td>
<td><p>Temps en pourcentage lors de la détection d’un écho dans le flux de capture du microphone. En règle générale, des valeurs faibles s’affichent pour les casques ou les combinés et des valeurs élevées pour les téléphones mains libres ou les haut-parleurs autonomes. Pour les appareils qui prennent en charge la suppression d’écho intégrée, des valeurs élevées indiquent une fuite d’écho. Pour les autres appareils, cette mesure ne doit pas être utilisée pour évaluer la qualité de l’appareil.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Source-réverbération (%)</strong></p></td>
<td><p>Oui</p></td>
<td><p>Pourcentage d’écho transmis à d’autres utilisateurs.</p></td>
</tr>
<tr class="even">
<td><p><strong>Appels avec écho (%)</strong></p></td>
<td><p>Oui</p></td>
<td><p>Pourcentage du nombre total d’appels dont l’écho a dépassé le niveau acceptable.</p>
<p></p></td>
</tr>
</tbody>
</table>

