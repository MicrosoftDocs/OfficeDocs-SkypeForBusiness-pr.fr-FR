---
title: Définir une nouvelle jonction
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddTrunkPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e5d97b27-5ae8-41e0-8ee9-0c3f6d5dd123
description: 'Vous définissez une configuration de jonction nouvelle session initiation protocol (SIP) en fournissant les informations suivantes :'
ms.openlocfilehash: adb96085949a353443cf74031feee78500d7d4d7
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32226941"
---
# <a name="define-a-new-trunk"></a>Définir une nouvelle jonction

Vous définissez une configuration de jonction nouvelle session initiation protocol (SIP) en fournissant les informations suivantes :

- **Nom de la jonction**: nom unique dans votre topologie qui identifiera cette jonction

- **Passerelle de PSTN associée**: sélectionnez une passerelle PSTN déployée et configurée dans votre déploiement à partir de la liste

- **Port d’écoute pour la passerelle IP/PSTN**: port d’écoute sur la passerelle IP-PBX ou PSTN. Doit être unique à partir de tous les autres ports d’écoute jonction configurés dans votre déploiement

- **Protocole de Transport SIP**: sélectionnez dans la liste TCP ou TLS

- **Serveur de médiation associé**: sélectionnez dans la liste d’un serveur de médiation qui est déployé et configuré dans votre déploiement

- **Port du serveur de médiation associé**: définissez la valeur de port égale à la valeur du port TCP ou TLS du serveur de médiation cette jonction SIP utilisera

## <a name="see-also"></a>Voir aussi

[Jonction M:N dans Skype Entreprise Server 2015](../../plan-your-deployment/enterprise-voice-solution/m-n-trunk.md)

[Comment implémenter la jonction SIP ?](https://technet.microsoft.com/library/273a22b1-8a4c-4187-acf8-c57d5c6598ce.aspx)
