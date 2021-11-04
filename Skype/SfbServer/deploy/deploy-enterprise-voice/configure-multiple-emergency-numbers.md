---
title: Configurer plusieurs numéros d’urgence dans Skype Entreprise
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2e869df0-5fdb-4e70-bd81-cb012556eb1a
description: Lisez cette rubrique pour apprendre à configurer plusieurs numéros d’urgence dans Skype Entreprise Server.
ms.openlocfilehash: c8776ed65de04e19525d1b220022f47bee58754e
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60769672"
---
# <a name="configure-multiple-emergency-numbers-in-skype-for-business"></a>Configurer plusieurs numéros d’urgence dans Skype Entreprise

Lisez cette rubrique pour apprendre à configurer plusieurs numéros d’urgence dans Skype Entreprise Server.

Skype Entreprise Server prend désormais en charge plusieurs numéros d’urgence pour un client. Plusieurs numéros d’urgence sont une nouvelle fonctionnalité introduite dans la mise à jour cumulative de juin 2016. Avant de configurer votre environnement pour prendre en charge plusieurs numéros d’urgence, veillez à lire Planifier plusieurs numéros d’urgence [dans Skype Entreprise Server](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md).

> [!NOTE]
> Si vous n’avez pas encore mis à niveau vers la mise à jour cumulative de novembre 2016, voir Mises à jour [Skype Entreprise Server 2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015). Avec la mise à jour cumulative de novembre 2016, le nombre de numéros d’urgence de support augmente de 5 à 100.

## <a name="configure-multiple-emergency-numbers"></a>Configuration de plusieurs numéros d’urgence

Pour configurer plusieurs numéros d’urgence, utilisez l’cmdlet New-CsEmergencyNumber, puis spécifiez le paramètre EmergencyNumbers avec les cmdlets [New-CsLocationPolicy](/powershell/module/skype/new-cslocationpolicy?view=skype-ps) et [Set-CsLocationPolicy.](/powershell/module/skype/set-cslocationpolicy?view=skype-ps) Pour obtenir une description complète de tous les paramètres de stratégie d’emplacement, tels que l’utilisation PSTN et l’emplacement requis, voir [Set-CsLocationPolicy](/powershell/module/skype/set-cslocationpolicy?view=skype-ps).

La commande suivante crée un nouveau numéro d’urgence avec la chaîne de numérotation 911 à l’aide de la cmdlet New-CsEmergency suivante :

```powershell
> $a = New-CsEmergencyNumber -DialString 911
```

La commande suivante associe le numéro à la stratégie d’emplacement spécifiée en spécifiant le paramètre EmergencyNumbers dans la cmdlet Set-CsLocationPolicy suivante :

```powershell
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a}
```

Dans l’exemple suivant, un numéro d’urgence est créé avec un masque de numérotation unique, 112 :

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112
```

La commande suivante crée un numéro d’urgence avec plusieurs masques de numérotation :

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
```

L’exemple suivant ajoute plusieurs numéros d’urgence avec plusieurs masques de numérotation, puis associe les numéros d’urgence à la stratégie d’emplacement spécifiée :

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
> $b = New-CsEmergencyNumber -DialString 500 -DialMask 501;502
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a,$b}
```

L’exemple suivant configure plusieurs numéros d’urgence pour les fournisseurs de services de santé qui utilisent les numéros 911 et 450 :

```powershell
> $a = New-CsEmergencyNumber -DialString 911
> $b = New-CsEmergencyNumber -DialString 450
> Set-CsLocationPolicy -Identity US-Hospital -EmergencyNumbers @{add=$a,$b}
```

L’exemple suivant configure plusieurs numéros d’urgence pour la ville de Londres :

```powershell
> $a = New-CsEmergencyNumber -DialString 999 -DialMask 144
> $b = New-CsEmergencyNumber -DialString 112 -DialMask 911;117;118
> Set-CsLocationPolicy -Identity London -EmergencyNumbers @{add=$a,$b}
```

L’exemple suivant configure plusieurs numéros d’urgence pour l’Inde :

```powershell
> $a = New-CsEmergencyNumber -DialString 100 -DialMask 911
> $b = New-CsEmergencyNumber -DialString 101
> $c = New-CsEmergencyNumber -DialString 102
> Set-CsLocationPolicy -Identity India -EmergencyNumbers @{add=$a,$b,$c}
```

L’exemple suivant supprime une entrée existante avec la chaîne de numérotation 911 et les masques de numérotation 112 et 999 :

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{remove=$a}
```