---
title: "Conf. requise pour l’équilibreur de charge matérielle pour Lync Server 2013"
TOCTitle: Configuration requise pour l’équilibreur de charge matérielle
ms:assetid: 32891268-2059-43d0-adf4-af4ff1e9ce66
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ656815(v=OCS.15)
ms:contentKeyID: 49891297
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration requise pour l’équilibreur de charge matérielle pour Lync Server 2013

 

_**Dernière rubrique modifiée :** 2016-12-08_

La topologie Edge consolidée et mise à l’échelle de Lync Server 2013 est optimisée pour l’équilibrage de la charge DNS des nouveaux déploiements fédérés principalement avec d’autres organisations qui utilisent Lync Server. Si, dans l’un des scénarios suivants, la haute disponibilité est requise, vous devez utiliser un équilibreur de la charge matérielle sur les pools de serveur Edge pour prendre en charge ce qui suit :

  - fédération avec des entreprises qui utilisent Office Communications Server 2007 R2 ou Office Communications Server 2007 ;

  - messagerie unifiée Exchange pour les utilisateurs distants qui utilisent la messagerie unifiée Exchange avant Exchange 2010 avec SP1 ;

  - connectivité avec les utilisateurs de messagerie instantanée publique.

> [!IMPORTANT]  
> L’utilisation de l’équilibrage de la charge DNS sur une interface et de l’équilibrage de la charge matérielle sur l’autre n’est pas prise en charge. Sur les deux interfaces, vous devez utiliser soit l’équilibrage de la charge matérielle, soit l’équilibrage de la charge DNS.

> [!NOTE]  
> Si vous utilisez un équilibreur de la charge matérielle, celui qui est déployé pour les connexions au réseau interne doit être configuré pour équilibrer uniquement la charge liée au trafic en direction de serveurs exécutant le service d’accès Edge et le service Edge A/V. Il ne peut pas équilibrer la charge du trafic vers le service Edge de conférence web ou le service de proxy XMPP interne.

> [!NOTE]  
> Le mode NAT DSR (Direct Server Return) n’est pas pris en charge avec Lync Server 2013.

Pour déterminer si l’équilibreur de la charge matérielle prend en charge les fonctionnalités nécessaires au Lync Server 2013, reportez-vous à « Partenaires des programmes d’équilibrage de charge de Lync Server 2010 » à l’adresse [http://go.microsoft.com/fwlink/p/?linkId=202452](http://go.microsoft.com/fwlink/p/?linkid=202452).

## Configuration requise pour l’équilibreur de la charge matérielle des serveurs Edge exécutant le service Edge A/V

La configuration requise pour l’équilibreur de la charge matérielle des serveurs Edge exécutant le service Edge A/V est la suivante :

  - Désactivez le nagling TCP pour les ports 443 interne et externe. Le nagling est le processus qui consiste à combiner plusieurs petits paquets en un seul paquet plus volumineux afin de rendre la transmission plus efficace.

  - Désactivez le nagling TCP pour la plage de ports externes 50 000 – 59 999.

  - N’utilisez pas NAT sur le pare-feu interne ou externe.

  - L’interface interne Edge doit se trouver sur un autre réseau que l’interface externe du serveur Edge et le routage entre elles doit être désactivé.

  - L’interface externe du serveur Edge exécutant le service Edge A/V doit utiliser des adresses IP routables publiquement, mais aucune NAT ou conversion de port sur n’importe quelle adresse IP externe du service Edge.

## Exigences relatives au programme d’équilibrage de la charge matérielle

Les conditions requises en termes d’affinité basée sur les cookies ont été considérablement simplifiées dans Lync Server 2013 pour les services web. Si vous déployez Lync Server 2013 et que vous ne gardez pas les serveurs frontaux ou les pools de serveurs frontauxLync Server 2010, vous n’avez pas besoin de la persistance basée sur les cookies. Cependant, si vous conservez temporairement ou définitivement des serveurs frontaux ou pools de serveurs frontauxLync Server 2010, vous devrez toujours utiliser la persistance basée sur les cookies, car elle est déployée et configurée pour Lync Server 2010.

> [!NOTE]  
> <strong>Si vous décidez d’utiliser l’affinité basée sur les cookies même si votre déploiement n’en a pas besoin</strong>, aucun impact négatif n’en résultera.

Pour les déploiements qui **n’utiliseront pas** l’affinité basée sur les cookies :

  - Dans la règle de publication du proxy inverse pour le port 4443, définissez **Forward host header** sur la valeur True. Cela garantit que l’URL d’origine sera transférée.

Pour les déploiements qui **utiliseront** l’affinité basée sur les cookies :

  - Dans la règle de publication du proxy inverse pour le port 4443, définissez **Forward host header** sur la valeur True. Cela garantit que l’URL d’origine sera transférée.

  - Le cookie de l’équilibreur de la charge matérielle NE DOIT PAS être marqué httpOnly

  - Le cookie de l’équilibreur de la charge matérielle NE DOIT PAS inclure d’heure d’expiration

  - Le cookie de l’équilibreur de la charge matérielle DOIT être nommé **MS-WSMAN** (Il s’agit de la valeur attendue par les services web et elle ne peut pas être modifiée)

  - Le cookie de l’équilibreur de la charge matérielle DOIT être défini dans chaque réponse HTTP pour laquelle la requête HTTP entrante ne possédait pas de cookie, qu’une réponse HTTP précédente ait déjà obtenu ou non un cookie sur cette même connexion TCP. Si l’équilibreur de la charge optimise l’insertion de cookies afin qu’elle se produise une seule fois par connexion TCP, cette optimisation NE DOIT PAS être utilisée

> [!NOTE]  
> Les configurations habituelles de l’équilibreur de la charge matérielle utilisent l’affinité des adresses sources et une durée de vie de session TCP de 20 minutes, ce qui convient aux clients Lync Server et Lync 2013, car l’état de la session est maintenu pendant l’utilisation du client et/ou l’interaction des applications.

Si vous déployez des appareils mobiles, votre équilibreur de la charge matérielle doit être capable d’équilibrer la charge d’une requête individuelle au sein d’une session TCP (en effet, vous devez être en mesure d’équilibrer la charge d’une requête individuelle en fonction de l’adresse IP cible).

> [!WARNING]  
> Les programmes d’équilibrage de la charge matérielle F5 possèdent une fonctionnalité appelée OneConnect qui permet de veiller à ce que la charge de chaque requête au sein d’une connexion TCP soit individuellement équilibrée. Si vous déployez des appareils mobiles, veillez à ce que le fournisseur de votre équilibreur de la charge matérielle prenne en charge la même fonctionnalité. Les dernières applications pour mobile iOS d’Apple requièrent la version 1.2 de TLS (Transport Layer Security). F5 fournit les paramètres spécifiques pour cela.<br />
Pour plus d’informations sur les équilibreurs de charge matérielle tiers, reportez-vous à <a href="http://go.microsoft.com/fwlink/p/?linkid=230700">http://go.microsoft.com/fwlink/p/?linkId=230700</a>

La configuration requise de l’équilibreur de la charge matérielle des services web du directeur et du pool de serveurs frontaux est la suivante :

  - Pour les adresses IP virtuelles (VIP) des services web internes, définissez la persistance Source\_addr (port interne 80, 443) sur l’équilibreur de la charge matérielle. Pour Lync Server 2013, la persistance Source\_addr signifie que plusieurs connexions provenant d’une seule adresse IP sont toujours envoyées à un seul serveur pour maintenir l’état de la session.

  - Utilisez un délai d’inactivité TCP de 1 800 secondes.

  - Sur le pare-feu situé entre le proxy inverse et l’équilibreur de la charge matérielle du pool du tronçon suivant, créez une règle autorisant le trafic https: sur le port 4443, entre le proxy inverse et l’équilibreur de la charge matérielle. L’équilibreur de la charge matérielle doit être configuré pour écouter sur les ports 80, 443 et 4443.

## Synthèse des conditions requises en termes d’affinité pour l’équilibreur de la charge matérielle


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Emplacement du client/de l’utilisateur</th>
<th>Conditions requises en matière d’affinité pour le nom de domaine complet des services web externes</th>
<th>Conditions requises en matière d’affinité pour le nom de domaine complet des services web internes</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync Web App (utilisateurs internes et externes)</p>
<p>Appareil mobile (utilisateurs internes et externes)</p></td>
<td><p>Aucune affinité</p></td>
<td><p>Affinité des adresses sources</p></td>
</tr>
<tr class="even">
<td><p>Lync Web App (utilisateurs externes et internes)</p>
<p>Appareil mobile (utilisateurs internes et externes)</p></td>
<td><p>Aucune affinité</p></td>
<td><p>Affinité des adresses sources</p></td>
</tr>
<tr class="odd">
<td><p>Lync Web App (utilisateurs internes uniquement)</p>
<p>Appareil mobile (non déployé)</p></td>
<td><p>Aucune affinité</p></td>
<td><p>Affinité des adresses sources</p></td>
</tr>
</tbody>
</table>


## Surveillance des ports pour les programmes d’équilibrage de la charge matérielle

Vous définissez la surveillance des ports sur les équilibreurs de la charge matérielle pour déterminer si des services spécifiques ne sont plus disponibles suite à des échecs matériel ou de communication. Par exemple, si le service du serveur frontal (RTCSRV) s’arrête en raison d’un échec du serveur frontal ou du pool de serveurs frontaux, la surveillance du programme d’équilibrage de la charge matérielle doit aussi cesser de recevoir du trafic sur les services web. Vous implémentez la surveillance des ports sur le programme d’équilibrage de la charge matérielle pour surveiller les éléments suivants :

### Pool d’utilisateurs du serveur frontal – Interface interne HLB

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>IP/Port virtuel</th>
<th>Port de nœud</th>
<th>Nœud Ordinateur/Écran</th>
<th>Profil de persistance</th>
<th>Remarques</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>&lt;pool&gt;web-int_mco_443_vs</p>
<p>443</p></td>
<td><p>443</p></td>
<td><p>Serveur frontal</p>
<p>5061</p></td>
<td><p>Source</p></td>
<td><p>HTTPS</p></td>
</tr>
<tr class="even">
<td><p>&lt;pool&gt;web-int_mco_80_vs</p>
<p>80</p></td>
<td><p>80</p></td>
<td><p>Serveur frontal</p>
<p>5061</p></td>
<td><p>Source</p></td>
<td><p>HTTP</p></td>
</tr>
</tbody>
</table>


### Pool d’utilisateurs du serveur frontal – Interface externe HLB

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th>IP/Port virtuel</th>
<th>Port de nœud</th>
<th>Nœud Ordinateur/Écran</th>
<th>Profil de persistance</th>
<th>Remarques</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>&lt;pool&gt;web_mco_443_vs</p>
<p>443</p></td>
<td><p>4443</p></td>
<td><p>Serveur frontal</p>
<p>5061</p></td>
<td><p>Aucune</p></td>
<td><p>HTTPS</p></td>
</tr>
<tr class="even">
<td><p>&lt;pool&gt;web_mco_80_vs</p>
<p>80</p></td>
<td><p>8080</p></td>
<td><p>Serveur frontal</p>
<p>5061</p></td>
<td><p>Aucune</p></td>
<td><p>HTTP</p></td>
</tr>
</tbody>
</table>

