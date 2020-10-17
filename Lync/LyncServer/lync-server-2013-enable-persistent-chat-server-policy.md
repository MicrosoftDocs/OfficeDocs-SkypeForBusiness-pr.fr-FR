---
title: 'Lync Server 2013 : activation de la stratégie de serveur de conversation permanente'
description: 'Lync Server 2013 : activation de la stratégie de serveur de conversation permanente.'
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
ms.openlocfilehash: e58da577679795f00492af72b43ca72106d40f4f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547880"
---
# <a name="enable-persistent-chat-server-policy-in-lync-server-2013"></a>Activer la stratégie de serveur de conversation permanente dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-06_

Dans le panneau de configuration Lync Server 2013, vous pouvez utiliser la page **stratégie de conversation permanente** du groupe de **conversation permanente** pour gérer les stratégies au niveau global, du pool, du site ou de l’utilisateur, y compris la configuration de la stratégie globale par défaut et la création d’une ou de plusieurs stratégies d’utilisateur et de site supplémentaires pour votre déploiement. Si un utilisateur est activé pour le serveur de conversation permanente par stratégie, l’environnement de serveur de conversation permanente apparaît dans le client Lync 2013.

<div>


> [!NOTE]  
> Dans la topologie, les stratégies de site de serveur de conversation permanente s’appliquent globalement, par pool d’utilisateur, par site d’utilisateur ou par utilisateur.



</div>

La stratégie globale est créée automatiquement lorsque vous déployez le serveur de conversation permanente, et elle peut être configurée, mais pas supprimée. La stratégie globale s’appliquant à tous les utilisateurs, il n’est pas obligatoire de la définir par utilisateur.

Vous pouvez créer et configurer plusieurs stratégies de site et utilisateur qui, avec la stratégie globale, permettent aux utilisateurs de disposer d’un serveur de conversation permanente. Les stratégies de serveur de conversation permanente de pool et de site remplacent la stratégie de serveur de conversation permanente globale, mais uniquement pour les utilisateurs de ce site. Les stratégies utilisateur supplantent les stratégies utilisateur, de pool et globales pour les utilisateurs auxquels la stratégie utilisateur est assignée.

<div>


> [!NOTE]  
> Pour configurer et utiliser le serveur de conversation permanente, vous devez d’abord utiliser le générateur de topologie pour ajouter la prise en charge du serveur de conversation permanente à la topologie, puis publier la topologie. Pour plus d’informations, reportez-vous à la rubrique <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Ajout d’un serveur de conversation permanente à votre déploiement dans Lync Server 2013</A> dans la documentation de déploiement.



</div>

<div>

## <a name="in-this-section"></a>Dans cette section

  - [Configurer la stratégie globale pour la conversation permanente dans Lync Server 2013](lync-server-2013-configure-the-global-policy-for-persistent-chat.md)

  - [Créer une stratégie de site pour la conversation permanente dans Lync Server 2013](lync-server-2013-create-a-site-policy-for-persistent-chat.md)

  - [Créer une stratégie utilisateur pour la conversation permanente dans Lync Server 2013](lync-server-2013-create-a-user-policy-for-persistent-chat.md)

  - [Appliquer une stratégie de conversation permanente à un utilisateur ou un groupe d’utilisateurs dans Lync Server 2013](lync-server-2013-apply-a-persistent-chat-policy-to-a-user-or-user-group.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

