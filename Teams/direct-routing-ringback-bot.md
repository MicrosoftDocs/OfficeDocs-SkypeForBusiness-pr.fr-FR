---
title: Configurer le robot de rappel pour le routage direct
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.reviewer: filippse
ms.service: msteams
audience: admin
description: Découvrez comment utiliser le robot de rappel pour le routage direct afin d’éviter les silences inattendus qui peuvent se produire lors de la mise en place d’un appel.
localization_priority: Normal
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3fcb69ba1bc612fe940054ec982eb7462c6679be
ms.sourcegitcommit: a23f45ab3a2cb7b5c279356edddf61c4030c41bd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/10/2019
ms.locfileid: "39962501"
---
# <a name="set-up-the-ringback-bot-for-direct-routing"></a>Configurer le robot de rappel pour le routage direct

Cet article décrit le robot de rappel, que vous pouvez utiliser pour éviter les silences inattendus qui peuvent se produire lorsque les appels sont plus longs à établir. Le robot de rappel est disponible pour le routage direct en mode de contournement non multimédia.

Parfois, les appels entrants du réseau téléphonique public commuté (RTC) vers les clients teams peuvent prendre plus de temps que prévu. Cela peut se produire pour diverses raisons. Lorsque c’est le cas, l’appelant n’entend rien, le client Teams ne sonne pas et l’appel peut être annulé par certains fournisseurs de télécommunications.

Le robot de rappel permet d’éviter des silences inattendus qui peuvent se produire dans ce scénario. Pour les appels entrants des clients RTC aux équipes, le bot de rappel d’appel lit un signal audio distinctif pour l’appelant afin d’indiquer que les équipes sont dans le processus de création de l’appel.

> [!NOTE]
> Le robot de rappel génère des contenus multimédias au premier plan à partir du serveur principal Teams. Dans certains pays et régions, il est possible que vous deviez payer l’appel lorsque le média commence à circuler.

## <a name="configure-the-ringback-bot"></a>Configurer le robot de rappel

Utilisez les cmdlets [Set-CsOnlineGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway) et [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) conjointement avec le paramètre **GenerateRingingWhileLocatingUser** pour configurer le bot de rappel.

Pour activer le robot de rappel, définissez le paramètre **GenerateRingingWhileLocatingUser** sur **$true**. Il s’agit de la valeur par défaut. 

Pour désactiver le bot de rappel, définissez le paramètre **GenerateRingingWhileLocatingUser** sur **$false**. 

## <a name="related-topics"></a>Voir aussi

- [Aperçu de Teams PowerShell](teams-powershell-overview.md)