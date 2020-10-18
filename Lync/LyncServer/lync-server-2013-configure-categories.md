---
title: 'Lync Server 2013 : configuration des catégories'
description: 'Lync Server 2013 : configuration des catégories.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure categories
ms:assetid: 4547f514-f0c0-404d-890f-092ddeeac852
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204859(v=OCS.15)
ms:contentKeyID: 48184033
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1342ea0f5ee32284a32ac0dcc8ab3d370bb1dd91
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578134"
---
# <a name="configure-categories-in-lync-server-2013"></a><span data-ttu-id="17b9b-103">Configurer des catégories dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="17b9b-103">Configure categories in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="17b9b-104">_**Dernière modification de la rubrique :** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="17b9b-104">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="17b9b-105">Dans le panneau de configuration Lync Server 2013, vous pouvez utiliser la section **catégorie** de la page **conversation permanente** pour configurer des catégories.</span><span class="sxs-lookup"><span data-stu-id="17b9b-105">In Lync Server 2013 Control Panel, you can use the **Category** section of the **Persistent Chat** page to configure categories.</span></span> <span data-ttu-id="17b9b-106">Une catégorie de salle de conversation permanente est une structure logique pour l’Organisation des salles de conversation.</span><span class="sxs-lookup"><span data-stu-id="17b9b-106">A Persistent Chat room category is a logical structure for organizing chat rooms.</span></span> <span data-ttu-id="17b9b-107">Une catégorie définit un ensemble par défaut de listes de contrôle d’accès pour le contrôle des utilisateurs et groupes d’utilisateurs autorisés à créer ou rejoindre les salles de conversation.</span><span class="sxs-lookup"><span data-stu-id="17b9b-107">A category defines a default set of access control lists (ACLs) for controlling the users and user groups who may create or join the chat rooms.</span></span> <span data-ttu-id="17b9b-108">Vous pouvez utiliser des catégories pour appliquer des limites éthiques entre différentes subdivisions au sein de leurs organisations.</span><span class="sxs-lookup"><span data-stu-id="17b9b-108">You can use categories enforce ethical walls between different subdivisions within their organizations.</span></span>

<span data-ttu-id="17b9b-109">Les catégories de salle de conversation peuvent contenir des salles de conversation, mais pas d’autres catégories.</span><span class="sxs-lookup"><span data-stu-id="17b9b-109">Chat room categories may contain chat rooms, but not other categories.</span></span> <span data-ttu-id="17b9b-110">Chaque catégorie décrit son contenu avec des métadonnées, telles que le nom et la description.</span><span class="sxs-lookup"><span data-stu-id="17b9b-110">Each category describes its contents with metadata, such as Name and Description.</span></span> <span data-ttu-id="17b9b-111">De plus, la catégorie possède des propriétés qui peuvent être définies pour contrôler le comportement des salles de conversation qui lui appartiennent, par exemple si les salles de conversation autorisent les invitations ou les téléchargements de fichiers, ou si elles contiennent l’historique de conversation.</span><span class="sxs-lookup"><span data-stu-id="17b9b-111">In addition, the category has properties which can be set to control the behavior of the chat rooms belonging to it, such as if the chat rooms allow Invitations or File Uploads, or contain Chat History.</span></span>

<div>

## <a name="to-configure-categories-for-chat-rooms"></a><span data-ttu-id="17b9b-112">Pour configurer les catégories des salles de conversation</span><span class="sxs-lookup"><span data-stu-id="17b9b-112">To configure categories for chat rooms</span></span>

1.  <span data-ttu-id="17b9b-113">À partir d’un compte auquel le rôle CsPersistentChatAdministrator ou CsAdministrator est assigné, connectez-vous à n’importe quel ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="17b9b-113">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="17b9b-114">Dans le menu **Démarrer** , sélectionnez le panneau de configuration Lync Server ou ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration.</span><span class="sxs-lookup"><span data-stu-id="17b9b-114">From the **Start** menu, select the Lync Server Control Panel or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="17b9b-115">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration Lync Server, voir [Open Lync server 2013 administrative Tools](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="17b9b-115">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="17b9b-116">Vous pouvez également utiliser des applets de commande Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="17b9b-116">You can also use Windows PowerShell cmdlets.</span></span> <span data-ttu-id="17b9b-117">Pour plus d’informations, reportez-vous à la rubrique <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring persistent Chat Server by Using Windows PowerShell Cmdlets</A> dans la documentation de déploiement.</span><span class="sxs-lookup"><span data-stu-id="17b9b-117">For details, see <A href="configuring-persistent-chat-server-by-using-windows-powershell-cmdlets.md">Configuring Persistent Chat Server by using Windows PowerShell cmdlets</A> in the Deployment documentation.</span></span>

    
    </div>

3.  <span data-ttu-id="17b9b-118">Dans la barre de navigation de gauche, cliquez sur **Conversation permanente**, puis sur **Catégorie**.</span><span class="sxs-lookup"><span data-stu-id="17b9b-118">In the left navigation bar, click **Persistent Chat**, and then click **Category**.</span></span>
    
    <span data-ttu-id="17b9b-119">Pour plusieurs déploiements de pool de serveurs de conversation permanente, sélectionnez le pool approprié dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="17b9b-119">For multiple Persistent Chat Server pool deployments, select the appropriate pool from the drop-down list.</span></span>

4.  <span data-ttu-id="17b9b-120">Dans la page **Catégorie**, cliquez sur **Nouvelle** ou **Modifier**.</span><span class="sxs-lookup"><span data-stu-id="17b9b-120">On the **Category** page, click **New** or **Edit**.</span></span>

5.  <span data-ttu-id="17b9b-121">Dans **Sélectionner un service**, sélectionnez le service correspondant au pool de serveurs de conversation permanente sur lequel la catégorie doit être créée.</span><span class="sxs-lookup"><span data-stu-id="17b9b-121">In **Select a Service**, select the service corresponding to the Persistent Chat Server pool on which the category needs to be created.</span></span> <span data-ttu-id="17b9b-122">Le service est le pool de serveurs de conversation permanente utilisé par la conversation permanente (client) pour identifier le pool auquel la catégorie appartient.</span><span class="sxs-lookup"><span data-stu-id="17b9b-122">The service is the Persistent Chat Server pool that the Persistent Chat (client) uses to identify which pool the category belongs to.</span></span> <span data-ttu-id="17b9b-123">Une catégorie ne peut appartenir qu’à un seul pool de serveurs de conversation permanente et ne peut pas être déplacée vers une autre, ni partagée avec un autre pool.</span><span class="sxs-lookup"><span data-stu-id="17b9b-123">A category can belong to only one Persistent Chat Server pool, and cannot be moved to another one, or shared with another pool.</span></span>

6.  <span data-ttu-id="17b9b-124">Dans **Nouvelle catégorie**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="17b9b-124">In **New Category**, do the following:</span></span>
    
    1.  <span data-ttu-id="17b9b-125">Dans **Nom**, spécifiez un nom pour la nouvelle catégorie de salle.</span><span class="sxs-lookup"><span data-stu-id="17b9b-125">In **Name**, specify a name for the new room category.</span></span>
    
    2.  <span data-ttu-id="17b9b-126">Dans **Description**, fournissez une description détaillée de la catégorie de salle (exemple : catégorie de salle pour Contoso).</span><span class="sxs-lookup"><span data-stu-id="17b9b-126">In **Description**, provide a detailed description for the room category (for example, a room category for Contoso).</span></span>
    
    3.  <span data-ttu-id="17b9b-127">Pour contrôler si les invitations peuvent être activées pour les salles de conversation appartenant à cette catégorie, activez ou désactivez la case à cocher **activer les invitations** .</span><span class="sxs-lookup"><span data-stu-id="17b9b-127">To control whether invitations can be enabled for chat rooms that belong to this category, select or clear the **Enable invitations** check box.</span></span> <span data-ttu-id="17b9b-128">Si cette option est sélectionnée, les salles de cette catégorie peuvent avoir des invitations. Si ce n’est pas le cas, les salles de cette catégorie ne sont pas autorisées à avoir des invitations.</span><span class="sxs-lookup"><span data-stu-id="17b9b-128">If selected, rooms in this category may have invitations on or off; if cleared, the rooms in this category are not allowed to have invitations.</span></span> <span data-ttu-id="17b9b-129">Si une salle comporte des invitations, lorsqu’un nouveau membre est ajouté à une salle, il obtient une notification de la nouvelle salle dans son client de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="17b9b-129">If a room has invitations on, when a new member is added to a room, he or she gets a notification of the new room in their Persistent Chat client.</span></span>
    
    4.  <span data-ttu-id="17b9b-p107">Pour contrôler les téléchargements de fichiers dans les salles de conversation appartenant à cette catégorie, activez ou désactivez la case à cocher **Activer le téléchargement de fichiers**. Si la case à cocher est activée, les salles de cette catégorie peuvent activer ou désactiver les téléchargements de fichiers. Si la case à cocher est désactivée, les salles de cette catégorie ne sont pas autorisées à activer les téléchargements de fichiers.</span><span class="sxs-lookup"><span data-stu-id="17b9b-p107">To control file uploads in chat rooms belonging to this category, select or clear the **Enable file upload** check box. If selected, the rooms of this category can enable or disable file uploads; if cleared, the rooms of this category are not allowed to have file uploads.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <span data-ttu-id="17b9b-132">Ce paramètre est appliqué sur le serveur car les applications personnalisées ou les clients de conversation de groupe précédents qui utilisent le serveur de conversation de groupe Office Communications Server 2007 R2 &nbsp; ou Lync server 2010 peuvent publier des fichiers dans une salle.</span><span class="sxs-lookup"><span data-stu-id="17b9b-132">This setting is enforced on the server because custom applications or previous Group Chat clients that use Office Communications Server 2007 R2&nbsp;Group Chat Server or Lync Server 2010, Group Chat can post files to a room.</span></span> <span data-ttu-id="17b9b-133">Le client Lync 2013 ne dispose pas de la fonctionnalité de chargement/téléchargement de fichiers, de sorte que si vous avez un déploiement Lync 2013 pur ou un client Lync 2013, il n’est pas possible de publier des fichiers dans une salle de conversation de serveur de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="17b9b-133">The Lync 2013 client does not have file upload/download capability, so if you have a pure Lync 2013 deployment or Lync 2013 client, it is not possible to post files in a Persistent Chat Server chat room.</span></span>

        
        </div>
    
    5.  <span data-ttu-id="17b9b-134">Pour contrôler l’historique de la conversation, activez ou désactivez la case à cocher **activer l’historique** de la conversation.</span><span class="sxs-lookup"><span data-stu-id="17b9b-134">To control chat history, select or clear the **Enable chat history** check box.</span></span> <span data-ttu-id="17b9b-135">Si la case à cocher est activée, les conversations des salles deviennent permanentes ; sinon, les messages des conversations ne sont pas conservés.</span><span class="sxs-lookup"><span data-stu-id="17b9b-135">If selected, room chats become persistent; otherwise, chat messages are not persisted.</span></span> <span data-ttu-id="17b9b-136">Si la conformité est activée, les conversations des salles sont enregistrées à des fins de conformité mais les utilisateurs ne peuvent pas accéder aux anciens messages.</span><span class="sxs-lookup"><span data-stu-id="17b9b-136">If compliance is enabled, room chats will be saved in compliance, but users will not be able to access older messages.</span></span> <span data-ttu-id="17b9b-137">Cette option peut être utilisée pour les salles destinées aux collaborations en temps réel, ad hoc, qui n’ont pas besoin d’un historique des conversations permanent.</span><span class="sxs-lookup"><span data-stu-id="17b9b-137">This option can be used for rooms designated for real-time, ad hoc collaborations that don’t need chat history to be persisted.</span></span>

7.  <span data-ttu-id="17b9b-138">Dans **Modifier la catégorie**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="17b9b-138">In **Edit Category**, do the following:</span></span>
    
      - <span data-ttu-id="17b9b-139">Dans **appartenance**, dans la section **membres autorisés** , ajoutez ou supprimez des utilisateurs et d’autres principaux des services de domaine Active Directory (utilisateurs, groupes de distribution, unités d’organisation, etc.) autorisés à être ajoutés en tant que membres des salles de conversation appartenant à la catégorie.</span><span class="sxs-lookup"><span data-stu-id="17b9b-139">In **Membership**, in the **Allowed members** section, add or remove users and other Active Directory Domain Services principals (users, distribution groups, organizational units, and so on) that are permitted to be added as members of chat rooms belonging to the category.</span></span> <span data-ttu-id="17b9b-140">Les principaux autorisés par une catégorie peuvent rechercher les salles dans la catégorie (à moins que la salle ne soit masquée ; dans ce cas, seuls les membres de la salle peuvent la rechercher dans l’annuaire).</span><span class="sxs-lookup"><span data-stu-id="17b9b-140">Principals permitted by a category can search for the rooms in the category (unless the room is hidden, in which case only members of the room can search for it in the directory).</span></span>
    
      - <span data-ttu-id="17b9b-141">Dans **appartenance**, dans la section **membres refusés** , ajoutez ou supprimez des utilisateurs et d’autres principaux Active Directory associés à des membres refusés de la salle.</span><span class="sxs-lookup"><span data-stu-id="17b9b-141">In **Membership**, in the **Denied members** section, add or remove users and other Active Directory principals associated with members being denied from the room.</span></span>
    
      - <span data-ttu-id="17b9b-142">Dans **appartenance**, dans la section **créateurs** , ajoutez ou supprimez des utilisateurs et d’autres principaux Active Directory associés aux créateurs de la catégorie.</span><span class="sxs-lookup"><span data-stu-id="17b9b-142">In **Membership**, in the **Creators** section, add or remove users and other Active Directory principals associated with creators for the category.</span></span> <span data-ttu-id="17b9b-143">Un créateur est un utilisateur qui dispose des autorisations nécessaires pour créer des salles de conversation et leur attribuer des gestionnaires et des membres.</span><span class="sxs-lookup"><span data-stu-id="17b9b-143">A creator is a user who has permissions to create chat rooms and assign chat room managers and members.</span></span>

8.  <span data-ttu-id="17b9b-144">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="17b9b-144">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

