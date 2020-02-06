---
title: Gérer la participation aux conférences et laisser des annonces dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: cb09f9c2-c6dc-4083-b45a-8b6773341373
description: 'Résumé : Découvrez comment gérer la participation aux conférences et laisser des annonces dans Skype entreprise Server.'
ms.openlocfilehash: 5f975637ca1d85e11c6889a07ff90055ef79ffc5
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818545"
---
# <a name="manage-conference-join-and-leave-announcements-in-skype-for-business-server"></a><span data-ttu-id="1d224-103">Gérer la participation aux conférences et laisser des annonces dans Skype entreprise Server</span><span class="sxs-lookup"><span data-stu-id="1d224-103">Manage conference join and leave announcements in Skype for Business Server</span></span>
 
<span data-ttu-id="1d224-104">**Résumé :** Découvrez comment gérer la participation à des conférences et laisser des annonces dans Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="1d224-104">**Summary:** Learn how to manage conference join and leave announcements in Skype for Business Server.</span></span>
  
<span data-ttu-id="1d224-105">Lorsque des utilisateurs d’appels entrants rejoignent ou quittent une conférence, l’application d’annonce d’annonce peut annoncer leur ouverture ou leur sortie en jouant un message ou en prononçant leurs noms.</span><span class="sxs-lookup"><span data-stu-id="1d224-105">When dial-in users join or leave a conference, the Conferencing Announcement application can announce their entrance or exit by playing a tone or saying their names.</span></span> <span data-ttu-id="1d224-106">Vous pouvez modifier le mode de fonctionnement des annonces à l’aide de Skype entreprise Server Management Shell et de l’applet de commande **Set-CsDialinConferencing** avec les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="1d224-106">You can change how announcements work by using Skype for Business Server Management Shell and the **Set-CsDialinConferencing** cmdlet with the following parameters:</span></span>
  
- <span data-ttu-id="1d224-p102">EnableNameRecording : détermine si des participants anonymes doivent être invités à enregistrer leur nom ou pas avant de participer à la conférence. La valeur par défaut est « $true », ce qui signifie que les participants anonymes sont invités à donner leur nom avant de participer à une conférence. (Les participants authentifiés ne sont pas tenus d’indiquer leur nom, car leur nom complet est utilisé.)</span><span class="sxs-lookup"><span data-stu-id="1d224-p102">EnableNameRecording - Determines whether anonymous participants are asked to record their name before entering the conference. The default value is "$true," which means that anonymous participants are prompted to state their name when joining a conference. (Authenticated participants do not record their name because their display name is used instead.)</span></span>
    
- <span data-ttu-id="1d224-p103">EntryExitAnnouncementsEnabledByDefault : indique si les annonces sont activées ou désactivées par défaut. La valeur par défaut est « $false », ce qui signifie qu’aucune annonce n’est effectuée lorsque les participants rejoignent ou quittent une conférence. Lorsqu’il planifie une réunion, l’organisateur peut ignorer ce paramètre.</span><span class="sxs-lookup"><span data-stu-id="1d224-p103">EntryExitAnnouncementsEnabledByDefault - Indicates whether announcements are turned on or off by default. The default value is "$false," which means that by default there are no announcements when participants join or leave a conference. The meeting organizer can override this setting when scheduling a meeting.</span></span>
    
- <span data-ttu-id="1d224-p104">EntryExitAnnouncementsType : indique l’action entreprise à chaque fois qu’un participant rejoint ou quitte une conférence pour laquelle les annonces ont été activées. La valeur par défaut est « UseNames », ce qui signifie qu’une annonce similaire à la suivante est effectuée : « Ken Myer a rejoint la conférence » lorsque les annonces sont activées.</span><span class="sxs-lookup"><span data-stu-id="1d224-p104">EntryExitAnnouncementsType - Indicates the action taken whenever a participant joins or leaves a conference for which announcements are enabled. The default value is "UseNames," which means there is an announcement similar to the following: "Ken Myer has joined the conference" when announcements are turned on.</span></span>
    
<span data-ttu-id="1d224-p105">Vous pouvez configurer ces paramètres globalement ou au niveau d’un site. (Les paramètres configurés au niveau du site sont prioritaires sur les paramètres configurés au niveau global.)</span><span class="sxs-lookup"><span data-stu-id="1d224-p105">You can configure these settings at the global scope or at the site scope. Settings configured at the site scope take precedence over settings configured at the global scope.</span></span>
   

### <a name="to-modify-the-conference-join-and-leave-announcement-behavior"></a><span data-ttu-id="1d224-117">Pour modifier le comportement des annonces indiquant qu’un utilisateur rejoint ou quitte une conférence</span><span class="sxs-lookup"><span data-stu-id="1d224-117">To modify the conference join and leave announcement behavior</span></span>

1. <span data-ttu-id="1d224-118">Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins  ou du rôle Cs-ServerAdministrator  ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="1d224-118">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the Cs-ServerAdministrator or CsAdministrator role.</span></span>
    
2. <span data-ttu-id="1d224-119">Démarrez Skype entreprise Server Management Shell : cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Skype entreprise 2015**, puis cliquez sur **Skype entreprise Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="1d224-119">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="1d224-120">Exécutez la commande suivante dans l’invite de commandes :</span><span class="sxs-lookup"><span data-stu-id="1d224-120">Run the following at the command prompt:</span></span>
    
   ```PowerShell
   Get-CsDialinConferencingConfiguration
   ```

<span data-ttu-id="1d224-121">Cette applet de connexion récupère des informations sur la nécessité pour les participants d’enregistrer leur nom lorsqu’ils rejoignent une conférence et la façon dont Skype entreprise Server répond lorsque les participants rejoignent ou quittent une conférence rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="1d224-121">This cmdlet retrieves information about whether participants are required to record their name when joining a conference and how Skype for Business Server responds when participants join or leave a dial-in conference.</span></span>
    
4. <span data-ttu-id="1d224-122">Exécutez la commande suivante dans l’invite de commandes :</span><span class="sxs-lookup"><span data-stu-id="1d224-122">Run the following at the command prompt:</span></span>
    
   ```PowerShell
   Set-CsDialinConferencingConfiguration -Identity <identity of dial-in conferencing settings to be modified>
   [-EnableNameRecording <$true | $false>]
   [-EntryExitAnnouncementsEnabledByDefault <$true | $false>]
   [-EntryExitAnnouncementsType <UseNames | ToneOnly]
   ```

<span data-ttu-id="1d224-p106">Dans l’exemple ci-dessous, les paramètres sont configurés au niveau du site de Redmond. Les annonces sont activées, mais les participants ne sont pas invités à donner leur nom lorsqu’ils rejoignent une conférence. Une tonalité est émise lorsque les participants rejoignent ou quittent une conférence :</span><span class="sxs-lookup"><span data-stu-id="1d224-p106">In the following example, settings are configured at the site scope for Redmond. Announcements are turned on, but participants are not prompted to say their name when they join a conference. A tone is played when participants enter or leave a conference:</span></span>
  
```PowerShell
Set-CsDialinConferencingConfiguration -Identity site:Redmond
-EnableNameRecording $false
-EntryExitAnnouncementsEnabledByDefault $true
-EntryExitAnnouncementsType ToneOnly
```

<span data-ttu-id="1d224-126">Pour plus d’informations, y compris la syntaxe et une liste complète des paramètres, consultez la rubrique [Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="1d224-126">For more information, including syntax and a complete list of parameters, see [Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps).</span></span>
  

