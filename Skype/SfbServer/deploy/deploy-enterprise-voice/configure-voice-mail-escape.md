---
title: Configurer l’échappement de la messagerie vocale dans Skype entreprise
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a1d19e6c-82ff-4768-8ae5-da981368ce40
description: 'Résumé: Découvrez comment configurer l’échappement de la messagerie vocale dans Skype entreprise Server à l’aide de Skype entreprise Server Management Shell.'
ms.openlocfilehash: 89c449f538fee2f5230cb66a664317cada723220
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34289082"
---
# <a name="configure-voice-mail-escape-in-skype-for-business"></a>Configurer l’échappement de la messagerie vocale dans Skype entreprise

**Résumé:** Découvrez comment configurer l’échappement de la messagerie vocale dans Skype entreprise Server à l’aide de Skype entreprise Server Management Shell.

Lorsqu’un utilisateur configure une sonnerie simultanée sur un téléphone mobile, un appelant est généralement dirigé vers la messagerie vocale personnelle de l’utilisateur si ce dernier est éteint, n’est pas alimenté ou n’est pas à portée de batterie. Avec Skype entreprise Server, les utilisateurs peuvent choisir d’avoir accès à leur système de messagerie vocale d’entreprise. Plus précisément, un minuteur peut être configuré, et si l’appel est reçu par la messagerie vocale de l’opérateur dans la plage de temps définie, Skype entreprise Server se déconnecte du système de messagerie vocale de l’opérateur (et de la messagerie vocale personnelle de l’utilisateur), tandis que l’utilisateur les points de terminaison restants du système d’entreprise continuent de sonner. De cette façon, l’appelant est automatiquement routé vers la messagerie vocale de l’utilisateur.

Cette configuration est effectuée à l’aide de l’applet de commande Skype entreprise Server Management Shell, **Set-CsVoicePolicy**, au niveau de la stratégie vocale, avec les paramètres suivants.

### <a name="to-configure-voice-mail-escape"></a>Pour configurer la redirection vers la messagerie vocale

1. Démarrez Skype entreprise Server Management Shell: cliquez sur **Démarrer**, **tous les programmes**, cliquez sur **Skype entreprise 2015**, puis cliquez sur **Skype entreprise Server Management Shell**.

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

