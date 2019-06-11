---
title: 'Lync Server 2013: configuration requise pour la mobilité'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS requirements for mobility
ms:assetid: df6962bc-2a16-440e-a333-022ebd14f957
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690040(v=OCS.15)
ms:contentKeyID: 48185624
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6fb933e20b8da627ad48a30802ff86c7ed95faff
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831369"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-mobility-with-lync-server-2013"></a>Configuration DNS requise pour la mobilité avec Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-11-13_

Lorsque vous déployez la fonctionnalité de mobilité de Lync Server 2013, vous pouvez utiliser les nouvelles URL disponibles avec le service de découverte automatique Microsoft Lync Server 2013 ou utiliser vos URL de services Web existantes. Si vous utilisez vos URL existantes, les utilisateurs doivent entrer manuellement les URL dans leurs paramètres d’appareil mobile. Cette option est généralement utilisée pour la résolution des problèmes. Lorsque vous utilisez les nouvelles URL, les clients mobiles peuvent automatiquement découvrir les ressources de Lync Server 2013. Lorsque vous prenez en charge la découverte automatique, vous devez ajouter de nouveaux enregistrements DNS (Domain Name System). Cette section décrit les enregistrements DNS requis pour la découverte automatique.

Pour prendre en charge la découverte automatique, vous devez créer les enregistrements DNS suivants pour chaque domaine SIP:

  - Un enregistrement DNS interne pour prendre en charge les utilisateurs mobiles qui se connectent au sein du réseau de votre organisation.

  - Enregistrement DNS externe ou public permettant de prendre en charge les utilisateurs mobiles qui se connectent à partir d’Internet

L’URL de découverte automatique interne ne doit pas être adressable depuis l’extérieur de votre réseau. L’URL de découverte automatique externe ne doit pas être adressable à partir de votre réseau. Toutefois, si vous ne pouvez pas respecter cette exigence pour l’URL externe, le client mobile ne doit pas être affecté.

Les enregistrements DNS peuvent être des enregistrements CNAMe ou des enregistrements (Host).

**Enregistrements DNS internes**

Vous devez créer un des enregistrements DNS internes suivants:


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
<td><p>Nom de domaine complet des services Web internes (FQDN) de votre pool de directeurs, le cas échéant, ou de votre pool frontal si vous n’avez pas de réalisateur</p></td>
</tr>
<tr class="even">
<td><p>A (hôte)</p></td>
<td><p>lyncdiscoverinternal. &lt;sipdomain&gt;</p></td>
<td><p>Adresse IP des services Web internes (adresse IP virtuelle) si vous utilisez un équilibreur de charge, si vous en avez un, ou si vous n’avez pas de directeur...</p></td>
</tr>
</tbody>
</table>


**Enregistrements DNS externes**

Vous devez créer un des enregistrements DNS externes suivants:


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
<td><p>Nom de domaine complet des services Web externes pour votre pool de directeurs, le cas échéant, ou pour votre pool frontal si vous n’avez pas de réalisateur</p></td>
</tr>
<tr class="even">
<td><p>A (hôte)</p></td>
<td><p>lyncdiscover. &lt;sipdomain&gt;</p></td>
<td><p>Adresse IP externe ou publique (adresse VIP si vous utilisez un équilibreur de charge) du proxy inverse</p></td>
</tr>
<tr class="odd">
<td><p>SRV</p></td>
<td><p>_sipfederationtls._tcp. &lt;sipdomain&gt;</p>
<p>Se résout en enregistrement Host (A ou AAAA) pour le service Edge d’accès.</p></td>
<td><p>Pour prendre en charge les services de notifications de transmission et de notifications de type Apple, vous devez créer un enregistrement SRV pour chaque domaine SIP doté de clients mobiles Microsoft Lync.</p>
<div>

> [!IMPORTANT]  
> Cette condition s’applique uniquement aux clients mobiles Microsoft Lync sur les appareils mobiles Apple ou Microsoft. Les appareils Android et Nokia Symbian n’utilisent pas la notification de transmission.


</div></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Lyncdiscover, également connu sous le nom de découverte automatique, le trafic passe par le proxy inverse. Un enregistrement SRV pointe vers un enregistrement qui est résolu par le biais du service Edge d’accès.



</div>

</div>

<span> </span>

</div>

</div>

</div>

