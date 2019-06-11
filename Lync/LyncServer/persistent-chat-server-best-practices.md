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

# <a name="persistent-chat-server-best-practices"></a><span data-ttu-id="909bf-102">Meilleures pratiques liées au serveur de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="909bf-102">Persistent Chat Server best practices</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="909bf-103">_**Dernière modification de la rubrique:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="909bf-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="909bf-104">Lorsque vous créez des catégories et des salles de conversation permanente et que vous concevez votre étendue et votre appartenance, les conseils suivants peuvent vous aider à planifier:</span><span class="sxs-lookup"><span data-stu-id="909bf-104">As you create your categories and Persistent Chat rooms and design your scoping and membership, the following tips can help your planning:</span></span>

  - <span data-ttu-id="909bf-105">Si votre entreprise n’a pas besoin d’une paroi éthique, n’Affinez pas l’étendue dans votre arborescence de catégories.</span><span class="sxs-lookup"><span data-stu-id="909bf-105">If your company does not require an ethical wall, do not narrow the scope in your category tree.</span></span> <span data-ttu-id="909bf-106">Placez tous vos utilisateurs dans l’étendue d’une catégorie et créez toutes les salles de conversation dans cette catégorie.</span><span class="sxs-lookup"><span data-stu-id="909bf-106">Put all your users in the scope of one category, and create all chat rooms in that category.</span></span> <span data-ttu-id="909bf-107">Par la suite, utilisez uniquement les listes d’appartenance pour octroyer ou restreindre l’accès à chaque salle de conversation.</span><span class="sxs-lookup"><span data-stu-id="909bf-107">Subsequently, use only membership lists to grant or restrict access to each chat room.</span></span>

  - <span data-ttu-id="909bf-108">Dans la plupart des cas, vous devez permettre aux utilisateurs de créer des salles de conversation pour que les discussions relatives aux nouvelles rubriques puissent être démarrées à tout moment.</span><span class="sxs-lookup"><span data-stu-id="909bf-108">In most cases, you should enable users to create new chat rooms so that discussions about new topics can be started any time.</span></span> <span data-ttu-id="909bf-109">Pour cela, vous devez créer la liste de **créateurs** comme la liste **AllowedMembers** .</span><span class="sxs-lookup"><span data-stu-id="909bf-109">Do this by making the **Creators** list the same as the **AllowedMembers** list.</span></span> <span data-ttu-id="909bf-110">Toutefois, si vous voulez autoriser uniquement une équipe de support centrale ou des utilisateurs spécifiques à créer des salles, faites de la liste des **créateurs** en tant que sous-ensemble approprié.</span><span class="sxs-lookup"><span data-stu-id="909bf-110">However, if you want to allow only a central support team or designated users to create rooms, then make the **Creators** list as the appropriate subset.</span></span>

  - <span data-ttu-id="909bf-111">Donnez à chaque salle de conversation un nom complet et une description qui décrivent l’endroit où il s’inscrit à votre organisation.</span><span class="sxs-lookup"><span data-stu-id="909bf-111">Give each chat room a complete name and description summary that describes where it fits in with your organization.</span></span> <span data-ttu-id="909bf-112">Dans la mesure où les utilisateurs ne peuvent pas voir le nom de la catégorie lorsqu’ils utilisent la salle de conversation, vous ne pouvez pas compter sur le nom de la catégorie pour permettre aux utilisateurs de déterminer le Forum de discussion prévu pour la salle de conversation.</span><span class="sxs-lookup"><span data-stu-id="909bf-112">Because users cannot see the category name when they use the chat room, you cannot rely on the category name to help users determine the intended discussion forum for the chat room.</span></span>

  - <span data-ttu-id="909bf-113">Vous pouvez avoir besoin d’un flux de travail de création de salle personnalisé si vous disposez de certaines conventions d’affectation de noms ou de contrôles Access ou de validations à implémenter.</span><span class="sxs-lookup"><span data-stu-id="909bf-113">You may want to have a custom room creation workflow if you have certain naming conventions or other access controls or validations to implement.</span></span> <span data-ttu-id="909bf-114">La configuration de chat permanent vous permet de personnaliser le **RoomManagementUrl** sur un nom que vous avez hébergé.</span><span class="sxs-lookup"><span data-stu-id="909bf-114">The Persistent Chat configuration enables you to customize the **RoomManagementUrl** to something that you host.</span></span> <span data-ttu-id="909bf-115">Par exemple, quand un utilisateur clique sur **créer une salle** dans son client Lync, il peut être redirigé vers votre solution personnalisée.</span><span class="sxs-lookup"><span data-stu-id="909bf-115">For example, when users click **Create a room** in their Lync client, they can be redirected to your custom solution.</span></span>

  - <span data-ttu-id="909bf-116">Créez divers compléments qui vous permettent d’améliorer l’exploitation des salles de conversation en ajoutant d’autres données métiers dans des salles de conversation.</span><span class="sxs-lookup"><span data-stu-id="909bf-116">Create a variety of add-ins that help to enhance the experience of chat rooms by bringing in other business data into chat rooms.</span></span> <span data-ttu-id="909bf-117">Les administrateurs doivent inscrire les compléments qu’ils souhaitent autoriser dans le système.</span><span class="sxs-lookup"><span data-stu-id="909bf-117">Administrators must register the add-ins that they want to allow in the system.</span></span> <span data-ttu-id="909bf-118">Les gestionnaires de salle de conversation et les créateurs peuvent choisir dans la liste des compléments autorisés pour les composants les plus pertinents pour leurs salles respectives.</span><span class="sxs-lookup"><span data-stu-id="909bf-118">Chat room managers and creators can choose from the list of allowed add-ins for the ones most relevant to their respective rooms.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="909bf-119">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="909bf-119">See Also</span></span>


[<span data-ttu-id="909bf-120">Gestion des catégories, des salles et des compléments dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="909bf-120">Managing categories, rooms, and add-ins in Lync Server 2013</span></span>](lync-server-2013-managing-categories-rooms-and-add-ins.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

