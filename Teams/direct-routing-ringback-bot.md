---
title: Configurer le robot Ringback pour le routage direct
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.reviewer: filippse
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
description: Découvrez comment utiliser le bot Ringback pour le routage direct afin d’éviter des silences inattendus lorsqu’un appel est établi.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 91cea9183a85a804ca43464aab08f417ccaff1e8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827514"
---
# <a name="set-up-the-ringback-bot-for-direct-routing"></a>Configurer le robot Ringback pour le routage direct

Cet article décrit le robot Ringback, que vous pouvez utiliser pour éviter des silences inattendus lorsqu’il faut plus de temps pour que les appels soient établis. Le robot Ringback est disponible pour le routage direct en mode de dérivation non multimédia.

Parfois, les appels entrants du réseau téléphonique commuté (PSTN) vers les clients Teams peuvent prendre plus de temps que prévu. Cela peut se produire pour diverses raisons. Dans ce cas, il se peut que l’appelant n’entende rien, que le client Teams ne sonne pas et que certains fournisseurs de télécommunications peuvent annuler l’appel.

Le Robot Ringback permet d’éviter les silences inattendus qui peuvent se produire dans ce scénario. Pour les appels entrants entre les clients PSTN et Teams, le bot Ringback lit un signal audio distinct pour l’appelant pour indiquer que Teams est en train d’établir l’appel.

> [!NOTE]
> Le robot Ringback génère les premiers médias à partir du verso Teams. Dans certains pays et certaines régions, l’appel peut vous être facturé lorsque les médias commencent à circuler.

## <a name="configure-the-ringback-bot"></a>Configurer le robot Ringback

Utilisez la cmdlet [Set-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway) pour modifier une configuration de contrôleur de session (SBC) précédemment définie ou la cmdlet [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) pour créer une nouvelle configuration SBC, avec le paramètre **GenerateRingingWhileLocatingUser** pour configurer le robot Ringback :

- Pour activer le robot Ringback, définissez le paramètre **GenerateRingingWhileLocatingUser** **sur $True.** Ceci est la valeur par défaut. 

- Pour désactiver le robot Ringback, définissez le paramètre **GenerateRingingWhileLocatingUser** **sur $False.** 

## <a name="related-topics"></a>Sujets associés

- [Présentation de Teams PowerShell](teams-powershell-overview.md)
