---
title: Planification du mode partage de lignes dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/21/2016
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 6356aad4-700d-495c-8fc8-58eb1d4f6f18
description: Pour plus d’informations sur la planification de l’apparence des lignes partagées (SLA) dans Skype entreprise Server 2015, la mise à jour cumulative 2015 de novembre, reportez-vous à cette rubrique.
ms.openlocfilehash: 14f0f6cbd163ecff42543d3ad57bed0020434cfb
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802434"
---
# <a name="plan-for-shared-line-appearance-in-skype-for-business-server-2015"></a>Planification du mode partage de lignes dans Skype Entreprise Server 2015
 
Pour plus d’informations sur la planification de l’apparence des lignes partagées (SLA) dans Skype entreprise Server 2015, la mise à jour cumulative 2015 de novembre, reportez-vous à cette rubrique. 
  
L’apparence des lignes partagées est une fonctionnalité de Skype entreprise permettant de gérer plusieurs appels sur un numéro particulier appelé numéro partagé. SLA peut configurer n’importe quel utilisateur Skype entreprise doté d’un numéro de téléphone partagé sur plusieurs lignes pour répondre à des appels multiples. Les appels ne sont pas reçus réellement sur le numéro partagé, mais ils sont transférés vers les utilisateurs qui agissent en tant que délégués pour le numéro partagé. Les délégués peuvent prendre l’appel, tandis que les autres reçoivent une notification sur leur téléphone indiquant le nom de la personne qui a pris l’appel et la ligne qui est occupée. Le nombre de lignes et le nombre de délégués sont configurables pour un numéro partagé en mode partage de lignes. De plus, les options avancées, comme BusyOption (ce qui est le cas lorsque toutes les lignes sont occupées) et MissedCallOption (ce qui est le cas lorsqu’aucun des délégués ne prend d’appel), peuvent également être configurées pour un numéro partagé.
  
Le SLA est uniquement pris en charge sur les appareils mobiles suivants (il n’est pas pris en charge pour les clients Skype entreprise sur des ordinateurs, des téléphones mobiles ou d’autres appareils) : 
  
- Polycom VVX300 avec mise à jour du microprogramme 5.4.1
    
- Polycom VVX400 avec mise à jour du microprogramme 5.4.1
    
- Polycom VVX500 avec mise à jour du microprogramme 5.4.1
    
- Polycom VVX600 avec mise à jour du microprogramme 5.4.1
    
SLA est une nouvelle fonctionnalité de Skype entreprise Server, la mise à jour cumulative 2015 de novembre. 
  
Pour plus d’informations sur le déploiement du mode partage de lignes, reportez-vous à la rubrique [Deploy Shared Line Appearance in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/deploy-shared-line-appearance.md).
  
## <a name="feature-list"></a>Liste des fonctionnalités

La configuration d’un groupe de mode partage de lignes permet les actions suivantes :
  
- Tous les délégués du groupe peuvent répondre aux appels entrants vers le même numéro partagé. Ces appels peuvent être basés sur RTC ou le protocole SIP.
    
- Les délégués peuvent mettre en attente des appels ou les prendre.
    
- Les délégués peuvent transférer des appels vers un numéro extérieur au groupe de mode partage de lignes.
    
- Les délégués peuvent voir le nombre d’appels actuels sur le numéro partagé et afficher le statut de chacun de ces appels.
    
- Vous pouvez configurer un nombre maximal d’appels simultanés pour le numéro partagé. Vous pouvez également définir comment traiter les nouveaux appels une fois cette limite atteinte. Les appels hors limite peuvent être rejetés avec une tonalité Occupé, transférés vers un autre numéro ou transférés vers la messagerie vocale.
    
- Vous pouvez définir comment traiter les appels manqués (appels non pris après un certain temps). Si vous activez la messagerie vocale pour le groupe, les appels manqués sont redirigés automatiquement vers la messagerie vocale. Si vous n’avez pas activé la messagerie vocale pour le groupe (numéro partagé), vous pouvez décider de rejeter les appels manqués avec une tonalité Occupé, de les transférer vers un autre numéro ou de les déconnecter.
    

