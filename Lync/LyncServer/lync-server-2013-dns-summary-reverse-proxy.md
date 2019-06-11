---
title: 'Lync Server 2013 : Résumé DNS - Proxy inverse'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS summary - Reverse proxy
ms:assetid: 3073affa-4d92-4453-9974-3a82ca0c6445
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204781(v=OCS.15)
ms:contentKeyID: 48183755
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 47606fe71b271e01cc7fbefbcf319a2efe93f478
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831348"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-summary---reverse-proxy-in-lync-server-2013"></a>Résumé DNS - Proxy inverse dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-03-22_

Vous pouvez configurer deux cartes réseau dans votre proxy inverse en procédant comme suit:

<div>

## <a name="reverse-proxy-network-adapter-requirements"></a>Configuration requise pour la carte réseau du proxy inverse

  - Exemple **de carte réseau 1 (interface interne)**
    
    Interface interne avec 172.25.33.40 attribué.
    
    Aucune passerelle par défaut n’est définie.
    
    Assurez-vous qu’il existe un itinéraire du réseau contenant l’interface interne du proxy inverse vers tout réseau qui contient des serveurs de pool frontal Lync Server (par exemple, de 172.25.33.0 à 192.168.10.0).

  - Exemple **de carte réseau 2 (interface externe)**
    
    Au moins une adresse IP publique est affectée à cette carte réseau.
    
    La passerelle est définie de telle sorte qu’elle pointe vers le routeur ou le pare-feu intégré de votre périmètre externe. (10.45.16.1 dans les exemples de scénarios)

### <a name="dns-records-required-for-reverse-proxy"></a>Enregistrements DNS requis pour le proxy inverse

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Emplacement/TYPE/port</th>
<th>FQDN</th>
<th>Adresse IP</th>
<th>Cartes sur/Commentaires</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DNS/A externe</p></td>
<td><p>webext.contoso.com</p></td>
<td><p>Écouteur affecté pour les ressources publiées en externe</p></td>
<td><p>Services Web externes du déploiement interne. Il est possible de définir et de créer des enregistrements supplémentaires pour tous les domaines SIP qui utiliseront ce proxy inverse, ainsi que les services Web externes définis.</p></td>
</tr>
<tr class="even">
<td><p>DNS/A externe</p></td>
<td><p>webdirext.contoso.com</p></td>
<td><p>Écouteur affecté pour les ressources publiées en externe</p></td>
<td><p>Services Web externes pour les directeurs ou les pools de réalisateurs dans votre déploiement. Vous pouvez définir autant de directeurs qu’il existe de gestionnaires distincts, qui peuvent être associés à d’autres domaines SIP.</p>
<div>

> [!IMPORTANT]  
> La définition des enregistrements DNS pour et la publication des directeurs ne constituent pas le pool frontal ou la décision du réalisateur. Vous devez définir et publier le directeur et les services Web externes du pool frontal si vous utilisez des directeurs. Les types de trafic spécifiques (pour l’authentification et d’autres utilisations) seront d’abord envoyés au directeur, s’il est défini dans la topologie.


</div></td>
</tr>
<tr class="odd">
<td><p>DNS/A externe</p></td>
<td><p>dialin.contoso.com</p></td>
<td><p>Écouteur affecté pour les ressources publiées en externe</p></td>
<td><p>Conférence rendez-vous publiée en externe</p></td>
</tr>
<tr class="even">
<td><p>DNS/A externe</p></td>
<td><p>meet.contoso.com</p></td>
<td><p>Écouteur affecté pour les ressources publiées en externe</p></td>
<td><p>Conférences publiées en externe</p></td>
</tr>
<tr class="odd">
<td><p>DNS/A externe</p></td>
<td><p>officewebapps01.contoso.com</p></td>
<td><p>Écouteur attribué pour Office Web Apps Server</p></td>
<td><p>Office Web Apps Server déployé en interne ou dans le périmètre et publié pour un accès client externe</p></td>
</tr>
<tr class="even">
<td><p>DNS/A externe</p></td>
<td><p>lyncdiscover.contoso.com</p></td>
<td><p>Écouteur affecté pour les ressources publiées en externe</p></td>
<td><p>Lync Discover enregistrement externe pour une découverte automatique publiée en externe et inclut la mobilité, Microsoft Lync Web App et l’application Web du planificateur</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

