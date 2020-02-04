---
title: Complément de conversation permanente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.PersistentChatAddin
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 66124a70-67e8-4bda-9da5-8ab13afccf49
description: Vous pouvez utiliser la section complément de la page de conversation permanente pour associer des URL à des salles de conversation permanentes. Ces URL s’affichent sur le client dans la salle de conversation, dans le volet d’extensibilité de conversation. Un administrateur doit ajouter Compléments à la liste de compléments enregistrés et les créateurs/responsables de salles de conversation doivent associer les salles à l’un des compléments enregistrés pour que les utilisateurs puissent voir cette mise à niveau sur leur client.
ms.openlocfilehash: da971a43c8e113dc1fff8ee9dc600f55a2fea955
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41686217"
---
# <a name="persistent-chat-add-in"></a><span data-ttu-id="08f57-105">Complément de conversation permanente</span><span class="sxs-lookup"><span data-stu-id="08f57-105">Persistent Chat Add-in</span></span>

<span data-ttu-id="08f57-106">Vous pouvez utiliser la section **complément** de la page de **conversation permanente** pour associer des URL à des salles de conversation permanentes.</span><span class="sxs-lookup"><span data-stu-id="08f57-106">You can use the **Add-in** section of the **Persistent Chat** page to associate URLs with Persistent Chat rooms.</span></span> <span data-ttu-id="08f57-107">Ces URL s’affichent sur le client dans la salle de conversation, dans le volet d’extensibilité de conversation.</span><span class="sxs-lookup"><span data-stu-id="08f57-107">These URLs appear in the client in the chat room in the conversation extensibility pane.</span></span> <span data-ttu-id="08f57-108">Un administrateur doit ajouter Compléments à la liste de compléments enregistrés et les créateurs/responsables de salles de conversation doivent associer les salles à l’un des compléments enregistrés pour que les utilisateurs puissent voir cette mise à niveau sur leur client.</span><span class="sxs-lookup"><span data-stu-id="08f57-108">An administrator must add Add-ins to the list of registered add-ins, and chat room managers/Creators must associate rooms with one of the registered add-ins before users can see this upgrade in their client.</span></span>

<span data-ttu-id="08f57-109">Les compléments servent à étendre l’expérience dans la salle.</span><span class="sxs-lookup"><span data-stu-id="08f57-109">Add-ins are used to extend the in-room experience.</span></span> <span data-ttu-id="08f57-110">Un complément classique peut inclure une URL pointant vers une application Silverlight qui intercepte quand un code d’action est publié dans une salle de conversation et affiche l’historique des actions dans le volet extensibilité.</span><span class="sxs-lookup"><span data-stu-id="08f57-110">A typical add-in might include a URL pointing to a Silverlight application that intercepts when a stock ticker is posted to a chat room, and shows the stock history in the extensibility pane.</span></span> <span data-ttu-id="08f57-111">En guise d’autre exemple, citons l’incorporation d’une URL OneNote 2013 dans la salle de conversation en tant que complément servant à inclure un contexte partagé, comme « Tête de liste » ou « Sujet du jour ».</span><span class="sxs-lookup"><span data-stu-id="08f57-111">Other examples include embedding a OneNote 2013 URL in the chat room as an add-in to include some shared context, such as "Top of mind" or "Topic of the day."</span></span>

<span data-ttu-id="08f57-112">Pour créer des compléments pour des salles de conversation permanentes, voir [configurer des compléments pour les salles de conversation permanentes dans Skype entreprise Server 2015](../../manage/persistent-chat/configure-add-ins.md).</span><span class="sxs-lookup"><span data-stu-id="08f57-112">To create Add-ins for Persistent Chat rooms, see [Configure add-ins for Persistent Chat rooms in Skype for Business Server 2015](../../manage/persistent-chat/configure-add-ins.md).</span></span> <span data-ttu-id="08f57-113">Si vous êtes un administrateur de chat permanent, vous pouvez créer des compléments à l’aide du panneau de configuration ou des applets de commande Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="08f57-113">If you are a Persistent Chat Administrator, you can create add-ins by using the control panel or Windows PowerShell cmdlets.</span></span>

## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="08f57-114">Tâches que vous pouvez effectuer</span><span class="sxs-lookup"><span data-stu-id="08f57-114">Tasks that you can perform</span></span>

<span data-ttu-id="08f57-115">Dans la page **Complément**, vous pouvez effectuer les tâches suivantes :</span><span class="sxs-lookup"><span data-stu-id="08f57-115">You can perform the following tasks on the **Add-in** page:</span></span>

- [<span data-ttu-id="08f57-116">Configuration des compléments des salles de conversation permanente dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="08f57-116">Configure add-ins for Persistent Chat rooms in Skype for Business Server 2015</span></span>](../../manage/persistent-chat/configure-add-ins.md)

## <a name="to-configure-add-ins-for-chat-rooms"></a><span data-ttu-id="08f57-117">Configuration des compléments pour des salles de conversation</span><span class="sxs-lookup"><span data-stu-id="08f57-117">To configure Add-ins for chat rooms</span></span>

<span data-ttu-id="08f57-118">Les listes ci-dessous décrivent les menus, les commandes, les champs et les propriétés de la page.</span><span class="sxs-lookup"><span data-stu-id="08f57-118">The following lists describe the menus, command, fields, and properties on the page.</span></span>

1. <span data-ttu-id="08f57-119">À partir d’un compte d’utilisateur auquel le rôle CsPersistentChatAdministrator ou CsAdministrator est affecté, connectez-vous à un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="08f57-119">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2. <span data-ttu-id="08f57-120">Dans le menu **Démarrer** , sélectionnez le panneau de configuration Skype entreprise Server ou ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration.</span><span class="sxs-lookup"><span data-stu-id="08f57-120">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="08f57-121">Pour plus d’informations sur les différentes méthodes permettant de lancer le panneau de configuration, reportez-vous à la rubrique [Open Lync Server Administrative Tools](https://technet.microsoft.com/library/8c58de94-9e0a-4368-9e14-9afcaa1142d0.aspx).</span><span class="sxs-lookup"><span data-stu-id="08f57-121">For details about the different methods that you can use to start the control panel, see [Open Lync Server Administrative Tools](https://technet.microsoft.com/library/8c58de94-9e0a-4368-9e14-9afcaa1142d0.aspx).</span></span>

3. <span data-ttu-id="08f57-122">Dans la barre de navigation de gauche, cliquez sur **Conversation permanente**, puis sur **Complément**.</span><span class="sxs-lookup"><span data-stu-id="08f57-122">In the left navigation bar, click **Persistent Chat**, and then click **Add-in**.</span></span>

    <span data-ttu-id="08f57-123">Dans la liste déroulante des déploiements de pools de serveurs de chat permanent, sélectionnez le pool approprié.</span><span class="sxs-lookup"><span data-stu-id="08f57-123">For multiple Persistent Chat Server pool deployments, select the appropriate pool from the drop-down list.</span></span>

4. <span data-ttu-id="08f57-124">Dans la page **Complément**, cliquez sur **Créer**.</span><span class="sxs-lookup"><span data-stu-id="08f57-124">On the **Add-in** page, click **New**.</span></span>

5. <span data-ttu-id="08f57-125">Dans **Sélectionner un service**, sélectionnez le service correspondant au pool de serveurs de chat permanent pour lequel vous devez créer le complément.</span><span class="sxs-lookup"><span data-stu-id="08f57-125">In **Select a Service**, select the service corresponding to the Persistent Chat Server pool where you need to create the Add-in.</span></span> <span data-ttu-id="08f57-126">Les compléments ne peuvent pas être déplacés d’un pool vers un autre ou partagés entre les différents pools.</span><span class="sxs-lookup"><span data-stu-id="08f57-126">Add-ins cannot be moved from one pool to another or shared between different pools.</span></span>

6. <span data-ttu-id="08f57-127">Dans **Nouveau complément**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="08f57-127">In **New Add-in**, do the following:</span></span>

   - <span data-ttu-id="08f57-128">Dans **Nom**, spécifiez un nom pour le nouveau complément.</span><span class="sxs-lookup"><span data-stu-id="08f57-128">In **Name**, specify a name for the new add-in.</span></span>

   - <span data-ttu-id="08f57-p107">Dans **URL**, spécifiez l’URL à associer au complément. Les URL sont limitées aux protocoles http et https.</span><span class="sxs-lookup"><span data-stu-id="08f57-p107">In **URL**, specify the URL to be associated with the add-in. URLs are limited to http and https protocols.</span></span>

7. <span data-ttu-id="08f57-131">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="08f57-131">Click **Commit**.</span></span>

## <a name="see-also"></a><span data-ttu-id="08f57-132">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="08f57-132">See also</span></span>

<span data-ttu-id="08f57-133">Pour plus d’informations sur les fonctionnalités et les fonctionnalités du serveur de chat permanent, voir [planifier le serveur de chat permanent dans Skype entreprise server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md), [déployer le serveur de conversation permanente dans skype entreprise Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)et [gérer le serveur de conversation permanent dans Skype entreprise Server 2015](../../manage/persistent-chat/persistent-chat.md).</span><span class="sxs-lookup"><span data-stu-id="08f57-133">For details about Persistent Chat Server features and capabilities, see [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md), [Deploy Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md), and [Manage Persistent Chat Server in Skype for Business Server 2015](../../manage/persistent-chat/persistent-chat.md).</span></span>


