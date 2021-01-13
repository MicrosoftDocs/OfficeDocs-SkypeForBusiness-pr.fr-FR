---
title: Configurer la réunion sans code confidentiel dans Skype Entreprise Server
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
ms.assetid: c21e8861-bb75-45e8-8485-38daa3b8121c
description: 'Résumé : Découvrez comment configurer l’option de rejoindre une réunion sans code confidentiel dans Skype Entreprise Server.'
ms.openlocfilehash: 794bf13d92857a18254f903a1c5dcca98d0a1ec0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827984"
---
# <a name="configure-pin-less-meeting-join-in-skype-for-business-server"></a><span data-ttu-id="4cb5b-103">Configurer la réunion sans code confidentiel dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="4cb5b-103">Configure PIN-less meeting join in Skype for Business Server</span></span>
 
<span data-ttu-id="4cb5b-104">**Résumé :** Découvrez comment configurer l’option de rejoindre une réunion sans code confidentiel dans Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="4cb5b-104">**Summary:** Learn how to configure the PIN-less meeting join option in Skype for Business Server.</span></span>
  
<span data-ttu-id="4cb5b-105">Lorsqu’un appelant tente de participer à une réunion, le service d’Standard automatique de conférence (CAA) place l’appelant dans un stylet différent du &#x2014; de salle d’accueil si un présentateur n’est pas déjà en appel et que l’appelant n’a pas entré de code confidentiel d’leader.</span><span class="sxs-lookup"><span data-stu-id="4cb5b-105">When a dial-in caller attempts to join a meeting, the Conference Auto Attendant (CAA) service places the caller in a holding pen that is different from the Lobby &#x2014; if a presenter is not already on a call, and the dial-in caller has not entered a leader PIN.</span></span> <span data-ttu-id="4cb5b-106">L’option de rejoindre une réunion sans code confidentiel permet aux appelants de participer à une réunion sans entrer de code confidentiel d’leader, même s’ils sont la première personne à participer à un appel.</span><span class="sxs-lookup"><span data-stu-id="4cb5b-106">The PIN-less meeting join option allows dial-in callers to join a meeting without entering a leader PIN even if they are the first person on a call.</span></span> 
  
<span data-ttu-id="4cb5b-107">Gardez à l’esprit les questions suivantes lors de la configuration de cette fonctionnalité :</span><span class="sxs-lookup"><span data-stu-id="4cb5b-107">Keep the following in mind when configuring this feature:</span></span>
  
- <span data-ttu-id="4cb5b-108">S’applique uniquement aux réunions privées.</span><span class="sxs-lookup"><span data-stu-id="4cb5b-108">Applies to private meetings only.</span></span>
    
- <span data-ttu-id="4cb5b-109">Permet aux appelants PSTN de rester dans des réunions privées sans la présence d’utilisateurs authentifiés.</span><span class="sxs-lookup"><span data-stu-id="4cb5b-109">Allows PSTN callers to stay in private meetings without the presence of authenticated users.</span></span>
    
- <span data-ttu-id="4cb5b-110">Une fois le paramètre modifié, il s’applique à toutes les réunions privées existantes et nouvelles.</span><span class="sxs-lookup"><span data-stu-id="4cb5b-110">After the setting is changed, it applies to all existing and new private meetings.</span></span>
    
- <span data-ttu-id="4cb5b-111">Peut être activé au niveau du site de l’organisateur ou au niveau global.</span><span class="sxs-lookup"><span data-stu-id="4cb5b-111">Can be enabled either at the site of the organizer or at the global level.</span></span>
    
- <span data-ttu-id="4cb5b-112">Les options qui peuvent contourner la salle d’entrée peuvent être définies pour l’une des options suivantes :</span><span class="sxs-lookup"><span data-stu-id="4cb5b-112">Options for who can bypass the lobby can be set for either of the following:</span></span> 
    
  - <span data-ttu-id="4cb5b-113">**Tous les membres de mon organisation avec des appelants entrent directement**</span><span class="sxs-lookup"><span data-stu-id="4cb5b-113">**Anyone from my Organization with Callers get in directly**</span></span>
    
  - <span data-ttu-id="4cb5b-114">**Tout le monde (aucune restriction) avec** les appelants entre directement (il s’agit du paramètre par défaut.)</span><span class="sxs-lookup"><span data-stu-id="4cb5b-114">**Anyone (no restrictions) with Callers get in directly** (This is the default setting.)</span></span>
    
- <span data-ttu-id="4cb5b-115">Lorsqu’il est configuré pour activer la jointeur sans code confidentiel, le service CAA demande toujours un code confidentiel d’leader.</span><span class="sxs-lookup"><span data-stu-id="4cb5b-115">When configured to enable PIN-less join, the CAA service still prompts for a leader PIN.</span></span> <span data-ttu-id="4cb5b-116">Les utilisateurs peuvent participer à la réunion, qu’un code confidentiel soit entré ou non.</span><span class="sxs-lookup"><span data-stu-id="4cb5b-116">Users can join the meeting whether or not a PIN is entered.</span></span> <span data-ttu-id="4cb5b-117">Toutefois, le fait de conserver la possibilité d’entrer un code confidentiel d’leader permet à un appelant de s’authentifier en tant qu’dirigeant et de gérer la réunion si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="4cb5b-117">However, retaining the ability to enter a leader PIN allows a dial-in caller to authenticate as a leader and manage the meeting if necessary.</span></span>
    
## <a name="configure-pin-less-meeting-join"></a><span data-ttu-id="4cb5b-118">Configurer la réunion sans code confidentiel</span><span class="sxs-lookup"><span data-stu-id="4cb5b-118">Configure PIN-less meeting join</span></span>

<span data-ttu-id="4cb5b-119">Pour activer la réunion sans code confidentiel pour vos utilisateurs, utilisez l’cmdlet [Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) avec le paramètre AllowAnonymousPstnActivation comme suit :</span><span class="sxs-lookup"><span data-stu-id="4cb5b-119">To enable PIN-less meeting join for your users, use the [Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) cmdlet with the AllowAnonymousPstnActivation parameter as follows:</span></span>
  
```PowerShell
Set-CsDialInConferencingConfiguration -Identity  < global or site:sitename>  -AllowAnonymousPstnActivation $True
```

<span data-ttu-id="4cb5b-120">Par exemple, la commande suivante active la réunion sans code confidentiel pour le site Redmond :</span><span class="sxs-lookup"><span data-stu-id="4cb5b-120">For example, the following command enables PIN-less meeting join for the site Redmond:</span></span>
  
```PowerShell
Set-CsDialInConferencingConfiguration -Identity site:Redmond -AllowAnonymousPstnActivation $True
```

<span data-ttu-id="4cb5b-121">Pour des raisons de sécurité, lorsque la réunion sans code confidentiel est désactivée, vous pouvez limiter la numérotation des utilisateurs anonymes en vous assurant que conferencingPolicy est définie comme suit :</span><span class="sxs-lookup"><span data-stu-id="4cb5b-121">For security purposes, when PIN-less meeting join is turned on, you might want to restrict anonymous users from dialing out by ensuring the ConferencingPolicy is set as follows:</span></span>
  
```PowerShell
Set-CsConferencingPolicy [-Identity <XdsIdentity>] -AllowAnonymousUsersToDialOut $False
```

<span data-ttu-id="4cb5b-122">Pour plus d’informations, [voir Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="4cb5b-122">For more information, see [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span></span>
  

