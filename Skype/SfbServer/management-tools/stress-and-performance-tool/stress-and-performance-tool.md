---
title: Skype Entreprise Server 2015 Stress and Performance Tool
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
ms.date: 4/6/2016
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: f2f7d19b-18c8-4a41-9b17-80d35b73d742
description: L Skype Entreprise Server 2015 Stress and Performance Tool est utilisé lors de la planification de la capacité et de l’optimisation des performances dans les environnements de non-production ou de test.
ms.openlocfilehash: 565f868ae81915b6bcb595f13c2d184d82db62b8
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60766262"
---
# <a name="skype-for-business-server-2015-stress-and-performance-tool"></a>Skype Entreprise Server 2015 Stress and Performance Tool
 
L Skype Entreprise Server 2015 Stress and Performance Tool est utilisé lors de la planification de la capacité et de l’optimisation des performances dans les environnements de non-production ou de test.
  
L Skype Entreprise Server 2015 Stress and Performance Tool inclut des outils qui simplifieront votre planification de la capacité pour Skype Entreprise Server 2015. L Skype Entreprise Server 2015 Stress and Performance Tool vous aidera à :
  
- Simplifier la planification de votre matériel pour Skype Entreprise Server
    
- Donnez-vous des connaissances et des meilleures pratiques pour l’optimisation des performances
    
- Mesurer les performances de vos déploiements Skype Entreprise Server déploiements
    
En règle générale, vous utilisez cet outil après avoir utilisé l’outil de planification [Skype Entreprise Server 2015](../../management-tools/planning-tool/planning-tool.md) pour concevoir la topologie et affiner la topologie avec la calculatrice de planification de capacité [Skype Entreprise Server 2015.](../../management-tools/capacity-planning-calculator.md) 

> [!NOTE]
> Cet outil ne sera pas mis à jour Skype Entreprise Server 2019.
  
## <a name="tests"></a>Tests

L’outil Stress and Performance peut simuler ces types de charge utilisateur :
  
|&nbsp;|&nbsp;|
|:-----|:-----|
|Messagerie instantanée et présence   |Audioconférence   |
|Partage d'application   |Voix sur IP (VoIP), y compris la simulation de réseau téléphonique commuté (PTSN)   |
|Conférence client Web Access   |Attendant automatique de conférence   |
|Groupes Response Group   |Développement de listes de distribution   |
|Téléchargement du carnet d’adresses et requête de carnet d’adresses   |Appels enhanced 911 (E911) et profil d’emplacement (plan de numérotation)   |
|MultiView   |Collaboration de données   |
|Mobilité   ||
   
## <a name="applications-and-files-included-with-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Applications et fichiers inclus dans l Skype Entreprise Server 2015 Stress and Performance Tool

Ces applications font partie de l’outil Skype Entreprise Server stress and performance :
  
|Outil|Description|
|:-----|:-----|
|UserProvisioningTool.exe   |Cet outil est utilisé pour créer des utilisateurs et des contacts.   |
|UserProfileGenerator.exe   |Permet de configurer les caractéristiques de la charge utilisateur que vous simulez.   |
|LyncPerfTool.exe   |Outil qui simule la charge utilisateur.   |
|Default.tmx   |Requis pour utiliser l’outil Skype Entreprise Server journalisation 2015.   |
|Exemples de script d’approvisionnement   |Permet de configurer la topologie pour l’exécution de tests de charge, en fonction de scénarios spécifiques. Vous devrez probablement les modifier pour les rendre pertinentes pour votre environnement particulier.   |
   
## <a name="topics-in-this-section"></a>Rubriques de cette section

Pour en savoir plus, vous devez consulter les articles suivants :
  
- [Conditions préalables et configuration de la Skype de l’outil Stress and Performance de Busines](prerequisites-and-setup.md)
    
- [Scénarios de performances pour l Skype Entreprise Server 2015 Stress and Performance Tool](scenarios.md)
    
  - [Mise en service de la topologie pour exécuter la charge dans les scénarios de contrainte et de performances](provisioning-the-topology-to-run-load.md)
    
  - [Configuration des stratégies pour Skype Entreprise Server 2015 Stress and Performance Tool](configuring-policies.md)
    
- [Utilisation de l Skype Entreprise Server 2015 Stress and Performance Tool](using-the-tool.md)
    
- [FAQ sur l’outil Skype Entreprise Server stress and performance 2015](faq.md)
    

