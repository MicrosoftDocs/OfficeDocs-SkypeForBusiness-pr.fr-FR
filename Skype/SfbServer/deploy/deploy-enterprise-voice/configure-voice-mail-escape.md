---
title: Configurer la redirection vers la messagerie vocale dans Skype pour les entreprises
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a1d19e6c-82ff-4768-8ae5-da981368ce40
description: 'Résumé : Découvrez comment configurer redirection vers la messagerie vocale Skype pour Business Server à l’aide de la Skype pour Business Server Management Shell.'
ms.openlocfilehash: 6c1c6977949eb45c28cce482f98be67295ee4eef
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30891866"
---
# <a name="configure-voice-mail-escape-in-skype-for-business"></a>Configurer la redirection vers la messagerie vocale dans Skype pour les entreprises

**Résumé :** Découvrez comment configurer redirection vers la messagerie vocale Skype pour Business Server à l’aide de la Skype pour Business Server Management Shell.

Lorsqu’un utilisateur configure la sonnerie simultanée vers un téléphone mobile, un appelant généralement être acheminé vers la messagerie vocale personnelle de l’utilisateur si le téléphone mobile est éteint, en dehors de la batterie ou en dehors des limites. Avec Skype pour Business Server, les utilisateurs peuvent choisir de lié à l’entreprise d’appels acheminés vers leur système de messagerie vocale d’entreprise. En particulier, un minuteur peut être configuré, et si l’appel est reçu par la messagerie vocale de l’opérateur dans la plage définie, Skype pour Business Server déconnecte du système de messagerie vocale de l’opérateur (et la messagerie vocale personnelle de l’utilisateur), lors de l’utilisateur autres points de terminaison dans le système d’entreprise continuent à sonner. Ainsi, l’appelant est automatiquement dirigé vers la messagerie vocale d’entreprise de l’utilisateur.

Cette configuration est effectuée à l’aide de la Skype pour Business Server Management Shell cmdlet **Set-CsVoicePolicy**, au niveau de la stratégie de voix, avec les paramètres suivants.

### <a name="to-configure-voice-mail-escape"></a>Pour configurer la redirection vers la messagerie vocale

1. Démarrez le Skype pour Business Server Management Shell : cliquez sur **Démarrer**, sur **Tous les programmes**, cliquez sur **Skype pour Business 2015**, puis cliquez sur **Skype pour Business Server Management Shell**.

2. Spécifiez les paramètres ci-dessous sur **Set-CsVoicePolicy** :

   - **EnableVoicemailEscapeTimer** : active ou désactive le minuteur de redirection.

   - **PSTNVoicemailEscapeTimer** : spécifie la valeur de délai d’attente en millisecondes. La valeur par défaut est 1 500 millisecondes et la valeur peut être comprise entre 0 milliseconde et 8 000 millisecondes.

## <a name="example"></a>Exemple

```
Set-CsVoicePolicy UserVoicePolicy -EnableVoiceMailEscapeTimer $true - PSTNVoicemailEscapeTimer 2000
Set-CsVoicePolicy -Identity site:SitePolicy -EnableVoiceMailEscapeTimer $true -PSTNVoicemailEscapeTimer 1500
```

## <a name="see-also"></a>Voir aussi

[Configuring Voice Policies and PSTN Usage Records to Authorize Calling Features and Privileges](https://technet.microsoft.com/library/63f22010-a3d7-4cbd-86e8-6fc0e13c2b84.aspx)

