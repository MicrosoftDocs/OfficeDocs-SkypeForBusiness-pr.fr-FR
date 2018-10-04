---
title: Créer une stratégie d’archivage dans Skype pour Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 50c39731-ba2f-49c2-a571-6dc373f6aaeb
description: 'Résumé : Découvrez comment créer une stratégie d’archivage pour Skype pour Business Server.'
ms.openlocfilehash: 70c955d78e6c7b259732d50c47c53e8b3bedf97c
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25374408"
---
# <a name="create-a-new-archiving-policy-in-skype-for-business-server"></a><span data-ttu-id="9bf0a-103">Créer une stratégie d’archivage dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="9bf0a-103">Create a new archiving policy in Skype for Business Server</span></span>

<span data-ttu-id="9bf0a-104">**Résumé :** Découvrez comment créer une stratégie d’archivage pour Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="9bf0a-104">**Summary:** Learn how to create a new archiving policy for Skype for Business Server.</span></span>
  
<span data-ttu-id="9bf0a-105">Vous pouvez créer de nouvelles stratégies d’archivage à l’aide du panneau de configuration ou des applets de commande de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9bf0a-105">You can create new archiving policies by using the Control Panel or by using Windows PowerShell cmdlets.</span></span>
  
## <a name="create-a-new-archiving-policy-by-using-the-control-panel"></a><span data-ttu-id="9bf0a-106">Créer une nouvelle stratégie d’archivage à l’aide du panneau de configuration</span><span class="sxs-lookup"><span data-stu-id="9bf0a-106">Create a new archiving policy by using the Control Panel</span></span>

<span data-ttu-id="9bf0a-107">Pour créer une nouvelle stratégie d’archivage à l’aide du panneau de configuration :</span><span class="sxs-lookup"><span data-stu-id="9bf0a-107">To create a new archiving policy by using the Control Panel:</span></span>
  
1. <span data-ttu-id="9bf0a-108">À partir d’un compte d’utilisateur auquel est affecté un des rôles CsArchivingAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="9bf0a-108">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="9bf0a-109">Ouvrez une fenêtre de navigateur, puis entrez l’URL d’administration pour ouvrir le Skype pour le panneau de configuration serveur Business.</span><span class="sxs-lookup"><span data-stu-id="9bf0a-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="9bf0a-110">Dans la barre de navigation de gauche, cliquez sur **Surveillance et archivage**, puis sur **Stratégie d’archivage**.</span><span class="sxs-lookup"><span data-stu-id="9bf0a-110">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
4. <span data-ttu-id="9bf0a-111">Cliquez sur **Nouveau**, puis effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="9bf0a-111">Click **New**, and then do one of the following:</span></span> 
    
   - <span data-ttu-id="9bf0a-112">Pour créer une stratégie d’archivage au niveau du site, cliquez sur **Stratégie de site**, puis, dans **Sélectionner un site**, cliquez sur le site auquel la stratégie doit être appliquée.</span><span class="sxs-lookup"><span data-stu-id="9bf0a-112">To create a site-level archiving policy, click **Site policy**, and then, in **Select a site**, click the site to which the policy is to be applied.</span></span>
    
   - <span data-ttu-id="9bf0a-113">Pour créer une stratégie d’archivage au niveau de l’utilisateur, cliquez sur **Stratégie de l’utilisateur**.</span><span class="sxs-lookup"><span data-stu-id="9bf0a-113">To create a user-level archiving policy, click **User policy**.</span></span>
    
5. <span data-ttu-id="9bf0a-114">Dans **Nouvelle stratégie d’archivage**, procédez comme suit :</span><span class="sxs-lookup"><span data-stu-id="9bf0a-114">In **New Archiving Policy**, do the following:</span></span>
    
   - <span data-ttu-id="9bf0a-115">Dans **Nom**, spécifiez un nom pour la nouvelle stratégie (par exemple, externalContoso).</span><span class="sxs-lookup"><span data-stu-id="9bf0a-115">In **Name**, specify a name for the new policy (for example, externalContoso).</span></span>
    
   - <span data-ttu-id="9bf0a-116">Dans **Description**, entrez des informations décrivant la stratégie (par exemple, stratégie d’archivage des utilisateurs externes pour Contoso).</span><span class="sxs-lookup"><span data-stu-id="9bf0a-116">In **Description**, provide details about what the policy is (for example, External user archiving policy for Contoso).</span></span>
    
   - <span data-ttu-id="9bf0a-117">Pour contrôler l’archivage des communications avec les utilisateurs internes, activez ou désactivez la case à cocher **Archiver les communications internes**.</span><span class="sxs-lookup"><span data-stu-id="9bf0a-117">To control archiving of communications with internal users, select or clear the **Archive internal communications** check box.</span></span>
    
   - <span data-ttu-id="9bf0a-118">Pour contrôler l’archivage des communications avec les utilisateurs externes, activez ou désactivez la case à cocher **Archiver les communications externes**.</span><span class="sxs-lookup"><span data-stu-id="9bf0a-118">To control archiving of communications with external users, select or clear the **Archive external communications** check box.</span></span>
    
6. <span data-ttu-id="9bf0a-119">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="9bf0a-119">Click **Commit**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="9bf0a-120">Les paramètres d’une stratégie utilisateur ne s’appliquent qu’aux utilisateurs et groupes d’utilisateurs spécifiques pour lesquels la stratégie a été définie.</span><span class="sxs-lookup"><span data-stu-id="9bf0a-120">The settings of a user policy only apply to the specific users and user groups to which you apply the policy.</span></span> <span data-ttu-id="9bf0a-121">Pour plus d’informations, voir [appliquer une stratégie d’archivage pour les utilisateurs de Skype pour Business Server](apply-a-policy-to-users.md).</span><span class="sxs-lookup"><span data-stu-id="9bf0a-121">For details, see [Apply an archiving policy to users in Skype for Business Server](apply-a-policy-to-users.md).</span></span> 
  
## <a name="create-a-new-archiving-policy-by-using-windows-powershell"></a><span data-ttu-id="9bf0a-122">Créer une nouvelle stratégie d’archivage à l’aide de Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="9bf0a-122">Create a new archiving policy by using Windows PowerShell</span></span>

<span data-ttu-id="9bf0a-123">Vous pouvez également créer de nouvelles stratégies d’archivage à l’aide de l’applet de commande **New-CsArchivingPolicy** de Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9bf0a-123">You can also create new archiving policies by using the Windows PowerShell **New-CsArchivingPolicy** cmdlet.</span></span> <span data-ttu-id="9bf0a-124">Pour plus d’informations, consultez la rubrique d’aide pour l’applet de commande [New-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csarchivingpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="9bf0a-124">For more information, see the help topic for the [New-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csarchivingpolicy?view=skype-ps) cmdlet.</span></span>
  
### <a name="to-create-a-new-archiving-policy-at-the-site-level"></a><span data-ttu-id="9bf0a-125">Pour créer une nouvelle stratégie d’archivage au niveau du site :</span><span class="sxs-lookup"><span data-stu-id="9bf0a-125">To create a new archiving policy at the site level</span></span>

<span data-ttu-id="9bf0a-126">Cette commande crée une stratégie d’archivage pour le site Redmond :</span><span class="sxs-lookup"><span data-stu-id="9bf0a-126">This command creates a new archiving policy for the Redmond site:</span></span>
  
```
New-CsArchivingPolicy -Identity "site:Redmond"
```

### <a name="to-create-a-new-archiving-policy-at-the-per-user-level"></a><span data-ttu-id="9bf0a-127">Pour créer une nouvelle stratégie d’archivage au niveau de chaque utilisateur :</span><span class="sxs-lookup"><span data-stu-id="9bf0a-127">To create a new archiving policy at the per-user level</span></span>

<span data-ttu-id="9bf0a-128">Pour créer une stratégie d’archivage au niveau de l’étendue Utilisateur, il vous suffit de spécifier une identité unique lors de la création de la stratégie :</span><span class="sxs-lookup"><span data-stu-id="9bf0a-128">To create a new archiving policy at the per-user level, simply specify a unique Identity when creating the policy:</span></span>
  
```
New-CsArchivingPolicy -Identity "RedmondArchivingPolicy"
```

### <a name="to-create-a-new-archiving-policy-that-enables-archiving-of-internal-communication-sessions"></a><span data-ttu-id="9bf0a-129">Pour créer une nouvelle stratégie d’archivage qui permet d’archiver des sessions de communication interne</span><span class="sxs-lookup"><span data-stu-id="9bf0a-129">To create a new archiving policy that enables archiving of internal communication sessions</span></span>

<span data-ttu-id="9bf0a-130">Dans la mesure où aucun paramètre (à l’exception du paramètre obligatoire Identity) n’a été spécifié dans les commandes précédentes, les nouvelles stratégies utilisent les valeurs par défaut pour toutes leurs propriétés.</span><span class="sxs-lookup"><span data-stu-id="9bf0a-130">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding commands, the new policies will use the default values for all their properties.</span></span> <span data-ttu-id="9bf0a-131">Pour créer des stratégies qui utilisent des valeurs de propriétés distinctes, il vous suffit d’inclure le paramètre et la valeur de paramètre appropriés.</span><span class="sxs-lookup"><span data-stu-id="9bf0a-131">To create policies that use different property values, simply include the appropriate parameter and parameter value.</span></span> <span data-ttu-id="9bf0a-132">Par exemple, la commande suivante crée une stratégie d’archivage qui permet l’archivage des sessions de messagerie instantanée internes :</span><span class="sxs-lookup"><span data-stu-id="9bf0a-132">For example, the following command creates an archiving policy that permits archiving of internal instant messaging sessions:</span></span> 
  
```
New-CsArchivingPolicy -Identity "site:Redmond" -ArchiveInternal $True
```

### <a name="to-create-a-new-archiving-policy-that-enables-archiving-of-both-internal-and-external-communication-sessions"></a><span data-ttu-id="9bf0a-133">Pour créer une nouvelle stratégie d’archivage qui permet d’archiver des sessions de communication interne et externe</span><span class="sxs-lookup"><span data-stu-id="9bf0a-133">To create a new archiving policy that enables archiving of both internal and external communication sessions</span></span>

<span data-ttu-id="9bf0a-p104">Vous pouvez modifier plusieurs valeurs de propriétés en incluant plusieurs paramètres. Par exemple, cette commande permet de configurer la nouvelle stratégie visant à archiver les sessions de messagerie instantanée internes et externes :</span><span class="sxs-lookup"><span data-stu-id="9bf0a-p104">Multiple property values can be modified by including multiple parameters. For example, this command configures the new policy to archive both internal and external instant messaging sessions:</span></span>
  
```
New-CsArchivingPolicy -Identity "site:Redmond" -ArchiveInternal $True -ArchiveExternal $True
```