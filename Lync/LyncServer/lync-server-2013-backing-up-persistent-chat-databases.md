---
title: 'Lync Server 2013 : sauvegarde des bases de données de conversation permanente'
description: 'Lync Server 2013 : sauvegarde des bases de données de conversation permanente.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backing up Persistent Chat databases
ms:assetid: b99ebdc0-a025-44d7-9d74-37a7365f330d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945646(v=OCS.15)
ms:contentKeyID: 51541507
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9885eaf0065f5b558922c056fb1f669a5b821460
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563290"
---
# <a name="backing-up-persistent-chat-databases-in-lync-server-2013"></a>Sauvegarde de bases de données de conversation permanente dans Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-17_

Le contenu de la salle de conversation permanente est stocké dans la base de données de conversation permanente (MGC. mdf). Il s’agit de données stratégiques qui doivent être sauvegardées régulièrement. Outre le contenu de la salle de conversation, la base de données de conversation permanente stocke également des informations sur les principaux (par exemple, les utilisateurs et les groupes d’utilisateurs), ainsi que sur les rôles et l’accès dont ils disposent aux salles de conversation et à la salle de conversation.

Il existe deux manières de sauvegarder les données de conversation permanente.

  - Sauvegarde SQL Server

  - L' `Export-CsPersistentChatData` applet de commande, qui exporte les données de conversation permanente en tant que fichier

Les données créées à l’aide de la sauvegarde SQL Server nécessitent beaucoup plus d’espace disque, parfois 20 fois plus, que celles créées par `Export-CsPersistentChatData` , mais la sauvegarde SQL Server est plus susceptible d’être une procédure que les administrateurs connaissent.

</div>

<span> </span>

</div>

</div>

</div>

