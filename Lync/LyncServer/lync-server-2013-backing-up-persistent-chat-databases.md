---
title: 'Lync Server 2013 : sauvegarde des bases de données de conversation permanente'
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
ms.openlocfilehash: 98d4d69a09ad58d4578c0636f7e6bce54497cb9d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044966"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backing-up-persistent-chat-databases-in-lync-server-2013"></a>Sauvegarde de bases de données de conversation permanente dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-17_

Le contenu de la salle de conversation permanente est stocké dans la base de données de conversation permanente (MGC. mdf). Il s’agit de données stratégiques qui doivent être sauvegardées régulièrement. Outre le contenu de la salle de conversation, la base de données de conversation permanente stocke également des informations sur les principaux (par exemple, les utilisateurs et les groupes d’utilisateurs), ainsi que sur les rôles et l’accès dont ils disposent aux salles de conversation et à la salle de conversation.

Il existe deux manières de sauvegarder les données de conversation permanente.

  - Sauvegarde SQL Server

  - L' `Export-CsPersistentChatData` applet de commande, qui exporte les données de conversation permanente en tant que fichier

Les données créées à l’aide de la sauvegarde SQL Server nécessitent beaucoup plus d’espace disque, parfois 20 fois plus, que `Export-CsPersistentChatData`celles créées par, mais la sauvegarde SQL Server est plus susceptible d’être une procédure que les administrateurs connaissent.

</div>

<span> </span>

</div>

</div>

</div>

