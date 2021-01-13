---
title: Gérer les annonces de rejoindre et de quitter une conférence dans Skype Entreprise Server
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
ms.assetid: cb09f9c2-c6dc-4083-b45a-8b6773341373
description: 'Résumé : Découvrez comment gérer les annonces de rejoindre et de quitter une conférence dans Skype Entreprise Server.'
ms.openlocfilehash: 9ca73d3d32ce03a8119d805b5e7260c0a871eb27
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828104"
---
# <a name="manage-conference-join-and-leave-announcements-in-skype-for-business-server"></a><span data-ttu-id="3f873-103">Gérer les annonces de rejoindre et de quitter une conférence dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="3f873-103">Manage conference join and leave announcements in Skype for Business Server</span></span>
 
<span data-ttu-id="3f873-104">**Résumé :** Découvrez comment gérer les annonces de participer à une conférence et de laisser des annonces dans Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="3f873-104">**Summary:** Learn how to manage conference join and leave announcements in Skype for Business Server.</span></span>
  
<span data-ttu-id="3f873-105">Lorsque les utilisateurs d’appels d’accès rejoignent ou quittent une conférence, l’application Annonce de conférence peut annoncer leur entrée ou leur sortie en nonçant une tonalité ou en nonçant leurs noms.</span><span class="sxs-lookup"><span data-stu-id="3f873-105">When dial-in users join or leave a conference, the Conferencing Announcement application can announce their entrance or exit by playing a tone or saying their names.</span></span> <span data-ttu-id="3f873-106">Vous pouvez modifier le fonctionnement des annonces à l’aide de Skype Entreprise Server Management Shell et de l’cmdlet **Set-CsDialinConferencing** avec les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="3f873-106">You can change how announcements work by using Skype for Business Server Management Shell and the **Set-CsDialinConferencing** cmdlet with the following parameters:</span></span>
  
- <span data-ttu-id="3f873-107">EnableNameRecording : détermine si les participants anonymes sont invités à enregistrer leur nom avant d’accéder à la conférence.</span><span class="sxs-lookup"><span data-stu-id="3f873-107">EnableNameRecording - Determines whether anonymous participants are asked to record their name before entering the conference.</span></span> <span data-ttu-id="3f873-108">La valeur par défaut est « $true », ce qui signifie que les participants anonymes sont invités à donner leur nom avant de participer à une conférence.</span><span class="sxs-lookup"><span data-stu-id="3f873-108">The default value is "$true," which means that anonymous participants are prompted to state their name when joining a conference.</span></span> <span data-ttu-id="3f873-109">(Les participants authentifiés ne sont pas tenus d’indiquer leur nom, car leur nom complet est utilisé.)</span><span class="sxs-lookup"><span data-stu-id="3f873-109">(Authenticated participants do not record their name because their display name is used instead.)</span></span>
    
- <span data-ttu-id="3f873-110">EntryExitAnnouncementsEnabledByDefault : indique si les annonces sont allumées ou désactivées par défaut.</span><span class="sxs-lookup"><span data-stu-id="3f873-110">EntryExitAnnouncementsEnabledByDefault - Indicates whether announcements are turned on or off by default.</span></span> <span data-ttu-id="3f873-111">La valeur par défaut est « $false », ce qui signifie qu’aucune annonce n’est effectuée lorsque les participants rejoignent ou quittent une conférence.</span><span class="sxs-lookup"><span data-stu-id="3f873-111">The default value is "$false," which means that by default there are no announcements when participants join or leave a conference.</span></span> <span data-ttu-id="3f873-112">Lorsqu’il planifie une réunion, l’organisateur peut ignorer ce paramètre.</span><span class="sxs-lookup"><span data-stu-id="3f873-112">The meeting organizer can override this setting when scheduling a meeting.</span></span>
    
- <span data-ttu-id="3f873-113">EntryExitAnnouncementsType : indique l’action prise chaque fois qu’un participant rejoint ou quitte une conférence pour laquelle les annonces sont activées.</span><span class="sxs-lookup"><span data-stu-id="3f873-113">EntryExitAnnouncementsType - Indicates the action taken whenever a participant joins or leaves a conference for which announcements are enabled.</span></span> <span data-ttu-id="3f873-114">La valeur par défaut est « UseNames », ce qui signifie qu’une annonce similaire à la suivante est effectuée : « Ken Myer a rejoint la conférence » lorsque les annonces sont activées.</span><span class="sxs-lookup"><span data-stu-id="3f873-114">The default value is "UseNames," which means there is an announcement similar to the following: "Ken Myer has joined the conference" when announcements are turned on.</span></span>
    
<span data-ttu-id="3f873-p105">Vous pouvez configurer ces paramètres globalement ou au niveau d’un site. (Les paramètres configurés au niveau du site sont prioritaires sur les paramètres configurés au niveau global.)</span><span class="sxs-lookup"><span data-stu-id="3f873-p105">You can configure these settings at the global scope or at the site scope. Settings configured at the site scope take precedence over settings configured at the global scope.</span></span>
   

### <a name="to-modify-the-conference-join-and-leave-announcement-behavior"></a><span data-ttu-id="3f873-117">Pour modifier le comportement des annonces indiquant qu’un utilisateur rejoint ou quitte une conférence</span><span class="sxs-lookup"><span data-stu-id="3f873-117">To modify the conference join and leave announcement behavior</span></span>

1. <span data-ttu-id="3f873-118">Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou membre du rôle Cs-ServerAdministratorr ou CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="3f873-118">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the Cs-ServerAdministrator or CsAdministrator role.</span></span>
    
2. <span data-ttu-id="3f873-119">Démarrez Skype Entreprise Server Management Shell : cliquez sur **Démarrer,** sur Tous les **programmes,** sur Skype Entreprise **2015,** puis sur Skype Entreprise **Server Management Shell.**</span><span class="sxs-lookup"><span data-stu-id="3f873-119">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="3f873-120">Exécutez la commande suivante à l’invite de commandes :</span><span class="sxs-lookup"><span data-stu-id="3f873-120">Run the following at the command prompt:</span></span>
    
   ```PowerShell
   Get-CsDialinConferencingConfiguration
   ```

<span data-ttu-id="3f873-121">Cette cmdlet récupère des informations pour savoir si les participants doivent enregistrer leur nom lors de leur participation à une conférence et comment Skype Entreprise Server répond lorsque les participants rejoignent ou quittent une conférence téléphonique.</span><span class="sxs-lookup"><span data-stu-id="3f873-121">This cmdlet retrieves information about whether participants are required to record their name when joining a conference and how Skype for Business Server responds when participants join or leave a dial-in conference.</span></span>
    
4. <span data-ttu-id="3f873-122">Exécutez la commande suivante à l’invite de commandes :</span><span class="sxs-lookup"><span data-stu-id="3f873-122">Run the following at the command prompt:</span></span>
    
   ```PowerShell
   Set-CsDialinConferencingConfiguration -Identity <identity of dial-in conferencing settings to be modified>
   [-EnableNameRecording <$true | $false>]
   [-EntryExitAnnouncementsEnabledByDefault <$true | $false>]
   [-EntryExitAnnouncementsType <UseNames | ToneOnly]
   ```

<span data-ttu-id="3f873-123">Dans l’exemple suivant, les paramètres sont configurés au niveau de l’étendue Site pour Redmond.</span><span class="sxs-lookup"><span data-stu-id="3f873-123">In the following example, settings are configured at the site scope for Redmond.</span></span> <span data-ttu-id="3f873-124">Les annonces sont activées, mais les participants ne sont pas invités à donner leur nom lorsqu’ils rejoignent une conférence.</span><span class="sxs-lookup"><span data-stu-id="3f873-124">Announcements are turned on, but participants are not prompted to say their name when they join a conference.</span></span> <span data-ttu-id="3f873-125">Une tonalité est lus lorsque les participants entrent ou quittent une conférence :</span><span class="sxs-lookup"><span data-stu-id="3f873-125">A tone is played when participants enter or leave a conference:</span></span>
  
```PowerShell
Set-CsDialinConferencingConfiguration -Identity site:Redmond
-EnableNameRecording $false
-EntryExitAnnouncementsEnabledByDefault $true
-EntryExitAnnouncementsType ToneOnly
```

<span data-ttu-id="3f873-126">Pour plus d’informations, y compris la syntaxe et une liste complète des paramètres, voir [Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="3f873-126">For more information, including syntax and a complete list of parameters, see [Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps).</span></span>
  

