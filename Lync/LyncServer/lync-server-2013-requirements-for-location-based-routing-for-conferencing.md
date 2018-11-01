---
title: Conditions requises pour le routage géodépendant pour les conférences
TOCTitle: Conditions requises pour le routage géodépendant pour les conférences
ms:assetid: 766d9286-2c34-4faf-bb3e-f0ca478a70cf
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Dn362806(v=OCS.15)
ms:contentKeyID: 56269616
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Conditions requises pour le routage géodépendant pour les conférences

 

_**Dernière rubrique modifiée :** 2016-12-08_

Voici une liste des conditions requises pour l’installation et la configuration de l’application de conférence avec routage géodépendant :

  - La mise à jour cumulative 2 de Lync Server 2013 doit être déployée sur tous les serveurs ou pools de votre topologie.

> [!NOTE]  
> Si la mise à jour mise à jour cumulative 2 de Lync Server 2013 ou une mise à jour ultérieure n’est pas installée sur un pool ou un serveur Lync de votre topologie, l’application du routage géodépendant des réunions Lync ne peut pas être garanti.

  - Le routage géodépendant Lync Server 2013 est une condition préalable pour l’application de conférence avec routage géodépendant. Pour plus d’informations sur la configuration du routage géodépendant de Lync Server 2013, voir [Configuration du routage géodépendant](lync-server-2013-configuring-location-based-routing.md).

  - Les conditions requises pour l’application de conférence avec routage géodépendant sont les mêmes que celles requises pour le routage géodépendant de Lync Server 2013. Pour plus d’informations, voir [Planification du routage géodépendant](lync-server-2013-planning-for-location-based-routing.md).

## Serveurs pris en charge

L’application de conférence avec routage géodépendant nécessite que la mise à jour cumulative 2 de Lync Server 2013 soit déployée sur tous les pools frontaux et serveurs Standard Edition de votre topologie. Si elle n’est pas installée sur certains serveurs Lync de votre topologie, les restrictions de routage géodépendant ne peuvent pas être totalement appliquées aux réunions Lync et transferts d’appels consultatifs.

Le tableau suivant identifie les combinaisons de rôles serveur et versions prenant en charge le routage géodépendant.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Version de pool frontal</p></td>
<td><p>Version de serveur de médiation</p></td>
<td><p>Pris en charge</p></td>
</tr>
<tr class="even">
<td><p>Mise à jour cumulative 2 de Lync Server 2013</p></td>
<td><p>Mise à jour cumulative 2 de Lync Server 2013</p></td>
<td><p>Oui</p></td>
</tr>
<tr class="odd">
<td><p>Mise à jour cumulative 2 de Lync Server 2013</p></td>
<td><p>Mise à jour cumulative 1 de Lync Server 2013</p></td>
<td><p>Non</p></td>
</tr>
<tr class="even">
<td><p>Mise à jour cumulative 2 de Lync Server 2013</p></td>
<td><p>Lync Server 2010</p></td>
<td><p>Non</p></td>
</tr>
<tr class="odd">
<td><p>Mise à jour cumulative 2 de Lync Server 2013</p></td>
<td><p>Office Communications Server 2007 R2</p></td>
<td><p>Non</p></td>
</tr>
<tr class="even">
<td><p>Mise à jour cumulative 1 de Lync Server 2013</p></td>
<td><p>Indifférent</p></td>
<td><p>Non</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2010</p></td>
<td><p>Indifférent</p></td>
<td><p>Non</p></td>
</tr>
<tr class="even">
<td><p>Office Communications Server 2007 R2</p></td>
<td><p>Indifférent</p></td>
<td><p>Non</p></td>
</tr>
</tbody>
</table>


## Clients pris en charge

Les clients Lync qui prennent en charge le routage géodépendant des réunions Lync sont ceux qui prennent en charge le routage géodépendant de Lync Server 2013. Pour plus d’informations, voir [Prise en charge des clients et serveurs pour le routage géodépendant](lync-server-2013-client-and-server-support-for-location-based-routing.md).

## Conditions requises du serveur de médiation pour les transferts d’appels consultatifs

L’application de conférence avec routage géodépendant nécessite le déploiement de serveurs de médiation indépendants de manière à appliquer les restrictions de routage géodépendant aux transferts d’appels consultatifs.

Pour appliquer le routage géodépendant des transferts d’appels consultatifs, le serveur de médiation doit être associé à un seul serveur de médiation homologue (par exemple, PBX, passerelle SIP, etc.) dans les régions réseau où le routage géodépendant est requis. Si d’autres serveurs de médiation homologues sont déployés dans la même région réseau, le serveur de médiation homologue doit être associé à un serveur de médiation différent. Cette condition requise comporte les détails suivants :

  - Serveur de médiation unique par serveurs de médiation homologues. Lorsqu’un transfert d’appel consultatif est routé vers un serveur de médiation homologue via un serveur de médiation configuré avec plusieurs jonctions SIP vers plusieurs homologues (par exemple, des PBX et des passerelles), le transfert d’appel consultatif est bloqué pour empêcher le contournement des frais de réseau téléphonique commuté, si le transfert d’appel consultatif est autorisé via certaines jonctions SIP mais non autorisé via d’autres.
    
    Par exemple, dans le cas d’un serveur de médiation unique utilisé pour la maintenance d’un serveur de médiation homologue de passerelle PSTN et d’un serveur de médiation homologue de PBX, le comportement suivant sera observé :
    
      - Lorsqu’un utilisateur de Lync d’un site donné (par exemple, site 1) tente de transférer un appel avec un point de terminaison PSTN vers un utilisateur Lync d’un autre site (par exemple, site 2) via un transfert consultatif, l’appel ne sera pas autorisé afin d’empêcher le contournement des frais de réseau téléphonique commuté.
    
      - Lorsqu’un utilisateur Lync d’un site donné (par exemple, site 1) tente de transférer un appel avec un point de terminaison PBX au sein du même site (site 1) vers un utilisateur Lync d’un site différent (site 2) via un transfert consultatif, l’appel ne sera pas autorisé, même s’il n’occasionne pas d’éventuel contournement des frais de réseau téléphonique commuté.

  - Serveurs de médiation distincts par serveur de médiation homologue
    
    Lorsqu’un transfert consultatif est adressé à un serveur de médiation homologue, le transfert consultatif est évalué par rapport au serveur de médiation homologue unique traité par le serveur de médiation. L’appel sera autorisé ou non en fonction de son potentiel à occasionner un contournement des frais de réseau téléphonique commuté, quels que soient les autres homologues du site puisqu’ils sont traités par des serveurs de médiation distincts.
    
    Par exemple, dans le cas d’un serveur de médiation distinct utilisé pour la maintenance d’un homologue de passerelle PSTN et d’un homologue de PBX, le comportement suivant sera observé :
    
      - Lorsqu’un utilisateur de Lync d’un site donné (par exemple, site 1) tente de transférer un appel avec un point de terminaison PSTN vers un utilisateur Lync d’un autre site (par exemple, site 2) via un transfert consultatif, l’appel ne sera pas autorisé afin d’empêcher le contournement des frais de réseau téléphonique commuté.
    
      - Lorsqu’un utilisateur Lync d’un site donné (par exemple, site 1) tente de transférer un appel avec un point de terminaison PBX au sein du même site (site 1) vers un utilisateur Lync d’un site différent (site 2) via un transfert consultatif, l’appel sera autorisé, puisqu’il n’occasionnera pas d’éventuel contournement des frais de réseau téléphonique commuté.

## Fonctionnalités non prises en charge par l’application de conférence avec routage géodépendant

Les fonctionnalités suivantes ne sont pas prises en charge par l’application de conférence avec routage géodépendant :

  - Conférence rendez-vous. Le routage géodépendant ne peut pas être appliqué pour la conférence rendez-vous. Les demandes de rendez-vous pour une conférence donnée ne seront pas restreintes par le routage géodépendant même si l’organisateur de la conférence est un utilisateur Lync prenant en charge le routage géodépendant.

  - Il est recommandé de ne pas configurer les numéros d’accès de conférence dans des régions où des restrictions de routage géodépendant doivent être appliquées.

