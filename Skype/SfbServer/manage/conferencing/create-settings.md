---
title: Créer des paramètres de configuration de réunion dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6d8f9ff8-2a04-4175-9bf0-1ec5d78fd015
description: 'Résumé : Découvrez comment créer des paramètres de configuration de réunion dans Skype Entreprise Server.'
ms.openlocfilehash: edc498ed3847618b17970fb2270c21fd3f4ec025
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828204"
---
# <a name="create-meeting-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="b4615-103">Créer des paramètres de configuration de réunion dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="b4615-103">Create meeting configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="b4615-104">**Résumé :** Découvrez comment créer des paramètres de configuration de réunion dans Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="b4615-104">**Summary:** Learn how to create meeting configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="b4615-105">Vous pouvez créer des paramètres de configuration de réunion à l’aide du Panneau de configuration de Skype Entreprise Server ou de Skype Entreprise Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="b4615-105">You can create meeting configuration settings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="create-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="b4615-106">Créer des paramètres de configuration de réunion à l’aide du Panneau de configuration de Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="b4615-106">Create meeting configuration settings by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="b4615-107">Avec un compte d’utilisateur affecté au rôle CsUserAdministrator ou CsAdministrator, ouvrez une session sur un ordinateur dans votre déploiement interne.</span><span class="sxs-lookup"><span data-stu-id="b4615-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="b4615-108">Ouvrez le Panneau de contrôle Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="b4615-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="b4615-109">Dans la barre de navigation de gauche, cliquez sur **Conférence,** puis sur **Configuration de la réunion.**</span><span class="sxs-lookup"><span data-stu-id="b4615-109">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
4. <span data-ttu-id="b4615-110">Dans la page **Configuration de la réunion**, cliquez sur **Nouveau**, puis effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="b4615-110">On the **Meeting Configuration** page, click **New**, and then do one of the following:</span></span>
    
    - <span data-ttu-id="b4615-p101">Pour créer une stratégie au niveau du site, cliquez sur **Configuration du site**. Dans le champ de recherche **Sélectionner un site**, tapez le nom du site (en totalité ou partiellement) pour lequel vous souhaitez définir des paramètres de participation aux réunions. Dans la liste des sites obtenus, cliquez sur le site voulu, puis sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="b4615-p101">To create a site-level policy, click **Site configuration**. In the **Select a Site** search field, type all or part of the name of the site for which you want to define meeting join settings. In the resulting list of sites, click the site you want, and then click **OK**.</span></span>
    
    - <span data-ttu-id="b4615-p102">Pour créer une stratégie au niveau du pool, cliquez sur **Configuration du pool**. Dans le champ de recherche **Sélectionner un service**, tapez le nom du service de pool (en totalité ou partiellement) pour lequel vous souhaitez définir des paramètres de participation aux réunions. Dans la liste des services obtenus, cliquez sur le pool de votre choix, puis sur **OK**.</span><span class="sxs-lookup"><span data-stu-id="b4615-p102">To create a pool-level policy, click **Pool configuration**. In the **Select a Service** search field, type all or part of the name of the pool service for which you want to define meeting join settings. In the resulting list of services, click the pool you want, and then click **OK**.</span></span>
    
5. <span data-ttu-id="b4615-p103">Pour acheminer les participants qui appellent depuis le réseau téléphonique commuté (RTC) via la salle d’attente, désactivez la case à cocher **Les appelants PSTN ignorent la salle d’attente**. Par défaut, les participants qui appellent depuis un réseau RTC accèdent directement à la réunion.</span><span class="sxs-lookup"><span data-stu-id="b4615-p103">To route participants who dial in from the public switched telephone network (PSTN) through the lobby, clear the **PSTN callers bypass lobby** check box. By default, participants dialing in from the PSTN go directly to the meeting.</span></span>
    
6. <span data-ttu-id="b4615-119">Pour désigner le présentateur de la réunion, dans **Désigné comme présentateur**, effectuez l’une des opérations suivantes :</span><span class="sxs-lookup"><span data-stu-id="b4615-119">To configure who can be a presenter in the meeting, in **Designate as presenter**, do one of the following:</span></span>
    
   - <span data-ttu-id="b4615-120">Pour n’autoriser que l’organisateur à être présentateur, cliquez sur **Aucun**.</span><span class="sxs-lookup"><span data-stu-id="b4615-120">To not allow anyone other than the organizer to be a presenter, click **None**.</span></span>
    
   - <span data-ttu-id="b4615-p104">Pour n’autoriser que les participants membres de votre entreprise à être présentateur, cliquez sur **Société**. Il s’agit du paramètre par défaut.</span><span class="sxs-lookup"><span data-stu-id="b4615-p104">To allow only participants who are members of your organization to be a presenter, click **Company**. This is the default setting.</span></span>
    
   - <span data-ttu-id="b4615-123">Pour autoriser tous les participants à être présentateur, cliquez sur **Tout le monde**.</span><span class="sxs-lookup"><span data-stu-id="b4615-123">To allow any participants to be a presenter, click **Everyone**.</span></span>
    
7. <span data-ttu-id="b4615-p105">Pour permettre à l’organisateur de sélectionner un type de conférence lors de la planification d’une réunion, désactivez la case à cocher **Type de conférence affecté par défaut**. Par défaut, le type de conférence est automatiquement affecté.</span><span class="sxs-lookup"><span data-stu-id="b4615-p105">To have the organizer select a conference type when scheduling a meeting, clear the **Assigned conference type by default** check box. By default, the conference type is automatically assigned.</span></span>
    
8. <span data-ttu-id="b4615-p106">Pour empêcher les utilisateurs anonymes (non identifiés) d’être automatiquement admis, désactivez la case à cocher **Admettre les utilisateurs anonymes par défaut**. Par défaut, les utilisateurs anonymes sont automatiquement admis aux réunions.</span><span class="sxs-lookup"><span data-stu-id="b4615-p106">To prevent anonymous (unauthenticated) users from being automatically admitted, clear the **Admit anonymous users by default** check box. By default, anonymous users are automatically admitted to meetings.</span></span>
    
9. <span data-ttu-id="b4615-128">Pour personnaliser l’invitation à la réunion envoyée aux participants, procédez comme suit.</span><span class="sxs-lookup"><span data-stu-id="b4615-128">To customize the meeting invite that is sent out to participants, do the following.</span></span> <span data-ttu-id="b4615-129">Notez que la longueur maximale des URL et du texte de pied de page personnalisé est de 1 Ko.</span><span class="sxs-lookup"><span data-stu-id="b4615-129">Note that the maximum length for URLs and custom footer text is 1KB.</span></span> <span data-ttu-id="b4615-130">Sauf pour l’**URL de l’aide**, si vous ne spécifiez pas une valeur pour les personnalisations, elles ne seront pas incluses dans la réunion.</span><span class="sxs-lookup"><span data-stu-id="b4615-130">Except for **Help URL**, if you do not specify a value for the customizations, they will not be included in the meeting.</span></span> <span data-ttu-id="b4615-131">Si vous n’incluez pas d’URL d’aide personnalisée, l’URL d’aide par défaut pour Skype Entreprise s’affiche dans l’invitation.</span><span class="sxs-lookup"><span data-stu-id="b4615-131">If you do not include a custom help URL, the default help URL for Skype for Business will be displayed in the invite.</span></span> 
    
   - <span data-ttu-id="b4615-132">Pour personnaliser le logo qui apparaît dans l’invitation à la réunion, dans **URL du logo**, entrez l’emplacement du logo.</span><span class="sxs-lookup"><span data-stu-id="b4615-132">To customize the logo that appears in the meeting invite, in **Logo URL**, enter the location of the logo.</span></span> <span data-ttu-id="b4615-133">Le logo doit être une image GIF ou JPG d’une taille de 188 par 30 pixels.</span><span class="sxs-lookup"><span data-stu-id="b4615-133">The logo must be a GIF or JPG image with a size of 188 by 30 pixels.</span></span> 
    
   - <span data-ttu-id="b4615-134">Pour personnaliser le texte d’aide qui apparaît dans l’invitation à la réunion, dans **URL de l’aide**, entrez l’emplacement du texte d’aide.</span><span class="sxs-lookup"><span data-stu-id="b4615-134">To customize the help text that appears in the meeting invite, in **Help URL**, enter the location of the help text.</span></span>
    
   - <span data-ttu-id="b4615-135">Pour personnaliser les informations légales qui apparaissent dans l’invitation à la réunion, dans **URL des informations légales**, entrez l’emplacement des informations légales.</span><span class="sxs-lookup"><span data-stu-id="b4615-135">To customize the legal text that appears in the meeting invite, in **Legal text URL**, enter the location of the legal text.</span></span>
    
   - <span data-ttu-id="b4615-136">Pour personnaliser le texte de pied de page qui apparaît dans l’invitation à la réunion, dans **Texte de pied de page personnalisé**, entrez le texte.</span><span class="sxs-lookup"><span data-stu-id="b4615-136">To customize the footer text that appears in the meeting invite, in **Custom footer text**, enter text.</span></span>
    
10. <span data-ttu-id="b4615-137">Cliquez sur **Valider**.</span><span class="sxs-lookup"><span data-stu-id="b4615-137">Click **Commit**.</span></span>
    
## <a name="create-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="b4615-138">Créer des paramètres de configuration de réunion à l’aide de Skype Entreprise Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="b4615-138">Create meeting configuration settings by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="b4615-139">Pour créer des paramètres de configuration de réunion, utilisez l’cmdlet **New-CsMeetingConfiguration.**</span><span class="sxs-lookup"><span data-stu-id="b4615-139">To create meeting configuration settings, use the **New-CsMeetingConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="b4615-140">La commande suivante crée un nouvel ensemble de paramètres de configuration de réunion pour le site Redmond :</span><span class="sxs-lookup"><span data-stu-id="b4615-140">The following command creates a new set of meeting configuration settings for the Redmond site:</span></span>
  
```PowerShell
New-CsMeetingConfiguration -Identity "site:Redmond"
```

<span data-ttu-id="b4615-141">Comme aucun paramètre (autre que le paramètre d’identité obligatoire) n’est spécifié dans la commande précédente, les nouveaux paramètres de configuration de réunion utiliseront les valeurs par défaut pour toutes ses propriétés.</span><span class="sxs-lookup"><span data-stu-id="b4615-141">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new meeting configuration settings will use the default values for all its properties.</span></span>
  
<span data-ttu-id="b4615-p109">Pour créer des paramètres qui utilisent différentes valeurs de propriété, incluez simplement le paramètre et la valeur de paramètre appropriés. Par exemple, pour créer une collection de paramètres de configuration de réunion qui, par défaut, admet tout le monde à une réunion comme présentateur, utilisez une commande semblable à la suivante :</span><span class="sxs-lookup"><span data-stu-id="b4615-p109">To create settings that use different property values, simply include the appropriate parameter and parameter value. For example, to create a collection of meeting configuration settings that, by default, admit everyone to a meeting as a presenter use a command like this:</span></span>
  
```PowerShell
New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone"
```

<span data-ttu-id="b4615-144">Plusieurs valeurs de propriété peuvent être définies en incluant plusieurs paramètres.</span><span class="sxs-lookup"><span data-stu-id="b4615-144">Multiple property values can be set by including multiple parameters.</span></span> <span data-ttu-id="b4615-145">Par exemple, la commande suivante admet tout le monde à une réunion en tant que présentateur et force également les utilisateurs PSTN à attendre dans la salle d’attente jusqu’à ce qu’ils soient officiellement admis à la réunion :</span><span class="sxs-lookup"><span data-stu-id="b4615-145">For example, the following command admits everyone to a meeting as a presenter and also forces PSTN users to wait in the lobby until they are formally admitted to the meeting:</span></span>
  
```PowerShell
New-CsMeetingConfiguration -Identity "site:Redmond" -DesignateAsPresenter "Everyone" -PSTNUCallersBypassLobby $True
```

<span data-ttu-id="b4615-146">Pour plus d’informations, y compris une liste complète des paramètres, voir [New-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="b4615-146">For more information, including a complete list of parameters, see [New-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps).</span></span>
  

