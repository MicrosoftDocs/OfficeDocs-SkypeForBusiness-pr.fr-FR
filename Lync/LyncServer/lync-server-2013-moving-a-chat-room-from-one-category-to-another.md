---
title: 'Lync Server 2013 : transfert d’une salle de conversation d’une catégorie à une autre'
description: 'Lync Server 2013 : transfert d’une salle de conversation d’une catégorie à une autre.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Moving a chat room from one category to another
ms:assetid: 7e93b8f6-5a18-4476-a432-3918e01bcfa6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215877(v=OCS.15)
ms:contentKeyID: 48706004
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4066732a90a94414b55d6a567fde0d496e4faf13
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48541998"
---
# <a name="moving-a-chat-room-from-one-category-to-another-in-lync-server-2013"></a>Migration d’une salle de conversation d’une catégorie vers une autre dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-11-01_

Nous vous recommandons de ne pas modifier la catégorie d’une salle de conversation permanente une fois la salle de conversation créée. Cependant, si le gestionnaire de la salle de conversation à des privilèges **Créateur** dans une autre catégorie, il peut déplacer la salle d’une catégorie à une autre. La salle n’est pas supprimée et recréée. Seule son association dans la base de données est modifiée.

La modification d’une catégorie de salle de conversation est très rare. Une catégorie détermine l’appartenance autorisée pour la salle de conversation, donc si une salle de conversation est déplacée vers une autre catégorie, toutes les listes de contrôle d’accès système (SACLs) qui ne sont plus prises en charge par la nouvelle catégorie sont vidées. Par exemple, si un utilisateur était membre de la salle et qu’il n’est plus un **AllowedMember** dans la nouvelle catégorie, l’appartenance de la salle sera modifiée et l’utilisateur sera supprimé de la salle.

Pour plus d’informations sur le transfert d’une salle de conversation à l’aide de l’interface de ligne de commande Windows PowerShell, voir « gestion des salles » dans [Configuring persistent Chat Server by Using Windows PowerShell Cmdlets](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).

Pour plus d’informations sur la configuration des salles de conversation, voir [configure rooms in Lync Server 2013](lync-server-2013-configure-rooms.md) dans la documentation de déploiement.

</div>

<span> </span>

</div>

</div>

</div>

