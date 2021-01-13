---
title: Gestion des salles de conversation dans le serveur de conversation permanente dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 7b2e1302-280c-4efe-9ec8-787687b414da
description: 'Résumé : Découvrez comment gérer les salles de conversation du serveur de conversation permanente dans Skype Entreprise Server 2015.'
ms.openlocfilehash: 2b1b2e3bdc3411a4bacae5f1dc81b626abb92a91
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815104"
---
# <a name="manage-chat-rooms-in-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="6632c-103">Gestion des salles de conversation dans le serveur de conversation permanente dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="6632c-103">Manage chat rooms in Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="6632c-104">**Résumé :** Découvrez comment gérer les salles de conversation du serveur de conversation permanente dans Skype Entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="6632c-104">**Summary:** Learn how to manage Persistent Chat Server chat rooms in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="6632c-105">La création et la gestion des salles de conversation sont beaucoup plus faciles avec l’utilisation correcte des catégories.</span><span class="sxs-lookup"><span data-stu-id="6632c-105">Creating and managing chat rooms is much easier with the correct use of categories.</span></span> <span data-ttu-id="6632c-106">Une catégorie définit qui peut créer ou rejoindre les salles de conversation.</span><span class="sxs-lookup"><span data-stu-id="6632c-106">A category defines who can create or join the chat rooms.</span></span> <span data-ttu-id="6632c-107">Avant d’essayer de gérer les salles de conversation, veillez à lire les catégories de conversation permanente, les salles de conversation et les rôles d’utilisateur dans Skype Entreprise [Server 2015](../../plan-your-deployment/persistent-chat-server/categories-chat-rooms-and-user-roles.md) et à gérer les catégories dans le serveur de conversation permanente dans Skype Entreprise [Server 2015.](categories.md)</span><span class="sxs-lookup"><span data-stu-id="6632c-107">Before you attempt to manage chat rooms, be sure to read [Persistent chat categories, chat rooms, and user roles in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/categories-chat-rooms-and-user-roles.md) and [Manage categories in Persistent Chat Server in Skype for Business Server 2015](categories.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="6632c-108">La conversation permanente est disponible dans Skype Entreprise Server 2015, mais n’est plus prise en charge dans Skype Entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="6632c-108">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="6632c-109">La même fonctionnalité est disponible dans Teams.</span><span class="sxs-lookup"><span data-stu-id="6632c-109">The same functionality is available in Teams.</span></span> <span data-ttu-id="6632c-110">Pour plus d’informations, voir [La mise à niveau de Microsoft Teams.](/microsoftteams/upgrade-start-here)</span><span class="sxs-lookup"><span data-stu-id="6632c-110">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="6632c-111">Si vous devez utiliser la conversation permanente, vous pouvez migrer les utilisateurs nécessitant cette fonctionnalité vers Teams ou continuer à utiliser Skype Entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="6632c-111">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

<span data-ttu-id="6632c-112">Vous pouvez configurer et gérer des salles de conversation à l’aide de l’interface de ligne de commande Windows PowerShell ou à l’aide du client Skype Entreprise si vous êtes membre de la salle de conversation.</span><span class="sxs-lookup"><span data-stu-id="6632c-112">You can configure and manage chat rooms by using the Windows PowerShell command-line interface, or by using the Skype for Business client if you are a member of the chat room.</span></span> <span data-ttu-id="6632c-113">Cette rubrique décrit comment gérer les salles de conversation à l’aide de l Windows PowerShell interface de ligne de commande.</span><span class="sxs-lookup"><span data-stu-id="6632c-113">This topic describes how to manage chat rooms by using the Windows PowerShell command-line interface.</span></span> <span data-ttu-id="6632c-114">Si vous souhaitez gérer des salles de conversation à l’aide du client Skype Entreprise, consultez l’aide du client.</span><span class="sxs-lookup"><span data-stu-id="6632c-114">If you want to manage chat rooms by using the Skype for Business client, see the client help.</span></span> 
  
<span data-ttu-id="6632c-115">Les salles de conversation peuvent être de deux types : Normal et Auditorium.</span><span class="sxs-lookup"><span data-stu-id="6632c-115">Chat rooms can be one of two types: Normal and Auditorium.</span></span> <span data-ttu-id="6632c-116">Une salle de conversation normale permet à tous les membres de publier et de lire des messages.</span><span class="sxs-lookup"><span data-stu-id="6632c-116">A Normal chat room allows all members to post and read messages.</span></span> <span data-ttu-id="6632c-117">Un auditorium est un type de salle de conversation dans laquelle seuls les présentateurs peuvent publier, mais où tout le monde peut lire.</span><span class="sxs-lookup"><span data-stu-id="6632c-117">An Auditorium is a type of chat room where only Presenters can post, but everyone can read.</span></span>
  
<span data-ttu-id="6632c-118">Les personnes qui peuvent accéder aux salles de conversation et les gérer dépendent des rôles des utilisateurs comme suit :</span><span class="sxs-lookup"><span data-stu-id="6632c-118">Who can access and manage chat rooms depends on user roles as follows:</span></span>
  
- <span data-ttu-id="6632c-119">Les utilisateurs doivent être membres d’une salle de conversation pour pouvoir publier et lire des messages.</span><span class="sxs-lookup"><span data-stu-id="6632c-119">Users must be Members of a chat room to be able to post and read messages.</span></span>
    
- <span data-ttu-id="6632c-120">Les présentateurs sont autorisés à publier dans les salles auditorium.</span><span class="sxs-lookup"><span data-stu-id="6632c-120">Presenters are allowed to post to Auditorium rooms.</span></span>
    
- <span data-ttu-id="6632c-121">Les administrateurs peuvent supprimer du contenu précédant, par exemple du contenu publié avant une certaine date, d’une salle de conversation afin que la base de données ne devienne pas ingérable de part sa taille.</span><span class="sxs-lookup"><span data-stu-id="6632c-121">Administrators can delete earlier content (for example, content that was posted before a certain date) from any chat room to keep the database from growing too large.</span></span> <span data-ttu-id="6632c-122">Les administrateurs peuvent également supprimer ou remplacer des messages qui sont considérés inappropriés pour une salle de conversation particulière.</span><span class="sxs-lookup"><span data-stu-id="6632c-122">Administrators can also remove or replace messages that are considered inappropriate for a particular chat room.</span></span>
    
- <span data-ttu-id="6632c-123">Les utilisateurs finaux, y compris les auteurs de messages, ne peuvent pas supprimer du contenu de salle de conversation.</span><span class="sxs-lookup"><span data-stu-id="6632c-123">End users, including message authors, cannot delete content from any chat room.</span></span>
    
- <span data-ttu-id="6632c-124">Les responsables de salles de conversation peuvent apporter des modifications à toutes les propriétés de la salle de conversation, y compris la désactivation des salles.</span><span class="sxs-lookup"><span data-stu-id="6632c-124">Chat room Managers can make changes to all chat room properties, including disabling rooms.</span></span> <span data-ttu-id="6632c-125">Les responsables ne peuvent toutefois pas supprimer une salle ou modifier la catégorie d’une salle.</span><span class="sxs-lookup"><span data-stu-id="6632c-125">Managers cannot, however, delete a room, or change the category of a room.</span></span> 
    
- <span data-ttu-id="6632c-126">Seuls les administrateurs peuvent supprimer une salle de conversation après sa création.</span><span class="sxs-lookup"><span data-stu-id="6632c-126">Only Administrators can delete a chat room after it has been created.</span></span>
    
<span data-ttu-id="6632c-127">Vous pouvez configurer et gérer des salles de conversation à l’aide des cmdlets Windows PowerShell suivantes :</span><span class="sxs-lookup"><span data-stu-id="6632c-127">You can configure and manage chat rooms by using the following Windows PowerShell cmdlets:</span></span>
  

|<span data-ttu-id="6632c-128">**Applet de commande**</span><span class="sxs-lookup"><span data-stu-id="6632c-128">**Cmdlet**</span></span>|<span data-ttu-id="6632c-129">**Description**</span><span class="sxs-lookup"><span data-stu-id="6632c-129">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="6632c-130">New-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="6632c-130">New-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="6632c-131">Créer une salle de conversation</span><span class="sxs-lookup"><span data-stu-id="6632c-131">Create a new chat room</span></span>  <br/> |
|<span data-ttu-id="6632c-132">Set-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="6632c-132">Set-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="6632c-133">Configurer les paramètres d’une salle existante ; affecter des utilisateurs et des groupes d’utilisateurs à la salle</span><span class="sxs-lookup"><span data-stu-id="6632c-133">Configure settings for an existing room; assign users and user groups to the room</span></span>  <br/> |
|<span data-ttu-id="6632c-134">Get-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="6632c-134">Get-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="6632c-135">Récupérer des informations sur les salles</span><span class="sxs-lookup"><span data-stu-id="6632c-135">Retrieve information about rooms</span></span>  <br/> |
|<span data-ttu-id="6632c-136">Clear-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="6632c-136">Clear-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="6632c-137">Effacer une salle ou des messages d’une salle</span><span class="sxs-lookup"><span data-stu-id="6632c-137">Clear a room or messages from a room</span></span>  <br/> |
|<span data-ttu-id="6632c-138">Remove-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="6632c-138">Remove-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="6632c-139">Supprimer une salle</span><span class="sxs-lookup"><span data-stu-id="6632c-139">Remove a room</span></span>  <br/> |
|<span data-ttu-id="6632c-140">Remove-CsPersistentChatMessage</span><span class="sxs-lookup"><span data-stu-id="6632c-140">Remove-CsPersistentChatMessage</span></span>  <br/> |<span data-ttu-id="6632c-141">Supprimer des messages d’une salle</span><span class="sxs-lookup"><span data-stu-id="6632c-141">Remove messages from a room</span></span>  <br/> |
   
<span data-ttu-id="6632c-142">Vous utilisez l’cmdlet **New-CsPersistentChatRoom** pour créer des salles de conversation et l’cmdlet **Set-CsPersistentChatRoom** pour configurer une salle de conversation existante, y compris l’ajout d’utilisateurs à la salle de conversation.</span><span class="sxs-lookup"><span data-stu-id="6632c-142">You use the **New-CsPersistentChatRoom** cmdlet to create chat rooms and the **Set-CsPersistentChatRoom** cmdlet to configure an existing chat room, including adding users to the chat room.</span></span> <span data-ttu-id="6632c-143">Vous pouvez configurer les paramètres suivants pour les salles de conversation :</span><span class="sxs-lookup"><span data-stu-id="6632c-143">You can configure the following parameters for chat rooms:</span></span>
  
- <span data-ttu-id="6632c-144">Désactivé.</span><span class="sxs-lookup"><span data-stu-id="6632c-144">Disabled.</span></span> <span data-ttu-id="6632c-145">Permet de désactiver ou d’activer une salle de conversation.</span><span class="sxs-lookup"><span data-stu-id="6632c-145">Lets you disable or enable a chat room.</span></span> 
    
- <span data-ttu-id="6632c-146">Invitations.</span><span class="sxs-lookup"><span data-stu-id="6632c-146">Invitations.</span></span> <span data-ttu-id="6632c-147">Permet d’activer ou de désactiver les invitations aux salles de conversation, qui sont utilisées pour informer les utilisateurs lorsqu’ils ont été ajoutés en tant que membres de la salle de conversation.</span><span class="sxs-lookup"><span data-stu-id="6632c-147">Lets you enable or disable chat room invitations, which are used to notify users when they have been added as chat room members.</span></span> <span data-ttu-id="6632c-148">Le paramètre par défaut pour les invitations dans hérite, ce qui a entraîné l’adoption par la salle de conversation du paramètre d’invitation configuré sur la catégorie à laquelle elle appartient.</span><span class="sxs-lookup"><span data-stu-id="6632c-148">The default setting for invitations in inherit, which caused the chat room to adopt the invitation setting configured on the category it belongs to.</span></span> <span data-ttu-id="6632c-149">La configuration du paramètre d’invitations sur False au niveau de la salle de conversation permet de faire en place le paramètre de catégorie.</span><span class="sxs-lookup"><span data-stu-id="6632c-149">Configuring the invitations setting to false at the chat room level allows the category setting to be overridden.</span></span> 
    
- <span data-ttu-id="6632c-150">Confidentialité.</span><span class="sxs-lookup"><span data-stu-id="6632c-150">Privacy.</span></span> <span data-ttu-id="6632c-151">Permet de spécifier si une salle de conversation est ouverte, fermée ou secrète.</span><span class="sxs-lookup"><span data-stu-id="6632c-151">Lets you specify whether a chat room is Open, Closed, or Secret.</span></span> <span data-ttu-id="6632c-152">Les salles ouvertes peuvent être recherchés et accessibles par tout le monde.</span><span class="sxs-lookup"><span data-stu-id="6632c-152">Open rooms can be searched and accessed by anyone.</span></span> <span data-ttu-id="6632c-153">Les salles fermées peuvent être recherchés par n’importe qui, mais sont accessibles uniquement par les membres.</span><span class="sxs-lookup"><span data-stu-id="6632c-153">Closed rooms can be searched by anyone, but can be accessed only by members.</span></span> <span data-ttu-id="6632c-154">Les salles secrètes ne sont accessibles qu’aux membres de la salle.</span><span class="sxs-lookup"><span data-stu-id="6632c-154">Secret rooms can be searched and accessed only by members of the room.</span></span> <span data-ttu-id="6632c-155">Par défaut, chaque nouvelle salle est initialement configurée comme fermée.</span><span class="sxs-lookup"><span data-stu-id="6632c-155">By default, each new room is initially configured as Closed.</span></span>
    
- <span data-ttu-id="6632c-156">Type.</span><span class="sxs-lookup"><span data-stu-id="6632c-156">Type.</span></span> <span data-ttu-id="6632c-157">Permet de spécifier si une salle de conversation est une salle normale, qui accepte les messages publiés par un membre, ou une salle auditorium, qui accepte les messages publiés uniquement par un présentateur.</span><span class="sxs-lookup"><span data-stu-id="6632c-157">Lets you specify whether a chat room is a Normal room, which accepts messages posted by any member, or an Auditorium room, which accepts messages posted only by a Presenter.</span></span>
    
- <span data-ttu-id="6632c-158">Addin.</span><span class="sxs-lookup"><span data-stu-id="6632c-158">Addin.</span></span> <span data-ttu-id="6632c-159">Permet d’associer un add-in précédemment configuré à une salle de conversation, ce qui permet aux membres d’afficher le contenu de l’URL tout en participant.</span><span class="sxs-lookup"><span data-stu-id="6632c-159">Lets you associate a previously configured add-in with a chat room, which allows URL content to be viewed by members while participating.</span></span>
    
<span data-ttu-id="6632c-160">Outre les paramètres ci-dessus, l’cmdlet **Set-CsPersistentChatRoom** vous permet d’affecter des utilisateurs à la salle de conversation comme suit :</span><span class="sxs-lookup"><span data-stu-id="6632c-160">In addition to the above parameters, the **Set-CsPersistentChatRoom** cmdlet lets you assign users to the chat room as follows:</span></span>
  
- <span data-ttu-id="6632c-161">Membres.</span><span class="sxs-lookup"><span data-stu-id="6632c-161">Members.</span></span> <span data-ttu-id="6632c-162">Configure l’appartenance à la salle de conversation.</span><span class="sxs-lookup"><span data-stu-id="6632c-162">Configures membership for the chat room.</span></span> <span data-ttu-id="6632c-163">Vous pouvez ajouter ou supprimer un ou plusieurs membres à l’aide d’une seule cmdlet en spécifiant l’adresse SIP des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="6632c-163">You can add or remove either the individual or multiple members using a single cmdlet by specifying the SIP address of the users.</span></span> <span data-ttu-id="6632c-164">Pour autoriser l’ajout en bloc d’utilisateurs, vous pouvez également spécifier des unités d’organisation ou des groupes de distribution Active Directory.</span><span class="sxs-lookup"><span data-stu-id="6632c-164">To allow users to be added in bulk, Active Directory organizational units or distribution groups can also be specified.</span></span>
    
- <span data-ttu-id="6632c-165">Responsables.</span><span class="sxs-lookup"><span data-stu-id="6632c-165">Managers.</span></span> <span data-ttu-id="6632c-166">Permet d’affecter des responsables à la salle de conversation.</span><span class="sxs-lookup"><span data-stu-id="6632c-166">Lets you assign managers to the chat room.</span></span> <span data-ttu-id="6632c-167">Les responsables ont les autorisations pour définir l’appartenance à une salle de conversation avec d’autres paramètres.</span><span class="sxs-lookup"><span data-stu-id="6632c-167">Managers have the permissions to define membership of a chat room along with other settings.</span></span>
    
- <span data-ttu-id="6632c-168">Présentateurs.</span><span class="sxs-lookup"><span data-stu-id="6632c-168">Presenters.</span></span> <span data-ttu-id="6632c-169">Permet d’affecter des présentateurs à une salle de conversation auditorium.</span><span class="sxs-lookup"><span data-stu-id="6632c-169">Lets you assign presenters to an Auditorium chat room.</span></span> 
    
  <span data-ttu-id="6632c-170">Pour plus d’informations sur la syntaxe, y compris tous les paramètres, voir [Skype Entreprise Server 2015 Management Shell](../management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="6632c-170">For details about syntax, including all parameters, see [Skype for Business Server 2015 Management Shell](../management-shell.md).</span></span>
  
## <a name="create-a-new-room"></a><span data-ttu-id="6632c-171">Créer une salle</span><span class="sxs-lookup"><span data-stu-id="6632c-171">Create a new room</span></span>

<span data-ttu-id="6632c-172">Vous pouvez créer une salle à l’aide de l’cmdlet **New-CsPersistentChatRoom.**</span><span class="sxs-lookup"><span data-stu-id="6632c-172">You can create a new room by using the **New-CsPersistentChatRoom** cmdlet.</span></span> <span data-ttu-id="6632c-173">Par exemple, la commande suivante crée une salle de conversation nommée ITChatRoom sur le pool atl-cs-001.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="6632c-173">For example, the following command creates a new chat room named ITChatRoom on the pool atl-cs-001.contoso.com.</span></span> <span data-ttu-id="6632c-174">Dans cet exemple, la salle de conversation est ajoutée à la catégorie IT :</span><span class="sxs-lookup"><span data-stu-id="6632c-174">In this example, the chat room is added to the IT category:</span></span>
  
```PowerShell
New-CsPersistentChatRoom -Name "ITChatRoom" -PersistentChatPoolFqdn "atl-cs-001.contoso.com"-Category "IT"
```

<span data-ttu-id="6632c-175">**Remarque :** PersistentChatPoolFqdn n’est pas nécessaire si l’une des valeurs suivantes est vraie :</span><span class="sxs-lookup"><span data-stu-id="6632c-175">**Note:** PersistentChatPoolFqdn is not needed if one of the following is true:</span></span> 
  
- <span data-ttu-id="6632c-176">Il n’existe qu’un seul pool de serveurs de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="6632c-176">There is only one Persistent Chat Server pool.</span></span>
    
- <span data-ttu-id="6632c-177">Vous fournissez un nom de domaine complet (FQDN) de pool à la catégorie.</span><span class="sxs-lookup"><span data-stu-id="6632c-177">You provide a pool FQDN to the category.</span></span>
    
- <span data-ttu-id="6632c-178">Vous fournissez un nom de domaine complet (FQDN) à l’ajout de la salle.</span><span class="sxs-lookup"><span data-stu-id="6632c-178">You provide a pool FQDN to adding the room.</span></span>
    
## <a name="configure-an-existing-room"></a><span data-ttu-id="6632c-179">Configurer une salle existante</span><span class="sxs-lookup"><span data-stu-id="6632c-179">Configure an existing room</span></span>

<span data-ttu-id="6632c-180">Vous pouvez configurer une salle existante à l’aide de l’cmdlet **Set-CsPersistentChatRoom.**</span><span class="sxs-lookup"><span data-stu-id="6632c-180">You can configure an existing room by using the **Set-CsPersistentChatRoom** cmdlet.</span></span> <span data-ttu-id="6632c-181">Par exemple, la commande suivante affecte user1 en tant que membre et présentateur, et user2 en tant que responsable, de la salle auditorium testCat :</span><span class="sxs-lookup"><span data-stu-id="6632c-181">For example, the following command assigns user1 as a Member and Presenter, and user2 as a Manager, of the testCat Auditorium room:</span></span>
  
```PowerShell
Set-CsPersistentChatRoom -Identity testCat -Members @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}
Set-CsPersistentChatRoom -Identity testCat -Presenters @{Add="sip:user1@contoso.com"}
Set-CsPersistentChatRoom -Identity testCat -Managers @{Add="sip:user2@contoso.com"}
```

 <span data-ttu-id="6632c-182">L’exemple suivant ajoute tous les utilisateurs de l’ou NorthAmericaUsers dans Active Directory à la salle de conversation NorthAmerica :</span><span class="sxs-lookup"><span data-stu-id="6632c-182">The next example adds all the users from the NorthAmericaUsers OU in active Directory to the NorthAmerica chat room:</span></span>
  
```PowerShell
Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.contoso.com\NorthAmerica" -Members @{Add="OU=NorthAmericaUsers,DC=contoso,DC=com"}
```

<span data-ttu-id="6632c-183">L’exemple suivant ajoute tous les membres du groupe de distribution Finance à la même salle de conversation :</span><span class="sxs-lookup"><span data-stu-id="6632c-183">The next example adds all the members from the Finance distribution group to the same chat room:</span></span>
  
```PowerShell
Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.contoso.com\NorthAmerica" -Members @{Add="CN=Finance,OU=ExternalUsers,DC=contoso,DC=com"}
```

## <a name="disable-or-enable-a-room"></a><span data-ttu-id="6632c-184">Désactiver ou activer une salle</span><span class="sxs-lookup"><span data-stu-id="6632c-184">Disable or enable a room</span></span>

<span data-ttu-id="6632c-185">Si la rubrique d’une salle de conversation permanente n’est plus pertinente, vous pouvez rendre la salle de conversation inaccessible aux utilisateurs en la désactivant.</span><span class="sxs-lookup"><span data-stu-id="6632c-185">If the topic of a Persistent Chat room is no longer relevant, you can make the chat room unavailable to users by disabling it.</span></span> <span data-ttu-id="6632c-186">Lorsqu’une salle de conversation est désactivée, tous les membres sont immédiatement déconnectés de la salle.</span><span class="sxs-lookup"><span data-stu-id="6632c-186">When a chat room is disabled, all members are immediately disconnected from the room.</span></span> <span data-ttu-id="6632c-187">Une fois une salle de conversation désactivée, les utilisateurs ne peuvent ni la rejoindre, ni la trouver lors de recherches de salles de conversation.</span><span class="sxs-lookup"><span data-stu-id="6632c-187">After a chat room is disabled, users cannot rejoin it or find it in chat room searches.</span></span>
  
<span data-ttu-id="6632c-188">Si l’historique de la salle de conversation persiste, le contenu est conservé lorsque la salle de conversation est désactivée.</span><span class="sxs-lookup"><span data-stu-id="6632c-188">If the chat room's history persists, the content is preserved when the chat room is disabled.</span></span> <span data-ttu-id="6632c-189">Toutefois, le contenu n’apparaîtra pas dans les recherches tant que la salle de conversation demeurera dans son état de désactivation.</span><span class="sxs-lookup"><span data-stu-id="6632c-189">However, that content will not appear in searches during the time that the chat room remains in a disabled state.</span></span> <span data-ttu-id="6632c-190">Si vous activez ensuite la salle de conversation, les utilisateurs peuvent alors rechercher des messages ayant été publiés avant la désactivation de la salle.</span><span class="sxs-lookup"><span data-stu-id="6632c-190">If you later enable the chat room, users can search for messages that were posted before the chat room was disabled.</span></span> <span data-ttu-id="6632c-191">Pour plus d’informations sur la configuration de l’historique des salles de conversation, voir [Manage categories in Persistent Chat Server in Skype for Business Server 2015](categories.md).</span><span class="sxs-lookup"><span data-stu-id="6632c-191">For information about configuring chat room history, see [Manage categories in Persistent Chat Server in Skype for Business Server 2015](categories.md).</span></span> 
  
<span data-ttu-id="6632c-192">Si une salle de conversation est désactivée, sa liste d’adhésion et d’autres paramètres sont conservés.</span><span class="sxs-lookup"><span data-stu-id="6632c-192">If a chat room is disabled, its membership list and other settings are preserved.</span></span> <span data-ttu-id="6632c-193">En tant qu’administrateur, vous pouvez activer une salle qui a été désactivée et vous n’avez pas besoin de créer manuellement les paramètres.</span><span class="sxs-lookup"><span data-stu-id="6632c-193">As an administrator, you can enable a room that has been disabled, and you do not need to manually re-create the settings.</span></span>
  
<span data-ttu-id="6632c-194">Vous pouvez désactiver une salle à l’aide de l’cmdlet **Set-CsPersistentChatRoom** et définir le paramètre Disabled sur True :</span><span class="sxs-lookup"><span data-stu-id="6632c-194">You can disable a room by using the **Set-CsPersistentChatRoom** cmdlet and setting the Disabled parameter to True:</span></span>
  
```PowerShell
Set-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -Disabled $True
```

<span data-ttu-id="6632c-195">Pour activer une salle de conversation, définissez le paramètre Disabled sur False :</span><span class="sxs-lookup"><span data-stu-id="6632c-195">To enable a chat room, set the Disabled parameter to False:</span></span>
  
```PowerShell
Set-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -Disabled $False
```

## <a name="get-information-about-rooms"></a><span data-ttu-id="6632c-196">Obtenir des informations sur les salles</span><span class="sxs-lookup"><span data-stu-id="6632c-196">Get information about rooms</span></span>

<span data-ttu-id="6632c-197">Pour obtenir des informations sur les salles configurées pour être utilisés dans votre organisation, vous pouvez utiliser l’cmdlet **Get-CsPersistentChatRoom.**</span><span class="sxs-lookup"><span data-stu-id="6632c-197">To get information about the rooms configured for use in your organization, you can use the **Get-CsPersistentChatRoom** cmdlet.</span></span>
  
<span data-ttu-id="6632c-198">La commande suivante retourne des informations sur toutes les salles de conversation configurées pour être utilisés dans l’organisation :</span><span class="sxs-lookup"><span data-stu-id="6632c-198">The following command returns information about all the chat rooms configured for use in the organization:</span></span>
  
```PowerShell
Get-CsPersistentChatRoom
```

## <a name="remove-all-content-from-a-room"></a><span data-ttu-id="6632c-199">Supprimer tout le contenu d’une salle</span><span class="sxs-lookup"><span data-stu-id="6632c-199">Remove all content from a room</span></span>

<span data-ttu-id="6632c-200">Vous pouvez supprimer du contenu d’une salle à l’aide de l’cmdlet **Clear-CsPersistentChatRoom.**</span><span class="sxs-lookup"><span data-stu-id="6632c-200">You can remove content from a room by using the **Clear-CsPersistentChatRoom** cmdlet.</span></span> <span data-ttu-id="6632c-201">Par exemple, la commande suivante supprime tout le contenu de la salle de conversation permanente ITChatRoom qui a été ajoutée à la salle le ou avant le 1er mars 2015 :</span><span class="sxs-lookup"><span data-stu-id="6632c-201">For example, the following command removes all the content from the Persistent Chat room ITChatRoom that was added to the room on or before March 1, 2015:</span></span>
  
```PowerShell
Clear-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -EndDate "3/1/2015"
```

## <a name="remove-a-message-from-a-room"></a><span data-ttu-id="6632c-202">Supprimer un message d’une salle</span><span class="sxs-lookup"><span data-stu-id="6632c-202">Remove a message from a room</span></span>

<span data-ttu-id="6632c-203">Vous pouvez supprimer un ou plusieurs messages dans la base de données de conversation permanente et éventuellement remplacer le message par un message par défaut ou par un message fourni par l’administrateur, à l’aide de l';cmdlet **Remove-CsPersistentChatMessage.**</span><span class="sxs-lookup"><span data-stu-id="6632c-203">You can remove one or more messages in the Persistent Chat database, and optionally replace the message with a default message or with an administrator-provided message, by using the **Remove-CsPersistentChatMessage** cmdlet.</span></span> <span data-ttu-id="6632c-204">Par exemple, la commande suivante supprime tous les messages de la salle de conversation ITChatRoom qui ont été publiés par l’utilisateur kenmyer@contoso.com :</span><span class="sxs-lookup"><span data-stu-id="6632c-204">For example, the following command removes all the messages from the ITChatRoom chat room that were posted by the user kenmyer@contoso.com:</span></span>
  
```PowerShell
Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.contoso.com\ITChatRoom" -UserUri "sip:kenmyer@contoso.com"
```

<span data-ttu-id="6632c-205">L’exemple suivant remplace tous les messages supprimés par la note que le message n’est plus disponible :</span><span class="sxs-lookup"><span data-stu-id="6632c-205">The next example replaces any removed messages with the note that the message is no longer available:</span></span>
  
```PowerShell
Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.contoso.com\ITChatRoom" -UserUri "sip:kenmyer@contoso.com" -ReplaceMessage "This message is no longer available."
```

## <a name="remove-a-room"></a><span data-ttu-id="6632c-206">Supprimer une salle</span><span class="sxs-lookup"><span data-stu-id="6632c-206">Remove a room</span></span>

<span data-ttu-id="6632c-207">Vous pouvez supprimer une salle à l’aide de l’cmdlet **Remove-CsPersistentChatRoom.**</span><span class="sxs-lookup"><span data-stu-id="6632c-207">You can remove a room by using the **Remove-CsPersistentChatRoom** cmdlet.</span></span>
  
<span data-ttu-id="6632c-208">Par exemple, la commande suivante supprime la salle de conversation RedmondChatRoom :</span><span class="sxs-lookup"><span data-stu-id="6632c-208">For example, the following command removes the chat room RedmondChatRoom:</span></span>
  
```PowerShell
Remove-CsPersistentChatRoom -Identity "atl-gc-001.contoso.com\RedmondChatRoom"
```

## <a name="move-a-room-from-one-category-to-another"></a><span data-ttu-id="6632c-209">Déplacer une salle d’une catégorie vers une autre</span><span class="sxs-lookup"><span data-stu-id="6632c-209">Move a room from one category to another</span></span>

<span data-ttu-id="6632c-210">Si un responsable de salle de conversation **dispose** de privilèges Créateur dans une autre catégorie, il peut déplacer la salle d’une catégorie à une autre.</span><span class="sxs-lookup"><span data-stu-id="6632c-210">If a chat room manager has **Creator** privileges in another category, he or she can move the room from one category to another.</span></span> <span data-ttu-id="6632c-211">La salle n’est pas supprimée et recréée.</span><span class="sxs-lookup"><span data-stu-id="6632c-211">The room is not deleted and recreated.</span></span> <span data-ttu-id="6632c-212">Seule son association dans la base de données est modifiée.</span><span class="sxs-lookup"><span data-stu-id="6632c-212">It is a change of association within the database.</span></span>
  
<span data-ttu-id="6632c-213">La modification d’une catégorie de salle de conversation doit être effectuée rarement et avec précaution.</span><span class="sxs-lookup"><span data-stu-id="6632c-213">Changing a chat room category should be done rarely and with caution.</span></span> <span data-ttu-id="6632c-214">Une catégorie détermine l’appartenance autorisée pour la salle de conversation, donc si une salle de conversation est déplacée vers une autre catégorie, toutes les listes de contrôle d’accès système (SACLs) qui ne sont plus prises en charge par la nouvelle catégorie sont vidées.</span><span class="sxs-lookup"><span data-stu-id="6632c-214">A category determines the allowed membership for the chat room, so when a chat room is moved to another category, all the system access control lists (SACLs) that are no longer supported by the new category are purged.</span></span> <span data-ttu-id="6632c-215">Par exemple, si un utilisateur était membre de la salle et n’est plus un membre autorisé dans la nouvelle catégorie, l’appartenance à la salle sera modifiée et l’utilisateur sera supprimé de la salle.</span><span class="sxs-lookup"><span data-stu-id="6632c-215">For example, if a user was a member of the room and is no longer an allowed member in the new category, the room membership will be modified and the user will be removed from the room.</span></span>
  

