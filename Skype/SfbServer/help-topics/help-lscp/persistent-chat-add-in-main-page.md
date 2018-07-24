---
title: Complément de conversation permanente – Page principale
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.PersistentChatAddinMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0c0ecf64-258d-4b43-8fac-fa5ffa4e7646
description: Vous pouvez utiliser la section de la page de conversation permanente à associer les URL des salles de conversation permanente. Ces URL s’affichent sur le client dans la salle de conversation, dans le volet d’extensibilité de conversation. Un administrateur doit ajouter Compléments à la liste des compléments enregistrés et les créateurs/responsables de salles de conversation doivent associer les salles à l’un des compléments enregistrés pour que les utilisateurs puissent voir cette mise à niveau sur leur client.
ms.openlocfilehash: d165f770d7d10b7e1d599a4698561f3f833d7d82
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "21005873"
---
# <a name="persistent-chat-add-in-main-page"></a><span data-ttu-id="59e79-105">Complément de conversation permanente – Page principale</span><span class="sxs-lookup"><span data-stu-id="59e79-105">Persistent Chat Add-in Main Page</span></span>
 
<span data-ttu-id="59e79-106">Vous pouvez utiliser **la section de la page de **Conversation permanente** ** à associer les URL des salles de conversation permanente.</span><span class="sxs-lookup"><span data-stu-id="59e79-106">You can use the **Add-in** section of the **Persistent Chat** page to associate URLs with Persistent Chat rooms.</span></span> <span data-ttu-id="59e79-107">Ces URL s’affichent sur le client dans la salle de conversation, dans le volet d’extensibilité de conversation.</span><span class="sxs-lookup"><span data-stu-id="59e79-107">These URLs appear in the client in the chat room in the conversation extensibility pane.</span></span> <span data-ttu-id="59e79-108">Un administrateur doit ajouter Compléments à la liste des compléments enregistrés et les créateurs/responsables de salles de conversation doivent associer les salles à l’un des compléments enregistrés pour que les utilisateurs puissent voir cette mise à niveau sur leur client.</span><span class="sxs-lookup"><span data-stu-id="59e79-108">An administrator must add Add-ins to the list of registered add-ins, and chat room managers/Creators must associate rooms with one of the registered add-ins before users can see this upgrade in their client.</span></span>
  
<span data-ttu-id="59e79-109">Les compléments servent à étendre l’expérience dans la salle.</span><span class="sxs-lookup"><span data-stu-id="59e79-109">Add-ins are used to extend the in-room experience.</span></span> <span data-ttu-id="59e79-110">Un complément typique peut contenir une URL pointant vers une application Silverlight qui intercepte lorsqu’un téléscripteur est publié dans une salle de conversation et affiche l’historique des actions dans le volet de l’extensibilité.</span><span class="sxs-lookup"><span data-stu-id="59e79-110">A typical add-in might include a URL pointing to a Silverlight application that intercepts when a stock ticker is posted to a chat room, and shows the stock history in the extensibility pane.</span></span> <span data-ttu-id="59e79-111">En guise d’autre exemple, citons l’incorporation d’une URL OneNote 2013 dans la salle de conversation en tant que complément servant à inclure un contexte partagé, comme « Tête de liste » ou « Sujet du jour ».</span><span class="sxs-lookup"><span data-stu-id="59e79-111">Other examples include embedding a OneNote 2013 URL in the chat room as an add-in to include some shared context, such as "Top of mind" or "Topic of the day."</span></span>
  
<span data-ttu-id="59e79-112">Pour créer des compléments pour les salles de conversation permanente, consultez [configurer des compléments pour les salles de conversation permanente dans Skype pour Business Server 2015](../../manage/persistent-chat/configure-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="59e79-112">To create Add-ins for Persistent Chat rooms, see [Configure add-ins for Persistent Chat rooms in Skype for Business Server 2015](../../manage/persistent-chat/configure-add-ins.md).</span></span> <span data-ttu-id="59e79-113">Si vous êtes un administrateur de conversation permanente, vous pouvez créer des compléments à l’aide du Panneau de configuration ou les applets de commande Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="59e79-113">If you are a Persistent Chat Administrator, you can create add-ins by using the control panel or Windows PowerShell cmdlets.</span></span>
  
## <a name="tasks-you-can-perform"></a><span data-ttu-id="59e79-114">Tâches que vous pouvez effectuer</span><span class="sxs-lookup"><span data-stu-id="59e79-114">Tasks you can perform</span></span>

<span data-ttu-id="59e79-115">Dans la page **Complément**, vous pouvez effectuer les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="59e79-115">You can perform the following tasks on the **Add-in** page:</span></span>
  
- [<span data-ttu-id="59e79-116">Configuration des compléments des salles de conversation permanente dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="59e79-116">Configure add-ins for Persistent Chat rooms in Skype for Business Server 2015</span></span>](../../manage/persistent-chat/configure-add-ins.md)
    
## <a name="to-configure-add-ins-for-chat-rooms"></a><span data-ttu-id="59e79-117">Configuration des compléments pour des salles de conversation</span><span class="sxs-lookup"><span data-stu-id="59e79-117">To configure Add-ins for chat rooms</span></span>

<span data-ttu-id="59e79-118">Les listes ci-dessous décrivent les menus, les commandes, les champs et les propriétés de la page.</span><span class="sxs-lookup"><span data-stu-id="59e79-118">The following lists describe the menus, command, fields, and properties on the page.</span></span>
  
1. <span data-ttu-id="59e79-119">À partir d’un compte d’utilisateur auquel le rôle CsPersistentChatAdministrator ou CsAdministrator est affecté, connectez-vous à un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="59e79-119">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="59e79-120">Dans le menu **Démarrer** , sélectionnez le Skype pour le panneau de configuration serveur Business ou ouvrir une fenêtre de navigateur, puis entrez l’URL d’administration.</span><span class="sxs-lookup"><span data-stu-id="59e79-120">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="59e79-121">Pour plus d’informations sur les différentes méthodes que vous pouvez utiliser pour démarrer le panneau de configuration, voir [Ouvrir Outils d’administration Lync Server](http://technet.microsoft.com/library/8c58de94-9e0a-4368-9e14-9afcaa1142d0.aspx).</span><span class="sxs-lookup"><span data-stu-id="59e79-121">For details about the different methods that you can use to start control panel, see [Open Lync Server Administrative Tools](http://technet.microsoft.com/library/8c58de94-9e0a-4368-9e14-9afcaa1142d0.aspx).</span></span>
    
3. <span data-ttu-id="59e79-122">Dans la barre de navigation de gauche, cliquez sur **Conversation permanente**, puis sur **Complément**.</span><span class="sxs-lookup"><span data-stu-id="59e79-122">In the left navigation bar, click **Persistent Chat**, and then click **Add-in**.</span></span>
    
    <span data-ttu-id="59e79-123">Pour les déploiements de plusieurs pools de serveurs de conversation permanente, sélectionnez le pool approprié dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="59e79-123">For multiple Persistent Chat Server pool deployments, select the appropriate pool from the drop-down list.</span></span>
    
4. <span data-ttu-id="59e79-124">Dans la page **Complément**, cliquez sur **Créer**.</span><span class="sxs-lookup"><span data-stu-id="59e79-124">On the **Add-in** page, click **New**.</span></span>
    
5. <span data-ttu-id="59e79-125">Dans **Sélectionner un Service**, sélectionnez le service correspondant au pool de serveurs de conversation permanente où vous avez besoin pour créer le complément.</span><span class="sxs-lookup"><span data-stu-id="59e79-125">In **Select a Service**, select the service corresponding to the Persistent Chat Server pool where you need to create the Add-in.</span></span> <span data-ttu-id="59e79-126">Les compléments ne peuvent pas être déplacés d’un pool vers un autre ou partagés entre les différents pools.</span><span class="sxs-lookup"><span data-stu-id="59e79-126">Add-ins cannot be moved from one pool to another or shared between different pools.</span></span>
    
6. <span data-ttu-id="59e79-127">Dans **Nouveau complément**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="59e79-127">In **New Add-in**, do the following:</span></span>
    
  - <span data-ttu-id="59e79-128">Dans **Nom**, spécifiez un nom pour le nouveau complément.</span><span class="sxs-lookup"><span data-stu-id="59e79-128">In **Name**, specify a name for the new add-in.</span></span>
    
  - <span data-ttu-id="59e79-p107">Dans **URL**, spécifiez l’URL à associer au complément. Les URL sont limitées aux protocoles http et https.</span><span class="sxs-lookup"><span data-stu-id="59e79-p107">In **URL**, specify the URL to be associated with the add-in. URLs are limited to http and https protocols.</span></span>
    
7. <span data-ttu-id="59e79-131">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="59e79-131">Click **Commit**.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="59e79-132">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="59e79-132">See also</span></span>

<span data-ttu-id="59e79-133">Pour plus d’informations sur le serveur de conversation permanente des fonctionnalités, voir [Plan for Persistent Chat Server dans Skype pour Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md), [déployer Persistent Chat Server dans Skype pour Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)et [gérer le serveur de conversation permanente dans Skype pour Business Server 2015](../../manage/persistent-chat/persistent-chat.md).</span><span class="sxs-lookup"><span data-stu-id="59e79-133">For details about Persistent Chat Server features and capabilities, see [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md), [Deploy Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md), and [Manage Persistent Chat Server in Skype for Business Server 2015](../../manage/persistent-chat/persistent-chat.md).</span></span>
  

