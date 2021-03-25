---
title: Configurer plusieurs numéros d’urgence dans Skype Entreprise
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
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2e869df0-5fdb-4e70-bd81-cb012556eb1a
description: Lisez cette rubrique pour apprendre à configurer plusieurs numéros d’urgence dans Skype Entreprise Server.
ms.openlocfilehash: dc05e94e88b371bb9ee22568eff567e758311233
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51111890"
---
# <a name="configure-multiple-emergency-numbers-in-skype-for-business"></a><span data-ttu-id="e0146-103">Configurer plusieurs numéros d’urgence dans Skype Entreprise</span><span class="sxs-lookup"><span data-stu-id="e0146-103">Configure multiple emergency numbers in Skype for Business</span></span>

<span data-ttu-id="e0146-104">Lisez cette rubrique pour découvrir comment configurer plusieurs numéros d’urgence dans Skype Entreprise Server.</span><span class="sxs-lookup"><span data-stu-id="e0146-104">Read this topic to learn how to configure multiple emergency numbers in Skype for Business Server.</span></span>

<span data-ttu-id="e0146-105">Skype Entreprise Server prend désormais en charge plusieurs numéros d’urgence pour un client.</span><span class="sxs-lookup"><span data-stu-id="e0146-105">Skype for Business Server now supports multiple emergency numbers for a client.</span></span> <span data-ttu-id="e0146-106">Plusieurs numéros d’urgence sont une nouvelle fonctionnalité introduite dans la mise à jour cumulative de juin 2016.</span><span class="sxs-lookup"><span data-stu-id="e0146-106">Multiple emergency numbers is a new feature introduced in the June 2016 Cumulative Update.</span></span> <span data-ttu-id="e0146-107">Avant de configurer votre environnement pour prendre en charge plusieurs numéros d’urgence, veillez à lire Planifier plusieurs numéros d’urgence [dans Skype Entreprise Server.](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md)</span><span class="sxs-lookup"><span data-stu-id="e0146-107">Before you configure your environment to support multiple emergency numbers, be sure to read [Plan for multiple emergency numbers in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md).</span></span>

> [!NOTE]
> <span data-ttu-id="e0146-108">Si vous n’avez pas encore mis à niveau vers la mise à jour cumulative de novembre 2016, voir Mises à jour de Skype Entreprise [Server 2015.](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015)</span><span class="sxs-lookup"><span data-stu-id="e0146-108">If you have not yet upgraded to the November 2016 Cumulative Update, see [Updates to Skype for Business Server 2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span></span> <span data-ttu-id="e0146-109">Avec la mise à jour cumulative de novembre 2016, le nombre de numéros d’urgence de support augmente de 5 à 100.</span><span class="sxs-lookup"><span data-stu-id="e0146-109">With the November 2016 Cumulative Update, the number of support emergency numbers increases from 5 to 100.</span></span>

## <a name="configure-multiple-emergency-numbers"></a><span data-ttu-id="e0146-110">Configuration de plusieurs numéros d’urgence</span><span class="sxs-lookup"><span data-stu-id="e0146-110">Configure multiple emergency numbers</span></span>

<span data-ttu-id="e0146-111">Pour configurer plusieurs numéros d’urgence, utilisez l'New-CsEmergencyNumber cmdlet, puis spécifiez le paramètre EmergencyNumbers avec les cmdlets [New-CsLocationPolicy](/powershell/module/skype/new-cslocationpolicy?view=skype-ps) et [Set-CsLocationPolicy.](/powershell/module/skype/set-cslocationpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="e0146-111">To configure multiple emergency numbers, you use the New-CsEmergencyNumber cmdlet, and then you specify the EmergencyNumbers parameter with the [New-CsLocationPolicy](/powershell/module/skype/new-cslocationpolicy?view=skype-ps) and [Set-CsLocationPolicy](/powershell/module/skype/set-cslocationpolicy?view=skype-ps) cmdlets.</span></span> <span data-ttu-id="e0146-112">Pour obtenir une description complète de tous les paramètres de stratégie d’emplacement, tels que l’utilisation PSTN et l’emplacement requis, voir [Set-CsLocationPolicy](/powershell/module/skype/set-cslocationpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="e0146-112">For a complete description of all the location policy parameters, such as PSTN usage and Location required, see [Set-CsLocationPolicy](/powershell/module/skype/set-cslocationpolicy?view=skype-ps).</span></span>

<span data-ttu-id="e0146-113">La commande suivante crée un nouveau numéro d’urgence avec la chaîne de numérotation 911 à l’aide de la cmdlet New-CsEmergency suivante :</span><span class="sxs-lookup"><span data-stu-id="e0146-113">The following command creates a new emergency number with dial string 911 by using the New-CsEmergency cmdlet:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911
```

<span data-ttu-id="e0146-114">La commande suivante associe le numéro à la stratégie d’emplacement spécifiée en spécifiant le paramètre EmergencyNumbers dans la cmdlet Set-CsLocationPolicy suivante :</span><span class="sxs-lookup"><span data-stu-id="e0146-114">The next command associates the number with the specified location policy by specifying the EmergencyNumbers parameter in the Set-CsLocationPolicy cmdlet:</span></span>

```powershell
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a}
```

<span data-ttu-id="e0146-115">Dans l’exemple suivant, un numéro d’urgence est créé avec un masque de numérotation unique, 112 :</span><span class="sxs-lookup"><span data-stu-id="e0146-115">In the next example, an emergency number is created with a single dial mask, 112:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112
```

<span data-ttu-id="e0146-116">La commande suivante crée un numéro d’urgence avec plusieurs masques de numérotation :</span><span class="sxs-lookup"><span data-stu-id="e0146-116">The next command creates an emergency number with multiple dial masks:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
```

<span data-ttu-id="e0146-117">L’exemple suivant ajoute plusieurs numéros d’urgence avec plusieurs masques de numérotation, puis associe les numéros d’urgence à la stratégie d’emplacement spécifiée :</span><span class="sxs-lookup"><span data-stu-id="e0146-117">The next example adds multiple emergency numbers with multiple dial masks, and then associates the emergency numbers with the specified location policy:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
> $b = New-CsEmergencyNumber -DialString 500 -DialMask 501;502
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a,$b}
```

<span data-ttu-id="e0146-118">L’exemple suivant configure plusieurs numéros d’urgence pour les fournisseurs de services de santé qui utilisent les numéros 911 et 450 :</span><span class="sxs-lookup"><span data-stu-id="e0146-118">The next example configures multiple emergency numbers for health care providers that use both 911 and 450:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911
> $b = New-CsEmergencyNumber -DialString 450
> Set-CsLocationPolicy -Identity US-Hospital -EmergencyNumbers @{add=$a,$b}
```

<span data-ttu-id="e0146-119">L’exemple suivant configure plusieurs numéros d’urgence pour la ville de Londres :</span><span class="sxs-lookup"><span data-stu-id="e0146-119">The next example configures multiple emergency numbers for the city of London:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 999 -DialMask 144
> $b = New-CsEmergencyNumber -DialString 112 -DialMask 911;117;118
> Set-CsLocationPolicy -Identity London -EmergencyNumbers @{add=$a,$b}
```

<span data-ttu-id="e0146-120">L’exemple suivant configure plusieurs numéros d’urgence pour l’Inde :</span><span class="sxs-lookup"><span data-stu-id="e0146-120">The next example configures multiple emergency numbers for India:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 100 -DialMask 911
> $b = New-CsEmergencyNumber -DialString 101
> $c = New-CsEmergencyNumber -DialString 102
> Set-CsLocationPolicy -Identity India -EmergencyNumbers @{add=$a,$b,$c}
```

<span data-ttu-id="e0146-121">L’exemple suivant supprime une entrée existante avec la chaîne de numérotation 911 et les masques de numérotation 112 et 999 :</span><span class="sxs-lookup"><span data-stu-id="e0146-121">The next example removes an existing entry with Dial string 911 and Dial masks 112 and 999:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{remove=$a}
```