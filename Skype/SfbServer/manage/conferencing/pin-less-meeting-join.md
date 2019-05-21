---
title: Configuration d’une participation aux réunions sans code confidentiel dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c21e8861-bb75-45e8-8485-38daa3b8121c
description: 'Résumé: Découvrez comment configurer l’option de participation à une réunion sans punaise dans Skype entreprise Server.'
ms.openlocfilehash: ecd1d2bf184dd6b9e1ff78e16c2ca1eb8da73ef9
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34280382"
---
# <a name="configure-pin-less-meeting-join-in-skype-for-business-server"></a><span data-ttu-id="5dddd-103">Configuration d’une participation aux réunions sans code confidentiel dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="5dddd-103">Configure PIN-less meeting join in Skype for Business Server</span></span>
 
<span data-ttu-id="5dddd-104">**Résumé:** Découvrez comment configurer l’option de participation à une réunion sans punaise dans Skype entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="5dddd-104">**Summary:** Learn how to configure the PIN-less meeting join option in Skype for Business Server.</span></span>
  
<span data-ttu-id="5dddd-105">Lorsqu’un appelant rendez-vous tente de participer à une réunion, le service de la Conférence automatique (CAA) place l’appelant dans un stylet qui est différent de la salle d’attente & # x2014; Si un présentateur n’est pas en cours d’appel, et si le numéro d’appelant n’a pas été entré,</span><span class="sxs-lookup"><span data-stu-id="5dddd-105">When a dial-in caller attempts to join a meeting, the Conference Auto Attendant (CAA) service places the caller in a holding pen that is different from the Lobby &#x2014; if a presenter is not already on a call, and the dial-in caller has not entered a leader PIN.</span></span> <span data-ttu-id="5dddd-106">L’option de participation à une réunion sans code confidentiel autorise les appelants à participer à une téléconférence sans entrer de code d’organisateur même s’ils sont les premiers à rejoindre un appel.</span><span class="sxs-lookup"><span data-stu-id="5dddd-106">The PIN-less meeting join option allows dial-in callers to join a meeting without entering a leader PIN even if they are the first person on a call.</span></span> 
  
<span data-ttu-id="5dddd-107">Lors de la configuration de cette fonctionnalité, rappelez-vous des points suivants :</span><span class="sxs-lookup"><span data-stu-id="5dddd-107">Keep the following in mind when configuring this feature:</span></span>
  
- <span data-ttu-id="5dddd-108">Cette option n’est valable que pour les réunions privées.</span><span class="sxs-lookup"><span data-stu-id="5dddd-108">Applies to private meetings only.</span></span>
    
- <span data-ttu-id="5dddd-109">Elle permet aux appelants RTC de rester dans des réunions privées sans qu’un utilisateur authentifié ne soit présent.</span><span class="sxs-lookup"><span data-stu-id="5dddd-109">Allows PSTN callers to stay in private meetings without the presence of authenticated users.</span></span>
    
- <span data-ttu-id="5dddd-110">Une fois le paramètre modifié, il s’applique à toutes les nouvelles réunions privées et aux réunions privées existantes.</span><span class="sxs-lookup"><span data-stu-id="5dddd-110">After the setting is changed, it applies to all existing and new private meetings.</span></span>
    
- <span data-ttu-id="5dddd-111">Il peut être activé sur le site de l’organisateur ou au niveau global.</span><span class="sxs-lookup"><span data-stu-id="5dddd-111">Can be enabled either at the site of the organizer or at the global level.</span></span>
    
- <span data-ttu-id="5dddd-112">Les options permettant de définir qui peut contourner la salle d’attente sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="5dddd-112">Options for who can bypass the lobby can be set for either of the following:</span></span> 
    
  - <span data-ttu-id="5dddd-113">**Tous les appelants venant de mon organisation sont admis directement**</span><span class="sxs-lookup"><span data-stu-id="5dddd-113">**Anyone from my Organization with Callers get in directly**</span></span>
    
  - <span data-ttu-id="5dddd-114">**N’importe quel autre appelant (aucune restriction) est admis directement** (il s’agit du paramètre par défaut).</span><span class="sxs-lookup"><span data-stu-id="5dddd-114">**Anyone (no restrictions) with Callers get in directly** (This is the default setting.)</span></span>
    
- <span data-ttu-id="5dddd-115">Lorsque la participation sans code confidentiel est activée, le service CAA invite quand même à entrer un code d’organisateur.</span><span class="sxs-lookup"><span data-stu-id="5dddd-115">When configured to enable PIN-less join, the CAA service still prompts for a leader PIN.</span></span> <span data-ttu-id="5dddd-116">Les utilisateurs peuvent participer à la réunion en saisissant ou non un code.</span><span class="sxs-lookup"><span data-stu-id="5dddd-116">Users can join the meeting whether or not a PIN is entered.</span></span> <span data-ttu-id="5dddd-117">Néanmoins, si nécessaire, le maintien de la possibilité d’entrer un code confidentiel permet à un appelant rendez-vous de s’authentifier en tant que leader et de gérer la réunion si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="5dddd-117">However, retaining the ability to enter a leader PIN allows a dial-in caller to authenticate as a leader and manage the meeting if necessary.</span></span>
    
## <a name="configure-pin-less-meeting-join"></a><span data-ttu-id="5dddd-118">Configurer la participation à la réunion sans code confidentiel</span><span class="sxs-lookup"><span data-stu-id="5dddd-118">Configure PIN-less meeting join</span></span>

<span data-ttu-id="5dddd-119">Pour activer la fonction de réunion sans punaise pour vos utilisateurs, utilisez l’applet de connexion [Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) avec le paramètre AllowAnonymousPstnActivation comme suit:</span><span class="sxs-lookup"><span data-stu-id="5dddd-119">To enable PIN-less meeting join for your users, use the [Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) cmdlet with the AllowAnonymousPstnActivation parameter as follows:</span></span>
  
```
Set-CsDialInConferencingConfiguration -Identity  < global or site:sitename>  -AllowAnonymousPstnActivation $True
```

<span data-ttu-id="5dddd-120">Par exemple, la commande suivante active une participation sans code confidentiel pour le site Redmond :</span><span class="sxs-lookup"><span data-stu-id="5dddd-120">For example, the following command enables PIN-less meeting join for the site Redmond:</span></span>
  
```
Set-CsDialInConferencingConfiguration -Identity site:Redmond -AllowAnonymousPstnActivation $True
```

<span data-ttu-id="5dddd-121">Pour des raisons de sécurité, lorsque la participation sans code confidentiel est activée, vous souhaiterez peut être empêcher les utilisateurs anonymes d’appeler, en vous assurant que la ConferencingPolicy est définie comme suit :</span><span class="sxs-lookup"><span data-stu-id="5dddd-121">For security purposes, when PIN-less meeting join is turned on, you might want to restrict anonymous users from dialing out by ensuring the ConferencingPolicy is set as follows:</span></span>
  
```
Set-CsConferencingPolicy [-Identity <XdsIdentity>] -AllowAnonymousUsersToDialOut $False
```

<span data-ttu-id="5dddd-122">Pour plus d’informations, consultez la rubrique [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="5dddd-122">For more information, see [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span></span>
  

