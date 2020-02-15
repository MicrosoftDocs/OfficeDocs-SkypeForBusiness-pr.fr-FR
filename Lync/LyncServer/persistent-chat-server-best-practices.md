---
title: Meilleures pratiques pour le serveur de conversation permanente
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Persistent Chat Server best practices
ms:assetid: dc18e7f7-599b-4d32-abf7-cd9e691426a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398970(v=OCS.15)
ms:contentKeyID: 48185612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 10790495f38a469218e00f6906cad589f96c57e5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034454"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="persistent-chat-server-best-practices"></a><span data-ttu-id="fad68-102">Meilleures pratiques pour le serveur de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="fad68-102">Persistent Chat Server best practices</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fad68-103">_**Dernière modification de la rubrique :** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="fad68-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="fad68-104">Lors de la création des catégories et des salles de conversation permanente et de la conception de votre étendue et de votre appartenance, les conseils suivants peuvent vous aider dans votre planification :</span><span class="sxs-lookup"><span data-stu-id="fad68-104">As you create your categories and Persistent Chat rooms and design your scoping and membership, the following tips can help your planning:</span></span>

  - <span data-ttu-id="fad68-p101">Si votre société ne requiert pas la mise en place d’une séparation déontologique, ne limitez pas l’étendue dans l’arborescence de votre catégorie. Mettez tous vos utilisateurs dans l’étendue d’une catégorie et créez toutes les salles de conversation dans cette catégorie. Ensuite, utilisez uniquement des listes d’appartenance pour accorder ou restreindre l’accès à chaque salle de conversation.</span><span class="sxs-lookup"><span data-stu-id="fad68-p101">If your company does not require an ethical wall, do not narrow the scope in your category tree. Put all your users in the scope of one category, and create all chat rooms in that category. Subsequently, use only membership lists to grant or restrict access to each chat room.</span></span>

  - <span data-ttu-id="fad68-p102">Dans la plupart des cas, vous devez permettre aux utilisateurs de créer des salles de conversation afin de pouvoir démarrer des discussions sur de nouveaux sujets à tout moment. Pour cela, vous devez rendre la liste **Creators** identique à la liste **AllowedMembers**. Cependant, pour autoriser uniquement une équipe de support centrale ou des utilisateurs désignés à créer des salles, vous devez définir la liste **Creators** comme sous-ensemble approprié.</span><span class="sxs-lookup"><span data-stu-id="fad68-p102">In most cases, you should enable users to create new chat rooms so that discussions about new topics can be started any time. Do this by making the **Creators** list the same as the **AllowedMembers** list. However, if you want to allow only a central support team or designated users to create rooms, then make the **Creators** list as the appropriate subset.</span></span>

  - <span data-ttu-id="fad68-p103">Donnez un nom complet et une synthèse de description à chaque salle de conversation. Ces derniers permettent une identification claire avec votre organisation. Étant donné que les utilisateurs ne peuvent pas voir le nom de la catégorie lorsqu’ils utilisent la salle de conversation, vous ne pouvez pas compter dessus pour aider les utilisateurs à déterminer le forum de discussion prévu pour la salle de conversation.</span><span class="sxs-lookup"><span data-stu-id="fad68-p103">Give each chat room a complete name and description summary that describes where it fits in with your organization. Because users cannot see the category name when they use the chat room, you cannot rely on the category name to help users determine the intended discussion forum for the chat room.</span></span>

  - <span data-ttu-id="fad68-113">Vous pouvez appliquer un flux de travail de création de salle personnalisé si vous utilisez certaines conventions d’affectation de noms ou d’autres contrôles d’accès ou validations à mettre en œuvre.</span><span class="sxs-lookup"><span data-stu-id="fad68-113">You may want to have a custom room creation workflow if you have certain naming conventions or other access controls or validations to implement.</span></span> <span data-ttu-id="fad68-114">La configuration de la conversation permanente vous permet de personnaliser le **RoomManagementUrl** sur un événement que vous hébergez.</span><span class="sxs-lookup"><span data-stu-id="fad68-114">The Persistent Chat configuration enables you to customize the **RoomManagementUrl** to something that you host.</span></span> <span data-ttu-id="fad68-115">Par exemple, lorsque les utilisateurs cliquent sur **créer une salle** dans leur client Lync, ils peuvent être redirigés vers votre solution personnalisée.</span><span class="sxs-lookup"><span data-stu-id="fad68-115">For example, when users click **Create a room** in their Lync client, they can be redirected to your custom solution.</span></span>

  - <span data-ttu-id="fad68-p105">Vous pouvez créer divers compléments qui permettent d’améliorer l’expérience des salles de conversation en y apportant d’autres données métier. Les administrateurs doivent inscrire les compléments qu’ils veulent autoriser dans le système. Les responsables et créateurs de salle de conversation peuvent choisir dans la liste des compléments autorisés ceux qui sont adaptés à leurs salles respectives.</span><span class="sxs-lookup"><span data-stu-id="fad68-p105">Create a variety of add-ins that help to enhance the experience of chat rooms by bringing in other business data into chat rooms. Administrators must register the add-ins that they want to allow in the system. Chat room managers and creators can choose from the list of allowed add-ins for the ones most relevant to their respective rooms.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="fad68-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="fad68-119">See Also</span></span>


[<span data-ttu-id="fad68-120">Gestion des catégories, des salles et des compléments dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fad68-120">Managing categories, rooms, and add-ins in Lync Server 2013</span></span>](lync-server-2013-managing-categories-rooms-and-add-ins.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

