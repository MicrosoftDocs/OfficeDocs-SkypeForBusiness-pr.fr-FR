---
title: Planifier l’apparence des lignes partagées Skype Entreprise Server 2015
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/21/2016
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection:
  - IT_Skype16
  - Strat_SB_Admin
ms.custom: null
ms.assetid: 6356aad4-700d-495c-8fc8-58eb1d4f6f18
description: 'Lisez cette rubrique pour découvrir comment planifier l’apparence des lignes partagées (SLA) dans Skype Entreprise Server 2015, mise à jour cumulative de novembre 2015.'
---

# <a name="plan-for-shared-line-appearance-in-skype-for-business-server-2015"></a>Planifier l’apparence des lignes partagées Skype Entreprise Server 2015
 
Lisez cette rubrique pour découvrir comment planifier l’apparence des lignes partagées (SLA) dans Skype Entreprise Server 2015, mise à jour cumulative de novembre 2015. 
  
L’apparence de ligne partagée est une fonctionnalité Skype Entreprise pour gérer plusieurs appels sur un numéro spécifique appelé numéro partagé. Le SLA peut configurer n’importe quel utilisateur Skype Entreprise voix d’entreprise en tant que numéro partagé avec plusieurs lignes pour répondre à plusieurs appels. Les appels ne sont pas réellement reçus sur le numéro partagé, mais ils sont transmis aux utilisateurs qui agissent en tant que délégués du numéro partagé. N’importe lequel des délégués peut prendre l’appel pendant que le reste des délégués reçoit une notification sur leur téléphone pour savoir qui a pris l’appel et quelle ligne est occupée. Le nombre de lignes et les délégués sont configurables pour un numéro partagé dans le SLA. En outre, les options avancées, telles que BusyOption (ce qui se produit lorsque toutes les lignes sont occupées) et MissedCallOption (le cas où aucun délégué ne prend un appel), peuvent également être configurées pour un numéro partagé.
  
Le SLA est pris en charge uniquement sur les appareils téléphoniques suivants (il n’est pas pris en charge pour les clients Skype Entreprise sur des ordinateurs, des téléphones mobiles ou d’autres appareils) : 
  
- Polycom VVX300 avec mise à jour du microprogramme 5.4.1
    
- Polycom VVX400 avec mise à jour du microprogramme 5.4.1
    
- Polycom VVX500 avec mise à jour du microprogramme 5.4.1
    
- Polycom VVX600 avec mise à jour du microprogramme 5.4.1
    
Le SLA est une nouvelle fonctionnalité de Skype Entreprise Server, mise à jour cumulative de novembre 2015. 
  
Pour plus d’informations sur le déploiement du SLA, voir [Deploy Shared Line Appearance in Skype Entreprise Server 2015](../../deploy/deploy-enterprise-voice/deploy-shared-line-appearance.md).
  
## <a name="feature-list"></a>Liste des fonctionnalités

La configuration d’un groupe de SLA active les paramètres suivants :
  
- Tous les délégués du groupe peuvent répondre aux appels entrants vers le même numéro partagé. Les appels peuvent être basés sur PSTN ou SIP.
    
- Les délégués peuvent conserver et prendre des appels.
    
- Les délégués peuvent transférer des appels vers un numéro en dehors du groupe SLA.
    
- Les délégués peuvent voir le nombre d’appels actuellement sur le numéro partagé et afficher l’état de chacun de ces appels.
    
- Vous pouvez configurer un nombre maximal d’appels simultanés pour le numéro partagé. Vous pouvez également définir la façon dont vous souhaitez que les appels supplémentaires soient gérés une fois ce maximum atteint. Les appels superflus peuvent être rejetés avec une signal occupé, transmis à un autre numéro ou transmis à la messagerie vocale.
    
- Vous pouvez configurer la façon dont vous souhaitez que les appels manqués (appels non pris après un certain temps) soient gérés. Si vous activez la messagerie vocale pour l’identité du groupe, les appels manqués sont automatiquement envoyés à la messagerie vocale. Si la messagerie vocale n’est pas activée pour l’identité du groupe (numéro partagé), vous pouvez choisir de rejeter les appels manqués avec une signal d’occupé, de les envoyer à un autre numéro ou de les déconnecter.
    

