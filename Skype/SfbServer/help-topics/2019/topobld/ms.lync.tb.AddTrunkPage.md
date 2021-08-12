---
title: Définir une nouvelle jonction
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddTrunkPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e5d97b27-5ae8-41e0-8ee9-0c3f6d5dd123
ROBOTS: NOINDEX, NOFOLLOW
description: 'Vous définissez une nouvelle jonction (SIP) en fournissant les informations suivantes :'
ms.openlocfilehash: 49411ca6416a99d30d7a889aca0151f3ef89b9f7a8b7e559c39366c585144378
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54295421"
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

[M:N trunk in Skype Entreprise Server](../../../plan-your-deployment/enterprise-voice-solution/m-n-trunk.md)

[Comment implémenter une trunking SIP ?](/previous-versions/office/lync-server-2013/lync-server-2013-how-do-i-implement-sip-trunking)