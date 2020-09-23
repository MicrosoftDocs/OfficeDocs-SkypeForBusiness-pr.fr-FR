---
title: Expanseur des paramètres de la jonction
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.TrunkSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3d00e8f4-e599-4094-a4a1-34fd6e8a5580
description: 'Pour modifier les paramètres d’une jonction SIP, procédez comme suit :'
ms.openlocfilehash: 6393ef52859f32ad93d363faf36af3bd34530a9b
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48215935"
---
# <a name="trunk-settings-expander"></a>Expanseur des paramètres de la jonction

Pour modifier les paramètres d’une jonction SIP, procédez comme suit :

 **Nom de la jonction** est une entrée requise et qui identifie de manière unique la jonction SIP dans le déploiement.

 **Passerelle PSTN associée** : sélectionnez une passerelle PSTN existante qui a été définie dans le déploiement.

 **Port d’écoute pour la passerelle IP/PSTN** : indique que le port TCP/IP de la passerelle écoutera les requêtes. Il se peut que la valeur requise diffère, en fonction du fournisseur de la passerelle, mais le port par défaut est 5067.

 **Protocole de transport SIP** : le protocole utilisé est soit TCP, soit TLS. TLS est le protocole par défaut. Consultez la documentation du fournisseur de la passerelle pour connaître la prise en charge de la passerelle. TLS, protocole par défaut, représente un choix plus sécurisé si la passerelle le prend en charge.

 **Serveur de médiation associé**: sélectionnez un serveur de médiation existant dans le déploiement à associer à la jonction SIP.

> [!NOTE]
> Seule la jonction racine peut être associée à un serveur de médiation Lync Server 2010 ou Lync Server 2013.

 **Port du serveur de médiation associé**: valeur requise, définie sur la valeur que le serveur de médiation est configuré pour écouter.

![Expanseur des paramètres de la jonction](../../media/Trunk_Settings_Expander.jpg)

## <a name="see-also"></a>Voir aussi

[Liste de vérification du déploiement de la jonction SIP](https://technet.microsoft.com/library/94f4f03e-19d5-4198-92be-e4076dbb959a.aspx)

[Composants et topologies pour la jonction SIP](https://technet.microsoft.com/library/8ed9a9d0-517e-4f36-a131-22cdafa257fa.aspx)
