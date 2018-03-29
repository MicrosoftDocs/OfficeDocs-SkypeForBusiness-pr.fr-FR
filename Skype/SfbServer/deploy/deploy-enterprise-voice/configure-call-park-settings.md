---
title: Configuration des paramètres de parcage d’appel dans Skype Entreprise 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 3bed9d09-8363-4fff-a220-f0f6d3a81241
description: Modifier les paramètres d’appel Park dans Skype pour Business Server Voix Entreprise.
ms.openlocfilehash: 56b0e2508fda61bddc94a6f8813708e8186c99c7
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="configure-call-park-settings-in-skype-for-business-2015"></a><span data-ttu-id="204cf-103">Configuration des paramètres de parcage d’appel dans Skype Entreprise 2015</span><span class="sxs-lookup"><span data-stu-id="204cf-103">Configure Call Park settings in Skype for Business 2015</span></span>
 
<span data-ttu-id="204cf-104">Modifier les paramètres d’appel Park dans Skype pour Business Server Voix Entreprise.</span><span class="sxs-lookup"><span data-stu-id="204cf-104">Modify Call Park settings in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="204cf-105">Si vous ne souhaitez pas utiliser les paramètres par défaut de parc d’appel, vous pouvez les personnaliser.</span><span class="sxs-lookup"><span data-stu-id="204cf-105">If you don't want to use default Call Park settings, you can customize them.</span></span> <span data-ttu-id="204cf-106">Lorsque vous installez l’application d’appel Park, paramètres globaux sont configurés par défaut.</span><span class="sxs-lookup"><span data-stu-id="204cf-106">When you install the Call Park application, global settings are configured by default.</span></span> <span data-ttu-id="204cf-107">Vous pouvez modifier les paramètres généraux et définir également des paramètres spécifiques à un site.</span><span class="sxs-lookup"><span data-stu-id="204cf-107">You can modify the global settings, and you can also specify site-specific settings.</span></span> <span data-ttu-id="204cf-108">Utilisez l’applet de commande **New-CsCpsConfiguration** pour créer des paramètres spécifiques au site.</span><span class="sxs-lookup"><span data-stu-id="204cf-108">Use the **New-CsCpsConfiguration** cmdlet to create new site-specific settings.</span></span> <span data-ttu-id="204cf-109">L’applet de commande **Set-CsCpsConfiguration** permet de modifier les paramètres existants.</span><span class="sxs-lookup"><span data-stu-id="204cf-109">Use the **Set-CsCpsConfiguration** cmdlet to modify existing settings.</span></span>
  
> [!NOTE]
> <span data-ttu-id="204cf-110">Nous vous recommandons de configurer au moins l’option **OnTimeoutURI** pour la destination de remplacement à utiliser lorsqu’un appel parqué échoue.</span><span class="sxs-lookup"><span data-stu-id="204cf-110">At a minimum, we recommend that you configure the **OnTimeoutURI** option for the fallback destination to use when a parked call times out and ringback fails.</span></span>
  
<span data-ttu-id="204cf-111">Utilisez l’applet de commande **New-CsCpsConfiguration** ou l’applet de commande **Set-CsCpsConfiguration** pour configurer les paramètres suivants :</span><span class="sxs-lookup"><span data-stu-id="204cf-111">Use **New-CsCpsConfiguration** cmdlet or the **Set-CsCpsConfiguration** cmdlet to configure any of the following settings:</span></span>
  
|<span data-ttu-id="204cf-112">**Cette option :**</span><span class="sxs-lookup"><span data-stu-id="204cf-112">**This option:**</span></span>|<span data-ttu-id="204cf-113">**Cela spécifie :**</span><span class="sxs-lookup"><span data-stu-id="204cf-113">**Specifies this:**</span></span>|
|:-----|:-----|
|<span data-ttu-id="204cf-114">**CallPickupTimeoutThreshold**</span><span class="sxs-lookup"><span data-stu-id="204cf-114">**CallPickupTimeoutThreshold**</span></span> <br/> |<span data-ttu-id="204cf-115">Période qui s’écoule entre le moment où un appel est parqué et le moment où il sonne de nouveau sur le téléphone auquel il était destiné.</span><span class="sxs-lookup"><span data-stu-id="204cf-115">The amount of time that elapses after a call has been parked before it rings back to the phone where the call was answered.</span></span>  <br/> <span data-ttu-id="204cf-p102">La valeur doit être entrée au format hh:mm:ss (heures, minutes, secondes). La valeur minimale est de 10 secondes et la valeur maximale, de 10 minutes. La valeur par défaut est 00:01:30.</span><span class="sxs-lookup"><span data-stu-id="204cf-p102">The value must be entered in the format hh:mm:ss to specify the hours, minutes, and seconds. The minimum value is 10 seconds, and the maximum value is 10 minutes. The default is 00:01:30.</span></span>  <br/> |
|<span data-ttu-id="204cf-119">**EnableMusicOnHold**</span><span class="sxs-lookup"><span data-stu-id="204cf-119">**EnableMusicOnHold**</span></span> <br/> |<span data-ttu-id="204cf-120">Si une musique est diffusée pour l’appelant pendant le parcage d’un appel.</span><span class="sxs-lookup"><span data-stu-id="204cf-120">Whether music plays for a caller while a call is parked.</span></span>  <br/> <span data-ttu-id="204cf-p103">Les valeurs sont True ou False. La valeur par défaut est True.</span><span class="sxs-lookup"><span data-stu-id="204cf-p103">Values are True or False. The default is True.</span></span>  <br/> |
|<span data-ttu-id="204cf-123">**MaxCallPickupAttempts**</span><span class="sxs-lookup"><span data-stu-id="204cf-123">**MaxCallPickupAttempts**</span></span> <br/> |<span data-ttu-id="204cf-p104">Nombre de sonnerie de rappel d’un appel parqué avant qu’il soit transféré vers l’URI de remplacement spécifié pour le paramètre **OnTimeoutURI**. La valeur par défaut est 1.</span><span class="sxs-lookup"><span data-stu-id="204cf-p104">The number of times a parked call rings back to the answering phone before it is forwarded to the fallback Uniform Resource Identifier (URI) that is specified for **OnTimeoutURI**. The default is 1.  </span></span><br/> |
|<span data-ttu-id="204cf-126">**OnTimeoutURI**</span><span class="sxs-lookup"><span data-stu-id="204cf-126">**OnTimeoutURI**</span></span> <br/> |<span data-ttu-id="204cf-127">Adresse SIP (Session Initiation Protocol) de l’utilisateur ou groupe Response Group vers laquelle l’appel parqué sans réponse est routé lorsque la valeur **MaxCallPickupAttempts** est atteinte.</span><span class="sxs-lookup"><span data-stu-id="204cf-127">The SIP address of the user or response group to which an unanswered parked call is routed when **MaxCallPickupAttempts** is exceeded.</span></span> <br/> <span data-ttu-id="204cf-p105">La valeur doit être une URI SIP (Session Initiation Protocol) et commencer par la chaîne « sip: ». Par exemple, sip:bob@contoso.com. La valeur par défaut est aucune adresse de transfert.</span><span class="sxs-lookup"><span data-stu-id="204cf-p105">Value must be a SIP URI beginning with the string sip:. For example, sip:bob@contoso.com. The default is no forwarding address.  </span></span><br/> |
   
### <a name="to-configure-call-park-settings"></a><span data-ttu-id="204cf-130">Pour configurer les paramètres d’appel Park</span><span class="sxs-lookup"><span data-stu-id="204cf-130">To configure Call Park settings</span></span>

1. <span data-ttu-id="204cf-131">Démarrez Skype Entreprise Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Skype Entreprise 2015**, puis sur **Skype Entreprise Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="204cf-131">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="204cf-132">Exécutez :</span><span class="sxs-lookup"><span data-stu-id="204cf-132">Run:</span></span>
    
   ```
   New-CsCpsConfiguration -Identity site:<sitename to apply settings> [-CallPickupTimeoutThreshold <hh:mm:ss>] -[EnableMusicOnHold <$true | $false>] [-MaxCallPickupAttempts <number of rings>] [-OnTimeoutURI sip:<sip URI for routing unanswered call>]
   ```

   > [!TIP]
   > <span data-ttu-id="204cf-133">Utilisez l’applet de commande **Get-CsSite** pour identifier le site.</span><span class="sxs-lookup"><span data-stu-id="204cf-133">Use the **Get-CsSite** cmdlet to identify the site.</span></span> <span data-ttu-id="204cf-134">Pour plus d’informations, consultez la documentation de Communications Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="204cf-134">For details, see Lync Server Management Shell documentation.</span></span>
  
    <span data-ttu-id="204cf-135">Par exemple :</span><span class="sxs-lookup"><span data-stu-id="204cf-135">For example:</span></span>
    
   ```
   New-CsCpsConfiguration -Identity site:Redmond1 -CallPickupTimeoutThreshold 00:01:00 -EnableMusicOnHold $false -MaxCallPickupAttempts 2 -OnTimeoutURI sip:bob@contoso.com
   ```

## <a name="see-also"></a><span data-ttu-id="204cf-136">Voir aussi</span><span class="sxs-lookup"><span data-stu-id="204cf-136">See also</span></span>

#### 

[<span data-ttu-id="204cf-137">Personnaliser des morceaux musicaux d’appel Park sur inSkype de blocage pour Business 2015</span><span class="sxs-lookup"><span data-stu-id="204cf-137">Customize Call Park music on hold inSkype for Business 2015</span></span>](customize-call-park-music-on-hold.md)
#### 

[<span data-ttu-id="204cf-138">Nouvelle-CsCpsConfiguration</span><span class="sxs-lookup"><span data-stu-id="204cf-138">New-CsCpsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cscpsconfiguration?view=skype-ps)
  
[<span data-ttu-id="204cf-139">Ensemble-CsCpsConfiguration</span><span class="sxs-lookup"><span data-stu-id="204cf-139">Set-CsCpsConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cscpsconfiguration?view=skype-ps)
  
[<span data-ttu-id="204cf-140">Get-CsSite</span><span class="sxs-lookup"><span data-stu-id="204cf-140">Get-CsSite</span></span>](https://docs.microsoft.com/powershell/module/skype/get-cssite?view=skype-ps)

