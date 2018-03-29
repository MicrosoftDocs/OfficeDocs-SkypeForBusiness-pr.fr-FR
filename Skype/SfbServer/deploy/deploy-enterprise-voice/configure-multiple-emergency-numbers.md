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
# <a name="configure-multiple-emergency-numbers-in-skype-for-business-2015"></a>Configuration de plusieurs numéros d'urgence dans Skype Entreprise 2015
 
Pour savoir comment configurer plusieurs numéros d'urgence dans Skype Entreprise Server 2015, lisez cette rubrique.
  
Skype pour Business Server prend désormais en charge plusieurs numéros d’urgence pour un client. Plusieurs numéros d’urgence sont une nouvelle fonctionnalité introduite dans le 2016 juin mise à jour Cumulative. Avant de configurer votre environnement pour la prise en charge de plusieurs numéros d’urgence, veillez à lire le [Plan pour plusieurs numéros d’urgence dans Skype pour Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md).
  
> [!NOTE]
> Si vous n'avez pas encore mis à niveau vers le 2016 novembre mise à jour Cumulative, consultez [mises à jour Skype pour Business Server 2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015). Avec le 2016 novembre mise à jour Cumulative, le nombre de numéros d’urgence de prise en charge augmente de 5 à 100. 
  
## <a name="configure-multiple-emergency-numbers"></a>Configuration de plusieurs numéros d'urgence

Pour configurer plusieurs numéros d’urgence, vous utilisez l’applet de commande New-CsEmergencyNumber, et puis vous spécifiez le paramètre EmergencyNumbers avec les applets de commande [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) et [CsLocationPolicy de l’ensemble](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps) . Pour une description complète de tous les paramètres de stratégie emplacement, comme l’utilisation de TLS et l’emplacement requis, voir [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps).
  
La commande suivante permet de créer un numéro d'urgence avec la chaîne de numérotation 911 à l'aide de l'applet de commande New-CsEmergency :
  
```
> $a = New-CsEmergencyNumber -DialString 911 

```

La commande suivante permet d'associer le numéro à la stratégie d'emplacement en spécifiant les paramètres EmergencyNumbers dans l'applet de commande Set-CsLocationPolicy :
  
```
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a} 

```

Dans l'exemple suivant, un numéro d'urgence est créé à l'aide d'un masque d'appel unique, le 112 :
  
```
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112 

```

La commande suivante crée un numéro d’urgence avec plusieurs masques à distance :
  
```
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999 

```

Dans l'exemple suivant, plusieurs numéros d'urgence sont ajoutés avec différents masques d'appel, puis associés aux numéros d'urgence avec la stratégie d'emplacement spécifiée :
  
```
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999 
> $b = New-CsEmergencyNumber -DialString 500 -DialMask 501;502
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a,$b} 

```

Dans l'exemple suivant, plusieurs numéros d'urgence destinés aux organismes de soin de santé utilisant 911 et 450 sont configurés :  
  
```
> $a = New-CsEmergencyNumber -DialString 911 
> $b = New-CsEmergencyNumber -DialString 450
> Set-CsLocationPolicy -Identity US-Hospital -EmergencyNumbers @{add=$a,$b}
```

Dans l'exemple suivant, plusieurs numéros d'urgence sont configurés pour la ville de Londres :
  
```
> $a = New-CsEmergencyNumber -DialString 999 -DialMask 144
> $b = New-CsEmergencyNumber -DialString 112 -DialMask 911;117;118
> Set-CsLocationPolicy -Identity London -EmergencyNumbers @{add=$a,$b}

```

Dans l'exemple suivant, plusieurs numéros d'urgence sont configurés pour l'Inde :
  
```
> $a = New-CsEmergencyNumber -DialString 100 -DialMask 911
> $b = New-CsEmergencyNumber -DialString 101 
> $c = New-CsEmergencyNumber -DialString 102 
> Set-CsLocationPolicy -Identity India -EmergencyNumbers @{add=$a,$b,$c}

```

Dans l'exemple suivant, une entrée existante est supprimée avec la chaîne de numérotation 911 et les masques d'appel 112 et 999 :
  
```
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{remove=$a} 

```


