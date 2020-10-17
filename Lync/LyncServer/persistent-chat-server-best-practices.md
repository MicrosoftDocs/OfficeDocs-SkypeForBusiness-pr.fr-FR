---
title: Meilleures pratiques pour le serveur de conversation permanente
description: Meilleures pratiques en matière de serveur de conversation permanente.
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
ms.openlocfilehash: 5c575c0afa0366e88748eadfcf4c04fccb20b375
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571260"
---
# <a name="persistent-chat-server-best-practices"></a>Meilleures pratiques pour le serveur de conversation permanente

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2012-10-06_

Lors de la création des catégories et des salles de conversation permanente et de la conception de votre étendue et de votre appartenance, les conseils suivants peuvent vous aider dans votre planification :

  - Si votre société ne requiert pas la mise en place d’une séparation déontologique, ne limitez pas l’étendue dans l’arborescence de votre catégorie. Mettez tous vos utilisateurs dans l’étendue d’une catégorie et créez toutes les salles de conversation dans cette catégorie. Ensuite, utilisez uniquement des listes d’appartenance pour accorder ou restreindre l’accès à chaque salle de conversation.

  - Dans la plupart des cas, vous devez permettre aux utilisateurs de créer des salles de conversation afin de pouvoir démarrer des discussions sur de nouveaux sujets à tout moment. Pour cela, vous devez rendre la liste **Creators** identique à la liste **AllowedMembers**. Cependant, pour autoriser uniquement une équipe de support centrale ou des utilisateurs désignés à créer des salles, vous devez définir la liste **Creators** comme sous-ensemble approprié.

  - Donnez un nom complet et une synthèse de description à chaque salle de conversation. Ces derniers permettent une identification claire avec votre organisation. Étant donné que les utilisateurs ne peuvent pas voir le nom de la catégorie lorsqu’ils utilisent la salle de conversation, vous ne pouvez pas compter dessus pour aider les utilisateurs à déterminer le forum de discussion prévu pour la salle de conversation.

  - Vous pouvez appliquer un flux de travail de création de salle personnalisé si vous utilisez certaines conventions d’affectation de noms ou d’autres contrôles d’accès ou validations à mettre en œuvre. La configuration de la conversation permanente vous permet de personnaliser le **RoomManagementUrl** sur un événement que vous hébergez. Par exemple, lorsque les utilisateurs cliquent sur **créer une salle** dans leur client Lync, ils peuvent être redirigés vers votre solution personnalisée.

  - Vous pouvez créer divers compléments qui permettent d’améliorer l’expérience des salles de conversation en y apportant d’autres données métier. Les administrateurs doivent inscrire les compléments qu’ils veulent autoriser dans le système. Les responsables et créateurs de salle de conversation peuvent choisir dans la liste des compléments autorisés ceux qui sont adaptés à leurs salles respectives.

<div>

## <a name="see-also"></a>Voir aussi


[Gestion des catégories, des salles et des compléments dans Lync Server 2013](lync-server-2013-managing-categories-rooms-and-add-ins.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

