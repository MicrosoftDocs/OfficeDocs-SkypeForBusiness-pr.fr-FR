---
title: 'Lync Server 2013 : restauration des données de conversation permanente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring Persistent Chat data
ms:assetid: c251a7fa-50da-434b-b39a-17f5978ce736
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945649(v=OCS.15)
ms:contentKeyID: 51541516
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 78d43cedaec50adac895b143a3643a6a1a1a8a48
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050366"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-persistent-chat-data-in-lync-server-2013"></a>Restauration des données de conversation permanente dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-18_

Le contenu de la salle de conversation permanente est stocké dans la base de données de conversation permanente (MGC. mdf). Il s’agit de données stratégiques qui doivent être sauvegardées régulièrement. En plus du contenu de la salle de conversation, les principaux (tels que les utilisateurs et les groupes), ainsi que les rôles et l’accès dont ils disposent aux salles de conversation et au contenu de la salle de conversation, sont également stockés dans la base de données de conversation permanente.

La manière dont vous restaurez vos données de conversation permanente dépend de la méthode que vous avez utilisée pour la sauvegarder.

  - Si vous avez utilisé les procédures de sauvegarde SQL Server, vous devez utiliser les procédures de restauration SQL Server.

  - Si vous avez utilisé l’applet de commande **Export-applet cspersistentchatdata** pour sauvegarder les données de conversation permanente, vous devez utiliser l’applet de commande **Import-applet cspersistentchatdata** pour restaurer les données.

</div>

<span> </span>

</div>

</div>

</div>

