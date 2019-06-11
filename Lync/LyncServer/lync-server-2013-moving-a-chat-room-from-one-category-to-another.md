---
title: 'Lync Server 2013 : Déplacement d’une salle de conversation d’une catégorie vers une autre'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Moving a chat room from one category to another
ms:assetid: 7e93b8f6-5a18-4476-a432-3918e01bcfa6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ215877(v=OCS.15)
ms:contentKeyID: 48706004
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c61d20ff1de7437054df36af224293dcdcb61d54
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826548"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="moving-a-chat-room-from-one-category-to-another-in-lync-server-2013"></a>Déplacement d’une salle de conversation d’une catégorie vers une autre dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-11-01_

Nous vous recommandons de ne pas modifier la catégorie d’une salle de conversation permanente après la création de la salle de conversation. Toutefois, si le gestionnaire de la salle de conversation dispose de privilèges de **création** dans une autre catégorie, il peut déplacer la salle d’une catégorie vers une autre. La salle n’est pas supprimée et recréée. Seule son association dans la base de données est modifiée.

Le changement de catégorie d’une salle de conversation doit être rarement réalisé. Une catégorie détermine l’appartenance autorisée pour la salle de conversation, donc si une salle de conversation est déplacée vers une autre catégorie, toutes les listes de contrôle d’accès système (SACL) qui ne sont plus prises en charge par la nouvelle catégorie sont vidées. Par exemple, si un utilisateur était membre de la salle et n’est plus **AllowedMember** dans la nouvelle catégorie, l’appartenance à la salle sera modifiée et l’utilisateur sera supprimé de la salle.

Pour plus d’informations sur le déplacement d’une salle de conversation à l’aide de l’interface de ligne de commande Windows PowerShell, reportez-vous à la section «gestion des salles» dans [configuration du serveur de chat permanent à l’aide des cmdlets Windows PowerShell](configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md).

Pour plus d’informations sur la configuration des salles de conversation, voir [configurer des salles dans Lync Server 2013](lync-server-2013-configure-rooms.md) dans la documentation de déploiement.

</div>

<span> </span>

</div>

</div>

</div>

