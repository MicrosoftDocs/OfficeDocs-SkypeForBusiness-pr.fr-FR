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
ms.openlocfilehash: 26738002ab333d2490ef0dac5674a1f7cdc19efd
ms.sourcegitcommit: 8974cd7a693bc879fed8222f551fd7ce3205dd65
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/25/2020
ms.locfileid: "49420954"
---
# <a name="set-up-the-ringback-bot-for-direct-routing"></a>Configurer le robot de rappel pour le routage direct

Cet article décrit le robot de rappel, que vous pouvez utiliser pour éviter les silences inattendus qui peuvent se produire lorsque les appels sont plus longs à établir. Le robot de rappel est disponible pour le routage direct en mode de contournement non multimédia.

Parfois, les appels entrants du réseau téléphonique public commuté (RTC) vers les clients teams peuvent prendre plus de temps que prévu. Cela peut se produire pour diverses raisons. Lorsque c’est le cas, l’appelant risque de n’entendre rien, le client Teams ne sonne pas et certains fournisseurs de télécommunications peuvent annuler l’appel.

Le robot de rappel permet d’éviter des silences inattendus qui peuvent se produire dans ce scénario. Pour les appels entrants des clients RTC aux équipes, le bot de rappel d’appel lit un signal audio distinctif pour l’appelant afin d’indiquer que les équipes sont dans le processus de création de l’appel.

> [!NOTE]
> Le robot de rappel génère des contenus multimédias au premier plan à partir du serveur principal Teams. Dans certains pays et régions, il est possible que vous deviez payer l’appel lorsque le média commence à circuler.

## <a name="configure-the-ringback-bot"></a>Configurer le robot de rappel

Utilisez l’applet de commande [Set-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway) pour modifier une configuration de contrôleur de frontière de session (SBC) déjà définie ou l’applet [de commande New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) pour créer une nouvelle configuration de SBC, ainsi que le paramètre **GenerateRingingWhileLocatingUser** pour configurer le bot de rappel :

- Pour activer le robot de rappel, définissez le paramètre **GenerateRingingWhileLocatingUser** sur **$true**. Il s’agit de la valeur par défaut. 

- Pour désactiver le bot de rappel, définissez le paramètre **GenerateRingingWhileLocatingUser** sur **$false**. 

## <a name="related-topics"></a>Sujets associés

- [Présentation de Teams PowerShell](teams-powershell-overview.md)
