---
title: 'Lync Server 2013 : Options de déploiement SIP direct'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Direct SIP deployment options
ms:assetid: 84691944-03f2-4a89-9f2b-1ab3d7f388cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398672(v=OCS.15)
ms:contentKeyID: 48184692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 277b64346dc17815438f2ac34da58f36d2b150f2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34831395"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="direct-sip-deployment-options-in-lync-server-2013"></a>Options de déploiement SIP direct dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-09-21_

Cette rubrique fournit des exemples de topologies pour le déploiement de connexions SIP directes.

<div id="sectionSection0" class="section">

<span id="BKMK_CommunicationsServerStand_Alone"></span>

<div>

## <a name="lync-server-stand-alone"></a>Serveur Lync autonome

Si votre organisation utilise l’un des déploiements décrits dans cette section, vous pouvez utiliser Lync Server 2013 comme seule solution de téléphonie pour une partie ou l’ensemble d’une organisation. Cette section décrit en détail les déploiements suivants:

  - **Déploiement incrémentiel:** Cette option part du principe que vous disposez d’une infrastructure PBX (Private Branch Exchange) existante et que vous envisagez d’introduire une voix entreprise de façon incrémentielle pour des groupes ou équipes plus petits au sein de votre organisation.

  - **Déploiement de Lync Server VoIP uniquement:** cette option suppose que vous envisagez le déploiement d’Enterprise Voice sur un site ne disposant pas d’une infrastructure de téléphonie classique.

<div>

## <a name="incremental-deployment"></a>Déploiement incrémental

Dans le cadre du déploiement incrémentiel, Lync Server 2013 est la seule solution de téléphonie pour les équipes ou services individuels, tandis que les autres utilisateurs d’une organisation continuent à utiliser un PBX. Cette stratégie de déploiement incrémental fournit un moyen d’introduire la téléphonie IP dans votre entreprise par le biais de programmes pilotes contrôlés. Les groupes de travail dont les besoins en matière de communication sont les plus appropriés par le biais de communications unifiées Microsoft sont déplacés vers voix entreprise, tandis que d’autres utilisateurs restent sur le système PBX existant. Vous pouvez migrer des groupes de travail supplémentaires vers Enterprise Voice, selon les besoins.

L’option incrémental est recommandée si vous avez clairement défini des groupes d’utilisateurs présentant des exigences de communication en commun et qui se prêtent à une gestion centralisée. Cette option est également utile si vous avez des équipes ou des services qui se propagent sur des zones géographiques larges, pour lesquelles l’économie des tarifs de grande distance peut être importante. En fait, cette option est utile pour créer des équipes virtuelles dont les membres pourront être disséminés dans le monde entier. Vous pouvez créer, modifier ou disperser le de telles équipes en réponse rapide au changement de configuration de votre entreprise.

La figure suivante illustre la topologie générique pour le déploiement de la voix entreprise derrière un PBX. Il s’agit de la topologie recommandée pour le déploiement incrémentiel.

**Option de déploiement incrémental**

![Diagramme d’option de migration départemental] (images/Gg398672.e951ecf4-7cd2-425a-9106-76977492d682(OCS.15).jpg "Diagramme d’option de migration départemental")

<div>


> [!NOTE]  
> Si vous connectez votre déploiement de Lync Server à un partenaire SIP direct certifié, une passerelle RTC (réseau téléphonique commuté) entre le serveur de médiation et le PBX n’est pas nécessaire. Pour obtenir la liste des partenaires SIP directs certifiés, voir le site Web Microsoft Unified Communications Open <A href="http://go.microsoft.com/fwlink/p/?linkid=203309">http://go.microsoft.com/fwlink/p/?linkId=203309</A>Interoperability du programme à l’adresse.



</div>

<div>


> [!NOTE]  
> Le chemin d’accès multimédia indiqué dans cette figure est associé au contournement de média activé (configuration recommandée). Si vous choisissez de désactiver le contournement multimédia, le chemin multimédia est routé par le biais du serveur de médiation.



</div>

Dans cette topologie, les services ou groupes de travail sélectionnés sont activés pour voix entreprise. Une passerelle RTC relie le groupe de travail VoIP au système PBX. Les utilisateurs qui sont activés pour voix entreprise, y compris les travailleurs distants, communiquent sur le réseau IP. Les appels d’utilisateurs vocaux d’entreprise vers le RTC et aux collègues qui ne sont pas activés pour voix entreprise sont routés vers la passerelle RTC appropriée. Les appels provenant de collègues qui se trouvent toujours sur le système PBX ou à partir des appelants sur le RTC sont routés vers la passerelle RTC, qui transfère les appels vers Lync Server pour le routage.

Il existe deux configurations recommandées pour la connexion de voix entreprise à une infrastructure PBX existante pour l’interopérabilité: voix entreprise derrière le PBX et voix entreprise en face du PBX.

<div>

## <a name="enterprise-voice-behind-the-pbx"></a>Voix entreprise à l’arrière-plan PBX

Lorsque Enterprise Voice est déployé derrière le système PBX, tous les appels à partir du RTC arrivent au PBX, ce qui achemine les appels vers une passerelle RTC et les appels vers des utilisateurs PBX vers le PBX.

</div>

<div>

## <a name="enterprise-voice-in-front-of-the-pbx"></a>Voix entreprise en face du PBX

Lorsque Enterprise Voice est déployé devant le PBX, tous les appels arrivent sur la passerelle RTC, qui achemine les appels pour les utilisateurs voix entreprise vers Lync Server et les appels aux utilisateurs PBX vers le PBX. Les appels vers le RTC provenant des utilisateurs de voix et de PBX entreprise sont routés via le réseau IP vers la passerelle RTC la plus économique. Le tableau suivant répertorie les avantages et inconvénients de cette configuration.

### <a name="advantages-and-disadvantages-of-deploying-enterprise-voice-in-front-of-pbx"></a>Avantages et inconvénients du déploiement d’Enterprise Voice en face du PBX

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Inconvénients</th>
<th>Liés</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Le système PBX répond toujours aux utilisateurs non activés pour voix entreprise.</p></td>
<td><p>Les passerelles existantes risquent de ne pas prendre en charge les fonctionnalités ou capacités de votre choix.</p></td>
</tr>
<tr class="even">
<td><p>Le système PBX gère tous les appareils antérieurs.</p></td>
<td><p>Il est nécessaire de disposer d’un Trunk de la passerelle au PBX et de la passerelle au serveur de médiation. Il est possible que vous ayez besoin de plus de circuits auprès du prestataire de services.</p></td>
</tr>
<tr class="odd">
<td><p>Les utilisateurs voix entreprise conservent les mêmes numéros de téléphone.</p></td>
<td><p> </p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="lync-server-voip-only-deployment"></a>Déploiement VoIP de Lync Server uniquement

Enterprise Voice offre de nouvelles entreprises ainsi que de nouveaux sites Office pour les entreprises existantes, avec la possibilité d’implémenter une solution VoIP complète sans avoir à vous soucier de l’intégration PBX ou induire le déploiement et la maintenance importants. coûts d’une infrastructure PBX IP. Cette solution prend en charge les travailleurs sur site et distants.

Dans ce déploiement, tous les appels sont routés via le réseau IP. Les appels vers le RTC sont routés vers la passerelle RTC appropriée. Lync 2013 ou Lync Phone Edition sert de téléphone téléphonique. Le contrôle d’appel distant n’est pas disponible et n’est pas nécessaire, car il n’y a pas de téléphone PBX pour le contrôle des utilisateurs. Les services de messagerie vocale et de standard automatique sont disponibles par le biais du déploiement facultatif de la messagerie unifiée Exchange (UM).

<div>


> [!NOTE]  
> Outre l’infrastructure réseau qui est requise pour la prise en charge de Lync Server 2013, un déploiement VoIP uniquement peut utiliser une petite passerelle qualifiée pour prendre en charge les télécopieurs et les appareils analogiques.



</div>

La figure suivante illustre une topologie classique pour un déploiement VoIP uniquement.

**Option de déploiement VoIP uniquement**

![Option de déploiement Greenfidle] (images/Gg398672.820dc5fe-0e20-431b-ae4e-fefdf2221d3b(OCS.15).jpg "Option de déploiement Greenfidle")

<div>


> [!NOTE]  
> Le chemin d’accès multimédia indiqué dans cette figure est associé au contournement de média activé (configuration recommandée). Si vous choisissez de désactiver le contournement multimédia, le chemin multimédia est routé par le biais du serveur de médiation.



</div>

</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

