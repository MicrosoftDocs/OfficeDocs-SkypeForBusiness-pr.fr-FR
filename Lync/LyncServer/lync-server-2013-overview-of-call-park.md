---
title: 'Lync Server 2013 : vue d’ensemble du parcage d’appel'
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
ms.openlocfilehash: 1624042b07bc024d837e55ffac402cb2f158922f
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42216362"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-call-park-in-lync-server-2013"></a>Vue d’ensemble du parcage d’appel dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-29_

L’application de parcage d’appel Lync Server 2013 permet aux utilisateurs de voix entreprise d’effectuer l’une des opérations suivantes :

  - Mettre un appel en attente, puis récupérer l’appel depuis le même téléphone ou un autre téléphone.

  - Mettre un appel en attente pour le transférer vers un service ou une zone générale (par exemple, vers un service commercial ou un entrepôt où il y a un téléphone de partie commune).

  - Mettre un appel en attente et conserver le téléphone d’origine gratuitement pour les autres appels.

Lorsqu’un utilisateur héberge un appel, Lync Server transfère l’appel vers un numéro temporaire, appelé *orbite*, où l’appel est conservé jusqu’à ce qu’il soit récupéré ou qu’il arrive à expiration. Lync Server envoie l’orbite à l’utilisateur qui a parqué l’appel. Pour récupérer l’appel parqué, l’utilisateur peut composer le numéro d’orbite ou cliquer sur le lien ou le bouton d’orbite dans la fenêtre de conversation.

L’utilisateur qui a parqué un appel peut informer quelqu’un pour qu’il récupère l’appel à l’aide d’un mécanisme externe, tel que la messagerie instantanée ou un système de radiomessagerie, pour communiquer le numéro d’orbite à une autre personne. L’utilisateur qui a parqué l’appel peut laisser la fenêtre de conversation ouverte pour recevoir une notification lorsque l’appel est récupéré.

Étant donné que les plages d’orbites sont globalement uniques, il est possible de récupérer des appels à partir de n’importe quel site ou téléphone PBX de Lync Server si le routage est correctement configuré. Si personne ne récupère l’appel dans un intervalle de temps configurable, l’appel sonne à la personne qui l’a parqué. Si cette personne ne répond pas au rappel, l’appel est transféré vers une destination de secours, telle qu’un opérateur, si elle est configurée. Vous pouvez configurer le nombre de sonneries de l’appel avant de le transférer d’une à dix fois. Si personne ne répond à un appel transféré, l’appel est déconnecté. L’orbite est libérée lors de l’extraction ou de la déconnexion de l’appel.

Lorsque vous déployez le parcage d’appel, vous devez réserver des plages de numéros de poste pour les appels de parking. Ces extensions doivent être des extensions virtuelles : les extensions auxquelles aucun utilisateur ou téléphone n’est affecté. Vous configurez ensuite la table d’orbites de parcage d’appel avec les plages de numéros d’extension et spécifiez quel service d’application héberge l’application de parcage d’appel qui gère chaque plage. Chaque pool frontal a une table de parcage d’appel sur le serveur principal correspondant qui est utilisé pour gérer les appels parqués sur le pool. La liste des plages d’orbites est stockée dans le magasin central de gestion et est utilisée pour acheminer les orbites vers le pool de destination. Chaque pool Lync Server où l’application de parcage d’appel est déployée et configurée peut avoir une ou plusieurs plages d’orbites. Les plages d’orbites doivent être uniques au niveau global dans le déploiement Lync Server.

Vous configurez également d’autres paramètres de parcage d’appel, tels que l’endroit où les appels sont redirigés s’ils expirent et si la personne sur le téléphone entend la musique quand elle est parqué. Vous pouvez également spécifier le fichier audio à lire pendant l’attente de l’appel.

<div>


> [!NOTE]  
> Les fichiers de mise en attente musicale personnalisés pour le parcage d’appel ne sont pas sauvegardés dans le cadre du processus de récupération d’urgence Lync Server 2013 et seront perdus si les fichiers chargés dans le pool sont endommagés, endommagés ou effacés. Conservez toujours une copie de sauvegarde distincte des fichiers de conservation musicaux personnalisés que vous avez téléchargés pour le parcage d’appel.



</div>

L’application de parcage d’appel est un composant de voix entreprise. Lorsque vous déployez voix entreprise, l’application de parcage d’appel est installée et activée automatiquement. Avant de pouvoir utiliser le parcage d’appel, l’administrateur de voix entreprise doit toutefois le configurer et l’activer pour les utilisateurs par le biais de la stratégie de voix.

</div>

<span> </span>

</div>

</div>

</div>

