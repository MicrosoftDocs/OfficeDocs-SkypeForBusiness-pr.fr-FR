---
title: 'Lync Server 2013 : Résumé des enregistrements DNS-proxy inverse'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS summary - Reverse proxy
ms:assetid: 3073affa-4d92-4453-9974-3a82ca0c6445
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204781(v=OCS.15)
ms:contentKeyID: 48183755
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a5f79437c5253365e4333e7cd064883bba968a54
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213100"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-summary---reverse-proxy-in-lync-server-2013"></a>Résumé des enregistrements DNS-proxy inverse dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-03-22_

Vous configurez deux cartes réseau dans votre serveur proxy inverse comme suit :

<div>

## <a name="reverse-proxy-network-adapter-requirements"></a>Cartes réseau de proxy inverse requises

  - **Carte réseau 1 (interface interne)** (exemple)
    
    Interface interne avec 172.25.33.40 affecté.
    
    Aucune passerelle par défaut n’est définie.
    
    Assurez-vous qu’il existe un itinéraire entre le réseau contenant l’interface interne du proxy inverse et les réseaux qui contiennent des serveurs de pools frontaux Lync Server (par exemple, de 172.25.33.0 à 192.168.10.0).

  - **Carte réseau 2 (interface externe)** (exemple)
    
    Au moins une adresse IP publique est affectée à cette carte réseau.
    
    La passerelle est définie de sorte à pointer sur le routeur ou le pare-feu intégré de votre périmètre extérieur. (10.45.16.1 dans les exemples de scénario)

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
<th>Mappage à/Commentaires</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DNS externe/A</p></td>
<td><p>webext.contoso.com</p></td>
<td><p>Écouteur assigné pour les ressources publiées à l’extérieur</p></td>
<td><p>Services web externes à partir du déploiement interne. Des enregistrements supplémentaires peuvent être définis et créés pour tous les pools et les serveurs uniques de tous les domaines SIP qui utilisent ce proxy inverse et qui ont défini des services web externes.</p></td>
</tr>
<tr class="even">
<td><p>DNS externe/A</p></td>
<td><p>webdirext.contoso.com</p></td>
<td><p>Écouteur assigné pour les ressources publiées à l’extérieur</p></td>
<td><p>Les services Web externes pour les directeurs ou les pools directeurs de votre déploiement. Vous pouvez définir autant de directeurs que de directeurs distincts, qui peuvent être associés à d’autres domaines SIP.</p>
<div>

> [!IMPORTANT]  
> La définition des enregistrements DNS pour la publication et la publication des directeurs n’est ni le pool frontal, ni la décision du directeur. Vous devez définir et publier le directeur et les services Web externes du pool frontal si vous utilisez des directeurs. Les types de trafic spécifiques (pour l’authentification et les autres utilisations) seront d’abord envoyés au directeur, s’il est défini dans la topologie.


</div></td>
</tr>
<tr class="odd">
<td><p>DNS externe/A</p></td>
<td><p>dialin.contoso.com</p></td>
<td><p>Écouteur assigné pour les ressources publiées à l’extérieur</p></td>
<td><p>Conférences rendez-vous publiées en externe</p></td>
</tr>
<tr class="even">
<td><p>DNS externe/A</p></td>
<td><p>meet.contoso.com</p></td>
<td><p>Écouteur assigné pour les ressources publiées à l’extérieur</p></td>
<td><p>Conférences publiées en externe</p></td>
</tr>
<tr class="odd">
<td><p>DNS externe/A</p></td>
<td><p>officewebapps01.contoso.com</p></td>
<td><p>Écouteur affecté pour Office Web Apps Server</p></td>
<td><p>Office Web Apps Server déployé en interne ou dans le périmètre et publié pour l’accès au client externe</p></td>
</tr>
<tr class="even">
<td><p>DNS externe/A</p></td>
<td><p>lyncdiscover.contoso.com</p></td>
<td><p>Écouteur assigné pour les ressources publiées à l’extérieur</p></td>
<td><p>Enregistrement externe de découverte Lync pour la découverte automatique publiée en externe et inclut la mobilité, Microsoft Lync Web App et le planificateur Web App</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

