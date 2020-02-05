---
title: Configuration de plusieurs numéros d’urgence dans Skype entreprise
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
description: Pour découvrir comment configurer plusieurs numéros d’urgence dans Skype entreprise Server, reportez-vous à cette rubrique.
ms.openlocfilehash: 9805462d8c9498af3e3cf1cb743e2af9e08ec285
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768117"
---
# <a name="configure-multiple-emergency-numbers-in-skype-for-business"></a>Configuration de plusieurs numéros d’urgence dans Skype entreprise

Pour découvrir comment configurer plusieurs numéros d’urgence dans Skype entreprise Server, reportez-vous à cette rubrique.

Skype entreprise Server prend désormais en charge plusieurs numéros d’urgence pour un client. Plusieurs numéros d’urgence constituent une nouvelle fonctionnalité introduite dans la mise à jour cumulative 2016 de juin. Avant de configurer votre environnement pour prendre en charge plusieurs numéros d’urgence, veillez à lire [plan pour plusieurs numéros d’urgence dans Skype entreprise Server](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md).

> [!NOTE]
> Si vous n’avez pas encore effectué la mise à jour vers la version cumulative 2016 de novembre, reportez-vous à la rubrique [mises à jour de Skype entreprise Server 2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015). Avec la mise à jour cumulative 2016 de novembre, le nombre de numéros d’urgence de prise en charge augmente de 5 à 100. 

## <a name="configure-multiple-emergency-numbers"></a>Configuration de plusieurs numéros d'urgence

Pour configurer plusieurs numéros d’urgence, vous utilisez l’applet de nouvelle applet de nouveau-CsEmergencyNumber, puis vous spécifiez le paramètre EmergencyNumbers avec les applets de [nouvelle cmdlet New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) et [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps) . Pour obtenir une description complète de tous les paramètres de stratégie d’emplacement, tels que l’utilisation RTC et l’emplacement requis, voir [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps).

La commande suivante permet de créer un numéro d'urgence avec la chaîne de numérotation 911 à l'aide de l'applet de commande New-CsEmergency :

```powershell
> $a = New-CsEmergencyNumber -DialString 911 
```

La commande suivante permet d'associer le numéro à la stratégie d'emplacement en spécifiant les paramètres EmergencyNumbers dans l'applet de commande Set-CsLocationPolicy :

```powershell
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a} 
```

Dans l'exemple suivant, un numéro d'urgence est créé à l'aide d'un masque d'appel unique, le 112 :

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112 
```

La commande suivante crée un numéro d’urgence avec plusieurs masques de numérotation :

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999 
```

Dans l'exemple suivant, plusieurs numéros d'urgence sont ajoutés avec différents masques d'appel, puis associés aux numéros d'urgence avec la stratégie d'emplacement spécifiée :

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999 
> $b = New-CsEmergencyNumber -DialString 500 -DialMask 501;502
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a,$b} 
```

Dans l'exemple suivant, plusieurs numéros d'urgence destinés aux organismes de soin de santé utilisant 911 et 450 sont configurés :  

```powershell
> $a = New-CsEmergencyNumber -DialString 911 
> $b = New-CsEmergencyNumber -DialString 450
> Set-CsLocationPolicy -Identity US-Hospital -EmergencyNumbers @{add=$a,$b}
```

Dans l'exemple suivant, plusieurs numéros d'urgence sont configurés pour la ville de Londres :

```powershell
> $a = New-CsEmergencyNumber -DialString 999 -DialMask 144
> $b = New-CsEmergencyNumber -DialString 112 -DialMask 911;117;118
> Set-CsLocationPolicy -Identity London -EmergencyNumbers @{add=$a,$b}
```

Dans l'exemple suivant, plusieurs numéros d'urgence sont configurés pour l'Inde :

```powershell
> $a = New-CsEmergencyNumber -DialString 100 -DialMask 911
> $b = New-CsEmergencyNumber -DialString 101 
> $c = New-CsEmergencyNumber -DialString 102 
> Set-CsLocationPolicy -Identity India -EmergencyNumbers @{add=$a,$b,$c}
```

Dans l'exemple suivant, une entrée existante est supprimée avec la chaîne de numérotation 911 et les masques d'appel 112 et 999 :

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{remove=$a} 
```


