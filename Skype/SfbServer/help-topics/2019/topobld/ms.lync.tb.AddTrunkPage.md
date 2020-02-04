---
title: Définir une nouvelle jonction
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddTrunkPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e5d97b27-5ae8-41e0-8ee9-0c3f6d5dd123
ROBOTS: NOINDEX, NOFOLLOW
description: 'Pour définir un nouveau Trunk SIP (Session Initiation Protocol), vous devez fournir les informations suivantes :'
ms.openlocfilehash: e6036942423e7d4f88050fead56e2a1336530cab
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41689043"
---
# <a name="define-a-new-trunk"></a>Définir une nouvelle jonction

Pour définir un nouveau Trunk SIP (Session Initiation Protocol), vous devez fournir les informations suivantes :

- **Nom du Trunk**: nom unique dans votre topologie qui identifie ce Trunk

- **Passerelle RTC associée**: sélectionnez une passerelle PSTN déployée et configurée dans votre déploiement à partir de la liste.

- **Port d’écoute pour la passerelle IP/PSTN**: port sur lequel le PBX IP ou la passerelle RTC écoutera. Doit être unique à partir de tous les autres ports d’écoute de Trunk configurés dans votre déploiement

- **Protocole de transport SIP**: effectuez une sélection dans la liste TCP ou TLS

- **Serveur de médiation associé**: sélectionnez dans la liste un serveur de médiation déployé et configuré dans votre déploiement.

- **Port du serveur de médiation associé**: définissez la valeur de port égale à la valeur de port TCP ou TLS du serveur de médiation que ce Trunk SIP utilisera.

## <a name="see-also"></a>Voir aussi

[M :N Trunk dans Skype entreprise Server](../../../plan-your-deployment/enterprise-voice-solution/m-n-trunk.md)

[Comment implémenter le trunking SIP ?](https://technet.microsoft.com/library/273a22b1-8a4c-4187-acf8-c57d5c6598ce.aspx)
