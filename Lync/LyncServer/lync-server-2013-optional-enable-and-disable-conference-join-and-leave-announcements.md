---
title: Module Activer et désactiver les annonces de participation et de congé de conférence
description: Module Activer et désactiver les annonces de participation et de congé de conférence.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Enable and disable conference join and leave announcements
ms:assetid: c9529568-e66c-48d8-aef2-9072f9c336ff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398834(v=OCS.15)
ms:contentKeyID: 48185403
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 70cd6b452a44d7d40f23d5ca96b6e4b7b063d2ec
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565780"
---
# <a name="optional-enable-and-disable-conference-join-and-leave-announcements-in-lync-server-2013"></a><span data-ttu-id="b0552-103">Module Activer et désactiver les annonces de participation et de sortie de conférence dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b0552-103">(Optional) Enable and disable conference join and leave announcements in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b0552-104">_**Dernière modification de la rubrique :** 2012-09-30_</span><span class="sxs-lookup"><span data-stu-id="b0552-104">_**Topic Last Modified:** 2012-09-30_</span></span>

<span data-ttu-id="b0552-105">Lorsque des utilisateurs d’appels entrants rejoignent ou quittent une conférence, l’application d’annonce de conférence peut annoncer leur entrée ou leur sortie en lisant une tonalité ou en disant leur nom.</span><span class="sxs-lookup"><span data-stu-id="b0552-105">When dial-in users join or leave a conference, the Conferencing Announcement application can announce their entrance or exit by playing a tone or saying their names.</span></span> <span data-ttu-id="b0552-106">Vous pouvez modifier le fonctionnement des annonces en exécutant des cmdlets.</span><span class="sxs-lookup"><span data-stu-id="b0552-106">You can change how announcements work by running cmdlets.</span></span> <span data-ttu-id="b0552-107">Cette étape est facultative.</span><span class="sxs-lookup"><span data-stu-id="b0552-107">This step is optional.</span></span>

<div>

## <a name="to-modify-the-conference-join-and-leave-announcement-behavior"></a><span data-ttu-id="b0552-108">Pour modifier le comportement des annonces indiquant qu’un utilisateur rejoint ou quitte une conférence</span><span class="sxs-lookup"><span data-stu-id="b0552-108">To modify the conference join and leave announcement behavior</span></span>

1.  <span data-ttu-id="b0552-109">Ouvrez une session sur l’ordinateur en tant que membre du groupe RTCUniversalServerAdmins ou membre du rôle **Cs-ServerAdministratorr** ou **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="b0552-109">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-ServerAdministrator** or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="b0552-110">Démarrez Lync Server Management Shell : cliquez sur \*\*Démarrer \*\*, \*\*Tous les programmes \*\*, \*\*Microsoft Lync Server 2013 \*\*, puis sur **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="b0552-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="b0552-111">Exécutez la commande suivante à l’invite de commandes :</span><span class="sxs-lookup"><span data-stu-id="b0552-111">Run the following at the command prompt:</span></span>
    
        Get-CsDialinConferencingConfiguration
    
    <span data-ttu-id="b0552-112">Cette applet de commande permet de récupérer des informations indiquant si les participants doivent enregistrer leur nom lors de la participation à une conférence et comment Lync Server répond quand les participants rejoignent ou quittent une conférence rendez-vous.</span><span class="sxs-lookup"><span data-stu-id="b0552-112">This cmdlet retrieves information about whether participants are required to record their name when joining a conference and how Lync Server responds when participants join or leave a dial-in conference.</span></span>

4.  <span data-ttu-id="b0552-113">Exécutez la commande suivante à l’invite de commandes :</span><span class="sxs-lookup"><span data-stu-id="b0552-113">Run the following at the command prompt:</span></span>
    
        Set-CsDialinConferencingConfiguration -Identity <identity of dial-in conferencing settings to be modified>
        [-EnableNameRecording <$true | $false>]
        [-EntryExitAnnouncementsEnabledByDefault <$true | $false>]
        [-EntryExitAnnouncementsType <UseNames | ToneOnly]
    
    <span data-ttu-id="b0552-114">**EnableNameRecording**     Détermine si les participants anonymes sont invités à enregistrer leur nom avant d’entrer dans la Conférence.</span><span class="sxs-lookup"><span data-stu-id="b0552-114">**EnableNameRecording**   Determines whether anonymous participants are asked to record their name before entering the conference.</span></span> <span data-ttu-id="b0552-115">La valeur par défaut est « $true », ce qui signifie que les participants anonymes sont invités à donner leur nom avant de participer à une conférence.</span><span class="sxs-lookup"><span data-stu-id="b0552-115">The default value is "$true," which means that anonymous participants are prompted to state their name when joining a conference.</span></span> <span data-ttu-id="b0552-116">(Les participants authentifiés ne sont pas tenus d’indiquer leur nom, car leur nom complet est utilisé.)</span><span class="sxs-lookup"><span data-stu-id="b0552-116">(Authenticated participants do not record their name because their display name is used instead.)</span></span>
    
    <span data-ttu-id="b0552-117">**EntryExitAnnouncementsEnabledByDefault**     Indique si les annonces sont activées ou désactivées par défaut.</span><span class="sxs-lookup"><span data-stu-id="b0552-117">**EntryExitAnnouncementsEnabledByDefault**   Indicates whether announcements are turned on or off by default.</span></span> <span data-ttu-id="b0552-118">La valeur par défaut est « $false », ce qui signifie qu’aucune annonce n’est effectuée lorsque les participants rejoignent ou quittent une conférence.</span><span class="sxs-lookup"><span data-stu-id="b0552-118">The default value is "$false," which means that by default there are no announcements when participants join or leave a conference.</span></span> <span data-ttu-id="b0552-119">Lorsqu’il planifie une réunion, l’organisateur peut ignorer ce paramètre.</span><span class="sxs-lookup"><span data-stu-id="b0552-119">The meeting organizer can override this setting when scheduling a meeting.</span></span>
    
    <span data-ttu-id="b0552-120">**EntryExitAnnouncementsType**     Indique l’action effectuée chaque fois qu’un participant rejoint ou quitte une conférence pour laquelle les annonces sont activées.</span><span class="sxs-lookup"><span data-stu-id="b0552-120">**EntryExitAnnouncementsType**   Indicates the action taken whenever a participant joins or leaves a conference for which announcements are enabled.</span></span> <span data-ttu-id="b0552-121">La valeur par défaut est « UseNames », ce qui signifie qu’une annonce similaire à la suivante est effectuée : « Ken Myer a rejoint la conférence » lorsque les annonces sont activées.</span><span class="sxs-lookup"><span data-stu-id="b0552-121">The default value is "UseNames," which means there is an announcement similar to the following: "Ken Myer has joined the conference" when announcements are turned on.</span></span>
    
    <span data-ttu-id="b0552-p105">Vous pouvez configurer ces paramètres globalement ou au niveau d’un site. (Les paramètres configurés au niveau du site sont prioritaires sur les paramètres configurés au niveau global.)</span><span class="sxs-lookup"><span data-stu-id="b0552-p105">You can configure these settings at the global scope or at the site scope. Settings configured at the site scope take precedence over settings configured at the global scope.</span></span>
    
    <span data-ttu-id="b0552-124">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="b0552-124">For example:</span></span>
    
        Set-CsDialinConferencingConfiguration -Identity site:Redmond
        -EnableNameRecording $false
        -EntryExitAnnouncementsEnabledByDefault $true
        -EntryExitAnnouncementsType ToneOnly
    
    <span data-ttu-id="b0552-p106">Dans cet exemple, les paramètres sont configurés au niveau du site de Redmond. Les annonces sont activées, mais les participants ne sont pas invités à donner leur nom lorsqu’ils rejoignent une conférence. Une tonalité est émise lorsque les participants rejoignent ou quittent une conférence.</span><span class="sxs-lookup"><span data-stu-id="b0552-p106">In this example, settings are configured at the site scope for Redmond. Announcements are turned on, but participants are not prompted to say their name when they join a conference. A tone is played when participants enter or leave a conference.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

