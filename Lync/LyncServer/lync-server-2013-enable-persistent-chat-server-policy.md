---
title: 'Lync Server 2013 : Activation d’une stratégie de serveur de conversation permanente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Persistent Chat Server policy
ms:assetid: 87063d6c-2e38-4970-b76d-2aa15f0de29e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205056(v=OCS.15)
ms:contentKeyID: 48184718
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 27d87277c813c24ae36de14430bc711d991d7181
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735984"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-persistent-chat-server-policy-in-lync-server-2013"></a>Activation d’une stratégie de serveur de conversation permanente dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-06_

Dans le panneau de configuration de Lync Server 2013, vous pouvez utiliser la page de **stratégie de chat permanent** du groupe de **conversation permanente** pour gérer les stratégies au niveau global, de pool, de site ou d’utilisateur, y compris la configuration de la stratégie globale par défaut et la création d’une ou plusieurs stratégies d’utilisateur et de site supplémentaires pour votre déploiement. Si un utilisateur est activé pour le serveur Chat permanent par stratégie, l’environnement serveur Chat permanent apparaît dans le client Lync 2013.

<div>


> [!NOTE]  
> Dans la topologie, les stratégies de site serveur de chat permanent s’appliquent globalement, le pool de chaque utilisateur, le site de chaque utilisateur ou par utilisateur.



</div>

La stratégie globale est créée automatiquement lorsque vous déployez le serveur Chat permanent et qu’elle peut être configurée, mais pas supprimée. Comme la stratégie globale s’appliquent à tous les utilisateurs, il n’est pas obligatoire de la définir par utilisateur.

Vous pouvez créer et configurer plusieurs stratégies de site et utilisateurs qui, conjointement avec la stratégie globale, permettent aux utilisateurs de chat permanent. Les stratégies de serveur de chat permanent de pool et de site remplacent la stratégie de serveur de chat permanent global, mais uniquement pour les utilisateurs de ce site. Les stratégies utilisateur remplacent les stratégies utilisateur, de pool et globales pour les utilisateurs auxquels la stratégie utilisateur est affectée.

<div>


> [!NOTE]  
> Pour configurer et utiliser le serveur de chat permanent, vous devez d’abord utiliser le générateur de topologie pour ajouter la prise en charge du serveur de chat permanent à la topologie, puis publier la topologie. Pour plus d’informations, reportez-vous à la rubrique <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Ajouter un serveur Chat permanent à votre déploiement dans Lync Server 2013</A> dans la documentation de déploiement.



</div>

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Configuration de la stratégie globale pour la conversation permanente dans Lync Server 2013](lync-server-2013-configure-the-global-policy-for-persistent-chat.md)

  - [Création d’une stratégie de site pour la conversation permanente dans Lync Server 2013](lync-server-2013-create-a-site-policy-for-persistent-chat.md)

  - [Création d’une stratégie utilisateur pour la conversation permanente dans Lync Server 2013](lync-server-2013-create-a-user-policy-for-persistent-chat.md)

  - [Application d’une stratégie de conversation permanente à un utilisateur ou à un groupe d’utilisateurs dans Lync Server 2013](lync-server-2013-apply-a-persistent-chat-policy-to-a-user-or-user-group.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

