---
title: Configuration de plusieurs numéros d'urgence dans Skype Entreprise 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 4/21/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: 2e869df0-5fdb-4e70-bd81-cb012556eb1a
description: Pour savoir comment configurer plusieurs numéros d'urgence dans Skype Entreprise Server 2015, lisez cette rubrique.
ms.openlocfilehash: 98d9bbef92f5f3894fb288c01e474288f9f7bb4c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="configure-multiple-emergency-numbers-in-skype-for-business-2015"></a><span data-ttu-id="5bc82-103">Configuration de plusieurs numéros d'urgence dans Skype Entreprise 2015</span><span class="sxs-lookup"><span data-stu-id="5bc82-103">Configure multiple emergency numbers in Skype for Business 2015</span></span>
 
<span data-ttu-id="5bc82-104">Pour savoir comment configurer plusieurs numéros d'urgence dans Skype Entreprise Server 2015, lisez cette rubrique.</span><span class="sxs-lookup"><span data-stu-id="5bc82-104">Read this topic to learn how to configure multiple emergency numbers in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="5bc82-105">Skype pour Business Server prend désormais en charge plusieurs numéros d’urgence pour un client.</span><span class="sxs-lookup"><span data-stu-id="5bc82-105">Skype for Business Server now supports multiple emergency numbers for a client.</span></span> <span data-ttu-id="5bc82-106">Plusieurs numéros d’urgence sont une nouvelle fonctionnalité introduite dans le 2016 juin mise à jour Cumulative.</span><span class="sxs-lookup"><span data-stu-id="5bc82-106">Multiple emergency numbers is a new feature introduced in the June 2016 Cumulative Update.</span></span> <span data-ttu-id="5bc82-107">Avant de configurer votre environnement pour la prise en charge de plusieurs numéros d’urgence, veillez à lire le [Plan pour plusieurs numéros d’urgence dans Skype pour Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="5bc82-107">Before you configure your environment to support multiple emergency numbers, be sure to read [Plan for multiple emergency numbers in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="5bc82-108">Si vous n'avez pas encore mis à niveau vers le 2016 novembre mise à jour Cumulative, consultez [mises à jour Skype pour Business Server 2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015).</span><span class="sxs-lookup"><span data-stu-id="5bc82-108">If you have not yet upgraded to the November 2016 Cumulative Update, see [Updates to Skype for Business Server 2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015).</span></span> <span data-ttu-id="5bc82-109">Avec le 2016 novembre mise à jour Cumulative, le nombre de numéros d’urgence de prise en charge augmente de 5 à 100.</span><span class="sxs-lookup"><span data-stu-id="5bc82-109">With the November 2016 Cumulative Update, the number of support emergency numbers increases from 5 to 100.</span></span> 
  
## <a name="configure-multiple-emergency-numbers"></a><span data-ttu-id="5bc82-110">Configuration de plusieurs numéros d'urgence</span><span class="sxs-lookup"><span data-stu-id="5bc82-110">Configure multiple emergency numbers</span></span>

<span data-ttu-id="5bc82-111">Pour configurer plusieurs numéros d’urgence, vous utilisez l’applet de commande New-CsEmergencyNumber, et puis vous spécifiez le paramètre EmergencyNumbers avec les applets de commande [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) et [CsLocationPolicy de l’ensemble](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="5bc82-111">To configure multiple emergency numbers, you use the New-CsEmergencyNumber cmdlet, and then you specify the EmergencyNumbers parameter with the [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) and [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps) cmdlets.</span></span> <span data-ttu-id="5bc82-112">Pour une description complète de tous les paramètres de stratégie emplacement, comme l’utilisation de TLS et l’emplacement requis, voir [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="5bc82-112">For a complete description of all the location policy parameters, such as PSTN usage and Location required, see [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps).</span></span>
  
<span data-ttu-id="5bc82-113">La commande suivante permet de créer un numéro d'urgence avec la chaîne de numérotation 911 à l'aide de l'applet de commande New-CsEmergency :</span><span class="sxs-lookup"><span data-stu-id="5bc82-113">The following command creates a new emergency number with dial string 911 by using the New-CsEmergency cmdlet:</span></span>
  
```
> $a = New-CsEmergencyNumber -DialString 911 

```

<span data-ttu-id="5bc82-114">La commande suivante permet d'associer le numéro à la stratégie d'emplacement en spécifiant les paramètres EmergencyNumbers dans l'applet de commande Set-CsLocationPolicy :</span><span class="sxs-lookup"><span data-stu-id="5bc82-114">The next command associates the number with the specified location policy by specifying the EmergencyNumbers parameter in the Set-CsLocationPolicy cmdlet:</span></span>
  
```
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a} 

```

<span data-ttu-id="5bc82-115">Dans l'exemple suivant, un numéro d'urgence est créé à l'aide d'un masque d'appel unique, le 112 :</span><span class="sxs-lookup"><span data-stu-id="5bc82-115">In the next example, an emergency number is created with a single dial mask, 112:</span></span>
  
```
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112 

```

<span data-ttu-id="5bc82-116">La commande suivante crée un numéro d’urgence avec plusieurs masques à distance :</span><span class="sxs-lookup"><span data-stu-id="5bc82-116">The next command creates an emergency number with multiple dial masks:</span></span>
  
```
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999 

```

<span data-ttu-id="5bc82-117">Dans l'exemple suivant, plusieurs numéros d'urgence sont ajoutés avec différents masques d'appel, puis associés aux numéros d'urgence avec la stratégie d'emplacement spécifiée :</span><span class="sxs-lookup"><span data-stu-id="5bc82-117">The next example adds multiple emergency numbers with multiple dial masks, and then associates the emergency numbers with the specified location policy:</span></span>
  
```
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999 
> $b = New-CsEmergencyNumber -DialString 500 -DialMask 501;502
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a,$b} 

```

<span data-ttu-id="5bc82-118">Dans l'exemple suivant, plusieurs numéros d'urgence destinés aux organismes de soin de santé utilisant 911 et 450 sont configurés : </span><span class="sxs-lookup"><span data-stu-id="5bc82-118">The next example configures multiple emergency numbers for health care providers that use both 911 and 450:</span></span> 
  
```
> $a = New-CsEmergencyNumber -DialString 911 
> $b = New-CsEmergencyNumber -DialString 450
> Set-CsLocationPolicy -Identity US-Hospital -EmergencyNumbers @{add=$a,$b}
```

<span data-ttu-id="5bc82-119">Dans l'exemple suivant, plusieurs numéros d'urgence sont configurés pour la ville de Londres :</span><span class="sxs-lookup"><span data-stu-id="5bc82-119">The next example configures multiple emergency numbers for the city of London:</span></span>
  
```
> $a = New-CsEmergencyNumber -DialString 999 -DialMask 144
> $b = New-CsEmergencyNumber -DialString 112 -DialMask 911;117;118
> Set-CsLocationPolicy -Identity London -EmergencyNumbers @{add=$a,$b}

```

<span data-ttu-id="5bc82-120">Dans l'exemple suivant, plusieurs numéros d'urgence sont configurés pour l'Inde :</span><span class="sxs-lookup"><span data-stu-id="5bc82-120">The next example configures multiple emergency numbers for India:</span></span>
  
```
> $a = New-CsEmergencyNumber -DialString 100 -DialMask 911
> $b = New-CsEmergencyNumber -DialString 101 
> $c = New-CsEmergencyNumber -DialString 102 
> Set-CsLocationPolicy -Identity India -EmergencyNumbers @{add=$a,$b,$c}

```

<span data-ttu-id="5bc82-121">Dans l'exemple suivant, une entrée existante est supprimée avec la chaîne de numérotation 911 et les masques d'appel 112 et 999 :</span><span class="sxs-lookup"><span data-stu-id="5bc82-121">The next example removes an existing entry with Dial string 911 and Dial masks 112 and 999:</span></span>
  
```
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{remove=$a} 

```


