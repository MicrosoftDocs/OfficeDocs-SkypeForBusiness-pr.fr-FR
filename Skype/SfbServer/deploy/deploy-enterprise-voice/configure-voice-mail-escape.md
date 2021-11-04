---
title: Configurer l’échappatoire de messagerie vocale dans Skype Entreprise
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
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a1d19e6c-82ff-4768-8ae5-da981368ce40
description: 'Résumé : Découvrez comment configurer la boîte aux lettres d’Skype Entreprise Server à l’aide de Skype Entreprise Server Management Shell.'
ms.openlocfilehash: 3414b099587b45918b28ac3e11dcf75924f41dd6
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60740100"
---
# <a name="configure-voice-mail-escape-in-skype-for-business"></a>Configurer l’échappatoire de messagerie vocale dans Skype Entreprise

**Résumé :** Découvrez comment configurer l’échappatoire de messagerie vocale dans Skype Entreprise Server à l’aide de Skype Entreprise Server Management Shell.

Lorsqu’un utilisateur configure la sonnerie simultanée sur un téléphone mobile, un appelant est généralement acheminé vers la messagerie vocale personnelle de l’utilisateur si le téléphone mobile est éteint, hors batterie ou hors de portée. Avec Skype Entreprise Server, les utilisateurs peuvent choisir d’avoir des appels professionnels acheminés vers leur système de messagerie vocale d’entreprise. Plus précisément, un système de temps peut être configuré et, si la messagerie vocale de l’opérateur répond à l’appel dans la plage de temps définie, Skype Entreprise Server se déconnecte du système de messagerie vocale de l’opérateur (et de la messagerie vocale personnelle de l’utilisateur), tandis que les points de terminaison restants de l’utilisateur dans le système d’entreprise continuent de sonner. Ainsi, l’appelant est automatiquement acheminé vers la messagerie vocale d’entreprise de l’utilisateur.

Cette configuration est effectuée à l’aide de l’Skype Entreprise Server Management Shell, **Set-CsVoicePolicy,** au niveau de la stratégie de voix, avec les paramètres suivants.

### <a name="to-configure-voice-mail-escape"></a>Pour configurer l’échappage de messagerie vocale

1. Démarrez l Skype Entreprise Server Management Shell : cliquez sur **Démarrer,** sur Tous les **programmes,** sur **Skype Entreprise 2015,** puis sur Skype Entreprise Server **Management Shell.**

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