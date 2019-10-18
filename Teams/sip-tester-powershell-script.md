---
title: Script PowerShell pour tester les connexions du contrôleur de bordure de session de routage direct
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.reviewer: filippse
ms.service: msteams
audience: admin
description: Utilisez cet exemple de script PowerShell pour tester les connexions du contrôleur de bordereaux de routage direct dans Microsoft Teams.
localization_priority: Normal
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: c6df8ee654696ceef89c36a354d943c97139bf8b
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37568676"
---
# <a name="powershell-script-to-test-direct-routing-session-border-controller-connections"></a>Script PowerShell pour tester les connexions du contrôleur de bordure de session de routage direct

Le client du testeur SIP est un exemple de script PowerShell que vous pouvez utiliser pour tester les connexions de contrôleur de session de routage direct (SBC) dans Microsoft Teams. Ce script teste les fonctionnalités de base d’un Trunk SIP (Session Initiation Protocol) avec le routage direct.

Le script envoie un test SIP au testeur de tests, attend le résultat, puis le présente dans un format lisible par l’utilisateur. Vous pouvez utiliser ce script pour tester les scénarios suivants :

- Appels sortants et entrants
- Sonnerie simultanée
- Réaffectation de médias
- Transfert de consultation

## <a name="download-the-script-and-documentation"></a>Télécharger le script et la documentation

Téléchargez le [script et la documentation client du testeur SIP](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/sip-tester-client/siptesterclient.zip?raw=true).