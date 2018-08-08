---
title: Configurer plusieurs numéros d’urgence dans Skype pour les entreprises
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2e869df0-5fdb-4e70-bd81-cb012556eb1a
description: Lisez cette rubrique pour savoir comment configurer plusieurs numéros d’urgence dans Skype pour Business Server.
ms.openlocfilehash: 01dc72e2d165ff3c4076aa4180768ca941607b93
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20985422"
---
# <a name="configure-multiple-emergency-numbers-in-skype-for-business"></a>Configurer plusieurs numéros d’urgence dans Skype pour les entreprises
 
Lisez cette rubrique pour savoir comment configurer plusieurs numéros d’urgence dans Skype pour Business Server.
  
Skype pour Business Server prend désormais en charge plusieurs numéros d’urgence pour un client. Plusieurs numéros d’urgence sont une nouveauté dans le 2016 juin mise à jour Cumulative. Avant de configurer votre environnement pour prendre en charge plusieurs numéros d’urgence, veillez à lire [planifier plusieurs numéros d’urgence dans Skype pour Business Server](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md).
  
> [!NOTE]
> Si vous n'avez pas encore mis à niveau vers la 2016 novembre mise à jour Cumulative, consultez [mises à jour Skype pour Business Server 2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015). Mise à jour Cumulative, le nombre de numéros d’urgence de prise en charge avec la 2016 novembre augmente 5 à 100. 
  
## <a name="configure-multiple-emergency-numbers"></a>Configuration de plusieurs numéros d'urgence

Pour configurer plusieurs numéros d’urgence, vous utilisez l’applet de commande New-CsEmergencyNumber, puis vous spécifiez le paramètre EmergencyNumbers avec les applets de commande [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) et [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps) . Pour une description complète de tous les paramètres de stratégie emplacement, telles que l’utilisation PSTN et l’emplacement requis, voir [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps).
  
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

La commande suivante crée un numéro d’urgence avec plusieurs masques de numérotation :
  
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


