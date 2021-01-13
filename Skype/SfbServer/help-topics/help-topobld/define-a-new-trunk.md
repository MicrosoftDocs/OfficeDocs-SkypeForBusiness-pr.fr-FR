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
ms.openlocfilehash: bbed07920bdeddb78217e435e8813c89231cdcc9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833044"
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

[Comment implémenter une trunking SIP ?](https://technet.microsoft.com/library/273a22b1-8a4c-4187-acf8-c57d5c6598ce.aspx)
