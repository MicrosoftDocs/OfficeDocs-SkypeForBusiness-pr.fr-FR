---
title: Expanseur des paramètres de la jonction
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.TrunkSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3d00e8f4-e599-4094-a4a1-34fd6e8a5580
description: 'Pour modifier les paramètres d’une jonction SIP, procédez comme suit :'
ms.openlocfilehash: 13ea9abfb6d53b57333c2c96b8a2f8adde963ebf
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="trunk-settings-expander"></a>Expanseur des paramètres de la jonction
 
Pour modifier les paramètres d’une jonction SIP, procédez comme suit :
  
 **Nom de la jonction** : entrée requise, qui identifie de manière unique la jonction SIP dans le déploiement.
  
 **Passerelle RTC associée** : sélectionnez une passerelle RTC existante définie dans le déploiement.
  
 **Port d’écoute pour la passerelle IP/RTC** : indique le port TCP/IP de la passerelle sur lequel les requêtes seront écoutées. La valeur obligatoire peut différer en fonction du fournisseur de la passerelle, mais le port par défaut est le port 5067.
  
 **Protocole de transport SIP** : le protocole utilisé est le protocole TCP ou le protocole TLS. Le protocole TLS est le protocole par défaut. Pour connaître la prise en charge de la passerelle, reportez-vous à la documentation du fournisseur de la passerelle. Le protocole par défaut, le protocole TLS, est un choix plus sécurisé si la passerelle le prend en charge.
  
 **Associé à un serveur de médiation**: sélectionnez un serveur de médiation existant dans le déploiement à associer à la jonction SIP.
  
> [!NOTE]
> Uniquement le tronc racine peut être associé à un Microsoft Lync Server 2010 ou un serveur de médiation de Lync Server 2013. 
  
 **Port de serveur de médiation associé**: une valeur requise, il est défini à la valeur configurée pour le serveur de médiation écoutent.
  
![Expanseur des paramètres de la jonction](../../media/Trunk_Settings_Expander.jpg)
  
## <a name="see-also"></a>Voir aussi

#### 

[Liste de vérification de déploiement SIP Trunking](http://technet.microsoft.com/library/94f4f03e-19d5-4198-92be-e4076dbb959a.aspx)
  
[Les composants et les Topologies pour SIP Trunking](http://technet.microsoft.com/library/8ed9a9d0-517e-4f36-a131-22cdafa257fa.aspx)

