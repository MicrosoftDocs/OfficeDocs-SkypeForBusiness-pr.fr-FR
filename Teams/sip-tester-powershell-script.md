---
title: Script PowerShell de test des connexions du contrôleur de bordure de session de routage direct
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.reviewer: filippse
ms.service: msteams
audience: admin
description: Utilisez cet exemple de script PowerShell pour tester les connexions du contrôleur de bordure de session de routage direct Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: c52febae3d734af49d1b23c7c65ceb0c2f746f7a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834274"
---
# <a name="powershell-script-to-test-direct-routing-session-border-controller-connections"></a>Script PowerShell de test des connexions du contrôleur de bordure de session de routage direct

Le client de test SIP est un exemple de script PowerShell que vous pouvez utiliser pour tester les connexions du contrôleur de bordure de session de routage direct (SBC) Microsoft Teams. Ce script teste la fonctionnalité de base d’une ligne SIP (Session Initiation Protocol) couplée au client avec le routage direct.

Le script envoie un test SIP au deuxième résultat, attend le résultat, puis le présente dans un format lisible par l’homme. Vous pouvez utiliser ce script pour tester les scénarios suivants :

- Appels sortants et entrants
- Sonnerie simultanée
- Escalade multimédia
- Transfert consultatif

## <a name="download-the-script-and-documentation"></a>Télécharger le script et la documentation

Téléchargez le script client et la documentation du [test SIP.](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/sip-tester-client/siptesterclient.zip?raw=true)

  > [!NOTE]
  > Le script client SIP Tester prend adal.ps uniquement en charge la version 3.19.8.1. Une erreur est renvoyée si une version ultérieure du adal.ps est utilisée.
  
  
