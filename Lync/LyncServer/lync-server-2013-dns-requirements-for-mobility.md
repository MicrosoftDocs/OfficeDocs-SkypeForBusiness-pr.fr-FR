---
title: 'Lync Server 2013 : configuration DNS requise pour la mobilité'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for mobility
ms:assetid: df6962bc-2a16-440e-a333-022ebd14f957
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690040(v=OCS.15)
ms:contentKeyID: 48185624
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0201a9e8870a1b7d8cc579eb270ca67c929cae5d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029605"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-mobility-with-lync-server-2013"></a>Configuration DNS requise pour la mobilité avec Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-11-13_

Lorsque vous déployez la fonctionnalité de mobilité Lync Server 2013, vous pouvez utiliser les nouvelles URL disponibles avec le service de découverte automatique Microsoft Lync Server 2013 ou vous pouvez utiliser vos URL de services Web existantes. Si vous utilisez vos URL existantes, les utilisateurs doivent entrer manuellement les URL dans les paramètres de leur appareil mobile. Cette option est généralement utilisée à des fins de dépannage. Lorsque vous utilisez les nouvelles URL, les clients mobiles peuvent découvrir automatiquement les ressources Lync Server 2013. Lorsque vous prenez en charge la découverte automatique, vous devez ajouter de nouveaux enregistrements DNS (Domain Name System). Cette section décrit les enregistrements DNS nécessaires pour la découverte automatique.

Pour prendre en charge la découverte automatique, vous devez créer les enregistrements DNS suivants pour chaque domaine SIP :

  - un enregistrement DNS interne afin de prendre en charge les utilisateurs qui se connectent depuis le réseau de votre organisation ;

  - un enregistrement DNS externe, ou public, afin de prendre en charge les utilisateurs mobiles qui se connectent depuis Internet.

L’URL de découverte automatique interne ne doit pas être adressable depuis l’extérieur de votre réseau. L’URL de découverte automatique externe ne doit pas être adressable depuis votre réseau. Toutefois, si cette condition ne peut pas être remplie pour l’URL externe, la fonctionnalité du client mobile ne devrait pas être affectée.

Les enregistrements DNS peuvent être des enregistrements CNAME ou des enregistrements A (hôte).

**Enregistrements DNS internes**

Vous devez créer l’un des enregistrements DNS internes suivants :


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Type d’enregistrement</th>
<th>Nom d’hôte ou définition SRV</th>
<th>Résolu en</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CNAME</p></td>
<td><p>lyncdiscoverinternal. &lt;sipdomain&gt;</p></td>
<td><p>Nom de domaine complet (FQDN) des services Web internes pour votre pool Directeur, si vous en avez un, ou pour votre pool frontal si vous ne disposez pas d’un directeur</p></td>
</tr>
<tr class="even">
<td><p>A (hôte)</p></td>
<td><p>lyncdiscoverinternal. &lt;sipdomain&gt;</p></td>
<td><p>Adresse IP interne des services Web (adresse IP virtuelle (VIP) si vous utilisez un programme d’équilibrage de la charge) de votre pool Directeur, si vous en avez un, ou de votre pool frontal si vous ne disposez pas d’un directeur</p></td>
</tr>
</tbody>
</table>


**Enregistrements DNS externes**

Vous devez créer l’un des enregistrements DNS externes suivants :


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Type d’enregistrement</th>
<th>Nom d’hôte</th>
<th>Résolu en</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CNAME</p></td>
<td><p>lyncdiscover. &lt;sipdomain&gt;</p></td>
<td><p>Nom de domaine complet externe des services Web pour votre pool Directeur, si vous en avez un, ou pour votre pool frontal si vous n’avez pas de directeur</p></td>
</tr>
<tr class="even">
<td><p>A (hôte)</p></td>
<td><p>lyncdiscover. &lt;sipdomain&gt;</p></td>
<td><p>Adresse IP externe ou publique (adresse VIP si vous utilisez un programme d’équilibrage de la charge) du proxy inverse</p></td>
</tr>
<tr class="odd">
<td><p>SRV</p></td>
<td><p>_sipfederationtls. _tcp. &lt;sipdomain&gt;</p>
<p>Résout l’enregistrement d’hôte (A ou AAAA) pour le service Edge d’accès</p></td>
<td><p>Pour prendre en charge le service de notifications et le service de notifications d’Apple, vous devez créer un enregistrement SRV pour chaque domaine SIP doté de clients Microsoft Lync mobile.</p>
<div>

> [!IMPORTANT]  
> Cette exigence s’applique uniquement aux clients mobiles Microsoft Lync sur des appareils mobiles Apple ou Microsoft. Les appareils Android et Nokia Symbian n’utilisent pas de notification push.


</div></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Lyncdiscover, également appelé découverte automatique, le trafic passe par le proxy inverse. L’enregistrement SRV pointe vers un enregistrement qui est résolu via le service Edge d’accès.



</div>

</div>

<span> </span>

</div>

</div>

</div>

