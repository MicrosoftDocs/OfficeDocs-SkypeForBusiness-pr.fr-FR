---
title: Configurer l’échappatoire de messagerie vocale dans Skype Entreprise
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a1d19e6c-82ff-4768-8ae5-da981368ce40
description: 'Résumé : Découvrez comment configurer la messagerie vocale dans Skype Entreprise Server à l’aide de Skype Entreprise Server Management Shell.'
ms.openlocfilehash: c74142cf3b0f6c9d5a871e116d8e163a095ad3cd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51106370"
---
# <a name="configure-voice-mail-escape-in-skype-for-business"></a><span data-ttu-id="962d1-103">Configurer l’échappatoire de messagerie vocale dans Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="962d1-103">Configure voice mail escape in Skype for Business</span></span>

<span data-ttu-id="962d1-104">**Résumé :** Découvrez comment configurer la messagerie vocale dans Skype Entreprise Server à l’aide de Skype Entreprise Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="962d1-104">**Summary:** Learn how to configure voice mail escape in Skype for Business Server by using the Skype for Business Server Management Shell.</span></span>

<span data-ttu-id="962d1-105">Lorsqu’un utilisateur configure la sonnerie simultanée sur un téléphone mobile, un appelant est généralement acheminé vers la messagerie vocale personnelle de l’utilisateur si le téléphone mobile est éteint, hors batterie ou hors de portée.</span><span class="sxs-lookup"><span data-stu-id="962d1-105">When a user configures simultaneous ringing to a mobile phone, a caller will typically be routed to the user's personal voice mail if the mobile phone is turned off, out of battery power, or out of range.</span></span> <span data-ttu-id="962d1-106">Avec Skype Entreprise Server, les utilisateurs peuvent choisir d’avoir des appels professionnels acheminés vers leur système de messagerie vocale d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="962d1-106">With Skype for Business Server , users can opt to have business-related calls routed to their corporate voice mail system.</span></span> <span data-ttu-id="962d1-107">Plus précisément, un timer peut être configuré et, si la messagerie vocale de l’opérateur répond à l’appel dans la plage de temps définie, Skype Entreprise Server se déconnecte du système de messagerie vocale de l’opérateur (et de la messagerie vocale personnelle de l’utilisateur), tandis que les points de terminaison restants de l’utilisateur dans le système d’entreprise continuent de sonner.</span><span class="sxs-lookup"><span data-stu-id="962d1-107">Specifically, a timer can be configured, and if the call is answered by the carrier's voice mail within the range of time defined, Skype for Business Server will disconnect from the carrier's voice mail system (and the user's personal voice mail), while the user's remaining endpoints in the corporate system continue to ring.</span></span> <span data-ttu-id="962d1-108">Ainsi, l’appelant est automatiquement acheminé vers la messagerie vocale d’entreprise de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="962d1-108">This way, the caller is automatically routed to the user's corporate voice mail.</span></span>

<span data-ttu-id="962d1-109">Cette configuration est effectuée à l’aide de l’cmdlet Skype Entreprise Server Management Shell, **Set-CsVoicePolicy,** au niveau de la stratégie de voix, avec les paramètres suivants.</span><span class="sxs-lookup"><span data-stu-id="962d1-109">This configuration is performed using the Skype for Business Server Management Shell cmdlet, **Set-CsVoicePolicy**, at the voice policy level, with the following parameters.</span></span>

### <a name="to-configure-voice-mail-escape"></a><span data-ttu-id="962d1-110">Pour configurer l’échappage de messagerie vocale</span><span class="sxs-lookup"><span data-stu-id="962d1-110">To configure voice mail escape</span></span>

1. <span data-ttu-id="962d1-111">Démarrez Skype Entreprise Server Management Shell : cliquez sur **Démarrer,** sur Tous les **programmes,** sur Skype Entreprise **2015,** puis sur Skype Entreprise **Server Management Shell.**</span><span class="sxs-lookup"><span data-stu-id="962d1-111">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="962d1-112">Spécifiez les paramètres suivants de **Set-CsVoicePolicy** :</span><span class="sxs-lookup"><span data-stu-id="962d1-112">Specify the following parameters to **Set-CsVoicePolicy**:</span></span>

   - <span data-ttu-id="962d1-113">**EnableVoicemailEscapeTimer** - Active ou désactive le minuteur d’échappement.</span><span class="sxs-lookup"><span data-stu-id="962d1-113">**EnableVoicemailEscapeTimer** - Enables or disables the escape timer.</span></span>

   - <span data-ttu-id="962d1-p102">**PSTNVoicemailEscapeTimer** - Spécifie la valeur de délai d’attente en millisecondes. La valeur par défaut est 1500 millisecondes et la valeur peut être comprise entre 0 milliseconde et 8000 millisecondes.</span><span class="sxs-lookup"><span data-stu-id="962d1-p102">**PSTNVoicemailEscapeTimer** - Specifies the timeout value in milliseconds. The default value is 1500 milliseconds, and the value can range from 0 milliseconds to 8000 milliseconds.</span></span>

## <a name="example"></a><span data-ttu-id="962d1-116">Exemple</span><span class="sxs-lookup"><span data-stu-id="962d1-116">Example</span></span>

```powershell
Set-CsVoicePolicy UserVoicePolicy -EnableVoiceMailEscapeTimer $true - PSTNVoicemailEscapeTimer 2000
Set-CsVoicePolicy -Identity site:SitePolicy -EnableVoiceMailEscapeTimer $true -PSTNVoicemailEscapeTimer 1500
```

## <a name="see-also"></a><span data-ttu-id="962d1-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="962d1-117">See also</span></span>

[<span data-ttu-id="962d1-118">Configuration des stratégies de voix et des enregistrements d’utilisation PSTN pour autoriser les privilèges et les fonctionnalités d’appel</span><span class="sxs-lookup"><span data-stu-id="962d1-118">Configuring Voice Policies and PSTN Usage Records to Authorize Calling Features and Privileges</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges)