---
title: 'Lync Server 2013 : vue d’ensemble du parc d’appels'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Call Park
ms:assetid: 985dc326-0aef-4308-b98b-c1d0069311e7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205124(v=OCS.15)
ms:contentKeyID: 48184939
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c5deeff873b37c0056bf03c598c39e448cba4379
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755588"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-call-park-in-lync-server-2013"></a>Présentation du parc d’appels dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-29_

L’application de parc d’appels de Lync Server 2013 permet aux utilisateurs voix entreprise de procéder de l’une des façons suivantes :

  - mettre un appel en attente, puis récupérer l’appel depuis le même téléphone ou un autre téléphone ;

  - mettre un appel en attente pour le transférer vers un service ou une zone générale (par exemple, vers un service commercial ou un entrepôt où il y a un téléphone de partie commune) ;

  - mettre un appel en attente et garder le téléphone d’origine libre pour répondre aux autres appels.

Lorsqu’un utilisateur travaille sur un appel, Lync Server transfère l’appel vers un numéro temporaire, appelé *orbite*, où l’appel est maintenu jusqu’à ce qu’il soit récupéré ou qu’il arrive à expiration. Lync Server envoie l’orbite à l’utilisateur qui a parqué l’appel. Pour récupérer l’appel parqué, l’utilisateur peut composer le numéro de l’orbite ou cliquer sur le lien ou le bouton d’orbite dans la fenêtre de conversation.

L’utilisateur qui a parqué un appel peut avertir quelqu’un pour récupérer l’appel en ayant recours à un mécanisme externe, tel qu’un système de messagerie instantanée ou de radiomessagerie, pour communiquer le numéro d’orbite à quelqu’un d’autre. L’utilisateur qui a parqué l’appel peut laisser la fenêtre de conversation ouverte pour recevoir une notification quand l’appel est récupéré.

Étant donné que les plages d’orbites sont globalement uniques, il est possible de récupérer les appels à partir d’un site ou d’un téléphone PBX du serveur Lync si le routage est configuré de manière appropriée. Si personne ne récupère l’appel dans un délai configurable, la personne qui l’a parqué est rappelée. Si cette personne ne répond pas au rappel, l’appel est transféré vers une destination de remplacement, telle qu’un opérateur, si la configuration est définie de la sorte. Vous pouvez configurer le nombre de sonneries de rappel avant le transfert, de une à dix. Si personne ne répond à un appel transféré, l’appel est déconnecté. L’orbite est libérée lorsque l’appel est récupéré ou déconnecté.

Quand vous déployez le parcage d’appel, vous devez réserver des plages de numéros d’extension pour le parcage des appels. Il doit s’agir d’extensions virtuelles, c’est-à-dire d’extensions auxquelles aucun utilisateur ou téléphone n’est attribué. Vous configurez ensuite la table d’orbites de parcage d’appel avec les plages de numéros d’extension, puis spécifiez quel service d’application héberge l’application de parcage d’appel qui gère chaque plage. Chaque pool frontal possède une table de parc d’appels sur le serveur principal correspondant qui est utilisé pour gérer les appels qui sont emparking sur le pool. La liste des plages d’orbites qui est stockée dans le magasin central de gestion est utilisée pour diriger les orbites vers le pool de destination. Chaque pool de serveurs Lync dans lequel l’application de parc d’appels est déployée et configurée peut avoir une ou plusieurs plages d’orbite. Les plages orbites doivent être globalement uniques dans le déploiement de Lync Server.

Vous configurez également d’autres paramètres de parcage d’appel, tels que l’endroit où sont redirigés les appels s’ils arrivent à expiration et si la personne en ligne entend de la musique lorsque son appel est parqué. Vous pouvez aussi spécifier le fichier de musique à lire lorsque l’appel est en attente.

<div>


> [!NOTE]  
> Les fichiers de conservation de musique personnalisés pour le parc d’appels ne sont pas sauvegardés dans le cadre du processus de reprise après sinistre de Lync Server 2013 et seront perdus si les fichiers téléchargés sur le pool sont endommagés, endommagés ou supprimés. Veillez à toujours conserver une copie de sauvegarde distincte des fichiers de mise en attente musicale personnalisés que vous avez téléchargés pour le parcage d’appel.



</div>

The Call Park application is a component of Enterprise Voice. Lorsque vous déployez Enterprise Voice, l’application de parc d’appels est installée et activée automatiquement. Pour que vous puissiez utiliser le parc d’appels, vous devez toutefois le configurer et l’activer pour les utilisateurs via la stratégie vocale.

</div>

<span> </span>

</div>

</div>

</div>

