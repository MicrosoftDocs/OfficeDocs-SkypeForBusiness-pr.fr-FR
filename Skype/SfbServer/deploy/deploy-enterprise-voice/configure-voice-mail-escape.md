---
title: Configuration de la redirection vers la messagerie vocale dans Skype Entreprise 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: a1d19e6c-82ff-4768-8ae5-da981368ce40
description: 'Résumé : Apprenez à configurer d’échappement de messagerie vocale dans Skype pour 2015 de serveur d’entreprise à l’aide de la Skype pour Business Server Management Shell.'
ms.openlocfilehash: 07586f38127b2831ecdb2900f005ff43b4184292
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="configure-voice-mail-escape-in-skype-for-business-2015"></a>Configuration de la redirection vers la messagerie vocale dans Skype Entreprise 2015
 
**Résumé :** Apprenez à configurer d’échappement de messagerie vocale dans Skype pour 2015 de serveur d’entreprise à l’aide de la Skype pour Business Server Management Shell.
  
Lorsqu’un utilisateur configure des appels simultanés à un téléphone portable, un appelant sera habituellement vos messages vocaux personnels de l’utilisateur si le téléphone mobile est éteint, en panne de batterie ou hors limites. Avec Skype pour Business Server, les utilisateurs peuvent choisir de recevoir professionnelles des appels acheminés vers leur système de messagerie vocale d’entreprise. Plus précisément, une minuterie peut être configurée et si l’appel est reçu par messagerie vocale de l’opérateur dans l’intervalle de temps défini, Skype pour Business Server déconnecte du système de messagerie vocale de l’opérateur (et vocaux personnels à l’utilisateur), lors de l’utilisateur autres points de terminaison dans le système d’entreprise continuent à l’anneau. De cette façon, l’appelant est automatiquement acheminé vers messagerie vocale d’entreprise de l’utilisateur.
  
Cette configuration s’effectue à l’aide de la Skype pour l’applet de commande Business Server Management Shell, **Ensemble-CsVoicePolicy**, au niveau de stratégie voice, avec les paramètres suivants.
  
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

[Configuration des stratégies de la voix et les enregistrements d’utilisation de TLS pour autoriser des privilèges et des fonctionnalités d’appel](http://technet.microsoft.com/library/63f22010-a3d7-4cbd-86e8-6fc0e13c2b84.aspx)

