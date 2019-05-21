---
title: Inclure le centre de sécurité dans Skype entreprise Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4b1d9125-7488-419b-85dd-a8dd3ab5add3
description: Planification de l’inclusion du centre de sécurité de votre organisation dans un déploiement E9-1-1 dans Skype entreprise Server Voice.
ms.openlocfilehash: 7be3533879f36c897d148194345e1496945359b6
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34276453"
---
# <a name="include-the-security-desk-in-skype-for-business-server"></a>Inclure le centre de sécurité dans Skype entreprise Server
 
Planification de l’inclusion du centre de sécurité de votre organisation dans un déploiement E9-1-1 dans Skype entreprise Server Voice.
  
Votre entreprise est susceptible de demander au service de sécurité de prendre part au traitement d’un appel d’urgence. Pour vous aider à décider comment intégrer le service de sécurité dans votre déploiement E9-1-1, répondez aux questions suivantes.
  
**Souhaitez-vous que le service de sécurité soit averti en cas d’appel d’urgence ?**
  
Vous pouvez configurer la stratégie d’emplacement de sorte que Skype entreprise Server envoie des alertes de messagerie instantanée aux adresses SIP de Skype entreprise d’un ou plusieurs membres du personnel de sécurité. Ces alertes contiennent le nom, le numéro et l’emplacement de la personne qui met l’appel d’urgence, et facilitent le personnel de sécurité en aidant à la situation d’urgence.
    
**Souhaitez-vous établir une conférence avec le service de sécurité pour chaque appel d’urgence ?**
  
Si elle est prise en charge par le fournisseur de services d’urgence, vous pouvez configurer la stratégie d’emplacement pour inclure un numéro de rappel à chaque appel d’urgence. Ce numéro est alors utilisé par le fournisseur pour établir une conférence avec le personnel de sécurité de votre organisation pour les appels d’urgence. Cette conférence peut être configurée dans la stratégie d’emplacement en mode unidirectionnel (écoute uniquement) ou bidirectionnel.
    
> [!NOTE]
> Si nécessaire, vous pouvez définir des membres du personnel différents pour chaque stratégie d’emplacement. Vous pouvez ainsi personnaliser la réponse en fonction des différents secteurs de votre entreprise ou créer un comportement spécifique pour les appels d’urgence passés dans le réseau et non en dehors du réseau. Vous pouvez utiliser des groupes de distribution pour spécifier le personnel à avertir. 
  

