---
title: Configurer la redirection vers la messagerie vocale dans Skype pour les entreprises
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a1d19e6c-82ff-4768-8ae5-da981368ce40
description: 'Résumé : Découvrez comment configurer redirection vers la messagerie vocale Skype pour Business Server à l’aide de la Skype pour Business Server Management Shell.'
ms.openlocfilehash: 260488701348fdf52eaccb82cc6dc41c19c68339
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/08/2018
ms.locfileid: "23891264"
---
# <a name="configure-voice-mail-escape-in-skype-for-business"></a><span data-ttu-id="655fa-103">Configurer la redirection vers la messagerie vocale dans Skype pour les entreprises</span><span class="sxs-lookup"><span data-stu-id="655fa-103">Configure voice mail escape in Skype for Business</span></span>

<span data-ttu-id="655fa-104">**Résumé :** Découvrez comment configurer redirection vers la messagerie vocale Skype pour Business Server à l’aide de la Skype pour Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="655fa-104">**Summary:** Learn how to configure voice mail escape in Skype for Business Server by using the Skype for Business Server Management Shell.</span></span>

<span data-ttu-id="655fa-105">Lorsqu’un utilisateur configure la sonnerie simultanée vers un téléphone mobile, un appelant généralement être acheminé vers la messagerie vocale personnelle de l’utilisateur si le téléphone mobile est éteint, en dehors de la batterie ou en dehors des limites.</span><span class="sxs-lookup"><span data-stu-id="655fa-105">When a user configures simultaneous ringing to a mobile phone, a caller will typically be routed to the user's personal voice mail if the mobile phone is turned off, out of battery power, or out of range.</span></span> <span data-ttu-id="655fa-106">Avec Skype pour Business Server, les utilisateurs peuvent choisir de lié à l’entreprise d’appels acheminés vers leur système de messagerie vocale d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="655fa-106">With Skype for Business Server , users can opt to have business-related calls routed to their corporate voice mail system.</span></span> <span data-ttu-id="655fa-107">En particulier, un minuteur peut être configuré, et si l’appel est reçu par la messagerie vocale de l’opérateur dans la plage définie, Skype pour Business Server déconnecte du système de messagerie vocale de l’opérateur (et la messagerie vocale personnelle de l’utilisateur), lors de l’utilisateur autres points de terminaison dans le système d’entreprise continuent à sonner.</span><span class="sxs-lookup"><span data-stu-id="655fa-107">Specifically, a timer can be configured, and if the call is answered by the carrier's voice mail within the range of time defined, Skype for Business Server will disconnect from the carrier's voice mail system (and the user's personal voice mail), while the user's remaining endpoints in the corporate system continue to ring.</span></span> <span data-ttu-id="655fa-108">Ainsi, l’appelant est automatiquement dirigé vers la messagerie vocale d’entreprise de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="655fa-108">This way, the caller is automatically routed to the user's corporate voice mail.</span></span>

<span data-ttu-id="655fa-109">Cette configuration est effectuée à l’aide de la Skype pour Business Server Management Shell cmdlet **Set-CsVoicePolicy**, au niveau de la stratégie de voix, avec les paramètres suivants.</span><span class="sxs-lookup"><span data-stu-id="655fa-109">This configuration is performed using the Skype for Business Server Management Shell cmdlet, **Set-CsVoicePolicy**, at the voice policy level, with the following parameters.</span></span>

### <a name="to-configure-voice-mail-escape"></a><span data-ttu-id="655fa-110">Pour configurer la redirection vers la messagerie vocale</span><span class="sxs-lookup"><span data-stu-id="655fa-110">To configure voice mail escape</span></span>

1. <span data-ttu-id="655fa-111">Démarrez Skype Entreprise Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Skype Entreprise 2015**, puis sur **Skype Entreprise Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="655fa-111">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="655fa-112">Spécifiez les paramètres ci-dessous sur **Set-CsVoicePolicy** :</span><span class="sxs-lookup"><span data-stu-id="655fa-112">Specify the following parameters to **Set-CsVoicePolicy**:</span></span>

   - <span data-ttu-id="655fa-113">**EnableVoicemailEscapeTimer** : active ou désactive le minuteur de redirection.</span><span class="sxs-lookup"><span data-stu-id="655fa-113">**EnableVoicemailEscapeTimer** - Enables or disables the escape timer.</span></span>

   - <span data-ttu-id="655fa-p102">**PSTNVoicemailEscapeTimer** : spécifie la valeur de délai d’attente en millisecondes. La valeur par défaut est 1 500 millisecondes et la valeur peut être comprise entre 0 milliseconde et 8 000 millisecondes.</span><span class="sxs-lookup"><span data-stu-id="655fa-p102">**PSTNVoicemailEscapeTimer** - Specifies the timeout value in milliseconds. The default value is 1500 milliseconds, and the value can range from 0 milliseconds to 8000 milliseconds.</span></span>

## <a name="example"></a><span data-ttu-id="655fa-116">Exemple</span><span class="sxs-lookup"><span data-stu-id="655fa-116">Example</span></span>

```
Set-CsVoicePolicy UserVoicePolicy -EnableVoiceMailEscapeTimer $true - PSTNVoicemailEscapeTimer 2000
Set-CsVoicePolicy -Identity site:SitePolicy -EnableVoiceMailEscapeTimer $true -PSTNVoicemailEscapeTimer 1500
```

## <a name="see-also"></a><span data-ttu-id="655fa-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="655fa-117">See also</span></span>

[<span data-ttu-id="655fa-118">Configuration de stratégies de voix et les enregistrements d’utilisation PSTN pour autoriser les privilèges et les fonctionnalités d’appel</span><span class="sxs-lookup"><span data-stu-id="655fa-118">Configuring Voice Policies and PSTN Usage Records to Authorize Calling Features and Privileges</span></span>](https://technet.microsoft.com/library/63f22010-a3d7-4cbd-86e8-6fc0e13c2b84.aspx)

