---
title: Configurer les paramètres de parcage d’appel dans Skype pour les entreprises
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 3bed9d09-8363-4fff-a220-f0f6d3a81241
description: Modifier les paramètres de parcage d’appel dans Skype pour Business Server Enterprise Voice.
ms.openlocfilehash: ab2fec9a0455316ea1b0fcba6a771b91f0d115d0
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30891649"
---
# <a name="configure-call-park-settings-in-skype-for-business"></a><span data-ttu-id="32491-103">Configurer les paramètres de parcage d’appel dans Skype pour les entreprises</span><span class="sxs-lookup"><span data-stu-id="32491-103">Configure Call Park settings in Skype for Business</span></span>

<span data-ttu-id="32491-104">Modifier les paramètres de parcage d’appel dans Skype pour Business Server Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="32491-104">Modify Call Park settings in Skype for Business Server Enterprise Voice.</span></span>

<span data-ttu-id="32491-105">Si vous ne souhaitez pas utiliser les paramètres de parcage d’appel par défaut, vous pouvez les personnaliser.</span><span class="sxs-lookup"><span data-stu-id="32491-105">If you don't want to use default Call Park settings, you can customize them.</span></span> <span data-ttu-id="32491-106">Lorsque vous installez l’application de parcage d’appel, les paramètres globaux sont configurés par défaut.</span><span class="sxs-lookup"><span data-stu-id="32491-106">When you install the Call Park application, global settings are configured by default.</span></span> <span data-ttu-id="32491-107">Vous pouvez modifier les paramètres généraux et définir également des paramètres spécifiques à un site.</span><span class="sxs-lookup"><span data-stu-id="32491-107">You can modify the global settings, and you can also specify site-specific settings.</span></span> <span data-ttu-id="32491-108">L’applet de commande **New-CsCpsConfiguration** permet de créer des paramètres spécifiques à un site.</span><span class="sxs-lookup"><span data-stu-id="32491-108">Use the **New-CsCpsConfiguration** cmdlet to create new site-specific settings.</span></span> <span data-ttu-id="32491-109">L’applet de commande **Set-CsCpsConfiguration** permet de modifier les paramètres existants.</span><span class="sxs-lookup"><span data-stu-id="32491-109">Use the **Set-CsCpsConfiguration** cmdlet to modify existing settings.</span></span>

> [!NOTE]
> <span data-ttu-id="32491-110">Nous vous recommandons de configurer au moins l’option **OnTimeoutURI** pour la destination de remplacement à utiliser lorsqu’un appel parqué échoue.</span><span class="sxs-lookup"><span data-stu-id="32491-110">At a minimum, we recommend that you configure the **OnTimeoutURI** option for the fallback destination to use when a parked call times out and ringback fails.</span></span>

<span data-ttu-id="32491-111">Les applets de commande **New-CsCpsConfiguration** et **Set-CsCpsConfiguration** permettent de configurer les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="32491-111">Use **New-CsCpsConfiguration** cmdlet or the **Set-CsCpsConfiguration** cmdlet to configure any of the following settings:</span></span>


| <span data-ttu-id="32491-112">**Cette option :**</span><span class="sxs-lookup"><span data-stu-id="32491-112">**This option:**</span></span>                     | <span data-ttu-id="32491-113">**Spécifie cet élément :**</span><span class="sxs-lookup"><span data-stu-id="32491-113">**Specifies this:**</span></span>                                                                                                                                                                                                                                                                                                                   |
|:-------------------------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="32491-114">**CallPickupTimeoutThreshold**</span><span class="sxs-lookup"><span data-stu-id="32491-114">**CallPickupTimeoutThreshold**</span></span> <br/> | <span data-ttu-id="32491-115">Période qui s’écoule entre le moment où un appel est parqué et le moment où il sonne de nouveau sur le téléphone auquel il était destiné.</span><span class="sxs-lookup"><span data-stu-id="32491-115">The amount of time that elapses after a call has been parked before it rings back to the phone where the call was answered.</span></span>  <br/> <span data-ttu-id="32491-p102">La valeur doit être entrée au format hh:mm:ss (heures, minutes, secondes). La valeur minimale est de 10 secondes et la valeur maximale, de 10 minutes. La valeur par défaut est 00:01:30.</span><span class="sxs-lookup"><span data-stu-id="32491-p102">The value must be entered in the format hh:mm:ss to specify the hours, minutes, and seconds. The minimum value is 10 seconds, and the maximum value is 10 minutes. The default is 00:01:30.</span></span>  <br/> |
| <span data-ttu-id="32491-119">**EnableMusicOnHold**</span><span class="sxs-lookup"><span data-stu-id="32491-119">**EnableMusicOnHold**</span></span> <br/>          | <span data-ttu-id="32491-120">Si une musique est diffusée pour l’appelant pendant le parcage d’un appel.</span><span class="sxs-lookup"><span data-stu-id="32491-120">Whether music plays for a caller while a call is parked.</span></span>  <br/> <span data-ttu-id="32491-p103">Les valeurs sont True ou False. La valeur par défaut est True.</span><span class="sxs-lookup"><span data-stu-id="32491-p103">Values are True or False. The default is True.</span></span>  <br/>                                                                                                                                                                                                                 |
| <span data-ttu-id="32491-123">**MaxCallPickupAttempts**</span><span class="sxs-lookup"><span data-stu-id="32491-123">**MaxCallPickupAttempts**</span></span> <br/>      | <span data-ttu-id="32491-p104">Nombre de sonnerie de rappel d’un appel parqué avant qu’il soit transféré vers l’URI de remplacement spécifié pour le paramètre **OnTimeoutURI**. La valeur par défaut est 1.</span><span class="sxs-lookup"><span data-stu-id="32491-p104">The number of times a parked call rings back to the answering phone before it is forwarded to the fallback Uniform Resource Identifier (URI) that is specified for **OnTimeoutURI**. The default is 1.  </span></span><br/>                                                                                                                         |
| <span data-ttu-id="32491-126">**OnTimeoutURI**</span><span class="sxs-lookup"><span data-stu-id="32491-126">**OnTimeoutURI**</span></span> <br/>               | <span data-ttu-id="32491-127">Adresse SIP (Session Initiation Protocol) de l’utilisateur ou groupe Response Group vers laquelle l’appel parqué sans réponse est routé lorsque la valeur **MaxCallPickupAttempts** est atteinte.</span><span class="sxs-lookup"><span data-stu-id="32491-127">The SIP address of the user or response group to which an unanswered parked call is routed when **MaxCallPickupAttempts** is exceeded.</span></span> <br/> <span data-ttu-id="32491-p105">La valeur doit être une URI SIP (Session Initiation Protocol) et commencer par la chaîne « sip: ». Par exemple, sip:bob@contoso.com. La valeur par défaut est aucune adresse de transfert.</span><span class="sxs-lookup"><span data-stu-id="32491-p105">Value must be a SIP URI beginning with the string sip:. For example, sip:bob@contoso.com. The default is no forwarding address.  </span></span><br/>                                                   |

### <a name="to-configure-call-park-settings"></a><span data-ttu-id="32491-131">Pour configurer les paramètres de parcage d’appel</span><span class="sxs-lookup"><span data-stu-id="32491-131">To configure Call Park settings</span></span>

1. <span data-ttu-id="32491-132">Démarrez le Skype pour Business Server Management Shell : cliquez sur **Démarrer**, sur **Tous les programmes**, cliquez sur **Skype pour Business 2015**, puis cliquez sur **Skype pour Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="32491-132">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="32491-133">Exécutez :</span><span class="sxs-lookup"><span data-stu-id="32491-133">Run:</span></span>

   ```
   New-CsCpsConfiguration -Identity site:<sitename to apply settings> [-CallPickupTimeoutThreshold <hh:mm:ss>] -[EnableMusicOnHold <$true | $false>] [-MaxCallPickupAttempts <number of rings>] [-OnTimeoutURI sip:<sip URI for routing unanswered call>]
   ```

   > [!TIP]
   > <span data-ttu-id="32491-134">L’applet de commande **Get-CsSite** permet d’identifier le site.</span><span class="sxs-lookup"><span data-stu-id="32491-134">Use the **Get-CsSite** cmdlet to identify the site.</span></span> <span data-ttu-id="32491-135">Pour plus d’informations, voir Skype pour la documentation sur Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="32491-135">For details, see Skype for Business Server Management Shell documentation.</span></span>

    <span data-ttu-id="32491-136">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="32491-136">For example:</span></span>

   ```
   New-CsCpsConfiguration -Identity site:Redmond1 -CallPickupTimeoutThreshold 00:01:00 -EnableMusicOnHold $false -MaxCallPickupAttempts 2 -OnTimeoutURI sip:bob@contoso.com
   ```

## <a name="see-also"></a><span data-ttu-id="32491-137">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="32491-137">See also</span></span>

[<span data-ttu-id="32491-138">Personnalisation de l’attente musicale du parcage d’appel dans Skype Entreprise 2015</span><span class="sxs-lookup"><span data-stu-id="32491-138">Customize Call Park music on hold inSkype for Business 2015</span></span>](customize-call-park-music-on-hold.md)

[<span data-ttu-id="32491-139">Nouvelle-CsCpsConfiguration</span><span class="sxs-lookup"><span data-stu-id="32491-139">New-CsCpsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cscpsconfiguration?view=skype-ps)

[<span data-ttu-id="32491-140">Set-CsCpsConfiguration</span><span class="sxs-lookup"><span data-stu-id="32491-140">Set-CsCpsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cscpsconfiguration?view=skype-ps)

[<span data-ttu-id="32491-141">Get-CsSite</span><span class="sxs-lookup"><span data-stu-id="32491-141">Get-CsSite</span></span>](https://docs.microsoft.com/powershell/module/skype/get-cssite?view=skype-ps)
