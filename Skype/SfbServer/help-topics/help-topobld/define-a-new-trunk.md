---
title: Définir une nouvelle jonction
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddTrunkPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e5d97b27-5ae8-41e0-8ee9-0c3f6d5dd123
description: 'Vous définissez une nouvelle jonction (SIP) en fournissant les informations suivantes :'
ms.openlocfilehash: 1b58da8880c65b0beecbd2756d0b5a5028f45e19
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095588"
---
# <a name="define-a-new-trunk"></a>Définir une nouvelle jonction

Vous définissez une nouvelle jonction (SIP) en fournissant les informations suivantes :

- **Nom de la jonction** : nom unique dans votre topologie qui identifiera cette jonction

- **Passerelle PSTN associée** : sélectionnez dans la liste une passerelle PSTN déployée et configurée dans votre déploiement

- **Port d’écoute pour la passerelle IP/PSTN** : port que le système IP-PBX ou la passerelle PSTN écoutera. Doit être différent de tous les autres ports d’écoute de jonction configurés dans votre déploiement

- **Protocole de transport SIP** : sélectionnez dans la liste soit TCP, soit TLS

- **Serveur de médiation associé**: sélectionnez dans la liste un serveur de médiation qui est déployé et configuré dans votre déploiement

- **Port du serveur** de médiation associé : définissez la valeur de port sur la valeur du port TCP ou TLS du serveur de médiation que cette trunk SIP utilisera

## <a name="see-also"></a>Voir aussi

[M:N trunk in Skype for Business Server 2015](../../plan-your-deployment/enterprise-voice-solution/m-n-trunk.md)

[Comment implémenter une trunking SIP ?](/previous-versions/office/lync-server-2013/lync-server-2013-how-do-i-implement-sip-trunking)