---
title: Inclure le service de sécurité dans Skype pour Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4b1d9125-7488-419b-85dd-a8dd3ab5add3
description: Planifiez la façon d’inclure le bureau de sécurité de votre organisation dans un déploiement E9-1-1, dans Skype pour Business Server Enterprise Voice.
ms.openlocfilehash: 9363956a9b0f1cc598224b9d573677ff424c9e23
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20989563"
---
# <a name="include-the-security-desk-in-skype-for-business-server"></a>Inclure le service de sécurité dans Skype pour Business Server
 
Planifiez la façon d’inclure le bureau de sécurité de votre organisation dans un déploiement E9-1-1, dans Skype pour Business Server Enterprise Voice.
  
Votre entreprise est susceptible de demander au service de sécurité de prendre part au traitement d’un appel d’urgence. Pour vous aider à décider comment intégrer le service de sécurité dans votre déploiement E9-1-1, répondez aux questions suivantes.
  
**Souhaitez-vous que le service de sécurité soit averti en cas d’appel d’urgence ?**
  
Vous pouvez configurer la stratégie d’emplacement afin que Skype pour Business Server envoie des alertes par messagerie instantanée (IM) à la Skype pour les adresses SIP Business du personnel de sécurité un ou plusieurs. Ces alertes contiennent le nom, le nombre et l’emplacement de la personne à l’appel d’urgence et facilitent le personnel de sécurité en aidant à la situation d’urgence.
    
**Souhaitez-vous établir une conférence avec le service de sécurité pour chaque appel d’urgence ?**
  
Si elle est prise en charge par le fournisseur de services d’urgence, vous pouvez configurer la stratégie d’emplacement pour inclure un numéro de rappel à chaque appel d’urgence. Ce numéro est alors utilisé par le fournisseur pour établir une conférence avec le personnel de sécurité de votre organisation pour les appels d’urgence. Cette conférence peut être configurée dans la stratégie d’emplacement en mode unidirectionnel (écoute uniquement) ou bidirectionnel.
    
> [!NOTE]
> Si nécessaire, vous pouvez définir des membres du personnel différents pour chaque stratégie d’emplacement. Vous pouvez ainsi personnaliser la réponse en fonction des différents secteurs de votre entreprise ou créer un comportement spécifique pour les appels d’urgence passés dans le réseau et non en dehors du réseau. Vous pouvez utiliser des groupes de distribution pour spécifier le personnel à avertir. 
  

