---
title: Configuration de la redirection vers la messagerie vocale dans Skype Entreprise 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: a1d19e6c-82ff-4768-8ae5-da981368ce40
description: 'Résumé : Apprenez à configurer d’échappement de messagerie vocale dans Skype pour 2015 de serveur d’entreprise à l’aide de la Skype pour Business Server Management Shell.'
ms.openlocfilehash: 07586f38127b2831ecdb2900f005ff43b4184292
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="configure-voice-mail-escape-in-skype-for-business-2015"></a><span data-ttu-id="43d31-103">Configuration de la redirection vers la messagerie vocale dans Skype Entreprise 2015</span><span class="sxs-lookup"><span data-stu-id="43d31-103">Configure voice mail escape in Skype for Business 2015</span></span>
 
<span data-ttu-id="43d31-104">**Résumé :** Apprenez à configurer d’échappement de messagerie vocale dans Skype pour 2015 de serveur d’entreprise à l’aide de la Skype pour Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="43d31-104">**Summary:** Learn how to configure voice mail escape in Skype for Business Server 2015 by using the Skype for Business Server Management Shell.</span></span>
  
<span data-ttu-id="43d31-105">Lorsqu’un utilisateur configure des appels simultanés à un téléphone portable, un appelant sera habituellement vos messages vocaux personnels de l’utilisateur si le téléphone mobile est éteint, en panne de batterie ou hors limites.</span><span class="sxs-lookup"><span data-stu-id="43d31-105">When a user configures simultaneous ringing to a mobile phone, a caller will typically be routed to the user's personal voice mail if the mobile phone is turned off, out of battery power, or out of range.</span></span> <span data-ttu-id="43d31-106">Avec Skype pour Business Server, les utilisateurs peuvent choisir de recevoir professionnelles des appels acheminés vers leur système de messagerie vocale d’entreprise.</span><span class="sxs-lookup"><span data-stu-id="43d31-106">With Skype for Business Server , users can opt to have business-related calls routed to their corporate voice mail system.</span></span> <span data-ttu-id="43d31-107">Plus précisément, une minuterie peut être configurée et si l’appel est reçu par messagerie vocale de l’opérateur dans l’intervalle de temps défini, Skype pour Business Server déconnecte du système de messagerie vocale de l’opérateur (et vocaux personnels à l’utilisateur), lors de l’utilisateur autres points de terminaison dans le système d’entreprise continuent à l’anneau.</span><span class="sxs-lookup"><span data-stu-id="43d31-107">Specifically, a timer can be configured, and if the call is answered by the carrier's voice mail within the range of time defined, Skype for Business Server will disconnect from the carrier's voice mail system (and the user's personal voice mail), while the user's remaining endpoints in the corporate system continue to ring.</span></span> <span data-ttu-id="43d31-108">De cette façon, l’appelant est automatiquement acheminé vers messagerie vocale d’entreprise de l’utilisateur.</span><span class="sxs-lookup"><span data-stu-id="43d31-108">This way, the caller is automatically routed to the user's corporate voice mail.</span></span>
  
<span data-ttu-id="43d31-109">Cette configuration s’effectue à l’aide de la Skype pour l’applet de commande Business Server Management Shell, **Ensemble-CsVoicePolicy**, au niveau de stratégie voice, avec les paramètres suivants.</span><span class="sxs-lookup"><span data-stu-id="43d31-109">This configuration is performed using the Skype for Business Server Management Shell cmdlet, **Set-CsVoicePolicy**, at the voice policy level, with the following parameters.</span></span>
  
### <a name="to-configure-voice-mail-escape"></a><span data-ttu-id="43d31-110">Pour configurer la redirection vers la messagerie vocale</span><span class="sxs-lookup"><span data-stu-id="43d31-110">To configure voice mail escape</span></span>

1. <span data-ttu-id="43d31-111">Démarrez Skype Entreprise Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Skype Entreprise 2015**, puis sur **Skype Entreprise Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="43d31-111">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="43d31-112">Spécifiez les paramètres ci-dessous sur **Set-CsVoicePolicy** :</span><span class="sxs-lookup"><span data-stu-id="43d31-112">Specify the following parameters to **Set-CsVoicePolicy**:</span></span>
    
   - <span data-ttu-id="43d31-113">**EnableVoicemailEscapeTimer** : active ou désactive le minuteur de redirection.</span><span class="sxs-lookup"><span data-stu-id="43d31-113">**EnableVoicemailEscapeTimer** - Enables or disables the escape timer.</span></span>
    
   - <span data-ttu-id="43d31-p102">**PSTNVoicemailEscapeTimer** : spécifie la valeur de délai d’attente en millisecondes. La valeur par défaut est 1 500 millisecondes et la valeur peut être comprise entre 0 milliseconde et 8 000 millisecondes.</span><span class="sxs-lookup"><span data-stu-id="43d31-p102">**PSTNVoicemailEscapeTimer** - Specifies the timeout value in milliseconds. The default value is 1500 milliseconds, and the value can range from 0 milliseconds to 8000 milliseconds.</span></span>
    
## <a name="example"></a><span data-ttu-id="43d31-116">Exemple</span><span class="sxs-lookup"><span data-stu-id="43d31-116">Example</span></span>

```
Set-CsVoicePolicy UserVoicePolicy -EnableVoiceMailEscapeTimer $true - PSTNVoicemailEscapeTimer 2000

Set-CsVoicePolicy -Identity site:SitePolicy -EnableVoiceMailEscapeTimer $true -PSTNVoicemailEscapeTimer 1500

```

## <a name="see-also"></a><span data-ttu-id="43d31-117">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="43d31-117">See also</span></span>

#### 

[<span data-ttu-id="43d31-118">Configuration des stratégies de la voix et les enregistrements d’utilisation de TLS pour autoriser des privilèges et des fonctionnalités d’appel</span><span class="sxs-lookup"><span data-stu-id="43d31-118">Configuring Voice Policies and PSTN Usage Records to Authorize Calling Features and Privileges</span></span>](http://technet.microsoft.com/library/63f22010-a3d7-4cbd-86e8-6fc0e13c2b84.aspx)

