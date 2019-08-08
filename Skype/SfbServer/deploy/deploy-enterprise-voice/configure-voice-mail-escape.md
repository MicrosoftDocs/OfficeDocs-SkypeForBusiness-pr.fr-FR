---
title: Configurer l’échappement de la messagerie vocale dans Skype entreprise
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a1d19e6c-82ff-4768-8ae5-da981368ce40
description: 'Résumé: Découvrez comment configurer l’échappement de la messagerie vocale dans Skype entreprise Server à l’aide de Skype entreprise Server Management Shell.'
ms.openlocfilehash: c9a858ead9261944c162cb10fda63840f8de86d3
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233573"
---
# <a name="configure-voice-mail-escape-in-skype-for-business"></a><span data-ttu-id="99cfe-103">Configurer l’échappement de la messagerie vocale dans Skype entreprise</span><span class="sxs-lookup"><span data-stu-id="99cfe-103">Configure voice mail escape in Skype for Business</span></span>

<span data-ttu-id="99cfe-104">**Résumé:** Découvrez comment configurer l’échappement de la messagerie vocale dans Skype entreprise Server à l’aide de Skype entreprise Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="99cfe-104">**Summary:** Learn how to configure voice mail escape in Skype for Business Server by using the Skype for Business Server Management Shell.</span></span>

<span data-ttu-id="99cfe-105">Lorsqu’un utilisateur configure une sonnerie simultanée sur un téléphone mobile, un appelant est généralement dirigé vers la messagerie vocale personnelle de l’utilisateur si ce dernier est éteint, n’est pas alimenté ou n’est pas à portée de batterie.</span><span class="sxs-lookup"><span data-stu-id="99cfe-105">When a user configures simultaneous ringing to a mobile phone, a caller will typically be routed to the user's personal voice mail if the mobile phone is turned off, out of battery power, or out of range.</span></span> <span data-ttu-id="99cfe-106">Avec Skype entreprise Server, les utilisateurs peuvent choisir d’avoir accès à leur système de messagerie vocale d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="99cfe-106">With Skype for Business Server , users can opt to have business-related calls routed to their corporate voice mail system.</span></span> <span data-ttu-id="99cfe-107">Plus précisément, un minuteur peut être configuré, et si l’appel est reçu par la messagerie vocale de l’opérateur dans la plage de temps définie, Skype entreprise Server se déconnecte du système de messagerie vocale de l’opérateur (et de la messagerie vocale personnelle de l’utilisateur), tandis que l’utilisateur les points de terminaison restants du système d’entreprise continuent de sonner.</span><span class="sxs-lookup"><span data-stu-id="99cfe-107">Specifically, a timer can be configured, and if the call is answered by the carrier's voice mail within the range of time defined, Skype for Business Server will disconnect from the carrier's voice mail system (and the user's personal voice mail), while the user's remaining endpoints in the corporate system continue to ring.</span></span> <span data-ttu-id="99cfe-108">De cette façon, l’appelant est automatiquement routé vers la messagerie vocale de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="99cfe-108">This way, the caller is automatically routed to the user's corporate voice mail.</span></span>

<span data-ttu-id="99cfe-109">Cette configuration est effectuée à l’aide de l’applet de commande Skype entreprise Server Management Shell, **Set-CsVoicePolicy**, au niveau de la stratégie vocale, avec les paramètres suivants.</span><span class="sxs-lookup"><span data-stu-id="99cfe-109">This configuration is performed using the Skype for Business Server Management Shell cmdlet, **Set-CsVoicePolicy**, at the voice policy level, with the following parameters.</span></span>

### <a name="to-configure-voice-mail-escape"></a><span data-ttu-id="99cfe-110">Pour configurer la redirection vers la messagerie vocale</span><span class="sxs-lookup"><span data-stu-id="99cfe-110">To configure voice mail escape</span></span>

1. <span data-ttu-id="99cfe-111">Démarrez Skype entreprise Server Management Shell: cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Skype entreprise 2015**, puis cliquez sur **Skype entreprise Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="99cfe-111">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="99cfe-112">Spécifiez les paramètres ci-dessous sur **Set-CsVoicePolicy** :</span><span class="sxs-lookup"><span data-stu-id="99cfe-112">Specify the following parameters to **Set-CsVoicePolicy**:</span></span>

   - <span data-ttu-id="99cfe-113">**EnableVoicemailEscapeTimer** : active ou désactive le minuteur de redirection.</span><span class="sxs-lookup"><span data-stu-id="99cfe-113">**EnableVoicemailEscapeTimer** - Enables or disables the escape timer.</span></span>

   - <span data-ttu-id="99cfe-p102">**PSTNVoicemailEscapeTimer** : spécifie la valeur de délai d’attente en millisecondes. La valeur par défaut est 1 500 millisecondes et la valeur peut être comprise entre 0 milliseconde et 8 000 millisecondes.</span><span class="sxs-lookup"><span data-stu-id="99cfe-p102">**PSTNVoicemailEscapeTimer** - Specifies the timeout value in milliseconds. The default value is 1500 milliseconds, and the value can range from 0 milliseconds to 8000 milliseconds.</span></span>

## <a name="example"></a><span data-ttu-id="99cfe-116">Exemple</span><span class="sxs-lookup"><span data-stu-id="99cfe-116">Example</span></span>

```
Set-CsVoicePolicy UserVoicePolicy -EnableVoiceMailEscapeTimer $true - PSTNVoicemailEscapeTimer 2000
Set-CsVoicePolicy -Identity site:SitePolicy -EnableVoiceMailEscapeTimer $true -PSTNVoicemailEscapeTimer 1500
```

## <a name="see-also"></a><span data-ttu-id="99cfe-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="99cfe-117">See also</span></span>

[<span data-ttu-id="99cfe-118">Configuring Voice Policies and PSTN Usage Records to Authorize Calling Features and Privileges</span><span class="sxs-lookup"><span data-stu-id="99cfe-118">Configuring Voice Policies and PSTN Usage Records to Authorize Calling Features and Privileges</span></span>](https://technet.microsoft.com/library/63f22010-a3d7-4cbd-86e8-6fc0e13c2b84.aspx)

