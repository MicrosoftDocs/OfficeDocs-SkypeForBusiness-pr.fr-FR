---
title: Gestion des salles de conversation sur un serveur de conversation permanente dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7b2e1302-280c-4efe-9ec8-787687b414da
description: 'Résumé : Découvrez comment gérer les salles de conversation Persistent Chat Server dans Skype pour Business Server 2015.'
ms.openlocfilehash: 8764b40651c9872393867ced205c405cfc2d4046
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32211641"
---
# <a name="manage-chat-rooms-in-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="d3749-103">Gestion des salles de conversation sur un serveur de conversation permanente dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="d3749-103">Manage chat rooms in Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="d3749-104">**Résumé :** Découvrez comment gérer les salles de conversation Persistent Chat Server dans Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="d3749-104">**Summary:** Learn how to manage Persistent Chat Server chat rooms in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="d3749-105">La création et la gestion des salles de conversation est beaucoup plus facile en cas d’utilisation pertinente des catégories.</span><span class="sxs-lookup"><span data-stu-id="d3749-105">Creating and managing chat rooms is much easier with the correct use of categories.</span></span> <span data-ttu-id="d3749-106">Une catégorie définit qui peut créer ou joindre les salles de conversation.</span><span class="sxs-lookup"><span data-stu-id="d3749-106">A category defines who can create or join the chat rooms.</span></span> <span data-ttu-id="d3749-107">Avant de pouvoir gérer les salles de conversation, veillez à lire les [catégories de conversation permanente, les salles de conversation et les rôles d’utilisateur dans Skype pour Business Server 2015](../../plan-your-deployment/persistent-chat-server/categories-chat-rooms-and-user-roles.md) et [Gérer les catégories dans Persistent Chat Server dans Skype pour Business Server 2015](categories.md).</span><span class="sxs-lookup"><span data-stu-id="d3749-107">Before you attempt to manage chat rooms, be sure to read [Persistent chat categories, chat rooms, and user roles in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/categories-chat-rooms-and-user-roles.md) and [Manage categories in Persistent Chat Server in Skype for Business Server 2015](categories.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="d3749-108">Conversation permanente est disponible dans Skype pour Business Server 2015, mais n’est plus pris en charge dans Skype pour Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="d3749-108">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="d3749-109">La même fonctionnalité est disponible dans les équipes.</span><span class="sxs-lookup"><span data-stu-id="d3749-109">The same functionality is available in Teams.</span></span> <span data-ttu-id="d3749-110">Pour plus d’informations, voir [parcours de Skype pour les entreprises aux équipes de Microsoft](/microsoftteams/journey-skypeforbusiness-teams).</span><span class="sxs-lookup"><span data-stu-id="d3749-110">For more information, see [Journey from Skype for Business to Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span></span> <span data-ttu-id="d3749-111">Si vous devez utiliser la conversation permanente, vos choix est pour migrer les utilisateurs ayant besoin de cette fonctionnalité aux équipes, ou pour continuer à utiliser Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="d3749-111">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

<span data-ttu-id="d3749-112">Vous pouvez configurer et gérer les salles de conversation à l’aide de l’interface de ligne de commande Windows PowerShell, ou en utilisant le Skype pour client d’entreprise si vous êtes membre de la salle de conversation.</span><span class="sxs-lookup"><span data-stu-id="d3749-112">You can configure and manage chat rooms by using the Windows PowerShell command-line interface, or by using the Skype for Business client if you are a member of the chat room.</span></span> <span data-ttu-id="d3749-113">Cette rubrique explique comment gérer les salles de conversation en utilisant l’interface de ligne de commande Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d3749-113">This topic describes how to manage chat rooms by using the Windows PowerShell command-line interface.</span></span> <span data-ttu-id="d3749-114">Si vous souhaitez gérer les salles de conversation à l’aide de la Skype pour client d’entreprise, voir l’aide du client.</span><span class="sxs-lookup"><span data-stu-id="d3749-114">If you want to manage chat rooms by using the Skype for Business client, see the client help.</span></span> 
  
<span data-ttu-id="d3749-115">Salles de conversation peut être une des deux types : Normal et type Auditorium.</span><span class="sxs-lookup"><span data-stu-id="d3749-115">Chat rooms can be one of two types: Normal and Auditorium.</span></span> <span data-ttu-id="d3749-116">Une salle de conversation normale permet à tous les membres de publier et de lire des messages.</span><span class="sxs-lookup"><span data-stu-id="d3749-116">A Normal chat room allows all members to post and read messages.</span></span> <span data-ttu-id="d3749-117">Un auditorium est un type de salle de conversation où seuls les présentateurs peuvent publier, mais où tout le monde peut lire.</span><span class="sxs-lookup"><span data-stu-id="d3749-117">An Auditorium is a type of chat room where only Presenters can post, but everyone can read.</span></span>
  
<span data-ttu-id="d3749-118">Les rôles utilisateur déterminent qui peut accéder aux salles de conversation et les gérer, comme suit :</span><span class="sxs-lookup"><span data-stu-id="d3749-118">Who can access and manage chat rooms depends on user roles as follows:</span></span>
  
- <span data-ttu-id="d3749-119">Les utilisateurs doivent être membres d’une salle de conversation pour pouvoir publier et lire des messages.</span><span class="sxs-lookup"><span data-stu-id="d3749-119">Users must be Members of a chat room to be able to post and read messages.</span></span>
    
- <span data-ttu-id="d3749-120">Les présentateurs sont autorisés à publier dans les salles de type Auditorium.</span><span class="sxs-lookup"><span data-stu-id="d3749-120">Presenters are allowed to post to Auditorium rooms.</span></span>
    
- <span data-ttu-id="d3749-121">Les administrateurs peuvent supprimer un contenu précédant (par exemple, du contenu publié avant une certaine date) d’une salle de conversation afin de conserver une taille de base de données raisonnable.</span><span class="sxs-lookup"><span data-stu-id="d3749-121">Administrators can delete earlier content (for example, content that was posted before a certain date) from any chat room to keep the database from growing too large.</span></span> <span data-ttu-id="d3749-122">Ils peuvent aussi supprimer ou remplacer des messages qu’ils considèrent inappropriés pour une salle de conversation spécifique.</span><span class="sxs-lookup"><span data-stu-id="d3749-122">Administrators can also remove or replace messages that are considered inappropriate for a particular chat room.</span></span>
    
- <span data-ttu-id="d3749-123">Les utilisateurs finaux, y compris les auteurs de messages, ne peuvent pas supprimer du contenu de salle de conversation.</span><span class="sxs-lookup"><span data-stu-id="d3749-123">End users, including message authors, cannot delete content from any chat room.</span></span>
    
- <span data-ttu-id="d3749-124">Les responsables de salle de conversation peuvent apporter des modifications à toutes les propriétés de la salle de conversation, notamment en désactivant des salles.</span><span class="sxs-lookup"><span data-stu-id="d3749-124">Chat room Managers can make changes to all chat room properties, including disabling rooms.</span></span> <span data-ttu-id="d3749-125">Les responsables ne peuvent pas, toutefois, supprimer une salle ou modifier la catégorie d’une salle.</span><span class="sxs-lookup"><span data-stu-id="d3749-125">Managers cannot, however, delete a room, or change the category of a room.</span></span> 
    
- <span data-ttu-id="d3749-126">Seuls les administrateurs peuvent supprimer une salle de conversation une fois qu’elle a été créée.</span><span class="sxs-lookup"><span data-stu-id="d3749-126">Only Administrators can delete a chat room after it has been created.</span></span>
    
<span data-ttu-id="d3749-127">Vous pouvez configurer et gérer des salles de conversation en utilisant les applets de commande Windows PowerShell :</span><span class="sxs-lookup"><span data-stu-id="d3749-127">You can configure and manage chat rooms by using the following Windows PowerShell cmdlets:</span></span>
  

|<span data-ttu-id="d3749-128">**Applet de commande**</span><span class="sxs-lookup"><span data-stu-id="d3749-128">**Cmdlet**</span></span>|<span data-ttu-id="d3749-129">**Description**</span><span class="sxs-lookup"><span data-stu-id="d3749-129">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d3749-130">New-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="d3749-130">New-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="d3749-131">Créer une salle de conversation</span><span class="sxs-lookup"><span data-stu-id="d3749-131">Create a new chat room</span></span>  <br/> |
|<span data-ttu-id="d3749-132">Set-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="d3749-132">Set-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="d3749-133">Configurer des paramètres pour une salle existante ; affecter des utilisateurs et des groupes d’utilisateurs à la salle</span><span class="sxs-lookup"><span data-stu-id="d3749-133">Configure settings for an existing room; assign users and user groups to the room</span></span>  <br/> |
|<span data-ttu-id="d3749-134">Get-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="d3749-134">Get-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="d3749-135">Récupérer des informations sur les salles</span><span class="sxs-lookup"><span data-stu-id="d3749-135">Retrieve information about rooms</span></span>  <br/> |
|<span data-ttu-id="d3749-136">Clear-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="d3749-136">Clear-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="d3749-137">Effacer une salle et les messages d’une salle</span><span class="sxs-lookup"><span data-stu-id="d3749-137">Clear a room or messages from a room</span></span>  <br/> |
|<span data-ttu-id="d3749-138">Remove-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="d3749-138">Remove-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="d3749-139">Supprimer une salle</span><span class="sxs-lookup"><span data-stu-id="d3749-139">Remove a room</span></span>  <br/> |
|<span data-ttu-id="d3749-140">Remove-CsPersistentChatMessage</span><span class="sxs-lookup"><span data-stu-id="d3749-140">Remove-CsPersistentChatMessage</span></span>  <br/> |<span data-ttu-id="d3749-141">Supprimer les messages d’une salle</span><span class="sxs-lookup"><span data-stu-id="d3749-141">Remove messages from a room</span></span>  <br/> |
   
<span data-ttu-id="d3749-142">Utilisez l’applet de commande **New-CsPersistentChatRoom** pour créer des salles de conversation et utilisez l’applet de commande **Set-CsPersistentChatRoom** pour configurer une salle de conversation existante, notamment pour ajouter des utilisateurs à la salle de conversation.</span><span class="sxs-lookup"><span data-stu-id="d3749-142">You use the **New-CsPersistentChatRoom** cmdlet to create chat rooms and the **Set-CsPersistentChatRoom** cmdlet to configure an existing chat room, including adding users to the chat room.</span></span> <span data-ttu-id="d3749-143">Vous pouvez configurer les paramètres suivants pour les salles de conversation :</span><span class="sxs-lookup"><span data-stu-id="d3749-143">You can configure the following parameters for chat rooms:</span></span>
  
- <span data-ttu-id="d3749-144">Disabled.</span><span class="sxs-lookup"><span data-stu-id="d3749-144">Disabled.</span></span> <span data-ttu-id="d3749-145">Vous permet de désactiver ou activer une salle de conversation.</span><span class="sxs-lookup"><span data-stu-id="d3749-145">Lets you disable or enable a chat room.</span></span> 
    
- <span data-ttu-id="d3749-146">Invitations.</span><span class="sxs-lookup"><span data-stu-id="d3749-146">Invitations.</span></span> <span data-ttu-id="d3749-147">Permet d’activer ou de désactiver des invitations aux salles de conversation, qui sont utilisées pour avertir les utilisateurs qu’ils ont été ajoutés en tant que membres de salle de conversation.</span><span class="sxs-lookup"><span data-stu-id="d3749-147">Lets you enable or disable chat room invitations, which are used to notify users when they have been added as chat room members.</span></span> <span data-ttu-id="d3749-148">Le paramétrage par défaut des invitations est inherit, ce qui a amené la salle de conversation à adopter le paramètre d’invitation configuré dans la catégorie à laquelle elle appartient.</span><span class="sxs-lookup"><span data-stu-id="d3749-148">The default setting for invitations in inherit, which caused the chat room to adopt the invitation setting configured on the category it belongs to.</span></span> <span data-ttu-id="d3749-149">La configuration du paramètre des invitations sur false au niveau de la salle de conversation permet de remplacer le paramétrage de la catégorie.</span><span class="sxs-lookup"><span data-stu-id="d3749-149">Configuring the invitations setting to false at the chat room level allows the category setting to be overridden.</span></span> 
    
- <span data-ttu-id="d3749-150">Privacy.</span><span class="sxs-lookup"><span data-stu-id="d3749-150">Privacy.</span></span> <span data-ttu-id="d3749-151">Permet de spécifier si une salle de conversation est ouverte, fermée ou secrète.</span><span class="sxs-lookup"><span data-stu-id="d3749-151">Lets you specify whether a chat room is Open, Closed, or Secret.</span></span> <span data-ttu-id="d3749-152">Les salles de type Ouvert peuvent faire l’objet d’une recherche et d’un accès de la part de tout le monde.</span><span class="sxs-lookup"><span data-stu-id="d3749-152">Open rooms can be searched and accessed by anyone.</span></span> <span data-ttu-id="d3749-153">Les salles de type Fermé peuvent faire l’objet d’une recherche de la part de tous, mais peuvent faire l’objet d’un accès uniquement de la part des membres.</span><span class="sxs-lookup"><span data-stu-id="d3749-153">Closed rooms can be searched by anyone, but can be accessed only by members.</span></span> <span data-ttu-id="d3749-154">Les salles de type Secret peuvent faire l’objet d’une recherche et d’un accès uniquement de la part des membres de la salle.</span><span class="sxs-lookup"><span data-stu-id="d3749-154">Secret rooms can be searched and accessed only by members of the room.</span></span> <span data-ttu-id="d3749-155">Par défaut, chaque nouvelle salle est initialement configurée comme fermée.</span><span class="sxs-lookup"><span data-stu-id="d3749-155">By default, each new room is initially configured as Closed.</span></span>
    
- <span data-ttu-id="d3749-156">Type.</span><span class="sxs-lookup"><span data-stu-id="d3749-156">Type.</span></span> <span data-ttu-id="d3749-157">Vous permet de spécifier si une salle de conversation est une salle Normal, qui accepte les messages publiés par n’importe quel membre, ou un auditorium, qui accepte les messages publiés uniquement par un présentateur.</span><span class="sxs-lookup"><span data-stu-id="d3749-157">Lets you specify whether a chat room is a Normal room, which accepts messages posted by any member, or an Auditorium room, which accepts messages posted only by a Presenter.</span></span>
    
- <span data-ttu-id="d3749-158">Addin.</span><span class="sxs-lookup"><span data-stu-id="d3749-158">Addin.</span></span> <span data-ttu-id="d3749-159">Permet d’associer un complément précédemment configuré avec une salle de conversation, ce qui permet aux membres de voir le contenu d’URL tout en participant.</span><span class="sxs-lookup"><span data-stu-id="d3749-159">Lets you associate a previously configured add-in with a chat room, which allows URL content to be viewed by members while participating.</span></span>
    
<span data-ttu-id="d3749-160">En plus des paramètres ci-dessus, l’applet de commande **Set-CsPersistentChatRoom** permet d’affecter des utilisateurs à la salle de conversation comme suit :</span><span class="sxs-lookup"><span data-stu-id="d3749-160">In addition to the above parameters, the **Set-CsPersistentChatRoom** cmdlet lets you assign users to the chat room as follows:</span></span>
  
- <span data-ttu-id="d3749-161">Members.</span><span class="sxs-lookup"><span data-stu-id="d3749-161">Members.</span></span> <span data-ttu-id="d3749-162">Configure les membres de la salle de conversation.</span><span class="sxs-lookup"><span data-stu-id="d3749-162">Configures membership for the chat room.</span></span> <span data-ttu-id="d3749-163">Vous pouvez ajouter ou supprimer des membres individuellement ou par groupe en utilisant une seule applet de commande en spécifiant l’adresse SIP des utilisateurs.</span><span class="sxs-lookup"><span data-stu-id="d3749-163">You can add or remove either the individual or multiple members using a single cmdlet by specifying the SIP address of the users.</span></span> <span data-ttu-id="d3749-164">Pour permettre aux utilisateurs d’être ajoutés par lot, des unités d’organisation ou des groupes de distribution Active Directory peuvent aussi être spécifiés.</span><span class="sxs-lookup"><span data-stu-id="d3749-164">To allow users to be added in bulk, Active Directory organizational units or distribution groups can also be specified.</span></span>
    
- <span data-ttu-id="d3749-165">Managers.</span><span class="sxs-lookup"><span data-stu-id="d3749-165">Managers.</span></span> <span data-ttu-id="d3749-166">Permet d’affecter des responsables à la salle de conversation.</span><span class="sxs-lookup"><span data-stu-id="d3749-166">Lets you assign managers to the chat room.</span></span> <span data-ttu-id="d3749-167">Les responsables ont les autorisations pour définir l’appartenance à une salle de conversation ainsi que d’autres paramètres.</span><span class="sxs-lookup"><span data-stu-id="d3749-167">Managers have the permissions to define membership of a chat room along with other settings.</span></span>
    
- <span data-ttu-id="d3749-p115">Presenters. Permet d’affecter des présentateurs à une salle de conversation Auditorium.</span><span class="sxs-lookup"><span data-stu-id="d3749-p115">Presenters. Lets you assign presenters to an Auditorium chat room.</span></span> 
    
  <span data-ttu-id="d3749-170">Pour des informations sur la syntaxe, notamment tous les paramètres, voir [Skype for Business Server 2015 Management Shell](../management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="d3749-170">For details about syntax, including all parameters, see [Skype for Business Server 2015 Management Shell](../management-shell.md).</span></span>
  
## <a name="create-a-new-room"></a><span data-ttu-id="d3749-171">Créer une salle</span><span class="sxs-lookup"><span data-stu-id="d3749-171">Create a new room</span></span>

<span data-ttu-id="d3749-172">Vous pouvez créer une nouvelle salle en utilisant l’applet de commande **New-CsPersistentChatRoom**.</span><span class="sxs-lookup"><span data-stu-id="d3749-172">You can create a new room by using the **New-CsPersistentChatRoom** cmdlet.</span></span> <span data-ttu-id="d3749-173">Par exemple, la commande suivante crée une nouvelle salle de conversation nommée ITChatRoom dans le pool atl-cs-001.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="d3749-173">For example, the following command creates a new chat room named ITChatRoom on the pool atl-cs-001.contoso.com.</span></span> <span data-ttu-id="d3749-174">Dans cet exemple, la salle de conversation est ajoutée à la catégorie IT :</span><span class="sxs-lookup"><span data-stu-id="d3749-174">In this example, the chat room is added to the IT category:</span></span>
  
```
New-CsPersistentChatRoom -Name "ITChatRoom" -PersistentChatPoolFqdn "atl-cs-001.contoso.com"-Category "IT"
```

<span data-ttu-id="d3749-175">**Remarque :** PersistentChatPoolFqdn n’est pas nécessaire si une des options suivantes est vraie :</span><span class="sxs-lookup"><span data-stu-id="d3749-175">**Note:** PersistentChatPoolFqdn is not needed if one of the following is true:</span></span> 
  
- <span data-ttu-id="d3749-176">Il n'existe qu’un seul pool de serveurs de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="d3749-176">There is only one Persistent Chat Server pool.</span></span>
    
- <span data-ttu-id="d3749-177">Vous fournissez un nom de domaine complet (FQDN) de pool à la catégorie.</span><span class="sxs-lookup"><span data-stu-id="d3749-177">You provide a pool FQDN to the category.</span></span>
    
- <span data-ttu-id="d3749-178">Vous fournissez un nom de domaine complet (FQDN) à l’ajout de la salle.</span><span class="sxs-lookup"><span data-stu-id="d3749-178">You provide a pool FQDN to adding the room.</span></span>
    
## <a name="configure-an-existing-room"></a><span data-ttu-id="d3749-179">Configurer une salle existante</span><span class="sxs-lookup"><span data-stu-id="d3749-179">Configure an existing room</span></span>

<span data-ttu-id="d3749-180">Vous pouvez configurer une salle existante à l’aide de l’applet de commande **Set-CsPersistentChatRoom** .</span><span class="sxs-lookup"><span data-stu-id="d3749-180">You can configure an existing room by using the **Set-CsPersistentChatRoom** cmdlet.</span></span> <span data-ttu-id="d3749-181">Par exemple, la commande suivante attribue user1 en tant que membre et présentateur et user2 en tant que gestionnaire, de la salle de type Auditorium testCat :</span><span class="sxs-lookup"><span data-stu-id="d3749-181">For example, the following command assigns user1 as a Member and Presenter, and user2 as a Manager, of the testCat Auditorium room:</span></span>
  
```
Set-CsPersistentChatRoom -Identity testCat -Members @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}
Set-CsPersistentChatRoom -Identity testCat -Presenters @{Add="sip:user1@contoso.com"}
Set-CsPersistentChatRoom -Identity testCat -Managers @{Add="sip:user2@contoso.com"}
```

 <span data-ttu-id="d3749-182">L’exemple suivant ajoute tous les utilisateurs de l’unité d’organisation NorthAmericaUsers dans Active Directory à la salle de conversation NorthAmerica :</span><span class="sxs-lookup"><span data-stu-id="d3749-182">The next example adds all the users from the NorthAmericaUsers OU in active Directory to the NorthAmerica chat room:</span></span>
  
```
Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.contoso.com\NorthAmerica" -Members @{Add="OU=NorthAmericaUsers,DC=contoso,DC=com"}
```

<span data-ttu-id="d3749-183">L’exemple suivant ajoute tous les membres du groupe de distribution Finance à la même salle de conversation :</span><span class="sxs-lookup"><span data-stu-id="d3749-183">The next example adds all the members from the Finance distribution group to the same chat room:</span></span>
  
```
Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.contoso.com\NorthAmerica" -Members @{Add="CN=Finance,OU=ExternalUsers,DC=contoso,DC=com"}
```

## <a name="disable-or-enable-a-room"></a><span data-ttu-id="d3749-184">Désactiver ou activer une salle de conversation</span><span class="sxs-lookup"><span data-stu-id="d3749-184">Disable or enable a room</span></span>

<span data-ttu-id="d3749-185">Si la rubrique d’une salle de conversation permanente n’est plus pertinente, vous pouvez rendre la salle de conversation à inaccessible aux utilisateurs en le désactivant.</span><span class="sxs-lookup"><span data-stu-id="d3749-185">If the topic of a Persistent Chat room is no longer relevant, you can make the chat room unavailable to users by disabling it.</span></span> <span data-ttu-id="d3749-186">Lorsqu’une salle de conversation est désactivée, tous les membres sont immédiatement déconnectés de la salle.</span><span class="sxs-lookup"><span data-stu-id="d3749-186">When a chat room is disabled, all members are immediately disconnected from the room.</span></span> <span data-ttu-id="d3749-187">Une fois qu’une salle de conversation est désactivée, les utilisateurs ne peuvent ni la rejoindre, ni la trouver lors de recherches de salles de conversation.</span><span class="sxs-lookup"><span data-stu-id="d3749-187">After a chat room is disabled, users cannot rejoin it or find it in chat room searches.</span></span>
  
<span data-ttu-id="d3749-188">Si l’historique de la salle de conversation persiste, le contenu est conservé lors de la salle de conversation est désactivée.</span><span class="sxs-lookup"><span data-stu-id="d3749-188">If the chat room's history persists, the content is preserved when the chat room is disabled.</span></span> <span data-ttu-id="d3749-189">Cependant, le contenu ne s’affichera pas dans les recherches tant que la salle de conversation demeurera désactivée.</span><span class="sxs-lookup"><span data-stu-id="d3749-189">However, that content will not appear in searches during the time that the chat room remains in a disabled state.</span></span> <span data-ttu-id="d3749-190">Si vous activez ensuite la salle de conversation, les utilisateurs peuvent alors rechercher des messages ayant été publiés avant la désactivation de la salle.</span><span class="sxs-lookup"><span data-stu-id="d3749-190">If you later enable the chat room, users can search for messages that were posted before the chat room was disabled.</span></span> <span data-ttu-id="d3749-191">Pour plus d’informations sur la configuration de l’historique de la salle de conversation, voir [Gérer les catégories dans Persistent Chat Server dans Skype pour Business Server 2015](categories.md).</span><span class="sxs-lookup"><span data-stu-id="d3749-191">For information about configuring chat room history, see [Manage categories in Persistent Chat Server in Skype for Business Server 2015](categories.md).</span></span> 
  
<span data-ttu-id="d3749-192">Si une salle de conversation est désactivée, sa liste d’adhésion et d’autres paramètres sont conservés.</span><span class="sxs-lookup"><span data-stu-id="d3749-192">If a chat room is disabled, its membership list and other settings are preserved.</span></span> <span data-ttu-id="d3749-193">En tant qu’administrateur, vous pouvez activer une salle qui a été désactivée, et vous n’avez pas besoin de recréer manuellement les paramètres.</span><span class="sxs-lookup"><span data-stu-id="d3749-193">As an administrator, you can enable a room that has been disabled, and you do not need to manually re-create the settings.</span></span>
  
<span data-ttu-id="d3749-194">Vous pouvez désactiver une salle en utilisant la cmdlet **Set-CsPersistentChatRoom** et en définissant le paramètre désactivé sur True :</span><span class="sxs-lookup"><span data-stu-id="d3749-194">You can disable a room by using the **Set-CsPersistentChatRoom** cmdlet and setting the Disabled parameter to True:</span></span>
  
```
Set-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -Disabled $True
```

<span data-ttu-id="d3749-195">Pour activer une salle de conversation, définissez le paramètre Disabled sur False :</span><span class="sxs-lookup"><span data-stu-id="d3749-195">To enable a chat room, set the Disabled parameter to False:</span></span>
  
```
Set-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -Disabled $False
```

## <a name="get-information-about-rooms"></a><span data-ttu-id="d3749-196">Obtenir des informations sur les salles</span><span class="sxs-lookup"><span data-stu-id="d3749-196">Get information about rooms</span></span>

<span data-ttu-id="d3749-197">Pour obtenir des informations sur les salles configurées à utiliser au sein de votre organisation, vous pouvez utiliser l’applet de commande **Get-CsPersistentChatRoom**.</span><span class="sxs-lookup"><span data-stu-id="d3749-197">To get information about the rooms configured for use in your organization, you can use the **Get-CsPersistentChatRoom** cmdlet.</span></span>
  
<span data-ttu-id="d3749-198">La commande suivante renvoie des informations relatives à toutes les salles de configuration configurées pour une utilisation dans votre organisation :</span><span class="sxs-lookup"><span data-stu-id="d3749-198">The following command returns information about all the chat rooms configured for use in the organization:</span></span>
  
```
Get-CsPersistentChatRoom
```

## <a name="remove-all-content-from-a-room"></a><span data-ttu-id="d3749-199">Supprimer tout le contenu d’une salle</span><span class="sxs-lookup"><span data-stu-id="d3749-199">Remove all content from a room</span></span>

<span data-ttu-id="d3749-p121">Vous pouvez supprimer un contenu d’une salle en utilisant l’applet de commande **Clear-CsPersistentChatRoom**. Par exemple, la commande suivante supprime tout le contenu de la salle de conversation permanente ITChatRoom qui a été ajouté à la salle jusqu’au 1er mars 2015 inclus :</span><span class="sxs-lookup"><span data-stu-id="d3749-p121">You can remove content from a room by using the **Clear-CsPersistentChatRoom** cmdlet. For example, the following command removes all the content from the Persistent Chat room ITChatRoom that was added to the room on or before March 1, 2015:</span></span>
  
```
Clear-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -EndDate "3/1/2015"
```

## <a name="remove-a-message-from-a-room"></a><span data-ttu-id="d3749-202">Supprimer un message d’une salle</span><span class="sxs-lookup"><span data-stu-id="d3749-202">Remove a message from a room</span></span>

<span data-ttu-id="d3749-p122">Vous pouvez supprimer un ou plusieurs messages dans la base de données de conversation permanente et, le cas échéant, remplacer le message par un message par défaut ou un message fourni par l’administrateur, en utilisant l’applet de commande **Remove-CsPersistentChatMessage**. Par exemple, la commande suivante supprime tous les messages de la salle de conversation ITChatRoom qui étaient publiés par l’utilisateur kenmyer@contoso.com :</span><span class="sxs-lookup"><span data-stu-id="d3749-p122">You can remove one or more messages in the Persistent Chat database, and optionally replace the message with a default message or with an administrator-provided message, by using the **Remove-CsPersistentChatMessage** cmdlet. For example, the following command removes all the messages from the ITChatRoom chat room that were posted by the user kenmyer@contoso.com:</span></span>
  
```
Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.contoso.com\ITChatRoom" -UserUri "sip:kenmyer@contoso.com"
```

<span data-ttu-id="d3749-205">L’exemple suivant remplace tous les messages supprimés par une note indiquant que le message n’est plus disponible :</span><span class="sxs-lookup"><span data-stu-id="d3749-205">The next example replaces any removed messages with the note that the message is no longer available:</span></span>
  
```
Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.contoso.com\ITChatRoom" -UserUri "sip:kenmyer@contoso.com" -ReplaceMessage "This message is no longer available."
```

## <a name="remove-a-room"></a><span data-ttu-id="d3749-206">Supprimer une salle</span><span class="sxs-lookup"><span data-stu-id="d3749-206">Remove a room</span></span>

<span data-ttu-id="d3749-207">Vous pouvez supprimer une salle en utilisant l’applet de commande **Remove-CsPersistentChatRoom**.</span><span class="sxs-lookup"><span data-stu-id="d3749-207">You can remove a room by using the **Remove-CsPersistentChatRoom** cmdlet.</span></span>
  
<span data-ttu-id="d3749-208">Par exemple, la commande suivante supprime la salle de conversation RedmondChatRoom :</span><span class="sxs-lookup"><span data-stu-id="d3749-208">For example, the following command removes the chat room RedmondChatRoom:</span></span>
  
```
Remove-CsPersistentChatRoom -Identity "atl-gc-001.contoso.com\RedmondChatRoom"
```

## <a name="move-a-room-from-one-category-to-another"></a><span data-ttu-id="d3749-209">Déplacer une salle de conversation d’une catégorie vers une autre</span><span class="sxs-lookup"><span data-stu-id="d3749-209">Move a room from one category to another</span></span>

<span data-ttu-id="d3749-p123">Si le responsable de la salle de conversation a des privilèges **Creator** dans une autre catégorie, il peut déplacer la salle d’une catégorie à une autre. La salle n’est pas supprimée et recréée. Seule son association dans la base de données est modifiée.</span><span class="sxs-lookup"><span data-stu-id="d3749-p123">If a chat room manager has **Creator** privileges in another category, he or she can move the room from one category to another. The room is not deleted and recreated. It is a change of association within the database.</span></span>
  
<span data-ttu-id="d3749-p124">La modification d’une catégorie de salle de conversation est très rare et exige de la prudence. Une catégorie détermine l’appartenance autorisée pour la salle de conversation, donc si une salle de conversation est déplacée vers une autre catégorie, toutes les listes de contrôle d’accès système (SACL) qui ne sont plus prises en charge par la nouvelle catégorie sont vidées. Par exemple, si un utilisateur était membre de la salle et qu’il n’est plus un membre autorisé dans la nouvelle catégorie, l’appartenance de la salle sera modifiée et l’utilisateur sera supprimé de la salle.</span><span class="sxs-lookup"><span data-stu-id="d3749-p124">Changing a chat room category should be done rarely and with caution. A category determines the allowed membership for the chat room, so when a chat room is moved to another category, all the system access control lists (SACLs) that are no longer supported by the new category are purged. For example, if a user was a member of the room and is no longer an allowed member in the new category, the room membership will be modified and the user will be removed from the room.</span></span>
  

