---
title: Meilleures pratiques pour le serveur de conversation permanente
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Persistent Chat Server best practices
ms:assetid: dc18e7f7-599b-4d32-abf7-cd9e691426a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398970(v=OCS.15)
ms:contentKeyID: 48185612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ebe9742b76ec6abfd7b7407f38edda937bdf6ecc
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751196"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="persistent-chat-server-best-practices"></a>Meilleures pratiques pour le serveur de conversation permanente

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-06_

Lors de la création des catégories et des salles de conversation permanente et de la conception de votre étendue et de votre appartenance, les conseils suivants peuvent vous aider dans votre planification :

  - If your company does not require an ethical wall, do not narrow the scope in your category tree. Put all your users in the scope of one category, and create all chat rooms in that category. Subsequently, use only membership lists to grant or restrict access to each chat room.

  - In most cases, you should enable users to create new chat rooms so that discussions about new topics can be started any time. Do this by making the **Creators** list the same as the **AllowedMembers** list. However, if you want to allow only a central support team or designated users to create rooms, then make the **Creators** list as the appropriate subset.

  - Give each chat room a complete name and description summary that describes where it fits in with your organization. Because users cannot see the category name when they use the chat room, you cannot rely on the category name to help users determine the intended discussion forum for the chat room.

  - Vous pouvez appliquer un flux de travail de création de salle personnalisé si vous utilisez certaines conventions d’affectation de noms ou d’autres contrôles d’accès ou validations à mettre en œuvre. La configuration de la conversation permanente vous permet de personnaliser le **RoomManagementUrl** sur un événement que vous hébergez. Par exemple, lorsque les utilisateurs cliquent sur **créer une salle** dans leur client Lync, ils peuvent être redirigés vers votre solution personnalisée.

  - Create a variety of add-ins that help to enhance the experience of chat rooms by bringing in other business data into chat rooms. Administrators must register the add-ins that they want to allow in the system. Chat room managers and creators can choose from the list of allowed add-ins for the ones most relevant to their respective rooms.

<div>

## <a name="see-also"></a>Voir aussi


[Gestion des catégories, des salles et des compléments dans Lync Server 2013](lync-server-2013-managing-categories-rooms-and-add-ins.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

