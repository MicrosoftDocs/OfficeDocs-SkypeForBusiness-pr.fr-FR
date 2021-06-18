---
title: Outil Stress and Performance de Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
ms.date: 4/6/2016
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f2f7d19b-18c8-4a41-9b17-80d35b73d742
description: L’outil Stress and Performance de Skype Entreprise Server 2015 est utilisé lors de la planification de la capacité et de l’optimisation des performances dans les environnements de non-production ou de test.
ms.openlocfilehash: 551e4e5f985fc18439a4f277685034e86c7cdfb6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814924"
---
# <a name="skype-for-business-server-2015-stress-and-performance-tool"></a>Outil Stress and Performance de Skype Entreprise Server 2015
 
L’outil Stress and Performance de Skype Entreprise Server 2015 est utilisé lors de la planification de la capacité et de l’optimisation des performances dans les environnements de non-production ou de test.
  
L’outil Stress and Performance de Skype Entreprise Server 2015 inclut des outils qui simplifieront votre planification de la capacité pour Skype Entreprise Server 2015. L’outil Stress and Performance de Skype Entreprise Server 2015 vous aidera à :
  
- Simplifier la planification de votre matériel pour Skype Entreprise Server
    
- Donnez-vous des connaissances et des meilleures pratiques pour l’optimisation des performances
    
- Mesurer les performances de vos déploiements Skype Entreprise Server
    
En règle générale, vous utilisez cet outil après avoir utilisé l’outil de planification de Skype Entreprise [Server 2015](../../management-tools/planning-tool/planning-tool.md) pour concevoir la topologie et affiner la topologie avec la calculatrice de planification de la capacité de Skype Entreprise [Server 2015.](../../management-tools/capacity-planning-calculator.md) 

> [!NOTE]
> Cet outil ne sera pas mis à jour pour Skype Entreprise Server 2019.
  
## <a name="tests"></a>Tests

L’outil Stress and Performance peut simuler ces types de charge utilisateur :
  
|||
|:-----|:-----|
|Messagerie instantanée et présence  <br/> |Audioconférence  <br/> |
|Partage d'application  <br/> |Voix sur IP (VoIP), y compris la simulation de réseau téléphonique commuté (PTSN)  <br/> |
|Conférence client Web Access  <br/> |Attendant automatique de conférence  <br/> |
|Groupes Response Group  <br/> |Développement de listes de distribution  <br/> |
|Téléchargement du carnet d’adresses et requête de carnet d’adresses  <br/> |Appels enhanced 911 (E911) et profil d’emplacement (plan de numérotation)  <br/> |
|MultiView  <br/> |Collaboration de données  <br/> |
|Mobilité  <br/> ||
   
## <a name="applications-and-files-included-with-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Applications et fichiers inclus avec l’outil Stress and Performance de Skype Entreprise Server 2015

Ces applications font partie de l’outil Stress and Performance de Skype Entreprise Server :
  
|**Outil**|**Description**|
|:-----|:-----|
|UserProvisioningTool.exe  <br/> |Cet outil est utilisé pour créer des utilisateurs et des contacts.  <br/> |
|UserProfileGenerator.exe  <br/> |Permet de configurer les caractéristiques de la charge utilisateur que vous simulez.  <br/> |
|LyncPerfTool.exe  <br/> |Outil qui simule la charge utilisateur.  <br/> |
|Default.tmx  <br/> |Requis pour utiliser l’outil de journalisation de Skype Entreprise Server 2015.  <br/> |
|Exemples de script d’approvisionnement  <br/> |Permet de configurer la topologie pour l’exécution de tests de charge, en fonction de scénarios spécifiques. Vous devrez probablement les modifier pour les rendre pertinentes pour votre environnement particulier.  <br/> |
   
## <a name="topics-in-this-section"></a>Rubriques de cette section

Pour en savoir plus, vous devez consulter les articles suivants :
  
- [Conditions préalables et configuration de l’outil Stress and Performance de Skype Entreprise](prerequisites-and-setup.md)
    
- [Scénarios de performances pour l’outil Stress and Performance de Skype Entreprise Server 2015](scenarios.md)
    
  - [Mise en service de la topologie pour exécuter la charge dans les scénarios de contrainte et de performances](provisioning-the-topology-to-run-load.md)
    
  - [Configuration des stratégies pour l’outil Stress and Performance de Skype Entreprise Server 2015](configuring-policies.md)
    
- [Utilisation de l’outil Stress and Performance de Skype Entreprise Server 2015](using-the-tool.md)
    
- [FAQ sur l’outil Stress and Performance de Skype Entreprise Server 2015](faq.md)
    

