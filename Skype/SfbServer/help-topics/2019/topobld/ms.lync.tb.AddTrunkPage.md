---
title: Définir une nouvelle jonction
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddTrunkPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e5d97b27-5ae8-41e0-8ee9-0c3f6d5dd123
ROBOTS: NOINDEX, NOFOLLOW
description: 'Pour définir un nouveau Trunk SIP (Session Initiation Protocol), vous devez fournir les informations suivantes:'
ms.openlocfilehash: c6586f9da069c3a3fc149b086562592db113b31e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34282479"
---
# <a name="define-a-new-trunk"></a>Définir une nouvelle jonction

Pour définir un nouveau Trunk SIP (Session Initiation Protocol), vous devez fournir les informations suivantes:

- **Nom du Trunk**: nom unique dans votre topologie qui identifie ce Trunk

- **Passerelle RTC associée**: sélectionnez une passerelle PSTN déployée et configurée dans votre déploiement à partir de la liste.

- **Port d’écoute pour la passerelle IP/PSTN**: port sur lequel le PBX IP ou la passerelle RTC écoutera. Doit être unique à partir de tous les autres ports d’écoute de Trunk configurés dans votre déploiement

- **Protocole de transport SIP**: effectuez une sélection dans la liste TCP ou TLS

- **Serveur de médiation associé**: sélectionnez dans la liste un serveur de médiation déployé et configuré dans votre déploiement.

- **Port du serveur de médiation associé**: définissez la valeur de port égale à la valeur de port TCP ou TLS du serveur de médiation que ce Trunk SIP utilisera.

## <a name="see-also"></a>Voir aussi

[M:N Trunk dans Skype entreprise Server](../../../plan-your-deployment/enterprise-voice-solution/m-n-trunk.md)

[Comment implémenter le trunking SIP?](https://technet.microsoft.com/library/273a22b1-8a4c-4187-acf8-c57d5c6598ce.aspx)
