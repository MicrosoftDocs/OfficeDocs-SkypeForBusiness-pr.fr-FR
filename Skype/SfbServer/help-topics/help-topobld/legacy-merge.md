---
title: Fusion héritée
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.LegacyMergeAddPicPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 085fde15-e33a-4d95-8d06-4da1d5d7c770
description: Le nom de domaine complet pour les conférences Web autorise les utilisateurs externes à participer à des réunions locales. Entrez le nom de domaine complet (FQDN) de l’interface externe de conférence Web du serveur Edge hérité.
ms.openlocfilehash: bb059855f7893ef7b2b9c601835bb53e6f0d280b
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41697089"
---
# <a name="legacy-merge"></a>Fusion héritée

Le **nom de domaine complet pour les conférences Web** autorise les utilisateurs externes à participer à des réunions locales. Entrez le nom de domaine complet (FQDN) de l’interface externe de conférence Web du serveur Edge hérité.

La valeur de **port externe de conférence Web externe** de **443** est le port SIP (Session Initiation Protocol) par défaut configuré pour les clients de conférence. Si la valeur par défaut n’a pas été utilisée, mettez à jour la valeur **port externe de conférence Web externe** .

Activez la case à cocher **ce pool Edge est utilisé pour la connectivité de Fédération et de messagerie instantanée publique** si vous prévoyez d’utiliser ce serveur Edge pour la Fédération. Si vous avez déployé plusieurs serveurs Edge, seul l’un d’eux sera activé pour la Fédération. Si vous n’activez pas cette case à cocher et que vous décidez par la suite d’activer la Fédération, vous devez exécuter de nouveau l’Assistant Fusion du générateur de topologie, et publier votre topologie. Pour plus d’informations, voir [phase 4 : fusionner des topologies](https://technet.microsoft.com/library/81eb5bb2-1fd7-4611-a2aa-eb2393c8abc9.aspx).


