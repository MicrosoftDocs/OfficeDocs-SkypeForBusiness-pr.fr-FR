---
title: Configuration d’une participation aux réunions sans code confidentiel dans Skype Entreprise Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c21e8861-bb75-45e8-8485-38daa3b8121c
description: 'Résumé : Apprenez à configurer la broche sans option de jointure dans Skype pour Business Server 2015 de réunion.'
ms.openlocfilehash: 6e9e26f856fec85b3f7436684d1b084eb3873ba9
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="configure-pin-less-meeting-join-in-skype-for-business-server"></a><span data-ttu-id="a8757-103">Configuration d’une participation aux réunions sans code confidentiel dans Skype Entreprise Server</span><span class="sxs-lookup"><span data-stu-id="a8757-103">Configure PIN-less meeting join in Skype for Business Server</span></span>
 
<span data-ttu-id="a8757-104">**Résumé :** Apprenez à configurer la broche sans option de jointure dans Skype pour Business Server 2015 de réunion.</span><span class="sxs-lookup"><span data-stu-id="a8757-104">**Summary:** Learn how to configure the PIN-less meeting join option in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="a8757-105">Lorsqu’un appelant d’accès à distance tente de joindre une réunion, le service de conférence Standard automatique (TCHA) place l’appelant un stylet d’exploitation qui est différente de la salle d’attente & #x 2014 ; Si un présentateur n’est pas déjà sur un appel et l’appelant à distance n’a pas entré un code confidentiel du leader.</span><span class="sxs-lookup"><span data-stu-id="a8757-105">When a dial-in caller attempts to join a meeting, the Conference Auto Attendant (CAA) service places the caller in a holding pen that is different from the Lobby &#x2014; if a presenter is not already on a call, and the dial-in caller has not entered a leader PIN.</span></span> <span data-ttu-id="a8757-106">L’option de participation à une réunion sans code confidentiel autorise les appelants à participer à une téléconférence sans entrer de code d’organisateur même s’ils sont les premiers à rejoindre un appel.</span><span class="sxs-lookup"><span data-stu-id="a8757-106">The PIN-less meeting join option allows dial-in callers to join a meeting without entering a leader PIN even if they are the first person on a call.</span></span> 
  
<span data-ttu-id="a8757-107">Lors de la configuration de cette fonctionnalité, rappelez-vous des points suivants :</span><span class="sxs-lookup"><span data-stu-id="a8757-107">Keep the following in mind when configuring this feature:</span></span>
  
- <span data-ttu-id="a8757-108">Cette option n’est valable que pour les réunions privées.</span><span class="sxs-lookup"><span data-stu-id="a8757-108">Applies to private meetings only.</span></span>
    
- <span data-ttu-id="a8757-109">Elle permet aux appelants RTC de rester dans des réunions privées sans qu’un utilisateur authentifié ne soit présent.</span><span class="sxs-lookup"><span data-stu-id="a8757-109">Allows PSTN callers to stay in private meetings without the presence of authenticated users.</span></span>
    
- <span data-ttu-id="a8757-110">Une fois le paramètre modifié, il s’applique à toutes les nouvelles réunions privées et aux réunions privées existantes.</span><span class="sxs-lookup"><span data-stu-id="a8757-110">After the setting is changed, it applies to all existing and new private meetings.</span></span>
    
- <span data-ttu-id="a8757-111">Il peut être activé sur le site de l’organisateur ou au niveau global.</span><span class="sxs-lookup"><span data-stu-id="a8757-111">Can be enabled either at the site of the organizer or at the global level.</span></span>
    
- <span data-ttu-id="a8757-112">Les options permettant de définir qui peut contourner la salle d’attente sont les suivantes :</span><span class="sxs-lookup"><span data-stu-id="a8757-112">Options for who can bypass the lobby can be set for either of the following:</span></span> 
    
  - <span data-ttu-id="a8757-113">**Tous les appelants venant de mon organisation sont admis directement**</span><span class="sxs-lookup"><span data-stu-id="a8757-113">**Anyone from my Organization with Callers get in directly**</span></span>
    
  - <span data-ttu-id="a8757-114">**N’importe quel autre appelant (aucune restriction) est admis directement** (il s’agit du paramètre par défaut).</span><span class="sxs-lookup"><span data-stu-id="a8757-114">**Anyone (no restrictions) with Callers get in directly** (This is the default setting.)</span></span>
    
- <span data-ttu-id="a8757-115">Lorsque la participation sans code confidentiel est activée, le service CAA invite quand même à entrer un code d’organisateur.</span><span class="sxs-lookup"><span data-stu-id="a8757-115">When configured to enable PIN-less join, the CAA service still prompts for a leader PIN.</span></span> <span data-ttu-id="a8757-116">Les utilisateurs peuvent participer à la réunion en saisissant ou non un code.</span><span class="sxs-lookup"><span data-stu-id="a8757-116">Users can join the meeting whether or not a PIN is entered.</span></span> <span data-ttu-id="a8757-117">Cependant, en conservant la possibilité d’entrer un code confidentiel du leader permet à un appelant d’accès à distance s’authentifier en tant que leader et de gérer la réunion si nécessaire.</span><span class="sxs-lookup"><span data-stu-id="a8757-117">However, retaining the ability to enter a leader PIN allows a dial-in caller to authenticate as a leader and manage the meeting if necessary.</span></span>
    
## <a name="configure-pin-less-meeting-join"></a><span data-ttu-id="a8757-118">Configurer la participation à la réunion sans code confidentiel</span><span class="sxs-lookup"><span data-stu-id="a8757-118">Configure PIN-less meeting join</span></span>

<span data-ttu-id="a8757-119">Pour activer la jointure sans code PIN réunion pour vos utilisateurs, vous devez utiliser l’applet de commande [Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) avec le paramètre AllowAnonymousPstnActivation comme suit :</span><span class="sxs-lookup"><span data-stu-id="a8757-119">To enable PIN-less meeting join for your users, use the [Set-CsDialInConferencingConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csdialinconferencingconfiguration?view=skype-ps) cmdlet with the AllowAnonymousPstnActivation parameter as follows:</span></span>
  
```
Set-CsDialInConferencingConfiguration -Identity  < global or site:sitename>  -AllowAnonymousPstnActivation $True
```

<span data-ttu-id="a8757-120">Par exemple, la commande suivante active une participation sans code confidentiel pour le site Redmond :</span><span class="sxs-lookup"><span data-stu-id="a8757-120">For example, the following command enables PIN-less meeting join for the site Redmond:</span></span>
  
```
Set-CsDialInConferencingConfiguration -Identity site:Redmond -AllowAnonymousPstnActivation $True

```

<span data-ttu-id="a8757-121">Pour des raisons de sécurité, lorsque la participation sans code confidentiel est activée, vous souhaiterez peut être empêcher les utilisateurs anonymes d’appeler, en vous assurant que la ConferencingPolicy est définie comme suit :</span><span class="sxs-lookup"><span data-stu-id="a8757-121">For security purposes, when PIN-less meeting join is turned on, you might want to restrict anonymous users from dialing out by ensuring the ConferencingPolicy is set as follows:</span></span>
  
```
Set-CsConferencingPolicy [-Identity <XdsIdentity>] -AllowAnonymousUsersToDialOut $False

```

<span data-ttu-id="a8757-122">Pour plus d’informations, voir [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="a8757-122">For more information, see [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span></span>
  

