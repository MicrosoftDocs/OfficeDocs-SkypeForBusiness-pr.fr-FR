---
title: Configurer plusieurs numéros d’urgence dans Skype entreprise
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Consultez cette rubrique pour découvrir comment configurer plusieurs numéros d’urgence dans Skype entreprise Server.
ms.openlocfilehash: 81d3dbed919c936eb8a656d123f5c44e445044d7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42027795"
---
# <a name="configure-multiple-emergency-numbers-in-skype-for-business"></a>Configurer plusieurs numéros d’urgence dans Skype entreprise

Consultez cette rubrique pour découvrir comment configurer plusieurs numéros d’urgence dans Skype entreprise Server.

Skype entreprise Server prend désormais en charge plusieurs numéros d’urgence pour un client. Plusieurs numéros d’urgence sont une nouvelle fonctionnalité introduite dans la mise à jour cumulative de juin 2016. Avant de configurer votre environnement pour qu’il prenne en charge plusieurs numéros d’urgence, veillez à consulter la page [plan for multiple Emergency Numbers in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md).

> [!NOTE]
> Si vous n’avez pas encore effectué la mise à niveau vers la mise à jour cumulative de novembre 2016, consultez la rubrique [mises à jour vers Skype entreprise Server 2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015). Avec la mise à jour cumulative de novembre 2016, le nombre de numéros d’urgence de prise en charge augmente de 5 à 100.

## <a name="configure-multiple-emergency-numbers"></a>Configurer plusieurs numéros d’urgence

Pour configurer plusieurs numéros d’urgence, vous utilisez la cmdlet New-applet csemergencynumber, puis vous spécifiez le paramètre EmergencyNumbers avec les cmdlets [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) et [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps) . Pour obtenir une description complète de tous les paramètres de stratégie d’emplacement, tels que l’utilisation PSTN et l’emplacement requis, reportez-vous à [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps).

La commande suivante crée un nouveau numéro d’urgence à l’aide de la chaîne de numérotation 911 à l’aide de la cmdlet New-CsEmergency :

```powershell
> $a = New-CsEmergencyNumber -DialString 911
```

La commande suivante associe le numéro à la stratégie d’emplacement spécifiée en spécifiant le paramètre EmergencyNumbers dans la cmdlet Set-CsLocationPolicy :

```powershell
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a}
```

Dans l’exemple suivant, un numéro d’urgence est créé à l’aide d’un masque de numérotation unique, 112 :

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112
```

La commande suivante permet de créer un numéro d’urgence avec plusieurs masques de numérotation :

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
```

Dans l’exemple suivant, plusieurs numéros d’urgence sont ajoutés avec plusieurs masques de numérotation, puis les numéros d’urgence sont associés à la stratégie d’emplacement spécifiée :

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
> $b = New-CsEmergencyNumber -DialString 500 -DialMask 501;502
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a,$b}
```

Dans l’exemple suivant, plusieurs numéros d’urgence sont configurés pour les fournisseurs de soins d’intégrité qui utilisent 911 et 450 :

```powershell
> $a = New-CsEmergencyNumber -DialString 911
> $b = New-CsEmergencyNumber -DialString 450
> Set-CsLocationPolicy -Identity US-Hospital -EmergencyNumbers @{add=$a,$b}
```

Dans l’exemple suivant, plusieurs numéros d’urgence sont configurés pour la ville de Londres :

```powershell
> $a = New-CsEmergencyNumber -DialString 999 -DialMask 144
> $b = New-CsEmergencyNumber -DialString 112 -DialMask 911;117;118
> Set-CsLocationPolicy -Identity London -EmergencyNumbers @{add=$a,$b}
```

Dans l’exemple suivant, plusieurs numéros d’urgence sont configurés pour l’Inde :

```powershell
> $a = New-CsEmergencyNumber -DialString 100 -DialMask 911
> $b = New-CsEmergencyNumber -DialString 101
> $c = New-CsEmergencyNumber -DialString 102
> Set-CsLocationPolicy -Identity India -EmergencyNumbers @{add=$a,$b,$c}
```

L’exemple suivant supprime une entrée existante à l’aide de la chaîne de numérotation 911 et des masques de numérotation 112 et 999 :

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{remove=$a}
```
