---
title: Planifier le serveur de conversation permanente dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 8/17/2015
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 9e652487-a123-40c0-ae61-47fb8ecc4a20
description: 'Résumé : Lisez cette rubrique pour découvrir comment planifier le serveur de conversation permanente Skype Entreprise Server 2015.'
ms.openlocfilehash: cb584fc1b618794d9956c2d91c004b8ecc008aa0
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58731093"
---
# <a name="plan-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Planifier le serveur de conversation permanente dans Skype Entreprise Server 2015
 
**Résumé :** Lisez cette rubrique pour découvrir comment planifier le serveur de conversation permanente Skype Entreprise Server 2015.
  
Le serveur de conversation permanente est un rôle facultatif qui permet à plusieurs utilisateurs de votre organisation de participer à des conversations de salle de conversation persistantes au fil du temps. Bien que les utilisateurs peuvent communiquer en temps réel au cours d’une session de conversation, le contenu de chaque session (y compris le texte, les liens et les fichiers) est persistant, ce qui signifie que les utilisateurs peuvent afficher et rechercher tout le contenu de la session à tout moment.
  
Le serveur de conversation permanente peut vous aider à améliorer la communication au sein de votre organisation en :
  
- Élargir la sensibilisation et la participation aux informations au sein de l’organisation
    
- Activation d’un partage d’informations efficace 
    
- Amélioration de la communication entre les équipes, y compris les équipes géographiquement dispersées et multifonctions
    
- Réduction de la surcharge d’informations
    
- Suivre les réglementations de conformité en déployant éventuellement le service de conformité de conversation permanente

> [!NOTE] 
> La conversation permanente est disponible Skype Entreprise Server 2015, mais n’est plus prise en charge Skype Entreprise Server 2019. La même fonctionnalité est disponible dans Teams. Pour plus d’informations, voir [Mise en Microsoft Teams mise à niveau.](/microsoftteams/upgrade-start-here) Si vous devez utiliser la conversation permanente, vous pouvez soit migrer des utilisateurs nécessitant cette fonctionnalité vers Teams, soit continuer à utiliser Skype Entreprise Server 2015. 
    
## <a name="persistent-chat-server-high-level-architecture"></a>Architecture de haut niveau du serveur de conversation permanente

Le diagramme suivant présente une vue de haut niveau de l’architecture du serveur de conversation permanente. 
  
![Architecture d'High-Level de conversation permanente.](../../media/0344f6e2-0c6d-4391-b4b3-ec31062b1576.png)
  
La conversation permanente se compose d’un rôle serveur frontal qui fournit les services de conversation permanente, ainsi qu’un composant de base de données SQL principal. Les composants frontaux et principaux sont inclus dans un pool de conversation permanente dédié. Chaque ordinateur qui héberge le serveur de conversation permanente doit avoir accès à une topologie Skype Entreprise Server 2015 existante. Dans ce diagramme, il existe un pool de serveurs de conversation permanente (A), qui dépend de Skype Entreprise Server pool A pour le routage des messages vers celui-ci.
  
Vous pouvez déployer un ou plusieurs pools de serveurs de conversation permanente, chacun avec jusqu’à quatre serveurs de conversation permanente actifs qui peuvent prendre en charge jusqu’à 80 000 utilisateurs simultanés.
  
Skype Entreprise Server 2015 communique avec le service de conversation permanente à l’aide du protocole SIP (Session Initiation Protocol) pour l’inscription et du protocole XCCOS (Extensible Chat Communication Over SIP) pour la conversation. 
  
## <a name="persistent-chat-services"></a>Services de conversation permanente

Le diagramme suivant illustre les services frontaux du serveur de conversation permanente et la façon dont ces services communiquent avec les composants de base de données principaux. Les composants frontaux incluent les services de conversation permanente et le service de conformité. Les composants principaux incluent le magasin de conversation permanente et le magasin de conformité de conversation permanente.
  
![Serveur de conversation permanente High-Level Services.](../../media/bcdbadbe-e868-4a46-8a73-36562648fdf7.png)
  
### <a name="chat-service"></a>Service de conversation

Le service de conversation, également appelé service de canal, est le service principal responsable du serveur de conversation permanente. Le service de conversation fournit les fonctions suivantes :
  
- acceptation des messages entrants ;
    
- Inscrit et répertorie les participants en ligne dans une salle de conversation permanente
    
- retransmission des messages vers les abonnés à d’autres canaux ;
    
- Implémente la logique pour la gestion des canaux, les invitations aux salles de conversation, la recherche et les nouvelles notifications de contenu
    
Le service de conversation permanente stocke et accède au contenu de la salle de conversation et à d’autres métadonnées système (règles d’autorisation, etc.) à l’aide du magasin de conversation permanente. Le service stocke les fichiers qui sont chargés dans les salles de conversation dans le magasin de fichiers de conversation permanente.
  
### <a name="compliance-service"></a>Service de conformité

Si votre organisation a des réglementations qui exigent l’archivage de l’activité de conversation permanente, vous pouvez déployer le service de conformité de conversation permanente facultatif. Le service de conformité est responsable de l’archivage du contenu et des événements de conversation, tels que la jointation et la sortie de salles, dans le magasin de fichiers de conformité de conversation permanente. Le service de conformité est installé sur chaque serveur de conversation permanente dans un pool de conversation permanente. 
  
### <a name="web-services"></a>Services Web

Les services web de conversation permanente s’exécutent sur Skype Entreprise serveurs frontaux. Les services web dépendent de Internet Information Services (IIS) et sont implémentés en tant que composants web :
  
- Les services web de conversation permanente pour le chargement et le téléchargement de fichiers sont chargés de publier et de récupérer des fichiers à partir des salles de conversation.
    
- Les services web de conversation permanente pour la gestion des salles de conversation sont chargés de fournir aux utilisateurs la possibilité de gérer leurs salles de conversation et de créer de nouvelles salles de conversation.
    
## <a name="defining-requirements-for-your-organization"></a>Définition des conditions requises pour votre organisation

Si vous décidez de déployer un serveur de conversation permanente, vous devez déterminer les besoins de votre organisation, puis définir la topologie, l’infrastructure et les exigences techniques pour répondre aux besoins de votre entreprise. Pour optimiser votre déploiement, vous devez répondre aux questions suivantes :
  
- Migrez-vous à partir d’une version antérieure du serveur de conversation de groupe ou d’une version antérieure du serveur de conversation permanente, ou déployez-vous le serveur de conversation permanente pour la première fois ?
    
- Qui pouvez utiliser le serveur de conversation permanente ? Vous spécifiez des stratégies de conversation permanente pour déterminer l’accès des utilisateurs au niveau global, du site ou de l’utilisateur.
    
- Combien d’utilisateurs auront besoin d’accéder au serveur de conversation permanente ? Le serveur de conversation permanente prend en charge 150 000 utilisateurs (activés par la stratégie) et un maximum de 80 000 utilisateurs simultanés. Un seul serveur de conversation permanente peut prendre en charge 20 000 utilisateurs connectés et un seul pool de serveurs de conversation permanente peut avoir jusqu’à 4 serveurs actifs pour un total de 80 000 utilisateurs connectés simultanément.
    
- Comment contrôler les étendues, les limites éthiques et l’accès ? Vous pouvez définir des catégories pour séparer ces limites et choisir les personnes autorisées à se trouver dans les salles créées dans chacune de ces catégories.
    
- Comment contrôler les personnes autorisées à créer des salles ? Vous pouvez définir des créateurs qui peuvent créer des salles. Les créateurs peuvent affecter d’autres membres en tant que responsables de salles de conversation pour la gestion continue des salles.
    
- Comment créer des salles ? Le serveur de conversation permanente fournit une fonctionnalité web pour la création et la gestion des salles. Il peut être lancé à partir du client Skype Entreprise client. Vous pouvez choisir de définir une solution client qui implémente les besoins de votre entreprise et les flux de travail, et configure le serveur de conversation permanente pour diriger les utilisateurs vers votre solution personnalisée.
    
- Quel genre de compléments voulez-vous approvisionner ? Les add-ins améliorent l’expérience dans la salle en tirant parti du volet d’extensibilité dans le client Skype Entreprise pour fournir un contexte pertinent pour la salle. Vous pouvez choisir les compléments généraux les plus utiles à vos yeux (par exemple, le site de votre entreprise, des documents de collaboration internes, etc.). Les gestionnaires de salles de conversation peuvent choisir l’un des compléments inscrits et l’associer à leurs salles, le cas échéant. 
    
- Quels types d’exigences en matière de haute disponibilité et de récupération d’urgence avez-vous ? Le serveur de conversation permanente prend en charge SQL Server mise en miroir et SQL Server clustering pour la haute disponibilité. Pour la récupération d’urgence, le serveur de conversation permanente prend en charge jusqu’à 8 serveurs (4 actifs et 4 de secours) dans un pool étiré avec la SQL Server de journaux de livraison. 
    
- Existe-t-il des exigences en matière de réglementation ? Si votre entreprise se trouve dans un pays ou une région où les données doivent être conservées dans le pays, vous devrez peut-être déployer plusieurs pools de serveurs de conversation permanente, chacun local dans une zone géographique spécifique. Une salle, une catégorie ou un add-in ne couvre pas les pools ; il n’appartient qu’à un seul pool de serveurs de conversation permanente. 
    
    > [!NOTE]
    > Le fait d’avoir plusieurs pools de serveurs de conversation permanente ne vous donne pas plus d’échelle (vous ne pouvez toujours avoir que 80 000 utilisateurs simultanés sur tous vos pools de serveurs de conversation permanente). La principale raison de la prise en charge de plusieurs pools de serveurs de conversation permanente est de prendre en charge les problèmes réglementaires. 
  
## <a name="for-more-information"></a>Pour plus d'informations

Pour plus d’informations sur l’installation et la configuration du serveur de conversation permanente, consultez les rubriques suivantes :
  
- Pour plus d’informations sur le déploiement d’un serveur de conversation permanente, voir [Deploy Persistent Chat Server in Skype Entreprise Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md). 
    
- Pour plus d’informations sur la configuration des paramètres sur votre déploiement de serveur de conversation permanente, voir [Manage Persistent Chat Server in Skype Entreprise Server 2015](../../manage/persistent-chat/persistent-chat.md).
    

