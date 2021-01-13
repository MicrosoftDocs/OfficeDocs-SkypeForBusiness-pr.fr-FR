---
title: Configuration des add-ins pour les salles de conversation permanente dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c1037909-0750-411a-98c1-3a327eed4ae8
description: 'Résumé : Découvrez comment configurer des add-ins pour les salles de conversation du serveur de conversation permanente dans Skype Entreprise Server 2015.'
ms.openlocfilehash: 1aca54f3db1229527256d1e2801cb057f4f79387
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815075"
---
# <a name="configure-add-ins-for-persistent-chat-rooms-in-skype-for-business-server-2015"></a><span data-ttu-id="882f6-103">Configuration des add-ins pour les salles de conversation permanente dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="882f6-103">Configure add-ins for Persistent Chat rooms in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="882f6-104">**Résumé :** Découvrez comment configurer des add-ins pour les salles de conversation du serveur de conversation permanente dans Skype Entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="882f6-104">**Summary:** Learn how to configure add-ins for Persistent Chat Server chat rooms in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="882f6-105">Les add-ins sont utilisés pour étendre l’expérience dans la salle en associant des URL à des salles de conversation.</span><span class="sxs-lookup"><span data-stu-id="882f6-105">Add-ins are used to extend the in-room experience by associating URLs with chat rooms.</span></span> <span data-ttu-id="882f6-106">Ces URL apparaissent dans le volet d’extensibilité de conversation client.</span><span class="sxs-lookup"><span data-stu-id="882f6-106">These URLs appear in the client conversation extensibility pane.</span></span> <span data-ttu-id="882f6-107">Un add-in type peut inclure une URL pointant vers une application Silverlight qui intercepte lorsqu’un ticker de stock est publié dans une salle de conversation et affiche l’historique des actions dans le volet d’extensibilité.</span><span class="sxs-lookup"><span data-stu-id="882f6-107">A typical add-in might include a URL pointing to a Silverlight application that intercepts when a stock ticker is posted to a chat room, and shows the stock history in the extensibility pane.</span></span> <span data-ttu-id="882f6-108">En guise d’autre exemple, citons l’incorporation d’une URL OneNote 2013 dans la salle de conversation en tant que complément pour inclure un contexte partagé, tel que « Tête de liste » ou « Sujet du jour ».</span><span class="sxs-lookup"><span data-stu-id="882f6-108">Other examples include embedding a OneNote 2013 URL in the chat room as an add-in to include some shared context, such as "Top of mind" or "Topic of the day."</span></span>
  
 <span data-ttu-id="882f6-109">Pour que les utilisateurs voient un add-in dans le client, vous devez l’ajouter à la liste des add-ins inscrits, et les responsables ou créateurs de salles de conversation doivent associer des salles au module.</span><span class="sxs-lookup"><span data-stu-id="882f6-109">Before users can see an add-in in the client, you must add the add-in to the list of registered add-ins, and chat room Managers or Creators need to associate rooms with the add-in.</span></span>
  
> [!NOTE]
> <span data-ttu-id="882f6-110">La conversation permanente est disponible dans Skype Entreprise Server 2015, mais n’est plus prise en charge dans Skype Entreprise Server 2019.</span><span class="sxs-lookup"><span data-stu-id="882f6-110">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="882f6-111">La même fonctionnalité est disponible dans Teams.</span><span class="sxs-lookup"><span data-stu-id="882f6-111">The same functionality is available in Teams.</span></span> <span data-ttu-id="882f6-112">Pour plus d’informations, voir [La mise à niveau de Microsoft Teams.](/microsoftteams/upgrade-start-here)</span><span class="sxs-lookup"><span data-stu-id="882f6-112">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="882f6-113">Si vous devez utiliser la conversation permanente, vous pouvez migrer les utilisateurs nécessitant cette fonctionnalité vers Teams ou continuer à utiliser Skype Entreprise Server 2015.</span><span class="sxs-lookup"><span data-stu-id="882f6-113">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

## <a name="configure-add-ins-for-chat-rooms-by-using-the-control-panel"></a><span data-ttu-id="882f6-114">Configurer des add-ins pour les salles de conversation à l’aide du Panneau de configuration</span><span class="sxs-lookup"><span data-stu-id="882f6-114">Configure add-ins for chat rooms by using the Control Panel</span></span>

<span data-ttu-id="882f6-115">Pour configurer des add-ins pour les salles de conversation à l’aide du Panneau de configuration :</span><span class="sxs-lookup"><span data-stu-id="882f6-115">To configure add-ins for chat rooms by using the Control Panel:</span></span>
  
1. <span data-ttu-id="882f6-116">À partir d’un compte auquel le rôle CsPersistentChatAdministrator ou CsAdministrator est assigné, connectez-vous à n’importe quel ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="882f6-116">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="882f6-117">Dans le menu **Démarrer,** sélectionnez le Panneau de contrôle Skype Entreprise Server ou ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration.</span><span class="sxs-lookup"><span data-stu-id="882f6-117">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="882f6-118">Dans la barre de navigation de gauche, cliquez sur **Conversation permanente**, puis sur **Complément**.</span><span class="sxs-lookup"><span data-stu-id="882f6-118">In the left navigation bar, click **Persistent Chat**, and then click **Add-in**.</span></span>
    
    <span data-ttu-id="882f6-119">Pour plusieurs déploiements de pool de serveurs de conversation permanente, sélectionnez le pool approprié dans la liste finale.</span><span class="sxs-lookup"><span data-stu-id="882f6-119">For multiple Persistent Chat Server pool deployments, select the appropriate pool from the drop-down list.</span></span>
    
4. <span data-ttu-id="882f6-120">Dans la page **Complément**, cliquez sur **Nouveau**.</span><span class="sxs-lookup"><span data-stu-id="882f6-120">On the **Add-in** page, click **New**.</span></span>
    
5. <span data-ttu-id="882f6-121">Dans **Sélectionner un service,** sélectionnez le service correspondant au pool de serveurs de conversation permanente où vous devez créer le add-in.</span><span class="sxs-lookup"><span data-stu-id="882f6-121">In **Select a Service**, select the service corresponding to the Persistent Chat Server pool where you need to create the Add-in.</span></span> <span data-ttu-id="882f6-122">Les compléments ne peuvent pas être déplacés d’un pool à un autre ou partagés parmi différents pools.</span><span class="sxs-lookup"><span data-stu-id="882f6-122">Add-ins cannot be moved from one pool to another or shared between different pools.</span></span>
    
6. <span data-ttu-id="882f6-123">Dans **Nouveau complément**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="882f6-123">In **New Add-in**, do the following:</span></span>
    
   - <span data-ttu-id="882f6-124">Dans **Nom**, spécifiez un nom pour le nouveau complément.</span><span class="sxs-lookup"><span data-stu-id="882f6-124">In **Name**, specify a name for the new add-in.</span></span>
    
   - <span data-ttu-id="882f6-125">Dans **URL**, spécifiez l’URL à associer au complément.</span><span class="sxs-lookup"><span data-stu-id="882f6-125">In **URL**, specify the URL to be associated with the add-in.</span></span> <span data-ttu-id="882f6-126">Les URL sont limitées aux protocoles http et https.</span><span class="sxs-lookup"><span data-stu-id="882f6-126">URLs are limited to the http and https protocols.</span></span>
    
7. <span data-ttu-id="882f6-127">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="882f6-127">Click **Commit**.</span></span>
    
## <a name="configure-add-ins-by-using-windows-powershell"></a><span data-ttu-id="882f6-128">Configurer des Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="882f6-128">Configure add-ins by using Windows PowerShell</span></span>

<span data-ttu-id="882f6-129">Vous pouvez configurer des add-ins pour les salles de conversation à l’aide des cmdlets Windows PowerShell suivantes.</span><span class="sxs-lookup"><span data-stu-id="882f6-129">You can configure add-ins for chat rooms by using the following Windows PowerShell cmdlets.</span></span> <span data-ttu-id="882f6-130">Pour plus d’informations sur la syntaxe, y compris tous les paramètres disponibles, voir [Skype Entreprise Server 2015 Management Shell](../management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="882f6-130">For details about syntax, including all available parameters, see [Skype for Business Server 2015 Management Shell](../management-shell.md).</span></span>
  

|<span data-ttu-id="882f6-131">**Applet de commande**</span><span class="sxs-lookup"><span data-stu-id="882f6-131">**Cmdlet**</span></span>|<span data-ttu-id="882f6-132">**Description**</span><span class="sxs-lookup"><span data-stu-id="882f6-132">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="882f6-133">New-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="882f6-133">New-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="882f6-134">Créer un nouveau add-in</span><span class="sxs-lookup"><span data-stu-id="882f6-134">Create a new add-in</span></span>  <br/> |
|<span data-ttu-id="882f6-135">Set-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="882f6-135">Set-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="882f6-136">Configurer les paramètres d’un add-in existant</span><span class="sxs-lookup"><span data-stu-id="882f6-136">Configure settings for an existing add-in</span></span>  <br/> |
|<span data-ttu-id="882f6-137">Get-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="882f6-137">Get-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="882f6-138">Récupérer des informations sur les modules complémentaires</span><span class="sxs-lookup"><span data-stu-id="882f6-138">Retrieve information about add-ins</span></span>  <br/> |
|<span data-ttu-id="882f6-139">Remove-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="882f6-139">Remove-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="882f6-140">Supprimer un add-in</span><span class="sxs-lookup"><span data-stu-id="882f6-140">Remove an add-in</span></span>  <br/> |
   
### <a name="create-a-new-add-in"></a><span data-ttu-id="882f6-141">Créer un nouveau add-in</span><span class="sxs-lookup"><span data-stu-id="882f6-141">Create a new add-in</span></span>

<span data-ttu-id="882f6-142">Vous pouvez créer un nouveau add-in à l’aide de l’cmdlet **New-CsPersistentChatAddin.**</span><span class="sxs-lookup"><span data-stu-id="882f6-142">You can create a new Add-in by using the **New-CsPersistentChatAddin** cmdlet.</span></span>
  
<span data-ttu-id="882f6-143">Par exemple, la commande suivante crée un nouveau module (avec le nom ITPersistentChatAddin) pour le pool atl-cs-001.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="882f6-143">For example, the following command creates a new add-in (with the name ITPersistentChatAddin) for the pool atl-cs-001.contoso.com.</span></span> <span data-ttu-id="882f6-144">Le paramètre URL et la valeur de paramètre spécifient l’emplacement de la page http://atl-cs-001.contoso.com/itchat web du add-in :</span><span class="sxs-lookup"><span data-stu-id="882f6-144">The URL parameter and the parameter value http://atl-cs-001.contoso.com/itchat specify the location of the add-in's webpage:</span></span>
  
```PowerShell
New-CsPersistentChatAddin -Name "ITPersistentChatAddin" -PersistentChatPoolFqdn "atl-cs-001.contoso.com" -Url "http://atl-cs-001.contoso.com/itchat"
```

### <a name="configure-settings-for-an-existing-add-in"></a><span data-ttu-id="882f6-145">Configurer les paramètres d’un add-in existant</span><span class="sxs-lookup"><span data-stu-id="882f6-145">Configure settings for an existing add-in</span></span>

<span data-ttu-id="882f6-146">Vous pouvez configurer les paramètres d’un application existante à l’aide de l’cmdlet **Set-CsPersistentChatAddIn.**</span><span class="sxs-lookup"><span data-stu-id="882f6-146">You can configure settings for an existing add-in by using the **Set-CsPersistentChatAddIn** cmdlet.</span></span> <span data-ttu-id="882f6-147">Par exemple, la commande suivante modifie l’URL attribuée au module de conversation permanente ITPersistentChatAddin.</span><span class="sxs-lookup"><span data-stu-id="882f6-147">For example, the following command modifies the URL assigned to the Persistent Chat add-in ITPersistentChatAddin.</span></span> <span data-ttu-id="882f6-148">Dans ce cas, l’URL est modifiée en http://atl-cs-001.contoso.com/itchat2:</span><span class="sxs-lookup"><span data-stu-id="882f6-148">In this case, the URL is changed to http://atl-cs-001.contoso.com/itchat2:</span></span>
  
```PowerShell
Set-CsPersistentChatAddin -Identity "atl-cs-001.contoso.com\ITPersistentChatAddin" -Url "http://atl-cs-001.contoso.com/itchat2"
```

### <a name="retrieve-information-about-add-ins"></a><span data-ttu-id="882f6-149">Récupérer des informations sur les modules complémentaires</span><span class="sxs-lookup"><span data-stu-id="882f6-149">Retrieve information about add-ins</span></span>

<span data-ttu-id="882f6-150">Vous pouvez obtenir des informations sur les modules complémentaires à l’aide de l’cmdlet **Get-CsPersistentChatAddin.**</span><span class="sxs-lookup"><span data-stu-id="882f6-150">You can get information about add-ins by using the **Get-CsPersistentChatAddin** cmdlet.</span></span> <span data-ttu-id="882f6-151">Par exemple, la commande suivante retourne des informations sur tous les modules de conversation permanente configurés pour être utilisés dans l’organisation :</span><span class="sxs-lookup"><span data-stu-id="882f6-151">For example, the following command returns information about all the Persistent Chat add-ins configured for use in the organization:</span></span>
  
```PowerShell
Get-CsPersistentChatAddin
```

### <a name="remove-an-add-in"></a><span data-ttu-id="882f6-152">Supprimer un add-in</span><span class="sxs-lookup"><span data-stu-id="882f6-152">Remove an add-in</span></span>

<span data-ttu-id="882f6-153">Vous pouvez supprimer un add-in à l’aide de **l’cmdlet Remove-CsPersistentChatAddIn.**</span><span class="sxs-lookup"><span data-stu-id="882f6-153">You can remove an Add-in by using the **Remove-CsPersistentChatAddIn** cmdlet.</span></span> <span data-ttu-id="882f6-154">Par exemple, la commande suivante supprime le add-in de conversation permanente ITChatAddin trouvé sur le pool atl-cs-001.contoso.com :</span><span class="sxs-lookup"><span data-stu-id="882f6-154">For example, the following command removes the Persistent Chat add-in ITChatAddin found on the pool atl-cs-001.contoso.com:</span></span>
  
```PowerShell
Remove-CsPersistentChatAddin -Identity "atl-cs-001.contoso.com\ITChatAddin"
```


