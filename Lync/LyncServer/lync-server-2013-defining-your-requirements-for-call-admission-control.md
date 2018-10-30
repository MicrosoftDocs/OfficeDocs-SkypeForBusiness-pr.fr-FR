---
title: "Lync Server 2013 : Déf. de la conf. req. pr le contrôle d’admission des appels"
TOCTitle: Définition de la configuration requise de l’organisation pour le contrôle d’admission des appels
ms:assetid: 5122171a-a5b0-4059-b033-846caec10d1e
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398334(v=OCS.15)
ms:contentKeyID: 49297200
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Définition de la configuration requise pour le contrôle d’admission des appels dans Lync Server 2013

 

_**Dernière rubrique modifiée :** 2015-03-09_

La planification du contrôle d’admission des appels (CAC) requiert des informations détaillées sur votre topologie de réseau d’entreprise. Pour vous aider à planifier vos stratégies de contrôle d’admission des appels, procédez comme suit.

1.  Identifiez les concentrateurs/dorsales principales (appelés *régions réseau* ) dans votre réseau d’entreprise.

2.  Identifiez les bureaux et emplacements (appelés *sites réseau* ) dans chaque région réseau.

3.  Déterminez l’itinéraire réseau entre chaque paire de régions réseau.

4.  Déterminez les limites de bande passante pour chaque liaison réseau étendu (WAN).
    
    > [!NOTE]  
    > Les limites de bande passante indiquent la quantité de bande passante sur une liaison réseau étendu allouée à Voix Entreprise et au trafic audio/vidéo. Quand une liaison réseau étendu est décrite comme « à bande passante restreinte », la liaison réseau étendu a une limite de bande passante inférieure au trafic maximal prévu sur la liaison.

5.  Identifiez les sous-réseaux IP affectés à chaque site réseau.

Pour expliquer ces concepts, nous prendrons l’exemple de topologie réseau présenté à la figure suivante.

**Exemple de topologie pour le contrôle d’admission des appels**

![Exemple de topologie réseau Litware Inc.](images/Gg398334.477f3b52-2973-4026-9bc0-b1c6bf9f4803(OCS.15).jpg "Exemple de topologie réseau Litware Inc.")

> [!NOTE]  
> Tous les sites réseau sont associés à une région réseau. Par exemple, Portland, Reno et Albuquerque sont inclus dans la région Amérique du Nord. Dans cette figure, seules les liaisons réseau étendu auxquelles des stratégies de service Contrôle d’admission des appels sont appliquées sont présentées, avec des limites de bande passante. Les sites réseau Chicago, New York et Détroit s’affichent dans l’ovale de la région Amérique du Nord, car ils ne sont soumis à aucune limite de bande passante et ne nécessitent donc aucune stratégie de service Contrôle d’admission des appels.

Les composants de cet exemple de topologie sont décrits dans les sections suivantes. Pour plus d’informations sur la façon dont cette topologie a été planifiée, dont les limites de bande passante, reportez-vous à [Exemple : collecte des données de la configuration requise pour le contrôle d’admission des appels dans Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md).

## Identifier les régions réseau

Une région réseau représente une dorsale principale ou un concentrateur réseau.

Une dorsale principale ou un concentrateur réseau fait partie de l’infrastructure réseau informatique qui interconnecte différents éléments du réseau, fournissant ainsi un chemin pour l’échange des informations entre différents réseaux locaux (LAN) ou sous-réseaux. Une dorsale principale peut lier divers réseaux d’un petit emplacement à une zone géographique étendue. La capacité de la dorsale principale est généralement plus grande que celle des réseaux qui s’y connectent.

Notre exemple de topologie comporte trois régions réseau : Amérique du Nord, EMEA et APAC. Une région réseau contient un ensemble de sites réseau (voir la définition des sites réseau dans la suite de cette rubrique). Collaborez avec votre équipe responsable des opérations réseau pour identifier vos régions réseau.

## Association d’un site central avec chaque région réseau

Le service Contrôle d’admission des appels nécessite qu’un site central Lync Server soit défini pour chaque région réseau. Le site central est sélectionné en fonction de la meilleure connectivité réseau et de la bande passante la plus élevée parmi les autres sites de la région réseau. L’exemple précédent de topologie réseau montre trois régions réseau, chacune comportant un site central qui gère les décisions du service Contrôle d’admission des appels. Dans l’exemple précédent, l’association appropriée est indiquée dans le tableau ci-après.

> [!NOTE]  
> Les sites centraux ne correspondent pas nécessairement aux sites réseau. Dans les exemples de cette documentation, certains sites centraux (Chicago, Londres et Pékin) portent les mêmes noms que les sites réseau. Cependant, si un site central et un site réseau partagent le même nom, le premier est un élément de la topologie Lync Server, alors que le second fait partie du réseau global où se trouve cette topologie Lync Server.

### Régions réseau, sites centraux et sites réseau

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Région réseau</th>
<th>Site central</th>
<th>Sites réseau</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Amérique du Nord</p></td>
<td><p>Chicago</p></td>
<td><p>Chicago</p>
<p>New York</p>
<p>Detroit</p>
<p>Portland</p>
<p>Reno</p>
<p>Albuquerque</p></td>
</tr>
<tr class="even">
<td><p>EMEA</p></td>
<td><p>Londres</p></td>
<td><p>Londres</p>
<p>Cologne</p></td>
</tr>
<tr class="odd">
<td><p>APAC</p></td>
<td><p>Pékin</p></td>
<td><p>Pékin</p>
<p>Manille</p></td>
</tr>
</tbody>
</table>


## Identifier les sites réseau

Un site réseau représente un lieu physique pour votre organisation, par exemple, des bureaux, un ensemble de bâtiments ou un campus. Tout lieu physique qui comporte un réseau local (LAN) et une connectivité de réseau étendu (WAN) vers d’autres sites est considéré comme un site réseau. Commencez par inventorier tous les bureaux de votre organisation. Dans notre exemple de topologie, la région réseau Amérique du Nord comporte les sites réseau suivants : New York, Chicago, Détroit, Portland, Reno et Albuquerque.

Vous devez associer chaque site réseau à une région réseau. Selon que le site réseau dispose d’une liaison réseau étendu restreinte, une stratégie de bande passante est associée au site réseau. Pour plus d’informations sur les stratégies de service Contrôle d’admission des appels et la bande passante que vous allouez en les utilisant, reportez-vous à « Définir des stratégies de bande passante » dans la suite de cette rubrique. Pour configurer le service Contrôle d’admission des appels, associez des sites réseau à des régions réseau, puis créez des stratégies d’allocation de bande passante qui doivent être appliquées aux connexions à bande passante restreinte entre un site ou une région spécifique, mais aussi aux connexions réseau étendu entre des sites et des régions.

## Identifier des liaisons réseau

Les liaisons réseau représentent les connexions au réseau étendu physique qui relient différentes régions et différents sites. Dans notre exemple de topologie, il y a deux liaisons réseau régionales, cinq liaisons réseau entre des régions et des sites, et une liaison réseau entre deux sites.

Les deux liaisons régionales sont entre Amérique du Nord et EMEA, représentés par NA-EMEA-LINK, et entre APAC et EMEA, représentés par EMEA-APAC-LINK.

Les liaisons de sites sont indiquées par des traits connectant Portland, Reno et Albuquerque à la région Amérique du Nord, Manille à la région APAC et Cologne à la région EMEA. Le trait entre Reno et Albuquerque indique une liaison réseau directe entre ces deux sites.

## Définir des stratégies de bande passante

Collaborez avec votre équipe responsable des opérations réseau pour déterminer la quantité de bande passante de réseau étendu mise à disposition du trafic audio et vidéo en temps réel sur les liaisons réseau étendu de votre organisation. Les stratégies de bande passante sont généralement appliquées aux liaisons réseau étendu si l’utilisation de la bande passante est restreinte ; c’est-à-dire, si on pense qu’elle sera supérieure à la bande passante pouvant être allouée aux modes audio et vidéo.

Les *stratégies de bande passante* du service Contrôle d’admission des appels définissent la bande passante maximale qui peut être réservée aux modes audio et vidéo en temps réel. Comme le service Contrôle d’admission des appels ne limite pas la bande passante d’un autre trafic de données, il ne peut pas empêcher les autres trafics de données (par exemple, un transfert de fichiers volumineux ou la diffusion en continu de morceaux de musique) d’utiliser toute la bande passante réseau.

Les stratégies de bande passante CAC peuvent définir un ou plusieurs des éléments suivants :

  - Bande passante totale maximale allouée à l’audio.

  - Bande passante totale maximale allouée à la vidéo.

  - Bande passante maximale allouée à un appel audio unique (session).

  - Bande passante maximale allouée à un appel vidéo unique (session).

> [!NOTE]  
> Toutes les valeurs de bande passante CAC représentent les limites de bande passante <em>unidirectionnelle</em> maximales.

> [!NOTE]  
> Les fonctionnalités de stratégie de voix Lync Server 2013 permettent de remplacer les contrôles de stratégie de bande passante pour les appels entrants destinés à l’utilisateur (et non pour les appels sortants passés par l’utilisateur). Une fois la session établie, la consommation de bande passante est calculée avec précision. Ce paramètre doit être utilisé avec modération. Pour plus d’informations, reportez-vous à <a href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">Créer une stratégie et voix et configurer les enregistrements d’utilisation PSTN dans Lync Server 2013</a> ou <a href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">Modifier une stratégie de voix et configurer des enregistrements d’utilisation PSTN dans Lync Server 2013</a> dans la documentation de déploiement.

Pour optimiser l’utilisation de la bande passante par session, tenez compte du type des codecs audio et vidéo qui seront utilisés. Plus particulièrement, allouez suffisamment de bande passante pour un codec que vous pensez utiliser fréquemment. À l’inverse, si vous souhaitez empêcher le média d’utiliser un codec nécessitant davantage de bande passante, définissez une bande passante maximale par session qui soit suffisamment basse pour décourager ce type d’utilisation. Pour l’audio, tous les codecs ne sont pas disponibles pour chaque scénario. Par exemple :

  - Les appels audio P2P entre les points de terminaison Lync utiliseront RTAudio (8 kHz) ou RTAudio (16 kHz) quand vous prendrez en compte la bande passante et la définition des priorités des codecs.

  - Les téléconférences entre les points de terminaison Lync et le service de conférence A/V utiliseront G.722 ou Siren.

  - Les appels passés au réseau téléphonique commuté (RTC), à destination ou en provenance des points de terminaison Lync, utiliseront G.711 ou RTAudio (8 kHz).

Utilisez le tableau suivant pour optimiser les paramètres de bande passante par session maximale.

### Utilisation de la bande passante par codecs

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Codec</th>
<th>Besoin en bande passante sans correction des erreurs de transfert (FEC)</th>
<th>Besoin en bande passante avec correction des erreurs de transfert (FEC)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RTAudio (8kHz)</p></td>
<td><p>49,8 Kbits/s</p></td>
<td><p>61,6 Kbits/s</p></td>
</tr>
<tr class="even">
<td><p>RTAudio (16 kHz)</p></td>
<td><p>67 Kbits/s</p></td>
<td><p>96 Kbits/s</p></td>
</tr>
<tr class="odd">
<td><p>Siren</p></td>
<td><p>57,6 Kbits/s</p></td>
<td><p>73,6 Kbits/s</p></td>
</tr>
<tr class="even">
<td><p>G0,711</p></td>
<td><p>102 Kbits/s</p></td>
<td><p>166 Kbits/s</p></td>
</tr>
<tr class="odd">
<td><p>G.722</p></td>
<td><p>105,6 Kbits/s</p></td>
<td><p>169,6 Kbits/s</p></td>
</tr>
<tr class="even">
<td><p>RTVideo (CIF 15 i/s)</p></td>
<td><p>260 Kbits/s</p></td>
<td><p>Non applicable</p></td>
</tr>
<tr class="odd">
<td><p>RTVideo (VGA 30 i/s)</p></td>
<td><p>610 Kbits/s</p></td>
<td><p>Non applicable</p></td>
</tr>
</tbody>
</table>


> [!NOTE]  
> Les besoins en bande passante prennent en compte le traitement des éléments suivants : Ethernet II, IP, UDP (User Datagram Protocol), RTP (Real-Time Transport Protocol) et SRTP (Secure Real-Time Transport Protocol). Ils incluent également 10 Kbits/s pour le traitement RTCP.

Les codecs G.722.1 et Siren sont similaires, mais offrent différentes vitesses de transmission.

G.722, codec par défaut de la conférence Lync Server, est complètement différent des codecs G.722.1 et Siren.

Le codec Siren est utilisé dans Lync Server, dans les situations suivantes :

  - La stratégie de bande passante est définie sur une valeur trop basse pour permettre l’utilisation de G.722.

  - Un client Communications Server 2007 ou Communications Server 2007 R2 se connecte à un service de conférence Lync Server (car ces clients ne prennent pas en charge le codec G.722).

### Utilisation de la bande passante par scénario

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Scénario</th>
<th>Besoins en bande passante optimisés pour la quantité (Kbits/s)</th>
<th>Besoins en bande passante pour le mode équilibré (Kbits/s)</th>
<th>Besoins en bande passante optimisés pour la qualité (Kbits/s)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Appels audio P2P</p></td>
<td><p>45 Kbits/s</p></td>
<td><p>62 Kbits/s</p></td>
<td><p>91 Kbits/s</p></td>
</tr>
<tr class="even">
<td><p>Téléconférences</p></td>
<td><p>53 Kbits/s</p></td>
<td><p>101 Kbits/s</p></td>
<td><p>165 Kbits/s</p></td>
</tr>
<tr class="odd">
<td><p>Appels RTC (entre Lync 2013 et la passerelle RTC, avec déviation du trafic multimédia)</p></td>
<td><p>97 Kbits/s</p></td>
<td><p>97 Kbits/s</p></td>
<td><p>161 Kbits/s</p></td>
</tr>
<tr class="even">
<td><p>Appels RTC (entre Lync 2013 et le serveur de médiation, sans déviation du trafic multimédia)</p></td>
<td><p>45 Kbits/s</p></td>
<td><p>97 Kbits/s</p></td>
<td><p>161 Kbits/s</p></td>
</tr>
<tr class="odd">
<td><p>Appels RTC (entre le serveur de médiation et la passerelle RTC, sans déviation du trafic multimédia)</p></td>
<td><p>97 Kbits/s</p></td>
<td><p>97 Kbits/s</p></td>
<td><p>161 Kbits/s</p></td>
</tr>
<tr class="even">
<td><p>Appels Lync - Polycom</p></td>
<td><p>101 Kbits/s</p></td>
<td><p>101 Kbits/s</p></td>
<td><p>101 Kbits/s</p></td>
</tr>
</tbody>
</table>


## Identifier les sous-réseaux IP

Pour chaque site réseau, vous devrez collaborer avec votre administrateur réseau pour déterminer les sous-réseaux IP affectés à chaque site réseau. Si votre administrateur réseau a déjà organisé les sous-réseaux IP en régions réseau et sites réseau, votre travail est considérablement simplifié.

Dans notre exemple, le site New York de la région Amérique du Nord se voit affecter les sous-réseaux IP suivants : 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24. Supposons que Bob, qui travaille généralement à Détroit, se rende dans les bureaux de New York pour suivre une formation. Quand il allume son ordinateur et se connecte au réseau, son ordinateur obtient une adresse IP dans l’une des quatre plages réservées à New York (par exemple, 172.29.80.103).

> [!WARNING]  
> Les sous-réseaux IP spécifiés pendant la configuration du réseau sur le serveur doivent correspondre au format fourni par les ordinateurs clients afin d’être correctement utilisés pour la déviation du trafic multimédia. Un client Lync prend son adresse IP locale et masque l’adresse IP avec le masque de sous-réseau associé. Lors de la détermination de l’ID de contournement associé à chaque client, le serveur d’inscriptions comparera la liste des sous-réseaux IP associés à chaque site réseau avec le sous-réseau fourni par le client pour obtenir une correspondance exacte. Pour cette raison, il est important que les sous-réseaux entrés lors de la configuration du réseau sur le serveur soient des sous-réseaux réels et non des sous-réseaux virtuels. (Si vous déployez le contrôle d’admission des appels, mais pas la déviation du trafic multimédia, le contrôle d’admission des appels fonctionnera correctement même si vous configurez des sous-réseaux virtuels.)<br />
Par exemple, si un client se connecte sur un ordinateur ayant l’adresse IP 172.29.81.57 et le masque de sous-réseau IP 255.255.255.0, Lync 2013 demandera l’ID de contournement associé au sous-réseau 172.29.81.0. Si le sous-réseau est défini comme 172.29.0.0/16, même si le client appartient au sous-réseau virtuel, le serveur d’inscriptions ne considérera pas cela comme une correspondance, car le serveur d’inscriptions recherche spécifiquement le sous-réseau 172.29.81.0. Ainsi, il est important que l’administrateur entre les sous-réseaux exacts fournis par les clients Lync (provisionnés avec des sous-réseaux lors de la configuration réseau soit de manière statique, soit par DHCP.)
