---
title: Configurer le robot de rappel pour le routage direct
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.reviewer: filippse
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
description: Découvrez comment utiliser le robot de rappel pour le routage direct afin d’éviter les silences inattendus qui peuvent se produire lors de la mise en place d’un appel.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1db113a610c153f821a0d92187744e6ca34e3ce3
ms.sourcegitcommit: 69ff557c79d6b1a3d1089fe5c8f5c8ed8ff7431e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/30/2020
ms.locfileid: "43951189"
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

## <a name="related-topics"></a>Sujets associés

- [Présentation de Teams PowerShell](teams-powershell-overview.md)