---
title: Inclure le service de sécurité dans Skype Entreprise Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4b1d9125-7488-419b-85dd-a8dd3ab5add3
description: Planification de l’utilisation du service de sécurité de votre organisation dans un déploiement E9-1-1, Skype Entreprise Server Voix Entreprise.
ms.openlocfilehash: c99bdcbfaaaa74a5050c833dca3fd9a046ca41e5
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58615600"
---
# <a name="include-the-security-desk-in-skype-for-business-server"></a>Inclure le service de sécurité dans Skype Entreprise Server
 
Planification de l’utilisation du service de sécurité de votre organisation dans un déploiement E9-1-1, Skype Entreprise Server Voix Entreprise.
  
Votre entreprise est susceptible de demander au service de sécurité de prendre part au traitement d’un appel d’urgence. Pour vous aider à décider comment intégrer le service de sécurité dans votre déploiement E9-1-1, répondez aux questions suivantes.
  
**Souhaitez-vous que le service de sécurité soit averti en cas d’appel d’urgence ?**
  
Vous pouvez configurer la stratégie d’emplacement de sorte qu’Skype Entreprise Server envoie des alertes de messagerie instantanée aux adresses SIP Skype Entreprise d’un ou plusieurs membres du personnel de sécurité. Ces alertes contiennent le nom, le numéro et l’emplacement de la personne qui passe l’appel d’urgence et facilitent l’assistance du personnel de sécurité en cas d’urgence.
    
**Souhaitez-vous établir une conférence avec le service de sécurité pour chaque appel d’urgence ?**
  
Si elle est prise en charge par le fournisseur de services d’urgence, vous pouvez configurer la stratégie d’emplacement pour inclure un numéro de rappel à chaque appel d’urgence. Ce numéro est alors utilisé par le fournisseur pour établir une conférence avec le personnel de sécurité de votre organisation pour les appels d’urgence. Cette conférence peut être configurée dans la stratégie d’emplacement en mode unidirectionnel (écoute uniquement) ou bidirectionnel.
    
> [!NOTE]
> Si nécessaire, vous pouvez définir des membres du personnel différents pour chaque stratégie d’emplacement. Vous pouvez ainsi personnaliser la réponse en fonction des différents secteurs de votre entreprise ou créer un comportement spécifique pour les appels d’urgence passés dans le réseau et non en dehors du réseau. Vous pouvez utiliser des groupes de distribution pour spécifier le personnel à avertir. 
  

