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
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 344bf59d401e43c40c6f643b334c2f34311d6cbe
ms.sourcegitcommit: 8665603fae8408ccbc083dd59cb01936ebe96c58
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/02/2020
ms.locfileid: "43116690"
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

  > [!NOTE]
  > Le script client du testeur SIP prend uniquement en charge adal.ps version 3.19.8.1. Une erreur est renvoyée si une version ultérieure du adal.ps est utilisée.
  
  
