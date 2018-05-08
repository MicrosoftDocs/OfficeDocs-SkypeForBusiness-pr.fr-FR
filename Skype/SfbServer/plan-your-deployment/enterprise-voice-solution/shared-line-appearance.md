---
title: Planification du mode partage de lignes dans Skype Entreprise Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/21/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6356aad4-700d-495c-8fc8-58eb1d4f6f18
description: Lisez cette rubrique pour savoir comment planifier pour Shared ligne apparence (SLA) dans Skype novembre 2015 Business Server 2015, mise à jour Cumulative.
ms.openlocfilehash: 3aa5f00294303ce38d74ddc2b959ff3c4956c135
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="plan-for-shared-line-appearance-in-skype-for-business-server-2015"></a>Planification du mode partage de lignes dans Skype Entreprise Server 2015
 
Lisez cette rubrique pour savoir comment planifier pour Shared ligne apparence (SLA) dans Skype novembre 2015 Business Server 2015, mise à jour Cumulative. 
  
Apparence de la ligne partagé est une fonctionnalité de Skype pour les entreprises pour gérer plusieurs appels sur un nombre spécifique appelé un numéro partagé. SLA peut configurer n’importe quel enterprise voice activé Skype pour utilisateur d’entreprise comme un nombre partagé avec plusieurs lignes pour répondre à plusieurs appels. Les appels ne sont pas reçus réellement sur le numéro partagé, mais ils sont transférés vers les utilisateurs qui agissent en tant que délégués pour le numéro partagé. Les délégués peuvent prendre l’appel, tandis que les autres reçoivent une notification sur leur téléphone indiquant le nom de la personne qui a pris l’appel et la ligne qui est occupée. Le nombre de lignes et le nombre de délégués sont configurables pour un numéro partagé en mode partage de lignes. De plus, les options avancées, comme BusyOption (ce qui est le cas lorsque toutes les lignes sont occupées) et MissedCallOption (ce qui est le cas lorsqu’aucun des délégués ne prend d’appel), peuvent également être configurées pour un numéro partagé.
  
SLA est pris en charge uniquement sur les appareils de téléphone suivants (il n'est pas pris en charge pour Skype pour les clients d’entreprise sur les ordinateurs, les téléphones mobiles ou les autres périphériques) : 
  
- Polycom VVX300 avec mise à jour du microprogramme 5.4.1
    
- Polycom VVX400 avec mise à jour du microprogramme 5.4.1
    
- Polycom VVX500 avec mise à jour du microprogramme 5.4.1
    
- Polycom VVX600 avec mise à jour du microprogramme 5.4.1
    
SLA est une nouvelle fonctionnalité dans Skype pour Business Server, novembre 2015 mise à jour Cumulative. 
  
Pour plus d’informations sur le déploiement de SLA, voir [Déployer Shared apparence de la ligne dans Skype pour Business Server 2015](../../deploy/deploy-enterprise-voice/deploy-shared-line-appearance.md).
  
## <a name="feature-list"></a>Liste des fonctionnalités

La configuration d’un groupe de mode partage de lignes permet les actions suivantes :
  
- Tous les délégués du groupe peuvent répondre aux appels entrants vers le même numéro partagé. Ces appels peuvent être basés sur RTC ou le protocole SIP.
    
- Les délégués peuvent mettre en attente des appels ou les prendre.
    
- Les délégués peuvent transférer des appels vers un numéro extérieur au groupe de mode partage de lignes.
    
- Les délégués peuvent voir le nombre d’appels actuels sur le numéro partagé et afficher le statut de chacun de ces appels.
    
- Vous pouvez configurer un nombre maximal d’appels simultanés pour le numéro partagé. Vous pouvez également définir comment traiter les nouveaux appels une fois cette limite atteinte. Les appels hors limite peuvent être rejetés avec une tonalité Occupé, transférés vers un autre numéro ou transférés vers la messagerie vocale.
    
- Vous pouvez définir comment traiter les appels manqués (appels non pris après un certain temps). Si vous activez la messagerie vocale pour le groupe, les appels manqués sont redirigés automatiquement vers la messagerie vocale. Si vous n’avez pas activé la messagerie vocale pour le groupe (numéro partagé), vous pouvez décider de rejeter les appels manqués avec une tonalité Occupé, de les transférer vers un autre numéro ou de les déconnecter.
    

