---
title: Fusion héritée
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.LegacyMergeAddPicPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 085fde15-e33a-4d95-8d06-4da1d5d7c770
description: Conférence Web externe complet permet aux utilisateurs externes de participer à des conférences de locaux. Entrez le nom de domaine pleinement qualifié (FQDN) de l’interface externe de la conférence web du serveur Edge hérités.
ms.openlocfilehash: 09bba6fa5532e85572a1272fde59dc0a1f7a9c1e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="legacy-merge"></a>Fusion héritée
 
Le **nom de domaine externe complet conférences sur le Web** permet aux utilisateurs externes de participer à des conférences de locaux. Entrez le nom de domaine pleinement qualifié (FQDN) de l’interface externe de la conférence web du serveur Edge hérités.
  
La valeur du **port externe de conférence Web externe** **443** est le port du protocole TCP (Transmission Control) protocole SIP (Session Initiation) par défaut configuré pour les clients de conférence. Si la valeur par défaut n’a pas été utilisée, mettre à jour la valeur du **port externe de conférence Web externe** .
  
Activez la case à cocher **bord ce pool est utilisé pour la fédération et la connectivité PIC** si vous envisagez d’utiliser ce serveur de transport Edge pour la fédération. Si vous avez plusieurs serveurs Edge déployés, un seul d'entre eux est activé pour la fédération. Si vous ne cochez pas cette case et que vous décidez ultérieurement que vous voulez activer la fédération, vous devez réexécuter l’Assistant de fusion de générateur de topologie, mais aussi publier votre topologie. Pour plus d’informations, consultez [Phase 4 : fusionner des Topologies](http://technet.microsoft.com/library/81eb5bb2-1fd7-4611-a2aa-eb2393c8abc9.aspx).
  

