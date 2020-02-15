---
title: 'Lync Server 2013 : options de déploiement SIP direct'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Direct SIP deployment options
ms:assetid: 84691944-03f2-4a89-9f2b-1ab3d7f388cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398672(v=OCS.15)
ms:contentKeyID: 48184692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b4bbacbbb6f1a420e989f4bed02ba2fc0db6f85f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036624"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="direct-sip-deployment-options-in-lync-server-2013"></a>Options de déploiement SIP direct dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-09-21_

Cette rubrique fournit des exemples de topologies pour le déploiement de connexions SIP directes.

<div id="sectionSection0" class="section">

<span id="BKMK_CommunicationsServerStand_Alone"></span>

<div>

## <a name="lync-server-stand-alone"></a>Autonome Lync Server

Si votre organisation utilise l’un des déploiements décrits dans cette section, vous pouvez utiliser Lync Server 2013 comme solution de téléphonie unique pour tout ou partie d’une organisation. Cette section décrit en détail les déploiements suivants :

  - **Déploiement incrémentiel :** Cette option suppose que vous disposez d’une infrastructure PBX (Private Branch Exchange) existante et que vous envisagez d’introduire une voix entreprise incrémentielle pour des groupes ou équipes plus petits au sein de votre organisation.

  - **Déploiement Lync Server VoIP uniquement :** cette option suppose que vous envisagez de déployer la voix entreprise sur un site qui ne dispose pas d’une infrastructure de téléphonie traditionnelle.

<div>

## <a name="incremental-deployment"></a>Déploiement incrémentiel

Dans un déploiement incrémentiel, Lync Server 2013 est la seule solution de téléphonie pour des équipes ou des services individuels, tandis que les autres utilisateurs d’une organisation continuent à utiliser un PBX. Cette stratégie de déploiement incrémentiel offre un moyen d’introduire la téléphonie IP dans votre entreprise par le biais de programmes pilotes contrôlés. Les groupes de travail dont les besoins en matière de communication sont les plus utilisés par les communications unifiées de Microsoft sont déplacés vers voix entreprise, tandis que d’autres utilisateurs demeurent sur le PBX existant. D’autres groupes de travail peuvent être migrés vers voix entreprise, selon les besoins.

L’option incrémentielle est recommandée si vous avez clairement défini des groupes d’utilisateurs ayant des exigences de communication en commun et qui se prêtent à la gestion centralisée. Cette option est également efficace si vous avez des équipes ou des services qui sont répartis sur des zones géographiques larges, où les économies de longue distance peuvent être importantes. En fait, cette option est utile pour créer des équipes virtuelles dont les membres peuvent être dispersés dans le monde entier. Vous pouvez créer, modifier ou DISBAND des équipes en réponse rapide aux besoins de l’entreprise.

La figure suivante illustre la topologie générique pour le déploiement de voix entreprise derrière un PBX. Il s’agit de la topologie recommandée pour le déploiement incrémentiel.

**Option de déploiement incrémentiel**

![Diagramme d’option de migration départementale](images/Gg398672.e951ecf4-7cd2-425a-9106-76977492d682(OCS.15).jpg "Diagramme d’option de migration départementale")

<div>


> [!NOTE]  
> Si vous connectez votre déploiement Lync Server à un partenaire SIP direct certifié, il n’est pas nécessaire d’avoir une passerelle de réseau téléphonique commuté (PSTN) entre le serveur de médiation et le PBX. Pour obtenir la liste des partenaires SIP directs certifiés, consultez le site Web Microsoft Unified Communications Open <A href="http://go.microsoft.com/fwlink/p/?linkid=203309">http://go.microsoft.com/fwlink/p/?linkId=203309</A>Interoperability Program à l’adresse.



</div>

<div>


> [!NOTE]  
> Le chemin d’accès multimédia indiqué dans cette figure a une déviation du trafic multimédia activé (configuration recommandée). Si vous choisissez de désactiver la déviation du trafic multimédia, le chemin d’accès multimédia est routé via le serveur de médiation.



</div>

Dans cette topologie, les services ou groupes de travail sélectionnés sont activés pour voix entreprise. Une passerelle PSTN relie le groupe de travail compatible VoIP (Voice over Internet Protocol) au PBX. Les utilisateurs qui sont activés pour voix entreprise, y compris les travailleurs distants, communiquent sur le réseau IP. Les appels émis par les utilisateurs voix entreprise vers le RTC et les collègues qui ne sont pas activés pour voix entreprise sont acheminés vers la passerelle PSTN appropriée. Les appels provenant de collègues qui sont toujours sur le système PBX ou des appelants sur le réseau téléphonique commuté (RTC) sont acheminés vers la passerelle PSTN, qui transfère les appels vers Lync Server pour le routage.

Il existe deux configurations recommandées pour la connexion de voix entreprise à une infrastructure PBX existante pour l’interopérabilité : voix entreprise derrière le PBX et voix entreprise devant le PBX.

<div>

## <a name="enterprise-voice-behind-the-pbx"></a>Voix entreprise derrière le PBX

Quand Enterprise Voice est déployé derrière le PBX, tous les appels provenant du RTC arrivent sur le PBX, qui achemine les appels vers une passerelle PSTN pour les utilisateurs de voix entreprise et les appels vers le PBX pour les utilisateurs PBX.

</div>

<div>

## <a name="enterprise-voice-in-front-of-the-pbx"></a>Voix entreprise devant le PBX

Quand Enterprise Voice est déployé devant le PBX, tous les appels arrivent à la passerelle PSTN, qui achemine les appels pour les utilisateurs voix entreprise vers Lync Server et appelle les utilisateurs PBX vers le PBX. Les appels vers le RTC provenant des utilisateurs de voix entreprise et PBX sont acheminés via le réseau IP vers la passerelle PSTN la plus économique. Le tableau suivant présente les avantages et les inconvénients de cette configuration.

### <a name="advantages-and-disadvantages-of-deploying-enterprise-voice-in-front-of-pbx"></a>Avantages et inconvénients du déploiement de voix entreprise devant le PBX

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Avantages</th>
<th>Inconvénients</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Le PBX sert toujours les utilisateurs non activés pour voix entreprise.</p></td>
<td><p>Il se peut que les passerelles existantes ne prennent pas en charge les fonctionnalités ou la capacité de votre choix.</p></td>
</tr>
<tr class="even">
<td><p>PBX gère tous les appareils antérieurs.</p></td>
<td><p>Nécessite une jonction de la passerelle vers le PBX et de la passerelle vers le serveur de médiation. Vous aurez peut-être besoin de plus de jonctions à partir du fournisseur de services.</p></td>
</tr>
<tr class="odd">
<td><p>Les utilisateurs de voix entreprise conservent les mêmes numéros de téléphone.</p></td>
<td><p> </p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="lync-server-voip-only-deployment"></a>Déploiement de Lync Server VoIP uniquement

Voix entreprise fournit de nouvelles entreprises, ainsi que de nouveaux sites Office pour les entreprises existantes, avec la possibilité de mettre en œuvre une solution VoIP complète sans avoir à se préoccuper de l’intégration de PBX ou d’un déploiement et d’une maintenance substantiels. coûts d’une infrastructure IP-PBX. Cette solution prend en charge les travailleurs à la fois sur site et distants.

Dans ce déploiement, tous les appels sont routés sur le réseau IP. Les appels vers le RTC sont acheminés vers la passerelle PSTN appropriée. Lync 2013 ou Lync Phone Edition sert de téléphone. Le contrôle d’appel distant n’est pas disponible et n’est pas nécessaire, car il n’existe aucun téléphone PBX que les utilisateurs peuvent contrôler. Les services de messagerie vocale et de standard automatique sont disponibles via le déploiement facultatif de la messagerie unifiée Exchange.

<div>


> [!NOTE]  
> En plus de l’infrastructure réseau requise pour prendre en charge Lync Server 2013, un déploiement VoIP uniquement peut utiliser une petite passerelle qualifiée pour prendre en charge les télécopieurs et les appareils analogiques.



</div>

La figure suivante illustre une topologie classique pour un déploiement VoIP uniquement.

**Option de déploiement VoIP uniquement**

![Option de déploiement Greenfidle](images/Gg398672.820dc5fe-0e20-431b-ae4e-fefdf2221d3b(OCS.15).jpg "Option de déploiement Greenfidle")

<div>


> [!NOTE]  
> Le chemin d’accès multimédia indiqué dans cette figure a une déviation du trafic multimédia activé (configuration recommandée). Si vous choisissez de désactiver la déviation du trafic multimédia, le chemin d’accès multimédia est routé via le serveur de médiation.



</div>

</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

