---
title: Expanseur des paramètres de la jonction
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.TrunkSettingsExpander
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 3d00e8f4-e599-4094-a4a1-34fd6e8a5580
description: 'Pour modifier les paramètres d’une jonction SIP, procédez comme suit :'
ms.openlocfilehash: ce5b7a82dbba580c96894cfdf51b4ca66dba7cbe
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60847467"
---
# <a name="trunk-settings-expander"></a>Expandeur des paramètres de la jonction

Pour modifier les paramètres d’une jonction SIP, procédez comme suit :

 **Nom de la jonction** est une entrée requise et qui identifie de manière unique la jonction SIP dans le déploiement.

 **Passerelle PSTN associée** : sélectionnez une passerelle PSTN existante qui a été définie dans le déploiement.

 **Port d’écoute pour la passerelle IP/PSTN** : indique que le port TCP/IP de la passerelle écoutera les requêtes. Il se peut que la valeur requise diffère, en fonction du fournisseur de la passerelle, mais le port par défaut est 5067.

 **Protocole de transport SIP** : le protocole utilisé est soit TCP, soit TLS. TLS est le protocole par défaut. Consultez la documentation du fournisseur de la passerelle pour connaître la prise en charge de la passerelle. TLS, protocole par défaut, représente un choix plus sécurisé si la passerelle le prend en charge.

 **Serveur de médiation associé**: sélectionnez un serveur de médiation existant dans le déploiement à associer à la ligne SIP.

> [!NOTE]
> Seule la troncation racine peut être associée à un serveur de médiation Lync Server 2010 ou Lync Server 2013.

 **Port du serveur de** médiation associé : valeur requise, définie sur la valeur que le serveur de médiation est configuré pour écouter.

![Trunk Paramètres Expander.](../../media/Trunk_Settings_Expander.jpg)

## <a name="see-also"></a>Voir aussi

[Liste de vérification du déploiement de la trunking SIP](/previous-versions/office/lync-server-2013/lync-server-2013-sip-trunk-deployment-checklist)

[Composants et topologies pour la jonction SIP](/previous-versions/office/lync-server-2013/lync-server-2013-components-and-topologies-for-sip-trunking)