---
title: Définir une nouvelle jonction
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.openlocfilehash: 4addcfbdb854de223f7942f55e2e2180136f9bbc
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218555"
---
# <a name="define-a-new-trunk"></a>Définir une nouvelle jonction

Vous définissez une nouvelle jonction (SIP) en fournissant les informations suivantes :

- **Nom de la jonction** : nom unique dans votre topologie qui identifiera cette jonction

- **Passerelle PSTN associée** : sélectionnez dans la liste une passerelle PSTN déployée et configurée dans votre déploiement

- **Port d’écoute pour la passerelle IP/PSTN** : port que le système IP-PBX ou la passerelle PSTN écoutera. Doit être différent de tous les autres ports d’écoute de jonction configurés dans votre déploiement

- **Protocole de transport SIP** : sélectionnez dans la liste soit TCP, soit TLS

- **Serveur de médiation associé**: sélectionnez dans la liste un serveur de médiation déployé et configuré dans votre déploiement

- **Port du serveur de médiation associé**: définissez la valeur de port sur la valeur de port TCP ou TLS du serveur de médiation que cette jonction SIP doit utiliser.

## <a name="see-also"></a>Voir aussi

[Jonction M :N dans Skype entreprise Server 2015](../../plan-your-deployment/enterprise-voice-solution/m-n-trunk.md)

[Comment implémenter la jonction SIP ?](https://technet.microsoft.com/library/273a22b1-8a4c-4187-acf8-c57d5c6598ce.aspx)
