---
title: Configuration des compléments des salles de conversation permanente dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c1037909-0750-411a-98c1-3a327eed4ae8
description: 'Résumé : Découvrez comment configurer des compléments pour les salles de conversation Persistent Chat Server Skype pour Business Server 2015.'
ms.openlocfilehash: 146f05b181998f995b6e15b0717034a55f518d7f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33910255"
---
# <a name="configure-add-ins-for-persistent-chat-rooms-in-skype-for-business-server-2015"></a><span data-ttu-id="bd462-103">Configuration des compléments des salles de conversation permanente dans Skype Entreprise Server 2015</span><span class="sxs-lookup"><span data-stu-id="bd462-103">Configure add-ins for Persistent Chat rooms in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="bd462-104">**Résumé :** Découvrez comment configurer des compléments pour les salles de conversation Persistent Chat Server Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="bd462-104">**Summary:** Learn how to configure add-ins for Persistent Chat Server chat rooms in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="bd462-105">Les compléments servent à étendre l’expérience dans la salle en associant des URL à des salles de conversation.</span><span class="sxs-lookup"><span data-stu-id="bd462-105">Add-ins are used to extend the in-room experience by associating URLs with chat rooms.</span></span> <span data-ttu-id="bd462-106">Ces URL apparaissent dans le volet d’extensibilité de conversation client.</span><span class="sxs-lookup"><span data-stu-id="bd462-106">These URLs appear in the client conversation extensibility pane.</span></span> <span data-ttu-id="bd462-107">Un complément typique peut contenir une URL pointant vers une application Silverlight qui intercepte lorsqu’un téléscripteur est publié dans une salle de conversation et affiche l’historique des actions dans le volet de l’extensibilité.</span><span class="sxs-lookup"><span data-stu-id="bd462-107">A typical add-in might include a URL pointing to a Silverlight application that intercepts when a stock ticker is posted to a chat room, and shows the stock history in the extensibility pane.</span></span> <span data-ttu-id="bd462-108">En guise d’autre exemple, citons l’incorporation d’une URL OneNote 2013 dans la salle de conversation en tant que complément servant à inclure un contexte partagé, comme « Tête de liste » ou « Sujet du jour ».</span><span class="sxs-lookup"><span data-stu-id="bd462-108">Other examples include embedding a OneNote 2013 URL in the chat room as an add-in to include some shared context, such as "Top of mind" or "Topic of the day."</span></span>
  
 <span data-ttu-id="bd462-109">Avant que les utilisateurs puissent voir un complément dans le client, vous devez ajouter le complément à la liste des compléments enregistrés, et les responsables ou créateurs de salles de conversation doivent associer des salles au complément.</span><span class="sxs-lookup"><span data-stu-id="bd462-109">Before users can see an add-in in the client, you must add the add-in to the list of registered add-ins, and chat room Managers or Creators need to associate rooms with the add-in.</span></span>
  
> [!NOTE]
> <span data-ttu-id="bd462-110">Conversation permanente est disponible dans Skype pour Business Server 2015, mais n’est plus pris en charge dans Skype pour Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="bd462-110">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="bd462-111">La même fonctionnalité est disponible dans les équipes.</span><span class="sxs-lookup"><span data-stu-id="bd462-111">The same functionality is available in Teams.</span></span> <span data-ttu-id="bd462-112">Pour plus d’informations, voir [parcours de Skype pour les entreprises aux équipes de Microsoft](/microsoftteams/journey-skypeforbusiness-teams).</span><span class="sxs-lookup"><span data-stu-id="bd462-112">For more information, see [Journey from Skype for Business to Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span></span> <span data-ttu-id="bd462-113">Si vous devez utiliser la conversation permanente, vos choix est pour migrer les utilisateurs ayant besoin de cette fonctionnalité aux équipes, ou pour continuer à utiliser Skype pour Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="bd462-113">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

## <a name="configure-add-ins-for-chat-rooms-by-using-the-control-panel"></a><span data-ttu-id="bd462-114">Configurer des compléments pour les salles de conversation en utilisant le Panneau de configuration</span><span class="sxs-lookup"><span data-stu-id="bd462-114">Configure add-ins for chat rooms by using the Control Panel</span></span>

<span data-ttu-id="bd462-115">Pour configurer compléments pour les salles de conversation en utilisant le Panneau de configuration :</span><span class="sxs-lookup"><span data-stu-id="bd462-115">To configure add-ins for chat rooms by using the Control Panel:</span></span>
  
1. <span data-ttu-id="bd462-116">À partir d’un compte auquel le rôle CsPersistentChatAdministrator ou CsAdministrator est affecté, connectez-vous à n’importe quel un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="bd462-116">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="bd462-117">Dans le menu **Démarrer** , sélectionnez le Skype pour le panneau de configuration serveur Business ou ouvrir une fenêtre de navigateur, puis entrez l’URL d’administration.</span><span class="sxs-lookup"><span data-stu-id="bd462-117">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="bd462-118">Dans la barre de navigation de gauche, cliquez sur **Conversation permanente**, puis sur **Complément**.</span><span class="sxs-lookup"><span data-stu-id="bd462-118">In the left navigation bar, click **Persistent Chat**, and then click **Add-in**.</span></span>
    
    <span data-ttu-id="bd462-119">Pour les déploiements de plusieurs pools de serveurs de conversation permanente, sélectionnez le pool approprié dans la liste déroulante.</span><span class="sxs-lookup"><span data-stu-id="bd462-119">For multiple Persistent Chat Server pool deployments, select the appropriate pool from the drop-down list.</span></span>
    
4. <span data-ttu-id="bd462-120">Dans la page **Complément**, cliquez sur **Créer**.</span><span class="sxs-lookup"><span data-stu-id="bd462-120">On the **Add-in** page, click **New**.</span></span>
    
5. <span data-ttu-id="bd462-121">Dans **Sélectionner un Service**, sélectionnez le service correspondant au pool de serveurs de conversation permanente où vous avez besoin pour créer le complément.</span><span class="sxs-lookup"><span data-stu-id="bd462-121">In **Select a Service**, select the service corresponding to the Persistent Chat Server pool where you need to create the Add-in.</span></span> <span data-ttu-id="bd462-122">Les compléments ne peuvent pas être déplacés d’un pool vers un autre ou partagés entre les différents pools.</span><span class="sxs-lookup"><span data-stu-id="bd462-122">Add-ins cannot be moved from one pool to another or shared between different pools.</span></span>
    
6. <span data-ttu-id="bd462-123">Dans **Nouveau complément**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="bd462-123">In **New Add-in**, do the following:</span></span>
    
   - <span data-ttu-id="bd462-124">Dans **Nom**, spécifiez un nom pour le nouveau complément.</span><span class="sxs-lookup"><span data-stu-id="bd462-124">In **Name**, specify a name for the new add-in.</span></span>
    
   - <span data-ttu-id="bd462-p104">Dans **URL**, spécifiez l’URL à associer au complément. Les URL sont limitées aux protocoles http et https.</span><span class="sxs-lookup"><span data-stu-id="bd462-p104">In **URL**, specify the URL to be associated with the add-in. URLs are limited to the http and https protocols.</span></span>
    
7. <span data-ttu-id="bd462-127">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="bd462-127">Click **Commit**.</span></span>
    
## <a name="configure-add-ins-by-using-windows-powershell"></a><span data-ttu-id="bd462-128">Configurer des compléments via Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="bd462-128">Configure add-ins by using Windows PowerShell</span></span>

<span data-ttu-id="bd462-p105">Vous pouvez configurer des compléments pour les salles de conversation en utilisant les applets de commande Windows PowerShell suivantes. Pour plus d’informations sur la syntaxe, notamment tous les paramètres disponibles, consultez [Skype for Business Server 2015 Management Shell](../management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="bd462-p105">You can configure add-ins for chat rooms by using the following Windows PowerShell cmdlets. For details about syntax, including all available parameters, see [Skype for Business Server 2015 Management Shell](../management-shell.md).</span></span>
  

|<span data-ttu-id="bd462-131">**Applet de commande**</span><span class="sxs-lookup"><span data-stu-id="bd462-131">**Cmdlet**</span></span>|<span data-ttu-id="bd462-132">**Description**</span><span class="sxs-lookup"><span data-stu-id="bd462-132">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="bd462-133">New-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="bd462-133">New-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="bd462-134">Créer un complément</span><span class="sxs-lookup"><span data-stu-id="bd462-134">Create a new add-in</span></span>  <br/> |
|<span data-ttu-id="bd462-135">Set-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="bd462-135">Set-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="bd462-136">Configurer des paramètres pour un complément existant</span><span class="sxs-lookup"><span data-stu-id="bd462-136">Configure settings for an existing add-in</span></span>  <br/> |
|<span data-ttu-id="bd462-137">Get-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="bd462-137">Get-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="bd462-138">Récupérer des informations sur les compléments</span><span class="sxs-lookup"><span data-stu-id="bd462-138">Retrieve information about add-ins</span></span>  <br/> |
|<span data-ttu-id="bd462-139">Remove-CsPersistentChatAddin</span><span class="sxs-lookup"><span data-stu-id="bd462-139">Remove-CsPersistentChatAddin</span></span>  <br/> |<span data-ttu-id="bd462-140">Supprimer un complément</span><span class="sxs-lookup"><span data-stu-id="bd462-140">Remove an add-in</span></span>  <br/> |
   
### <a name="create-a-new-add-in"></a><span data-ttu-id="bd462-141">Créer un complément</span><span class="sxs-lookup"><span data-stu-id="bd462-141">Create a new add-in</span></span>

<span data-ttu-id="bd462-142">Vous pouvez créer un complément à l’aide de l’applet de commande **New-CsPersistentChatAddin** .</span><span class="sxs-lookup"><span data-stu-id="bd462-142">You can create a new Add-in by using the **New-CsPersistentChatAddin** cmdlet.</span></span>
  
<span data-ttu-id="bd462-143">Par exemple, la commande suivante crée un nouveau complément (avec le nom ITPersistentChatAddin) pour le pool atl-cs-001.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="bd462-143">For example, the following command creates a new add-in (with the name ITPersistentChatAddin) for the pool atl-cs-001.contoso.com.</span></span> <span data-ttu-id="bd462-144">Le paramètre URL et la valeur du paramètre http://atl-cs-001.contoso.com/itchat spécifiez l’emplacement de la page de la macro complémentaire :</span><span class="sxs-lookup"><span data-stu-id="bd462-144">The URL parameter and the parameter value http://atl-cs-001.contoso.com/itchat specify the location of the add-in's webpage:</span></span>
  
```
New-CsPersistentChatAddin -Name "ITPersistentChatAddin" -PersistentChatPoolFqdn "atl-cs-001.contoso.com" -Url "http://atl-cs-001.contoso.com/itchat"
```

### <a name="configure-settings-for-an-existing-add-in"></a><span data-ttu-id="bd462-145">Configurer des paramètres pour un complément existant</span><span class="sxs-lookup"><span data-stu-id="bd462-145">Configure settings for an existing add-in</span></span>

<span data-ttu-id="bd462-146">Vous pouvez configurer les paramètres d’un complément existant en utilisant l’applet de commande **Set-CsPersistentChatAddIn**.</span><span class="sxs-lookup"><span data-stu-id="bd462-146">You can configure settings for an existing add-in by using the **Set-CsPersistentChatAddIn** cmdlet.</span></span> <span data-ttu-id="bd462-147">Par exemple, la commande suivante modifie l’URL affecté au complément Conversation permanente ITPersistentChatAddin.</span><span class="sxs-lookup"><span data-stu-id="bd462-147">For example, the following command modifies the URL assigned to the Persistent Chat add-in ITPersistentChatAddin.</span></span> <span data-ttu-id="bd462-148">Dans ce cas, l’URL est remplacée parhttp://atl-cs-001.contoso.com/itchat2:</span><span class="sxs-lookup"><span data-stu-id="bd462-148">In this case, the URL is changed to http://atl-cs-001.contoso.com/itchat2:</span></span>
  
```
Set-CsPersistentChatAddin -Identity "atl-cs-001.contoso.com\ITPersistentChatAddin" -Url "http://atl-cs-001.contoso.com/itchat2"
```

### <a name="retrieve-information-about-add-ins"></a><span data-ttu-id="bd462-149">Récupérer des informations sur les compléments</span><span class="sxs-lookup"><span data-stu-id="bd462-149">Retrieve information about add-ins</span></span>

<span data-ttu-id="bd462-p108">Vous pouvez obtenir des informations sur les compléments en utilisant l’applet de commande **Get-CsPersistentChatAddin**. Par exemple, la commande suivante retourne des informations sur tous les compléments Conversation permanente à utiliser dans l’organisation :</span><span class="sxs-lookup"><span data-stu-id="bd462-p108">You can get information about add-ins by using the **Get-CsPersistentChatAddin** cmdlet. For example, the following command returns information about all the Persistent Chat add-ins configured for use in the organization:</span></span>
  
```
Get-CsPersistentChatAddin
```

### <a name="remove-an-add-in"></a><span data-ttu-id="bd462-152">Supprimer un complément</span><span class="sxs-lookup"><span data-stu-id="bd462-152">Remove an add-in</span></span>

<span data-ttu-id="bd462-153">Vous pouvez supprimer un complément à l’aide de l’applet de commande **Remove-CsPersistentChatAddIn** .</span><span class="sxs-lookup"><span data-stu-id="bd462-153">You can remove an Add-in by using the **Remove-CsPersistentChatAddIn** cmdlet.</span></span> <span data-ttu-id="bd462-154">Par exemple, la commande suivante supprime le complément Conversation permanente ITChatAddin trouvé dans le pool atl-cs-001.contoso.com :</span><span class="sxs-lookup"><span data-stu-id="bd462-154">For example, the following command removes the Persistent Chat add-in ITChatAddin found on the pool atl-cs-001.contoso.com:</span></span>
  
```
Remove-CsPersistentChatAddin -Identity "atl-cs-001.contoso.com\ITChatAddin"
```


