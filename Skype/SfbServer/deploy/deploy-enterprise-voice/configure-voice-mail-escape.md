---
title: Configurer l’échappatoire de messagerie vocale dans Skype Entreprise
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
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a1d19e6c-82ff-4768-8ae5-da981368ce40
description: 'Résumé : Découvrez comment configurer la messagerie vocale dans Skype Entreprise Server à l’aide de Skype Entreprise Server Management Shell.'
ms.openlocfilehash: c74142cf3b0f6c9d5a871e116d8e163a095ad3cd
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51106370"
---
# <a name="configure-voice-mail-escape-in-skype-for-business"></a>Configurer l’échappatoire de messagerie vocale dans Skype Entreprise

**Résumé :** Découvrez comment configurer la messagerie vocale dans Skype Entreprise Server à l’aide de Skype Entreprise Server Management Shell.

Lorsqu’un utilisateur configure la sonnerie simultanée sur un téléphone mobile, un appelant est généralement acheminé vers la messagerie vocale personnelle de l’utilisateur si le téléphone mobile est éteint, hors batterie ou hors de portée. Avec Skype Entreprise Server, les utilisateurs peuvent choisir d’avoir des appels professionnels acheminés vers leur système de messagerie vocale d’entreprise. Plus précisément, un timer peut être configuré et, si la messagerie vocale de l’opérateur répond à l’appel dans la plage de temps définie, Skype Entreprise Server se déconnecte du système de messagerie vocale de l’opérateur (et de la messagerie vocale personnelle de l’utilisateur), tandis que les points de terminaison restants de l’utilisateur dans le système d’entreprise continuent de sonner. Ainsi, l’appelant est automatiquement acheminé vers la messagerie vocale d’entreprise de l’utilisateur.

Cette configuration est effectuée à l’aide de l’cmdlet Skype Entreprise Server Management Shell, **Set-CsVoicePolicy,** au niveau de la stratégie de voix, avec les paramètres suivants.

### <a name="to-configure-voice-mail-escape"></a>Pour configurer l’échappage de messagerie vocale

1. Démarrez Skype Entreprise Server Management Shell : cliquez sur **Démarrer,** sur Tous les **programmes,** sur Skype Entreprise **2015,** puis sur Skype Entreprise **Server Management Shell.**

2. Spécifiez les paramètres suivants de **Set-CsVoicePolicy** :

   - **EnableVoicemailEscapeTimer** - Active ou désactive le minuteur d’échappement.

   - **PSTNVoicemailEscapeTimer** - Spécifie la valeur de délai d’attente en millisecondes. La valeur par défaut est 1500 millisecondes et la valeur peut être comprise entre 0 milliseconde et 8000 millisecondes.

## <a name="example"></a>Exemple

```powershell
Set-CsVoicePolicy UserVoicePolicy -EnableVoiceMailEscapeTimer $true - PSTNVoicemailEscapeTimer 2000
Set-CsVoicePolicy -Identity site:SitePolicy -EnableVoiceMailEscapeTimer $true -PSTNVoicemailEscapeTimer 1500
```

## <a name="see-also"></a>Voir aussi

[Configuration des stratégies de voix et des enregistrements d’utilisation PSTN pour autoriser les privilèges et les fonctionnalités d’appel](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges)