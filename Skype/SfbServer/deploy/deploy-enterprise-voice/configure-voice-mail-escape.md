---
title: Configuration de la redirection vers la messagerie vocale dans Skype Entreprise 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a1d19e6c-82ff-4768-8ae5-da981368ce40
description: 'Résumé : Découvrez comment configurer redirection vers la messagerie vocale Skype pour Business Server 2015 à l’aide de la Skype pour Business Server Management Shell.'
ms.openlocfilehash: dea96ffb9eb670a430e9f983660a793444812438
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="configure-voice-mail-escape-in-skype-for-business-2015"></a>Configuration de la redirection vers la messagerie vocale dans Skype Entreprise 2015
 
**Résumé :** Découvrez comment configurer redirection vers la messagerie vocale Skype pour Business Server 2015 à l’aide de la Skype pour Business Server Management Shell.
  
Lorsqu’un utilisateur configure la sonnerie simultanée vers un téléphone mobile, un appelant généralement être acheminé vers la messagerie vocale personnelle de l’utilisateur si le téléphone mobile est éteint, en dehors de la batterie ou en dehors des limites. Avec Skype pour Business Server, les utilisateurs peuvent choisir de lié à l’entreprise d’appels acheminés vers leur système de messagerie vocale d’entreprise. En particulier, un minuteur peut être configuré, et si l’appel est reçu par la messagerie vocale de l’opérateur dans la plage définie, Skype pour Business Server déconnecte du système de messagerie vocale de l’opérateur (et la messagerie vocale personnelle de l’utilisateur), lors de l’utilisateur autres points de terminaison dans le système d’entreprise continuent à sonner. Ainsi, l’appelant est automatiquement dirigé vers la messagerie vocale d’entreprise de l’utilisateur.
  
Cette configuration est effectuée à l’aide de la Skype pour Business Server Management Shell cmdlet **Set-CsVoicePolicy**, au niveau de la stratégie de voix, avec les paramètres suivants.
  
### <a name="to-configure-voice-mail-escape"></a>Pour configurer la redirection vers la messagerie vocale

1. Démarrez Skype Entreprise Server Management Shell : cliquez successivement sur **Démarrer**, **Tous les programmes**, **Skype Entreprise 2015**, puis sur **Skype Entreprise Server Management Shell**.
    
2. Spécifiez les paramètres ci-dessous sur **Set-CsVoicePolicy** :
    
   - **EnableVoicemailEscapeTimer** : active ou désactive le minuteur de redirection.
    
   - **PSTNVoicemailEscapeTimer** : spécifie la valeur de délai d’attente en millisecondes. La valeur par défaut est 1 500 millisecondes et la valeur peut être comprise entre 0 milliseconde et 8 000 millisecondes.
    
## <a name="example"></a>Exemple

```
Set-CsVoicePolicy UserVoicePolicy -EnableVoiceMailEscapeTimer $true - PSTNVoicemailEscapeTimer 2000

Set-CsVoicePolicy -Identity site:SitePolicy -EnableVoiceMailEscapeTimer $true -PSTNVoicemailEscapeTimer 1500

```

## <a name="see-also"></a>Voir aussi

#### 

[Configuration de stratégies de voix et les enregistrements d’utilisation PSTN pour autoriser les privilèges et les fonctionnalités d’appel](http://technet.microsoft.com/library/63f22010-a3d7-4cbd-86e8-6fc0e13c2b84.aspx)

