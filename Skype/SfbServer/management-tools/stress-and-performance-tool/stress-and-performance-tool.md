---
title: Skype for Business Server 2015 Stress and Performance Tool
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 4/6/2016
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f2f7d19b-18c8-4a41-9b17-80d35b73d742
description: L’outil de stress et de performance de Skype entreprise Server 2015 est utilisé lors de la planification de la capacité et de l’optimisation des performances dans les environnements hors production et de test.
ms.openlocfilehash: d82d5ed33e6dca1303aed9f49150dd6b56fc4e1a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34299515"
---
# <a name="skype-for-business-server-2015-stress-and-performance-tool"></a>Skype for Business Server 2015 Stress and Performance Tool
 
L’outil de stress et de performance de Skype entreprise Server 2015 est utilisé lors de la planification de la capacité et de l’optimisation des performances dans les environnements hors production et de test.
  
L’outil de stress et de performance de Skype entreprise Server 2015 inclut des outils qui simplifient la planification de la capacité de Skype entreprise Server 2015. L’outil de stress et de performance de Skype entreprise Server 2015 vous aide à effectuer les opérations suivantes:
  
- Simplification de la planification de votre matériel pour Skype entreprise Server
    
- Vous offrir des connaissances et des meilleures pratiques en matière d’optimisation des performances
    
- Mesurer les performances de vos déploiements Skype entreprise Server
    
En règle générale, vous devez utiliser cet outil après l’utilisation de l' [outil de planification de Skype entreprise server 2015](../../management-tools/planning-tool/planning-tool.md) pour concevoir la topologie et affiner la topologie avec le [calculateur de planification de capacité de skype entreprise Server 2015](../../management-tools/capacity-planning-calculator.md). 

> [!NOTE]
> Cet outil ne sera pas mis à jour pour Skype entreprise Server 2019.
  
## <a name="tests"></a>Tests

L’outil de stress et de performance peut simuler les types de charge utilisateur suivants:
  
|||
|:-----|:-----|
|Messagerie instantanée et présence  <br/> |Audioconférence  <br/> |
|Partage d'application  <br/> |Voix sur IP (VoIP), y compris la simulation de réseau téléphonique commuté (PTSN)  <br/> |
|Conférences de clients d’accès Web  <br/> |Standard automatique de conférences  <br/> |
|Response Groups  <br/> |Extension de liste de distribution  <br/> |
|Requête de téléchargement du carnet d’adresses et du carnet d’adresses  <br/> |Le profil d’emplacement et les appels 911 (E911)  <br/> |
|Multivue  <br/> |Collaboration sur les données  <br/> |
|Mobilité  <br/> ||
   
## <a name="applications-and-files-included-with-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Applications et fichiers inclus dans l’outil de stress et de performance de Skype entreprise Server 2015

Ces applications font partie intégrante de l’outil de stress et de performance de Skype entreprise Server:
  
|**Il**|**Description**|
|:-----|:-----|
|UserProvisioningTool. exe  <br/> |Cet outil permet de créer des utilisateurs et des contacts.  <br/> |
|UserProfileGenerator. exe  <br/> |Permet de configurer les caractéristiques de la charge utilisateur que vous simulez.  <br/> |
|LyncPerfTool. exe  <br/> |Outil simulant la charge utilisateur.  <br/> |
|Default. TMX  <br/> |Requis pour utiliser l’outil de journalisation de Skype entreprise Server 2015.  <br/> |
|Exemples de script de mise en service  <br/> |Utilisé pour configurer la topologie pour exécuter des tests de charge, en fonction de scénarios spécifiques. Vous devrez peut-être les modifier pour qu’elles soient pertinentes pour votre environnement particulier.  <br/> |
   
## <a name="topics-in-this-section"></a>Rubriques de cette section

Pour en savoir plus, consultez les articles suivants:
  
- [Conditions préalables et configuration pour l'outil Stress and Performance de Skype Entreprise](prerequisites-and-setup.md)
    
- [Scénarios de performances de l’outil de stress et de performances de Skype entreprise Server 2015](scenarios.md)
    
  - [Approvisionnement de la topologie pour exécuter des scénarios de stress et de performance](provisioning-the-topology-to-run-load.md)
    
  - [Configuration des stratégies de l’outil de stress et de performance de Skype entreprise Server 2015](configuring-policies.md)
    
- [Utilisation de l’outil de stress et de performance 2015 de Skype entreprise Server](using-the-tool.md)
    
- [FAQ sur l’outil de stress et de performances de Skype entreprise Server 2015](faq.md)
    

