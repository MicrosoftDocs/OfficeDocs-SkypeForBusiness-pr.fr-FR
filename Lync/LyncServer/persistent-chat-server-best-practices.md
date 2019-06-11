---
title: Meilleures pratiques liées au serveur de conversation permanente
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Persistent Chat Server best practices
ms:assetid: dc18e7f7-599b-4d32-abf7-cd9e691426a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398970(v=OCS.15)
ms:contentKeyID: 48185612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3ac9419485212df8ecf0a11841a6eaee4c752640
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34846116"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="persistent-chat-server-best-practices"></a>Meilleures pratiques liées au serveur de conversation permanente

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2012-10-06_

Lorsque vous créez des catégories et des salles de conversation permanente et que vous concevez votre étendue et votre appartenance, les conseils suivants peuvent vous aider à planifier:

  - Si votre entreprise n’a pas besoin d’une paroi éthique, n’Affinez pas l’étendue dans votre arborescence de catégories. Placez tous vos utilisateurs dans l’étendue d’une catégorie et créez toutes les salles de conversation dans cette catégorie. Par la suite, utilisez uniquement les listes d’appartenance pour octroyer ou restreindre l’accès à chaque salle de conversation.

  - Dans la plupart des cas, vous devez permettre aux utilisateurs de créer des salles de conversation pour que les discussions relatives aux nouvelles rubriques puissent être démarrées à tout moment. Pour cela, vous devez créer la liste de **créateurs** comme la liste **AllowedMembers** . Toutefois, si vous voulez autoriser uniquement une équipe de support centrale ou des utilisateurs spécifiques à créer des salles, faites de la liste des **créateurs** en tant que sous-ensemble approprié.

  - Donnez à chaque salle de conversation un nom complet et une description qui décrivent l’endroit où il s’inscrit à votre organisation. Dans la mesure où les utilisateurs ne peuvent pas voir le nom de la catégorie lorsqu’ils utilisent la salle de conversation, vous ne pouvez pas compter sur le nom de la catégorie pour permettre aux utilisateurs de déterminer le Forum de discussion prévu pour la salle de conversation.

  - Vous pouvez avoir besoin d’un flux de travail de création de salle personnalisé si vous disposez de certaines conventions d’affectation de noms ou de contrôles Access ou de validations à implémenter. La configuration de chat permanent vous permet de personnaliser le **RoomManagementUrl** sur un nom que vous avez hébergé. Par exemple, quand un utilisateur clique sur **créer une salle** dans son client Lync, il peut être redirigé vers votre solution personnalisée.

  - Créez divers compléments qui vous permettent d’améliorer l’exploitation des salles de conversation en ajoutant d’autres données métiers dans des salles de conversation. Les administrateurs doivent inscrire les compléments qu’ils souhaitent autoriser dans le système. Les gestionnaires de salle de conversation et les créateurs peuvent choisir dans la liste des compléments autorisés pour les composants les plus pertinents pour leurs salles respectives.

<div>

## <a name="see-also"></a>Voir aussi


[Gestion des catégories, des salles et des compléments dans Lync Server 2013](lync-server-2013-managing-categories-rooms-and-add-ins.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

