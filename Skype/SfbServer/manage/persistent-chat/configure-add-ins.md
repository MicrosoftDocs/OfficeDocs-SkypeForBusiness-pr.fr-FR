---
title: Configuration des compléments des salles de conversation permanente dans Skype Entreprise Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c1037909-0750-411a-98c1-3a327eed4ae8
description: 'Résumé : Découvrez comment configurer des compléments pour les salles de conversation Persistent Chat Server Skype pour Business Server 2015.'
ms.openlocfilehash: 64017115370c24c8c4a117f595230a6f5f741afd
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569964"
---
# <a name="configure-add-ins-for-persistent-chat-rooms-in-skype-for-business-server-2015"></a><span data-ttu-id="0280d-103">Configuration des compléments des salles de conversation permanente dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="0280d-103">Configure add-ins for Persistent Chat rooms in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="0280d-104">**Résumé :** Découvrez comment configurer des compléments pour les salles de conversation Persistent Chat Server Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="0280d-104">**Summary:** Learn how to configure add-ins for Persistent Chat Server chat rooms in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="0280d-105">Les compléments servent à étendre l’expérience dans la salle en associant des URL à des salles de conversation.</span><span class="sxs-lookup"><span data-stu-id="0280d-105">Add-ins are used to extend the in-room experience by associating URLs with chat rooms.</span></span> <span data-ttu-id="0280d-106">Ces URL apparaissent dans le volet d’extensibilité de conversation client.</span><span class="sxs-lookup"><span data-stu-id="0280d-106">These URLs appear in the client conversation extensibility pane.</span></span> <span data-ttu-id="0280d-107">Un complément typique peut contenir une URL pointant vers une application Silverlight qui intercepte lorsqu’un téléscripteur est publié dans une salle de conversation et affiche l’historique des actions dans le volet de l’extensibilité.</span><span class="sxs-lookup"><span data-stu-id="0280d-107">A typical add-in might include a URL pointing to a Silverlight application that intercepts when a stock ticker is posted to a chat room, and shows the stock history in the extensibility pane.</span></span> <span data-ttu-id="0280d-108">En guise d’autre exemple, citons l’incorporation d’une URL OneNote 2013 dans la salle de conversation en tant que complément servant à inclure un contexte partagé, comme « Tête de liste » ou « Sujet du jour ».</span><span class="sxs-lookup"><span data-stu-id="0280d-108">Other examples include embedding a OneNote 2013 URL in the chat room as an add-in to include some shared context, such as "Top of mind" or "Topic of the day."</span></span>
  
 <span data-ttu-id="0280d-109">Avant que les utilisateurs puissent voir un complément dans le client, vous devez ajouter le complément à la liste des compléments enregistrés, et les responsables ou créateurs de salles de conversation doivent associer des salles au complément.</span><span class="sxs-lookup"><span data-stu-id="0280d-109">Before users can see an add-in in the client, you must add the add-in to the list of registered add-ins, and chat room Managers or Creators need to associate rooms with the add-in.</span></span>
  
## <a name="configure-add-ins-for-chat-rooms-by-using-the-control-panel"></a><span data-ttu-id="0280d-110">Configurer des compléments pour les salles de conversation en utilisant le Panneau de configuration</span><span class="sxs-lookup"><span data-stu-id="0280d-110">Configure add-ins for chat rooms by using the Control Panel</span></span>

<span data-ttu-id="0280d-111">Pour configurer compléments pour les salles de conversation en utilisant le Panneau de configuration :</span><span class="sxs-lookup"><span data-stu-id="0280d-111">To configure add-ins for chat rooms by using the Control Panel:</span></span>
  
1. <span data-ttu-id="0280d-112">À partir d’un compte auquel le rôle CsPersistentChatAdministrator ou CsAdministrator est affecté, connectez-vous à n’importe quel un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="0280d-112">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="0280d-113">Dans le menu **Démarrer** , sélectionnez le Skype pour le panneau de configuration serveur Business ou ouvrir une fenêtre de navigateur, puis entrez l’URL d’administration.</span><span class="sxs-lookup"><span data-stu-id="0280d-113">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="0280d-114">Dans la barre de navigation de gauche, cliquez sur **Conversation permanente**, puis sur **Complément**.</span><span class="sxs-lookup"><span data-stu-id="0280d-114">In the left navigation bar, click **Persistent Chat**, and then click **Add-in**.</span></span>
    
    <span data-ttu-id="0280d-115">Pour les déploiements de plusieurs pools de serveurs de conversation permanente, sélectionnez le pool approprié dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="0280d-115">For multiple Persistent Chat Server pool deployments, select the appropriate pool from the drop-down list.</span></span>
    
4. <span data-ttu-id="0280d-116">Dans la page **Complément**, cliquez sur **Créer**.</span><span class="sxs-lookup"><span data-stu-id="0280d-116">On the **Add-in** page, click **New**.</span></span>
    
5. <span data-ttu-id="0280d-117">Dans **Sélectionner un Service**, sélectionnez le service correspondant au pool de serveurs de conversation permanente où vous avez besoin pour créer le complément.</span><span class="sxs-lookup"><span data-stu-id="0280d-117">In **Select a Service**, select the service corresponding to the Persistent Chat Server pool where you need to create the Add-in.</span></span> <span data-ttu-id="0280d-118">Les compléments ne peuvent pas être déplacés d’un pool vers un autre ou partagés entre les différents pools.</span><span class="sxs-lookup"><span data-stu-id="0280d-118">Add-ins cannot be moved from one pool to another or shared between different pools.</span></span>
    
6. <span data-ttu-id="0280d-119">Dans **Nouveau complément**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="0280d-119">In **New Add-in**, do the following:</span></span>
    
  - <span data-ttu-id="0280d-120">Dans **Nom**, spécifiez un nom pour le nouveau complément.</span><span class="sxs-lookup"><span data-stu-id="0280d-120">In **Name**, specify a name for the new add-in.</span></span>
    
  - <span data-ttu-id="0280d-p103">Dans **URL**, spécifiez l’URL à associer au complément. Les URL sont limitées aux protocoles http et https.</span><span class="sxs-lookup"><span data-stu-id="0280d-p103">In **URL**, specify the URL to be associated with the add-in. URLs are limited to the http and https protocols.</span></span>
    
7. <span data-ttu-id="0280d-123">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="0280d-123">Click **Commit**.</span></span>
    
## <a name="configure-add-ins-by-using-windows-powershell"></a><span data-ttu-id="0280d-124">Configurer des compléments via Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0280d-124">Configure add-ins by using Windows PowerShell</span></span>

<span data-ttu-id="0280d-125">Vous pouvez configurer des compléments pour les salles de conversation en utilisant les applets de commande Windows PowerShell suivantes.</span><span class="sxs-lookup"><span data-stu-id="0280d-125">You can configure add-ins for chat rooms by using the following Windows PowerShell cmdlets.</span></span> <span data-ttu-id="0280d-126">Pour plus d’informations sur la syntaxe, y compris tous les paramètres disponibles, voir [Skype pour Business Server 2015 Management Shell](../management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="0280d-126">For details about syntax, including all available parameters, see [Skype for Business Server 2015 Management Shell](../management-shell.md).</span></span>
  

|<span data-ttu-id="0280d-127">**Applet de commande**</span><span class="sxs-lookup"><span data-stu-id="0280d-127">**Cmdlet**</span></span>|<span data-ttu-id="0280d-128">**Description**</span><span class="sxs-lookup"><span data-stu-id="0280d-128">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="0280d-129">New-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="0280d-129">New-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="0280d-130">Créer un complément</span><span class="sxs-lookup"><span data-stu-id="0280d-130">Create a new add-in</span></span>  <br/> |
|<span data-ttu-id="0280d-131">Set-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="0280d-131">Set-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="0280d-132">Configurer des paramètres pour un complément existant</span><span class="sxs-lookup"><span data-stu-id="0280d-132">Configure settings for an existing add-in</span></span>  <br/> |
|<span data-ttu-id="0280d-133">Get-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="0280d-133">Get-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="0280d-134">Récupérer des informations sur les compléments</span><span class="sxs-lookup"><span data-stu-id="0280d-134">Retrieve information about add-ins</span></span>  <br/> |
|<span data-ttu-id="0280d-135">Remove-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="0280d-135">Remove-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="0280d-136">Supprimer un complément</span><span class="sxs-lookup"><span data-stu-id="0280d-136">Remove an add-in</span></span>  <br/> |
   
### <a name="create-a-new-add-in"></a><span data-ttu-id="0280d-137">Créer un complément</span><span class="sxs-lookup"><span data-stu-id="0280d-137">Create a new add-in</span></span>

<span data-ttu-id="0280d-138">Vous pouvez créer un complément à l’aide de l’applet de commande **New-CsPersistentChatAddin** .</span><span class="sxs-lookup"><span data-stu-id="0280d-138">You can create a new Add-in by using the **New-CsPersistentChatAddin** cmdlet.</span></span>
  
<span data-ttu-id="0280d-139">Par exemple, la commande suivante crée un nouveau complément (avec le nom ITPersistentChatAddin) pour le pool atl-cs-001.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="0280d-139">For example, the following command creates a new add-in (with the name ITPersistentChatAddin) for the pool atl-cs-001.contoso.com.</span></span> <span data-ttu-id="0280d-140">Le paramètre URL et la valeur du paramètre http://atl-cs-001.contoso.com/itchat spécifiez l’emplacement de la page de la macro complémentaire :</span><span class="sxs-lookup"><span data-stu-id="0280d-140">The URL parameter and the parameter value http://atl-cs-001.contoso.com/itchat specify the location of the add-in's webpage:</span></span>
  
```
New-CsPersistentChatAddin -Name "ITPersistentChatAddin" -PersistentChatPoolFqdn "atl-cs-001.contoso.com" -Url "http://atl-cs-001.contoso.com/itchat"
```

### <a name="configure-settings-for-an-existing-add-in"></a><span data-ttu-id="0280d-141">Configurer des paramètres pour un complément existant</span><span class="sxs-lookup"><span data-stu-id="0280d-141">Configure settings for an existing add-in</span></span>

<span data-ttu-id="0280d-142">Vous pouvez configurer les paramètres d’un complément existant en utilisant l’applet de commande **Set-CsPersistentChatAddIn**.</span><span class="sxs-lookup"><span data-stu-id="0280d-142">You can configure settings for an existing add-in by using the **Set-CsPersistentChatAddIn** cmdlet.</span></span> <span data-ttu-id="0280d-143">Par exemple, la commande suivante modifie l’URL affecté au complément Conversation permanente ITPersistentChatAddin.</span><span class="sxs-lookup"><span data-stu-id="0280d-143">For example, the following command modifies the URL assigned to the Persistent Chat add-in ITPersistentChatAddin.</span></span> <span data-ttu-id="0280d-144">Dans ce cas, l’URL est remplacée parhttp://atl-cs-001.contoso.com/itchat2:</span><span class="sxs-lookup"><span data-stu-id="0280d-144">In this case, the URL is changed to http://atl-cs-001.contoso.com/itchat2:</span></span>
  
```
Set-CsPersistentChatAddin -Identity "atl-cs-001.contoso.com\ITPersistentChatAddin" -Url "http://atl-cs-001.contoso.com/itchat2"
```

### <a name="retrieve-information-about-add-ins"></a><span data-ttu-id="0280d-145">Récupérer des informations sur les compléments</span><span class="sxs-lookup"><span data-stu-id="0280d-145">Retrieve information about add-ins</span></span>

<span data-ttu-id="0280d-p107">Vous pouvez obtenir des informations sur les compléments en utilisant l’applet de commande **Get-CsPersistentChatAddin**. Par exemple, la commande suivante retourne des informations sur tous les compléments Conversation permanente à utiliser dans l’organisation :</span><span class="sxs-lookup"><span data-stu-id="0280d-p107">You can get information about add-ins by using the **Get-CsPersistentChatAddin** cmdlet. For example, the following command returns information about all the Persistent Chat add-ins configured for use in the organization:</span></span>
  
```
Get-CsPersistentChatAddin
```

### <a name="remove-an-add-in"></a><span data-ttu-id="0280d-148">Supprimer un complément</span><span class="sxs-lookup"><span data-stu-id="0280d-148">Remove an add-in</span></span>

<span data-ttu-id="0280d-149">Vous pouvez supprimer un complément à l’aide de l’applet de commande **Remove-CsPersistentChatAddIn** .</span><span class="sxs-lookup"><span data-stu-id="0280d-149">You can remove an Add-in by using the **Remove-CsPersistentChatAddIn** cmdlet.</span></span> <span data-ttu-id="0280d-150">Par exemple, la commande suivante supprime le complément Conversation permanente ITChatAddin trouvé dans le pool atl-cs-001.contoso.com :</span><span class="sxs-lookup"><span data-stu-id="0280d-150">For example, the following command removes the Persistent Chat add-in ITChatAddin found on the pool atl-cs-001.contoso.com:</span></span>
  
```
Remove-CsPersistentChatAddin -Identity "atl-cs-001.contoso.com\ITChatAddin"
```


