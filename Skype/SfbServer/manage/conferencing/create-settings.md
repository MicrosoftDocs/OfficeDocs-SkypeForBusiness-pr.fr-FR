---
title: Créer les paramètres de configuration dans Skype pour Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6d8f9ff8-2a04-4175-9bf0-1ec5d78fd015
description: 'Résumé : Apprenez à créer les paramètres de configuration dans Skype pour Business Server.'
ms.openlocfilehash: c154661e5e8b974e4a475c935b40749776e0499c
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32222799"
---
# <a name="create-meeting-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="b56d4-103">Créer les paramètres de configuration dans Skype pour Business Server</span><span class="sxs-lookup"><span data-stu-id="b56d4-103">Create meeting configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="b56d4-104">**Résumé :** Découvrez comment créer les paramètres de configuration dans Skype pour Business Server.</span><span class="sxs-lookup"><span data-stu-id="b56d4-104">**Summary:** Learn how to create meeting configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="b56d4-105">Vous pouvez créer des paramètres de configuration de réunion à l’aide de Skype pour le panneau de configuration serveur Business ou à l’aide de Skype pour Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="b56d4-105">You can create meeting configuration settings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="create-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="b56d4-106">Créer des paramètres de configuration de réunion à l’aide de Skype pour Business Server Control Panel</span><span class="sxs-lookup"><span data-stu-id="b56d4-106">Create meeting configuration settings by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="b56d4-107">À partir d’un compte d’utilisateur auquel est affecté le rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur de votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="b56d4-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="b56d4-108">Ouvrez le panneau de configuration serveur Business Skype.</span><span class="sxs-lookup"><span data-stu-id="b56d4-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="b56d4-109">Dans la barre de navigation de gauche, cliquez sur **Conférence**, puis sur **Configuration de la réunion**.</span><span class="sxs-lookup"><span data-stu-id="b56d4-109">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
4. <span data-ttu-id="b56d4-110">Dans la page **Configuration de la réunion**, cliquez sur **Nouveau**, puis effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="b56d4-110">On the **Meeting Configuration** page, click **New**, and then do one of the following:</span></span>
    
    - <span data-ttu-id="b56d4-p101">Pour créer une stratégie au niveau du site, cliquez sur **Configuration du site**. Dans le champ de recherche **Sélectionner un site**, tapez le nom du site (en totalité ou partiellement) pour lequel vous souhaitez définir des paramètres de participation aux réunions. Dans la liste des sites obtenus, cliquez sur le site voulu, puis sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="b56d4-p101">To create a site-level policy, click **Site configuration**. In the **Select a Site** search field, type all or part of the name of the site for which you want to define meeting join settings. In the resulting list of sites, click the site you want, and then click **OK**.</span></span>
    
    - <span data-ttu-id="b56d4-p102">Pour créer une stratégie au niveau du pool, cliquez sur **Configuration du pool**. Dans le champ de recherche **Sélectionner un service**, tapez le nom du service de pool (en totalité ou partiellement) pour lequel vous souhaitez définir des paramètres de participation aux réunions. Dans la liste des services obtenus, cliquez sur le pool de votre choix, puis sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="b56d4-p102">To create a pool-level policy, click **Pool configuration**. In the **Select a Service** search field, type all or part of the name of the pool service for which you want to define meeting join settings. In the resulting list of services, click the pool you want, and then click **OK**.</span></span>
    
5. <span data-ttu-id="b56d4-p103">Pour acheminer les participants qui appellent à partir du réseau téléphonique commuté (RTC) via la salle d’attente, désactivez la case à cocher **Les appelants RTC ignorent la salle d’attente**. Par défaut, les participants qui appellent d’un réseau RTC accèdent directement à la réunion.</span><span class="sxs-lookup"><span data-stu-id="b56d4-p103">To route participants who dial in from the public switched telephone network (PSTN) through the lobby, clear the **PSTN callers bypass lobby** check box. By default, participants dialing in from the PSTN go directly to the meeting.</span></span>
    
6. <span data-ttu-id="b56d4-119">Pour désigner le présentateur de la réunion, dans **Désigné comme présentateur**, effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="b56d4-119">To configure who can be a presenter in the meeting, in **Designate as presenter**, do one of the following:</span></span>
    
   - <span data-ttu-id="b56d4-120">Pour n’autoriser que l’organisateur à être présentateur, cliquez sur **Aucun**.</span><span class="sxs-lookup"><span data-stu-id="b56d4-120">To not allow anyone other than the organizer to be a presenter, click **None**.</span></span>
    
   - <span data-ttu-id="b56d4-p104">Pour n’autoriser que les participants membres de votre entreprise à être présentateur, cliquez sur **Société**. Il s’agit du paramètre par défaut.</span><span class="sxs-lookup"><span data-stu-id="b56d4-p104">To allow only participants who are members of your organization to be a presenter, click **Company**. This is the default setting.</span></span>
    
   - <span data-ttu-id="b56d4-123">Pour autoriser tous les participants à être présentateur, cliquez sur **Tout le monde**.</span><span class="sxs-lookup"><span data-stu-id="b56d4-123">To allow any participants to be a presenter, click **Everyone**.</span></span>
    
7. <span data-ttu-id="b56d4-p105">Pour permettre à l’organisateur de sélectionner un type de conférence lors de la planification d’une réunion, désactivez la case à cocher **Type de conférence affecté par défaut**. Par défaut, le type de conférence est affecté automatiquement.</span><span class="sxs-lookup"><span data-stu-id="b56d4-p105">To have the organizer select a conference type when scheduling a meeting, clear the **Assigned conference type by default** check box. By default, the conference type is automatically assigned.</span></span>
    
8. <span data-ttu-id="b56d4-p106">Pour empêcher les utilisateurs anonymes (non identifiés) d’être automatiquement admis, désactivez la case à cocher **Admettre les utilisateurs anonymes par défaut**. Par défaut, les utilisateurs anonymes sont automatiquement admis aux réunions.</span><span class="sxs-lookup"><span data-stu-id="b56d4-p106">To prevent anonymous (unauthenticated) users from being automatically admitted, clear the **Admit anonymous users by default** check box. By default, anonymous users are automatically admitted to meetings.</span></span>
    
9. <span data-ttu-id="b56d4-128">Pour personnaliser l’invitation à la réunion envoyée aux participants, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="b56d4-128">To customize the meeting invite that is sent out to participants, do the following.</span></span> <span data-ttu-id="b56d4-129">Notez que la longueur maximale des URL et du texte de pied de page personnalisé est de 1 Ko.</span><span class="sxs-lookup"><span data-stu-id="b56d4-129">Note that the maximum length for URLs and custom footer text is 1KB.</span></span> <span data-ttu-id="b56d4-130">Sauf pour l’**URL de l’aide**, si vous ne spécifiez pas une valeur pour les personnalisations, elles ne seront pas incluses dans la réunion.</span><span class="sxs-lookup"><span data-stu-id="b56d4-130">Except for **Help URL**, if you do not specify a value for the customizations, they will not be included in the meeting.</span></span> <span data-ttu-id="b56d4-131">Si vous n’incluez pas une URL d’aide personnalisé, l’URL d’aide par défaut pour Skype pour les entreprises s’affichera dans l’invitation.</span><span class="sxs-lookup"><span data-stu-id="b56d4-131">If you do not include a custom help URL, the default help URL for Skype for Business will be displayed in the invite.</span></span> 
    
   - <span data-ttu-id="b56d4-p108">Pour personnaliser le logo qui figure sur l’invitation à la réunion, dans **URL du logo**, entrez l’emplacement du logo. Le logo doit être une image GIF ou JPG d’une taille de 188 x 30 pixels.</span><span class="sxs-lookup"><span data-stu-id="b56d4-p108">To customize the logo that appears in the meeting invite, in **Logo URL**, enter the location of the logo. The logo must be a GIF or JPG image with a size of 188 by 30 pixels.</span></span> 
    
   - <span data-ttu-id="b56d4-134">Pour personnaliser le texte d’aide qui figure sur l’invitation à la réunion, dans **URL de l’aide**, entrez l’emplacement du texte d’aide.</span><span class="sxs-lookup"><span data-stu-id="b56d4-134">To customize the help text that appears in the meeting invite, in **Help URL**, enter the location of the help text.</span></span>
    
   - <span data-ttu-id="b56d4-135">Pour personnaliser les informations légales qui figurent sur l’invitation à la réunion, dans **URL des informations légales**, entrez l’emplacement des informations légales.</span><span class="sxs-lookup"><span data-stu-id="b56d4-135">To customize the legal text that appears in the meeting invite, in **Legal text URL**, enter the location of the legal text.</span></span>
    
   - <span data-ttu-id="b56d4-136">Pour personnaliser le texte de pied de page qui figure sur l’invitation à la réunion, dans **Texte de pied de page personnalisé**, entrez le texte.</span><span class="sxs-lookup"><span data-stu-id="b56d4-136">To customize the footer text that appears in the meeting invite, in **Custom footer text**, enter text.</span></span>
    
10. <span data-ttu-id="b56d4-137">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="b56d4-137">Click **Commit**.</span></span>
    
## <a name="create-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="b56d4-138">Créer des paramètres de configuration de réunion à l’aide de Skype pour Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="b56d4-138">Create meeting configuration settings by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="b56d4-139">Pour créer des paramètres de configuration de réunion, utilisez l’applet de commande **New-CsMeetingConfiguration**.</span><span class="sxs-lookup"><span data-stu-id="b56d4-139">To create meeting configuration settings, use the **New-CsMeetingConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="b56d4-140">La commande ci-dessous crée un ensemble de paramètres de configuration de réunion pour le site de Redmond :</span><span class="sxs-lookup"><span data-stu-id="b56d4-140">The following command creates a new set of meeting configuration settings for the Redmond site:</span></span>
  
```
New-CsMeetingConfiguration -Identity "site:Redmond"
```

<span data-ttu-id="b56d4-141">Comme aucun paramètre (autre que le paramètre d’identité obligatoire) n’est spécifié dans la commande précédente, les nouveaux paramètres de configuration de réunion utiliseront les valeurs par défaut pour toutes ses propriétés.</span><span class="sxs-lookup"><span data-stu-id="b56d4-141">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new meeting configuration settings will use the default values for all its properties.</span></span>
  
<span data-ttu-id="b56d4-p109">Pour créer des paramètres qui utilisent différentes valeurs de propriété, incluez simplement le paramètre et la valeur de paramètre appropriés. Par exemple, pour créer une collection de paramètres de configuration de réunion qui, par défaut, admet tout le monde à une réunion comme présentateur, utilisez une commande semblable à la suivante :</span><span class="sxs-lookup"><span data-stu-id="b56d4-p109">To create settings that use different property values, simply include the appropriate parameter and parameter value. For example, to create a collection of meeting configuration settings that, by default, admit everyone to a meeting as a presenter use a command like this:</span></span>
  
```
New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"
```

<span data-ttu-id="b56d4-p110">Plusieurs valeurs de propriété peuvent être définies en incluant plusieurs paramètres. Par exemple, la commande suivante admet tout le monde à une réunion comme présentateur et force aussi les utilisateurs RTC à attendre dans la salle d’attente jusqu’à ce qu’ils soient officiellement admis à la réunion :</span><span class="sxs-lookup"><span data-stu-id="b56d4-p110">Multiple property values can be set by including multiple parameters. For example, the following command admits everyone to a meeting as a presenter and also forces PSTN users to wait in the lobby until they are formally admitted to the meeting:</span></span>
  
```
New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone" -PSTNUCallersBypassLobby $True
```

<span data-ttu-id="b56d4-146">Pour plus d’informations, notamment une liste complète des paramètres, voir [New-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="b56d4-146">For more information, including a complete list of parameters, see [New-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps).</span></span>
  

