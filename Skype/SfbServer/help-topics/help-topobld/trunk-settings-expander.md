---
title: Expanseur des paramètres de la jonction
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.TrunkSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3d00e8f4-e599-4094-a4a1-34fd6e8a5580
description: 'Pour modifier les paramètres d’une jonction SIP, procédez comme suit :'
ms.openlocfilehash: 5b6c0384e2297f8bfd93ea493416fc7eea271033
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34282216"
---
# <a name="trunk-settings-expander"></a>Expanseur des paramètres de la jonction

Pour modifier les paramètres d’une jonction SIP, procédez comme suit :

 **Nom de la jonction** : entrée requise, qui identifie de manière unique la jonction SIP dans le déploiement.

 **Passerelle RTC associée** : sélectionnez une passerelle RTC existante définie dans le déploiement.

 **Port d’écoute pour la passerelle IP/RTC** : indique le port TCP/IP de la passerelle sur lequel les requêtes seront écoutées. La valeur obligatoire peut différer en fonction du fournisseur de la passerelle, mais le port par défaut est le port 5067.

 **Protocole de transport SIP** : le protocole utilisé est le protocole TCP ou le protocole TLS. Le protocole TLS est le protocole par défaut. Pour connaître la prise en charge de la passerelle, reportez-vous à la documentation du fournisseur de la passerelle. Le protocole par défaut, le protocole TLS, est un choix plus sécurisé si la passerelle le prend en charge.

 **Serveur de médiation associé**: sélectionnez un serveur de médiation existant du déploiement à associer à la ligne SIP.

> [!NOTE]
> Seule l’agrégation racine peut être associée à un serveur de médiation Lync Server 2010 ou Lync Server 2013.

 **Port du serveur de médiation associé**: une valeur requise, qui est définie sur la valeur sur laquelle le serveur de médiation est configuré pour l’écoute.

![Expanseur des paramètres de la jonction](../../media/Trunk_Settings_Expander.jpg)

## <a name="see-also"></a>Voir aussi

[Liste de vérification du déploiement SIP](https://technet.microsoft.com/library/94f4f03e-19d5-4198-92be-e4076dbb959a.aspx)

[Composants et topologies pour le trunking SIP](https://technet.microsoft.com/library/8ed9a9d0-517e-4f36-a131-22cdafa257fa.aspx)
