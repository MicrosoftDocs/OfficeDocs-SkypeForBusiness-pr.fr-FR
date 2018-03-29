---
title: Gestion des salles de conversation sur un serveur de conversation permanente dans Skype Entreprise Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7b2e1302-280c-4efe-9ec8-787687b414da
description: 'Résumé : Apprenez à gérer les salles de serveur de conversation permanents dans Skype pour Business Server 2015.'
ms.openlocfilehash: fd927e3a54f1f3a8df429677f481ea224534b984
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="manage-chat-rooms-in-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="ff9f9-103">Gestion des salles de conversation sur un serveur de conversation permanente dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="ff9f9-103">Manage chat rooms in Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="ff9f9-104">**Résumé :** Découvrez comment gérer les salles de serveur de conversation permanents dans Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="ff9f9-104">**Summary:** Learn how to manage Persistent Chat Server chat rooms in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="ff9f9-105">La création et la gestion des salles de conversation est beaucoup plus facile en cas d’utilisation pertinente des catégories.</span><span class="sxs-lookup"><span data-stu-id="ff9f9-105">Creating and managing chat rooms is much easier with the correct use of categories.</span></span> <span data-ttu-id="ff9f9-106">Une catégorie définit qui peut créer ou rejoindre les salles de conversation.</span><span class="sxs-lookup"><span data-stu-id="ff9f9-106">A category defines who can create or join the chat rooms.</span></span> <span data-ttu-id="ff9f9-107">Avant de pouvoir gérer les salles de conversation, veillez à lire les [catégories de conversation permanent, les salles de conversation et les rôles utilisateur dans Skype pour Business Server 2015](../../plan-your-deployment/persistent-chat-server/categories-chat-rooms-and-user-roles.md) et [Gérer les catégories dans le serveur de conversation permanents dans Skype pour Business Server 2015](categories.md).</span><span class="sxs-lookup"><span data-stu-id="ff9f9-107">Before you attempt to manage chat rooms, be sure to read [Persistent chat categories, chat rooms, and user roles in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/categories-chat-rooms-and-user-roles.md) and [Manage categories in Persistent Chat Server in Skype for Business Server 2015](categories.md).</span></span>
  
<span data-ttu-id="ff9f9-108">Vous pouvez configurer et gérer les salles de conversation à l’aide de l’interface de ligne de commande de Windows PowerShell, ou à l’aide de la Skype pour client d’entreprise si vous êtes un membre de la salle de conversation.</span><span class="sxs-lookup"><span data-stu-id="ff9f9-108">You can configure and manage chat rooms by using the Windows PowerShell command-line interface, or by using the Skype for Business client if you are a member of the chat room.</span></span> <span data-ttu-id="ff9f9-109">Cette rubrique explique comment gérer les salles de conversation en utilisant l’interface de ligne de commande Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ff9f9-109">This topic describes how to manage chat rooms by using the Windows PowerShell command-line interface.</span></span> <span data-ttu-id="ff9f9-110">Si vous souhaitez gérer les salles de conversation à l’aide de la Skype pour client d’entreprise, consultez l’aide du client.</span><span class="sxs-lookup"><span data-stu-id="ff9f9-110">If you want to manage chat rooms by using the Skype for Business client, see the client help.</span></span> 
  
<span data-ttu-id="ff9f9-111">Salles de conversation peut être de deux types : Normal et Auditorium.</span><span class="sxs-lookup"><span data-stu-id="ff9f9-111">Chat rooms can be one of two types: Normal and Auditorium.</span></span> <span data-ttu-id="ff9f9-112">Une salle de conversation normale permet à tous les membres de publier et de lire des messages.</span><span class="sxs-lookup"><span data-stu-id="ff9f9-112">A Normal chat room allows all members to post and read messages.</span></span> <span data-ttu-id="ff9f9-113">Un auditorium est un type de salle de conversation où seuls les présentateurs peuvent publier, mais où tout le monde peut lire.</span><span class="sxs-lookup"><span data-stu-id="ff9f9-113">An Auditorium is a type of chat room where only Presenters can post, but everyone can read.</span></span>
  
<span data-ttu-id="ff9f9-114">Les rôles utilisateur déterminent qui peut accéder aux salles de conversation et les gérer, comme suit :</span><span class="sxs-lookup"><span data-stu-id="ff9f9-114">Who can access and manage chat rooms depends on user roles as follows:</span></span>
  
- <span data-ttu-id="ff9f9-115">Les utilisateurs doivent être membres d’une salle de conversation pour pouvoir publier et lire des messages.</span><span class="sxs-lookup"><span data-stu-id="ff9f9-115">Users must be Members of a chat room to be able to post and read messages.</span></span>
    
- <span data-ttu-id="ff9f9-116">Les présentateurs sont autorisés à publier dans les salles de type Auditorium.</span><span class="sxs-lookup"><span data-stu-id="ff9f9-116">Presenters are allowed to post to Auditorium rooms.</span></span>
    
- <span data-ttu-id="ff9f9-117">Les administrateurs peuvent supprimer un contenu précédant (par exemple, du contenu publié avant une certaine date) d’une salle de conversation afin de conserver une taille de base de données raisonnable.</span><span class="sxs-lookup"><span data-stu-id="ff9f9-117">Administrators can delete earlier content (for example, content that was posted before a certain date) from any chat room to keep the database from growing too large.</span></span> <span data-ttu-id="ff9f9-118">Ils peuvent aussi supprimer ou remplacer des messages qu’ils considèrent inappropriés pour une salle de conversation spécifique.</span><span class="sxs-lookup"><span data-stu-id="ff9f9-118">Administrators can also remove or replace messages that are considered inappropriate for a particular chat room.</span></span>
    
- <span data-ttu-id="ff9f9-119">Les utilisateurs finaux, y compris les auteurs de messages, ne peuvent pas supprimer du contenu de salle de conversation.</span><span class="sxs-lookup"><span data-stu-id="ff9f9-119">End users, including message authors, cannot delete content from any chat room.</span></span>
    
- <span data-ttu-id="ff9f9-120">Les responsables de salle de conversation peuvent apporter des modifications à toutes les propriétés de la salle de conversation, notamment en désactivant des salles.</span><span class="sxs-lookup"><span data-stu-id="ff9f9-120">Chat room Managers can make changes to all chat room properties, including disabling rooms.</span></span> <span data-ttu-id="ff9f9-121">Les responsables ne peuvent pas, toutefois, supprimer une salle ou modifier la catégorie d’une salle.</span><span class="sxs-lookup"><span data-stu-id="ff9f9-121">Managers cannot, however, delete a room, or change the category of a room.</span></span> 
    
- <span data-ttu-id="ff9f9-122">Seuls les administrateurs peuvent supprimer une salle de conversation une fois qu’elle a été créée.</span><span class="sxs-lookup"><span data-stu-id="ff9f9-122">Only Administrators can delete a chat room after it has been created.</span></span>
    
<span data-ttu-id="ff9f9-123">Vous pouvez configurer et gérer des salles de conversation en utilisant les applets de commande Windows PowerShell :</span><span class="sxs-lookup"><span data-stu-id="ff9f9-123">You can configure and manage chat rooms by using the following Windows PowerShell cmdlets:</span></span>
  

|<span data-ttu-id="ff9f9-124">**Applet de commande**</span><span class="sxs-lookup"><span data-stu-id="ff9f9-124">**Cmdlet**</span></span>|<span data-ttu-id="ff9f9-125">**Description**</span><span class="sxs-lookup"><span data-stu-id="ff9f9-125">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ff9f9-126">Nouvelle-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="ff9f9-126">New-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="ff9f9-127">Créer une salle de conversation</span><span class="sxs-lookup"><span data-stu-id="ff9f9-127">Create a new chat room</span></span>  <br/> |
|<span data-ttu-id="ff9f9-128">Ensemble-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="ff9f9-128">Set-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="ff9f9-129">Configurer des paramètres pour une salle existante ; affecter des utilisateurs et des groupes d’utilisateurs à la salle</span><span class="sxs-lookup"><span data-stu-id="ff9f9-129">Configure settings for an existing room; assign users and user groups to the room</span></span>  <br/> |
|<span data-ttu-id="ff9f9-130">Get-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="ff9f9-130">Get-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="ff9f9-131">Récupérer des informations sur les salles</span><span class="sxs-lookup"><span data-stu-id="ff9f9-131">Retrieve information about rooms</span></span>  <br/> |
|<span data-ttu-id="ff9f9-132">CsPersistentChatRoom-clair</span><span class="sxs-lookup"><span data-stu-id="ff9f9-132">Clear-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="ff9f9-133">Effacer une salle et les messages d’une salle</span><span class="sxs-lookup"><span data-stu-id="ff9f9-133">Clear a room or messages from a room</span></span>  <br/> |
|<span data-ttu-id="ff9f9-134">Supprimer-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="ff9f9-134">Remove-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="ff9f9-135">Supprimer une salle</span><span class="sxs-lookup"><span data-stu-id="ff9f9-135">Remove a room</span></span>  <br/> |
|<span data-ttu-id="ff9f9-136">Supprimer-CsPersistentChatMessage</span><span class="sxs-lookup"><span data-stu-id="ff9f9-136">Remove-CsPersistentChatMessage</span></span>  <br/> |<span data-ttu-id="ff9f9-137">Supprimer les messages d’une salle</span><span class="sxs-lookup"><span data-stu-id="ff9f9-137">Remove messages from a room</span></span>  <br/> |
   
<span data-ttu-id="ff9f9-138">Utilisez l’applet de commande **New-CsPersistentChatRoom** pour créer des salles de conversation et utilisez l’applet de commande **Set-CsPersistentChatRoom** pour configurer une salle de conversation existante, notamment pour ajouter des utilisateurs à la salle de conversation.</span><span class="sxs-lookup"><span data-stu-id="ff9f9-138">You use the **New-CsPersistentChatRoom** cmdlet to create chat rooms and the **Set-CsPersistentChatRoom** cmdlet to configure an existing chat room, including adding users to the chat room.</span></span> <span data-ttu-id="ff9f9-139">Vous pouvez configurer les paramètres suivants pour les salles de conversation :</span><span class="sxs-lookup"><span data-stu-id="ff9f9-139">You can configure the following parameters for chat rooms:</span></span>
  
- <span data-ttu-id="ff9f9-140">Disabled.</span><span class="sxs-lookup"><span data-stu-id="ff9f9-140">Disabled.</span></span> <span data-ttu-id="ff9f9-141">Vous permet de désactiver ou d’activer une salle de conversation.</span><span class="sxs-lookup"><span data-stu-id="ff9f9-141">Lets you disable or enable a chat room.</span></span> 
    
- <span data-ttu-id="ff9f9-142">Invitations.</span><span class="sxs-lookup"><span data-stu-id="ff9f9-142">Invitations.</span></span> <span data-ttu-id="ff9f9-143">Permet d’activer ou de désactiver des invitations aux salles de conversation, qui sont utilisées pour avertir les utilisateurs qu’ils ont été ajoutés en tant que membres de salle de conversation.</span><span class="sxs-lookup"><span data-stu-id="ff9f9-143">Lets you enable or disable chat room invitations, which are used to notify users when they have been added as chat room members.</span></span> <span data-ttu-id="ff9f9-144">Le paramétrage par défaut des invitations est inherit, ce qui a amené la salle de conversation à adopter le paramètre d’invitation configuré dans la catégorie à laquelle elle appartient.</span><span class="sxs-lookup"><span data-stu-id="ff9f9-144">The default setting for invitations in inherit, which caused the chat room to adopt the invitation setting configured on the category it belongs to.</span></span> <span data-ttu-id="ff9f9-145">La configuration du paramètre des invitations sur false au niveau de la salle de conversation permet de remplacer le paramétrage de la catégorie.</span><span class="sxs-lookup"><span data-stu-id="ff9f9-145">Configuring the invitations setting to false at the chat room level allows the category setting to be overridden.</span></span> 
    
- <span data-ttu-id="ff9f9-146">Privacy.</span><span class="sxs-lookup"><span data-stu-id="ff9f9-146">Privacy.</span></span> <span data-ttu-id="ff9f9-147">Permet de spécifier si une salle de conversation est ouverte, fermée ou secrète.</span><span class="sxs-lookup"><span data-stu-id="ff9f9-147">Lets you specify whether a chat room is Open, Closed, or Secret.</span></span> <span data-ttu-id="ff9f9-148">Les salles de type Ouvert peuvent faire l’objet d’une recherche et d’un accès de la part de tout le monde.</span><span class="sxs-lookup"><span data-stu-id="ff9f9-148">Open rooms can be searched and accessed by anyone.</span></span> <span data-ttu-id="ff9f9-149">Les salles de type Fermé peuvent faire l’objet d’une recherche de la part de tous, mais peuvent faire l’objet d’un accès uniquement de la part des membres.</span><span class="sxs-lookup"><span data-stu-id="ff9f9-149">Closed rooms can be searched by anyone, but can be accessed only by members.</span></span> <span data-ttu-id="ff9f9-150">Les salles de type Secret peuvent faire l’objet d’une recherche et d’un accès uniquement de la part des membres de la salle.</span><span class="sxs-lookup"><span data-stu-id="ff9f9-150">Secret rooms can be searched and accessed only by members of the room.</span></span> <span data-ttu-id="ff9f9-151">Par défaut, chaque nouvelle salle est initialement configurée comme fermée.</span><span class="sxs-lookup"><span data-stu-id="ff9f9-151">By default, each new room is initially configured as Closed.</span></span>
    
- <span data-ttu-id="ff9f9-152">Type.</span><span class="sxs-lookup"><span data-stu-id="ff9f9-152">Type.</span></span> <span data-ttu-id="ff9f9-153">Permet de spécifier si une salle de conversation est un espace Normal, qui accepte les messages publiés par tout membre ou d’un espace Auditorium, qui accepte les messages publiés uniquement par un présentateur.</span><span class="sxs-lookup"><span data-stu-id="ff9f9-153">Lets you specify whether a chat room is a Normal room, which accepts messages posted by any member, or an Auditorium room, which accepts messages posted only by a Presenter.</span></span>
    
- <span data-ttu-id="ff9f9-154">Addin.</span><span class="sxs-lookup"><span data-stu-id="ff9f9-154">Addin.</span></span> <span data-ttu-id="ff9f9-155">Permet d’associer un complément précédemment configuré avec une salle de conversation, ce qui permet aux membres de voir le contenu d’URL tout en participant.</span><span class="sxs-lookup"><span data-stu-id="ff9f9-155">Lets you associate a previously configured add-in with a chat room, which allows URL content to be viewed by members while participating.</span></span>
    
<span data-ttu-id="ff9f9-156">Outre les paramètres ci-dessus, l’applet de commande **Set-CsPersistentChatRoom** vous permet d’affecter des utilisateurs à la salle de conversation comme suit :</span><span class="sxs-lookup"><span data-stu-id="ff9f9-156">In addition to the above parameters, the **Set-CsPersistentChatRoom** cmdlet lets you assign users to the chat room as follows:</span></span>
  
- <span data-ttu-id="ff9f9-157">Members.</span><span class="sxs-lookup"><span data-stu-id="ff9f9-157">Members.</span></span> <span data-ttu-id="ff9f9-158">Configure les membres de la salle de conversation.</span><span class="sxs-lookup"><span data-stu-id="ff9f9-158">Configures membership for the chat room.</span></span> <span data-ttu-id="ff9f9-159">Vous pouvez ajouter ou supprimer des membres individuellement ou par groupe en utilisant une seule applet de commande en spécifiant l’adresse SIP des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="ff9f9-159">You can add or remove either the individual or multiple members using a single cmdlet by specifying the SIP address of the users.</span></span> <span data-ttu-id="ff9f9-160">Pour permettre aux utilisateurs d’être ajoutés par lot, des unités d’organisation ou des groupes de distribution Active Directory peuvent aussi être spécifiés.</span><span class="sxs-lookup"><span data-stu-id="ff9f9-160">To allow users to be added in bulk, Active Directory organizational units or distribution groups can also be specified.</span></span>
    
- <span data-ttu-id="ff9f9-161">Managers.</span><span class="sxs-lookup"><span data-stu-id="ff9f9-161">Managers.</span></span> <span data-ttu-id="ff9f9-162">Permet d’affecter des responsables à la salle de conversation.</span><span class="sxs-lookup"><span data-stu-id="ff9f9-162">Lets you assign managers to the chat room.</span></span> <span data-ttu-id="ff9f9-163">Les responsables ont les autorisations pour définir l’appartenance à une salle de conversation ainsi que d’autres paramètres.</span><span class="sxs-lookup"><span data-stu-id="ff9f9-163">Managers have the permissions to define membership of a chat room along with other settings.</span></span>
    
- <span data-ttu-id="ff9f9-p114">Presenters. Permet d’affecter des présentateurs à une salle de conversation Auditorium.</span><span class="sxs-lookup"><span data-stu-id="ff9f9-p114">Presenters. Lets you assign presenters to an Auditorium chat room.</span></span> 
    
 <span data-ttu-id="ff9f9-166">Pour plus d’informations sur la syntaxe, y compris tous les paramètres, consultez [Skype pour Business Server 2015 Management Shell](../management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="ff9f9-166">For details about syntax, including all parameters, see [Skype for Business Server 2015 Management Shell](../management-shell.md).</span></span>
  
## <a name="create-a-new-room"></a><span data-ttu-id="ff9f9-167">Créer une salle</span><span class="sxs-lookup"><span data-stu-id="ff9f9-167">Create a new room</span></span>

<span data-ttu-id="ff9f9-168">Vous pouvez créer une nouvelle salle en utilisant l’applet de commande **New-CsPersistentChatRoom**.</span><span class="sxs-lookup"><span data-stu-id="ff9f9-168">You can create a new room by using the **New-CsPersistentChatRoom** cmdlet.</span></span> <span data-ttu-id="ff9f9-169">Par exemple, la commande suivante crée une nouvelle salle de chat nommée ITChatRoom sur le pool atl-cs-001.contoso.com. Dans cet exemple, la salle de conversation est ajoutée à la catégorie de l’informatique :</span><span class="sxs-lookup"><span data-stu-id="ff9f9-169">For example, the following command creates a new chat room named ITChatRoom on the pool atl-cs-001.contoso.com. In this example, the chat room is added to the IT category:</span></span>
  
```
New-CsPersistentChatRoom -Name "ITChatRoom" -PersistentChatPoolFqdn "atl-cs-001.contoso.com"-Category "IT"
```

<span data-ttu-id="ff9f9-170">**Remarque :** PersistentChatPoolFqdn n’est pas nécessaire si une des opérations suivantes est vraie :</span><span class="sxs-lookup"><span data-stu-id="ff9f9-170">**Note:** PersistentChatPoolFqdn is not needed if one of the following is true:</span></span> 
  
- <span data-ttu-id="ff9f9-171">Il n'existe qu’un seul pool de serveur de Chat persistant.</span><span class="sxs-lookup"><span data-stu-id="ff9f9-171">There is only one Persistent Chat Server pool.</span></span>
    
- <span data-ttu-id="ff9f9-172">Vous fournissez un nom de domaine complet (FQDN) de pool à la catégorie.</span><span class="sxs-lookup"><span data-stu-id="ff9f9-172">You provide a pool FQDN to the category.</span></span>
    
- <span data-ttu-id="ff9f9-173">Vous fournissez un nom de domaine complet (FQDN) à l’ajout de la salle.</span><span class="sxs-lookup"><span data-stu-id="ff9f9-173">You provide a pool FQDN to adding the room.</span></span>
    
## <a name="configure-an-existing-room"></a><span data-ttu-id="ff9f9-174">Configurer une salle existante</span><span class="sxs-lookup"><span data-stu-id="ff9f9-174">Configure an existing room</span></span>

<span data-ttu-id="ff9f9-175">Vous pouvez configurer un espace existant à l’aide de l’applet de commande **Set-CsPersistentChatRoom** .</span><span class="sxs-lookup"><span data-stu-id="ff9f9-175">You can configure an existing room by using the **Set-CsPersistentChatRoom** cmdlet.</span></span> <span data-ttu-id="ff9f9-176">Par exemple, la commande suivante attribue user1 en tant que membre et présenteur et Utilisateur2 en tant que responsable, de la testCat d’espace Auditorium :</span><span class="sxs-lookup"><span data-stu-id="ff9f9-176">For example, the following command assigns user1 as a Member and Presenter, and user2 as a Manager, of the testCat Auditorium room:</span></span>
  
```
Set-CsPersistentChatRoom -Identity testCat -Members @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}
Set-CsPersistentChatRoom -Identity testCat -Presenters @{Add="sip:user1@contoso.com"}
Set-CsPersistentChatRoom -Identity testCat -Managers @{Add="sip:user2@contoso.com"}
```

 <span data-ttu-id="ff9f9-177">L’exemple suivant ajoute tous les utilisateurs de l’unité d’organisation NorthAmericaUsers dans Active Directory à la salle de conversation NorthAmerica :</span><span class="sxs-lookup"><span data-stu-id="ff9f9-177">The next example adds all the users from the NorthAmericaUsers OU in active Directory to the NorthAmerica chat room:</span></span>
  
```
Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.contoso.com\NorthAmerica" -Members @{Add="OU=NorthAmericaUsers,DC=contoso,DC=com"}
```

<span data-ttu-id="ff9f9-178">L’exemple suivant ajoute tous les membres du groupe de distribution Finance à la même salle de conversation :</span><span class="sxs-lookup"><span data-stu-id="ff9f9-178">The next example adds all the members from the Finance distribution group to the same chat room:</span></span>
  
```
Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.contoso.com\NorthAmerica" -Members @{Add="CN=Finance,OU=ExternalUsers,DC=contoso,DC=com"}
```

## <a name="disable-or-enable-a-room"></a><span data-ttu-id="ff9f9-179">Désactiver ou activer une salle de conversation</span><span class="sxs-lookup"><span data-stu-id="ff9f9-179">Disable or enable a room</span></span>

<span data-ttu-id="ff9f9-180">Si la rubrique d’une salle de conversation permanent n’est plus pertinente, vous pouvez rendre la salle de conversation à inaccessible aux utilisateurs en le désactivant.</span><span class="sxs-lookup"><span data-stu-id="ff9f9-180">If the topic of a Persistent Chat room is no longer relevant, you can make the chat room unavailable to users by disabling it.</span></span> <span data-ttu-id="ff9f9-181">Lorsqu’une salle de conversation est désactivée, tous les membres sont immédiatement déconnectés de la salle.</span><span class="sxs-lookup"><span data-stu-id="ff9f9-181">When a chat room is disabled, all members are immediately disconnected from the room.</span></span> <span data-ttu-id="ff9f9-182">Une fois qu’une salle de conversation est désactivée, les utilisateurs ne peuvent ni la rejoindre, ni la trouver lors de recherches de salles de conversation.</span><span class="sxs-lookup"><span data-stu-id="ff9f9-182">After a chat room is disabled, users cannot rejoin it or find it in chat room searches.</span></span>
  
<span data-ttu-id="ff9f9-183">Si l’historique de la salle conversation persiste, le contenu est conservé lors de la salle de conversation est désactivée.</span><span class="sxs-lookup"><span data-stu-id="ff9f9-183">If the chat room's history persists, the content is preserved when the chat room is disabled.</span></span> <span data-ttu-id="ff9f9-184">Cependant, le contenu ne s’affichera pas dans les recherches tant que la salle de conversation demeurera désactivée.</span><span class="sxs-lookup"><span data-stu-id="ff9f9-184">However, that content will not appear in searches during the time that the chat room remains in a disabled state.</span></span> <span data-ttu-id="ff9f9-185">Si vous activez ensuite la salle de conversation, les utilisateurs peuvent alors rechercher des messages ayant été publiés avant la désactivation de la salle.</span><span class="sxs-lookup"><span data-stu-id="ff9f9-185">If you later enable the chat room, users can search for messages that were posted before the chat room was disabled.</span></span> <span data-ttu-id="ff9f9-186">Pour plus d’informations sur la configuration de l’historique de la salle de conversation, voir [Gérer les catégories dans le serveur de conversation permanents dans Skype pour Business Server 2015](categories.md).</span><span class="sxs-lookup"><span data-stu-id="ff9f9-186">For information about configuring chat room history, see [Manage categories in Persistent Chat Server in Skype for Business Server 2015](categories.md).</span></span> 
  
<span data-ttu-id="ff9f9-187">Si une salle de conversation est désactivée, sa liste d’adhésion et d’autres paramètres sont conservés.</span><span class="sxs-lookup"><span data-stu-id="ff9f9-187">If a chat room is disabled, its membership list and other settings are preserved.</span></span> <span data-ttu-id="ff9f9-188">En tant qu’administrateur, vous pouvez activer une salle qui a été désactivée, et vous n’avez pas besoin de recréer manuellement les paramètres.</span><span class="sxs-lookup"><span data-stu-id="ff9f9-188">As an administrator, you can enable a room that has been disabled, and you do not need to manually re-create the settings.</span></span>
  
<span data-ttu-id="ff9f9-189">Vous pouvez désactiver un espace à l’aide de l’applet de commande **Set-CsPersistentChatRoom** et le paramètre désactivé sur True :</span><span class="sxs-lookup"><span data-stu-id="ff9f9-189">You can disable a room by using the **Set-CsPersistentChatRoom** cmdlet and setting the Disabled parameter to True:</span></span>
  
```
Set-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -Disabled $True
```

<span data-ttu-id="ff9f9-190">Pour activer une salle de conversation, définissez le paramètre Disabled sur False :</span><span class="sxs-lookup"><span data-stu-id="ff9f9-190">To enable a chat room, set the Disabled parameter to False:</span></span>
  
```
Set-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -Disabled $False

```

## <a name="get-information-about-rooms"></a><span data-ttu-id="ff9f9-191">Obtenir des informations sur les salles</span><span class="sxs-lookup"><span data-stu-id="ff9f9-191">Get information about rooms</span></span>

<span data-ttu-id="ff9f9-192">Pour obtenir des informations sur les salles configurées à utiliser au sein de votre organisation, vous pouvez utiliser l’applet de commande **Get-CsPersistentChatRoom**.</span><span class="sxs-lookup"><span data-stu-id="ff9f9-192">To get information about the rooms configured for use in your organization, you can use the **Get-CsPersistentChatRoom** cmdlet.</span></span>
  
<span data-ttu-id="ff9f9-193">La commande suivante renvoie des informations relatives à toutes les salles de configuration configurées pour une utilisation dans votre organisation :</span><span class="sxs-lookup"><span data-stu-id="ff9f9-193">The following command returns information about all the chat rooms configured for use in the organization:</span></span>
  
```
Get-CsPersistentChatRoom
```

## <a name="remove-all-content-from-a-room"></a><span data-ttu-id="ff9f9-194">Supprimer tout le contenu d’une salle</span><span class="sxs-lookup"><span data-stu-id="ff9f9-194">Remove all content from a room</span></span>

<span data-ttu-id="ff9f9-p120">Vous pouvez supprimer un contenu d’une salle en utilisant l’applet de commande **Clear-CsPersistentChatRoom**. Par exemple, la commande suivante supprime tout le contenu de la salle de conversation permanente ITChatRoom qui a été ajouté à la salle jusqu’au 1er mars 2015 inclus :</span><span class="sxs-lookup"><span data-stu-id="ff9f9-p120">You can remove content from a room by using the **Clear-CsPersistentChatRoom** cmdlet. For example, the following command removes all the content from the Persistent Chat room ITChatRoom that was added to the room on or before March 1, 2015:</span></span>
  
```
Clear-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -EndDate "3/1/2015"
```

## <a name="remove-a-message-from-a-room"></a><span data-ttu-id="ff9f9-197">Supprimer un message d’une salle</span><span class="sxs-lookup"><span data-stu-id="ff9f9-197">Remove a message from a room</span></span>

<span data-ttu-id="ff9f9-p121">Vous pouvez supprimer un ou plusieurs messages dans la base de données de conversation permanente et, le cas échéant, remplacer le message par un message par défaut ou un message fourni par l’administrateur, en utilisant l’applet de commande **Remove-CsPersistentChatMessage**. Par exemple, la commande suivante supprime tous les messages de la salle de conversation ITChatRoom qui étaient publiés par l’utilisateur kenmyer@contoso.com :</span><span class="sxs-lookup"><span data-stu-id="ff9f9-p121">You can remove one or more messages in the Persistent Chat database, and optionally replace the message with a default message or with an administrator-provided message, by using the **Remove-CsPersistentChatMessage** cmdlet. For example, the following command removes all the messages from the ITChatRoom chat room that were posted by the user kenmyer@contoso.com:</span></span>
  
```
Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.contoso.com\ITChatRoom" -UserUri "sip:kenmyer@contoso.com"
```

<span data-ttu-id="ff9f9-200">L’exemple suivant remplace tous les messages supprimés par une note indiquant que le message n’est plus disponible :</span><span class="sxs-lookup"><span data-stu-id="ff9f9-200">The next example replaces any removed messages with the note that the message is no longer available:</span></span>
  
```
Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.contoso.com\ITChatRoom" -UserUri "sip:kenmyer@contoso.com" -ReplaceMessage "This message is no longer available."
```

## <a name="remove-a-room"></a><span data-ttu-id="ff9f9-201">Supprimer une salle</span><span class="sxs-lookup"><span data-stu-id="ff9f9-201">Remove a room</span></span>

<span data-ttu-id="ff9f9-202">Vous pouvez supprimer une salle en utilisant l’applet de commande **Remove-CsPersistentChatRoom**.</span><span class="sxs-lookup"><span data-stu-id="ff9f9-202">You can remove a room by using the **Remove-CsPersistentChatRoom** cmdlet.</span></span>
  
<span data-ttu-id="ff9f9-203">Par exemple, la commande suivante supprime la salle de conversation RedmondChatRoom :</span><span class="sxs-lookup"><span data-stu-id="ff9f9-203">For example, the following command removes the chat room RedmondChatRoom:</span></span>
  
```
Remove-CsPersistentChatRoom -Identity "atl-gc-001.contoso.com\RedmondChatRoom"
```

## <a name="move-a-room-from-one-category-to-another"></a><span data-ttu-id="ff9f9-204">Déplacer une salle de conversation d’une catégorie vers une autre</span><span class="sxs-lookup"><span data-stu-id="ff9f9-204">Move a room from one category to another</span></span>

<span data-ttu-id="ff9f9-p122">Si le responsable de la salle de conversation a des privilèges **Creator** dans une autre catégorie, il peut déplacer la salle d’une catégorie à une autre. La salle n’est pas supprimée et recréée. Seule son association dans la base de données est modifiée.</span><span class="sxs-lookup"><span data-stu-id="ff9f9-p122">If a chat room manager has **Creator** privileges in another category, he or she can move the room from one category to another. The room is not deleted and recreated. It is a change of association within the database.</span></span>
  
<span data-ttu-id="ff9f9-p123">La modification d’une catégorie de salle de conversation est très rare et exige de la prudence. Une catégorie détermine l’appartenance autorisée pour la salle de conversation, donc si une salle de conversation est déplacée vers une autre catégorie, toutes les listes de contrôle d’accès système (SACL) qui ne sont plus prises en charge par la nouvelle catégorie sont vidées. Par exemple, si un utilisateur était membre de la salle et qu’il n’est plus un membre autorisé dans la nouvelle catégorie, l’appartenance de la salle sera modifiée et l’utilisateur sera supprimé de la salle.</span><span class="sxs-lookup"><span data-stu-id="ff9f9-p123">Changing a chat room category should be done rarely and with caution. A category determines the allowed membership for the chat room, so when a chat room is moved to another category, all the system access control lists (SACLs) that are no longer supported by the new category are purged. For example, if a user was a member of the room and is no longer an allowed member in the new category, the room membership will be modified and the user will be removed from the room.</span></span>
  

