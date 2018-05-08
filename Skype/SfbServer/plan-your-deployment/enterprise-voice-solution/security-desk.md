---
title: Intégration du service de sécurité dans Skype Entreprise Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
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
ms.openlocfilehash: adaa1096651c5e3f86d15af1b2409a8de03e6c9c
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="include-the-security-desk-in-skype-for-business-server-2015"></a>Intégration du service de sécurité dans Skype Entreprise Server 2015
 
Planifiez la façon d’inclure le bureau de sécurité de votre organisation dans un déploiement E9-1-1, dans Skype pour Business Server Enterprise Voice.
  
Votre entreprise est susceptible de demander au service de sécurité de prendre part au traitement d’un appel d’urgence. Pour vous aider à décider comment intégrer le service de sécurité dans votre déploiement E9-1-1, répondez aux questions suivantes.
  
**Souhaitez-vous que le service de sécurité soit averti en cas d’appel d’urgence ?**
  
Vous pouvez configurer la stratégie d’emplacement afin que Skype pour Business Server envoie des alertes par messagerie instantanée (IM) à la Skype pour les adresses SIP Business du personnel de sécurité un ou plusieurs. Ces alertes contiennent le nom, le nombre et l’emplacement de la personne à l’appel d’urgence et facilitent le personnel de sécurité en aidant à la situation d’urgence.
    
**Souhaitez-vous établir une conférence avec le service de sécurité pour chaque appel d’urgence ?**
  
Si elle est prise en charge par le fournisseur de services d’urgence, vous pouvez configurer la stratégie d’emplacement pour inclure un numéro de rappel à chaque appel d’urgence. Ce numéro est alors utilisé par le fournisseur pour établir une conférence avec le personnel de sécurité de votre organisation pour les appels d’urgence. Cette conférence peut être configurée dans la stratégie d’emplacement en mode unidirectionnel (écoute uniquement) ou bidirectionnel.
    
> [!NOTE]
> Si nécessaire, vous pouvez définir des membres du personnel différents pour chaque stratégie d’emplacement. Vous pouvez ainsi personnaliser la réponse en fonction des différents secteurs de votre entreprise ou créer un comportement spécifique pour les appels d’urgence passés dans le réseau et non en dehors du réseau. Vous pouvez utiliser des groupes de distribution pour spécifier le personnel à avertir. 
  

