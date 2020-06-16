---
title: Recommandation Créer des annuaires de conférences
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: (Recommended) Create Conference Directories
ms:assetid: 787f4c94-1c96-468a-a74d-e06b7bd4b8a3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn832056(v=OCS.15)
ms:contentKeyID: 63146389
ms.date: 10/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d5ce338c6eb67f545439bfe1e9f2134cd7f1e6d1
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44757165"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="recommended-create-conference-directories"></a><span data-ttu-id="d798c-102">Recommandation Créer des annuaires de conférences</span><span class="sxs-lookup"><span data-stu-id="d798c-102">(Recommended) Create Conference Directories</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d798c-103">_**Dernière modification de la rubrique :** 2014-10-03_</span><span class="sxs-lookup"><span data-stu-id="d798c-103">_**Topic Last Modified:** 2014-10-03_</span></span>

<span data-ttu-id="d798c-104">Les annuaires de conférence maintiennent un mappage entre l’ID de réunion alphanumérique qu’un participant utilise pour participer à une conférence en utilisant Lync 2013 et l’ID de conférence numérique uniquement qu’un participant de conférence rendez-vous utilise pour rejoindre la Conférence.</span><span class="sxs-lookup"><span data-stu-id="d798c-104">Conference directories maintain a mapping between the alphanumeric meeting ID that a participant uses to join a conference when using Lync 2013, and the numeric-only conference ID that a dial-in conferencing participant uses to join the conference.</span></span> <span data-ttu-id="d798c-105">Le format de l’ID de conférence est le suivant :</span><span class="sxs-lookup"><span data-stu-id="d798c-105">The format of the conference ID is as follows:</span></span>

    <housekeeping digit (1 digit)><conference directory (usually 1-2 digits)><conference number (variable number of digits><check digit (1 digit)>

<span data-ttu-id="d798c-106">La création de plusieurs annuaires de conférences permet de s’assurer que les ID de conférence resteront courts jusqu’à ce qu’une quantité importante de conférences ait été créée.</span><span class="sxs-lookup"><span data-stu-id="d798c-106">Creating multiple conference directories will ensure that conference IDs will stay short until a significant amount of conferences have been created.</span></span> <span data-ttu-id="d798c-107">Dans une organisation avec un nombre classique de conférences par utilisateur, nous vous recommandons de créer un annuaire de conférences pour chaque 999 utilisateurs du pool.</span><span class="sxs-lookup"><span data-stu-id="d798c-107">In an organization with a typical number of conferences per user, we recommend that you create one conference directory for every 999 users in the pool.</span></span> <span data-ttu-id="d798c-108">À l’aide de cette instruction, les ID de conférence peuvent généralement être réduits.</span><span class="sxs-lookup"><span data-stu-id="d798c-108">Using this guideline the conference IDs can generally be kept small.</span></span> <span data-ttu-id="d798c-109">Toutefois, une fois que le nombre d’annuaires de conférence (dans les pools) dépasse 9, la longueur de l’ID de conférence augmentera pour prendre en charge des conférences supplémentaires.</span><span class="sxs-lookup"><span data-stu-id="d798c-109">However, once the number of conference directories (across the pools) exceed 9, the Conference ID length will grow to support additional conferences.</span></span>

<div>

## <a name="creating-a-conference-directory"></a><span data-ttu-id="d798c-110">Création d’un annuaire des conférences</span><span class="sxs-lookup"><span data-stu-id="d798c-110">Creating a conference directory</span></span>

1.  <span data-ttu-id="d798c-111">Dans Lync Server Management Shell, tapez l’applet de commande suivante :</span><span class="sxs-lookup"><span data-stu-id="d798c-111">In Lync Server Management Shell, type the following cmdlet:</span></span>
    
        New-CsConferenceDirectory -Identity <XdsGlobalRelativeIdentity> -HomePool <String> [-Confirm [<SwitchParameter>]] [-Force <SwitchParameter>] [-WhatIf [<SwitchParameter>]]
    
    <span data-ttu-id="d798c-112">Par exemple, le code suivant crée un annuaire des conférences avec l’identité 42, hébergée sur le pool atl-cs-001.litwareinc.com :</span><span class="sxs-lookup"><span data-stu-id="d798c-112">For example, the following creates a conference directory with the identity 42, hosted on the pool atl-cs-001.litwareinc.com:</span></span>
    
        New-CsConferenceDirectory -Identity 42 -HomePool "atl-cs-001.litwareinc.com"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d798c-113">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="d798c-113">See Also</span></span>


[<span data-ttu-id="d798c-114">Exigences en matière de conférence rendez-vous dans Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d798c-114">Dial-in conferencing requirements in Lync Server 2013</span></span>](lync-server-2013-dial-in-conferencing-requirements.md)  


[<span data-ttu-id="d798c-115">New-CsConferenceDirectory</span><span class="sxs-lookup"><span data-stu-id="d798c-115">New-CsConferenceDirectory</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsConferenceDirectory)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

