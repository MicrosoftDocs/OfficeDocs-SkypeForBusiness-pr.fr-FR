---
title: Script PowerShell pour tester les connexions du contrôleur de frontière de session de routage direct
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: article
ms.reviewer: filippse
ms.service: msteams
audience: admin
description: Utilisez cet exemple de script PowerShell pour tester les connexions du contrôleur de frontière de session de routage direct dans Microsoft Teams.
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 215edfed535352004c960182bd649721131aedb0
ms.sourcegitcommit: 472e46b6eb907f41920516616683a61f0fc6f741
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/30/2022
ms.locfileid: "66564132"
---
# <a name="powershell-script-to-test-direct-routing-session-border-controller-connections"></a>Script PowerShell pour tester les connexions du contrôleur de frontière de session de routage direct

Le client testeur SIP est un exemple de script PowerShell que vous pouvez utiliser pour tester les connexions SBC (Direct Routing Session Border Controller) dans Microsoft Teams. Ce script teste les fonctionnalités de base d’une jonction SIP (Session Initiation Protocol) associée au client avec routage direct.

Le script envoie un test SIP à l’exécuteur de test, attend le résultat, puis le présente dans un format lisible par l’homme. Vous pouvez utiliser ce script pour tester les scénarios suivants :

- Appels sortants et entrants
- Sonnerie simultanée
- Escalade des médias
- Transfert consultatif

## <a name="download-the-script-and-documentation"></a>Télécharger le script et la documentation

Téléchargez le [script client et la documentation du testeur SIP](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/sip-tester-client/siptesterclient.zip?raw=true).

  > [!NOTE]
  > Le script client du testeur SIP prend uniquement en charge adal.ps version 3.19.8.1. Une erreur est retournée si une version ultérieure du adal.ps est utilisée.
  
  
