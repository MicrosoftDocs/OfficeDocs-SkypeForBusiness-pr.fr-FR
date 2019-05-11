---
title: Skype for Business Server 2015 Stress and Performance Tool
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
ms.date: 4/6/2016
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: f2f7d19b-18c8-4a41-9b17-80d35b73d742
description: Le Skype pour Business Server 2015 Stress and Performance Tool est utilisé lors de la planification de capacité et de réglage des performances dans un environnement hors production ou de test.
ms.openlocfilehash: 7705e92c8389e0377e805bd7d8e09aee454d9160
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33904572"
---
# <a name="skype-for-business-server-2015-stress-and-performance-tool"></a>Skype for Business Server 2015 Stress and Performance Tool
 
Le Skype pour Business Server 2015 Stress and Performance Tool est utilisé lors de la planification de capacité et de réglage des performances dans un environnement hors production ou de test.
  
Le Skype pour Business Server 2015 Stress and Performance Tool inclut des outils qui simplifient votre planification de capacité pour Skype pour Business Server 2015. Le Skype pour Business Server 2015 Stress and Performance Tool vous aideront à :
  
- Simplifiez votre matériel planification de Skype pour Business Server
    
- Améliorent la base de connaissances et meilleures pratiques pour l’optimisation des performances
    
- Mesurer les performances de votre Skype pour les déploiements de serveur d’entreprise
    
Vous utiliserez généralement cet outil après que le [Skype pour l’outil de planification de 2015 Business Server](../../management-tools/planning-tool/planning-tool.md) vous permet de concevoir la topologie et affiner la topologie avec le [Skype pour Business Server 2015 planification des capacités](../../management-tools/capacity-planning-calculator.md). 

> [!NOTE]
> Cet outil ne système pas mis à jour pour Skype pour Business Server 2019.
  
## <a name="tests"></a>Tests

Le Stress and Performance Tool peuvent de simuler ces types de charge utilisateur :
  
|||
|:-----|:-----|
|Messagerie instantanée et présence  <br/> |Audioconférence  <br/> |
|Partage d'application  <br/> |Voix sur IP (VoIP), y compris le réseau téléphonique commuté simulation (PTSN)  <br/> |
|Conférences Web Client Access  <br/> |Standard automatique de conférence  <br/> |
|Groupes de réponses  <br/> |Développement de listes de distribution  <br/> |
|Téléchargement du carnet d’adresses et l’interrogation du carnet d’adresses  <br/> |Enhanced 911 (E911) appels et le profil d’emplacement (plan de numérotation)  <br/> |
|MultiView  <br/> |Collaboration de données  <br/> |
|Mobilité  <br/> ||
   
## <a name="applications-and-files-included-with-the-skype-for-business-server-2015-stress-and-performance-tool"></a>Applications et fichiers inclus dans le Skype pour Business Server 2015 Stress and Performance Tool

Ces applications font partie de la Skype pour Business Server Stress and Performance Tool :
  
|**Outil**|**Description**|
|:-----|:-----|
|UserProvisioningTool.exe  <br/> |Cet outil est utilisé pour créer des utilisateurs et des contacts.  <br/> |
|UserProfileGenerator.exe  <br/> |Utilisé pour configurer les caractéristiques de la charge utilisateur que vous êtes simulation.  <br/> |
|LyncPerfTool.exe  <br/> |L’outil qui simule la charge utilisateur.  <br/> |
|Default.TMX  <br/> |Requis pour utiliser le Skype pour l’outil de journalisation Business Server 2015.  <br/> |
|Exemples de scripts de mise en service  <br/> |Utilisé pour configurer la topologie pour l’exécution des tests de charge basés sur des scénarios spécifiques. Vous devrez probablement les modifier pour qu’elles soient adaptées à votre environnement.  <br/> |
   
## <a name="topics-in-this-section"></a>Rubriques de cette section

Si vous avez besoin pour en savoir plus, consultez les articles suivants :
  
- [Conditions préalables et configuration pour l'outil Stress and Performance de Skype Entreprise](prerequisites-and-setup.md)
    
- [Scénarios de performances pour le Skype pour Business Server 2015 Stress and Performance Tool](scenarios.md)
    
  - [Mise en service de la topologie pour exécuter la charge dans les scénarios de Stress and Performance](provisioning-the-topology-to-run-load.md)
    
  - [Configuration des stratégies pour le Skype pour Business Server 2015 Stress and Performance Tool](configuring-policies.md)
    
- [À l’aide de la Skype pour Business Server 2015 Stress and Performance Tool](using-the-tool.md)
    
- [Forum aux questions concernant la Skype pour Business Server 2015 Stress and Performance Tool](faq.md)
    

