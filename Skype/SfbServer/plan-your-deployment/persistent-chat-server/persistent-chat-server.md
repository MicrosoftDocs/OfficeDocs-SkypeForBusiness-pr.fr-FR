---
title: Planifier un serveur de conversation permanente dans Skype Entreprise Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9e652487-a123-40c0-ae61-47fb8ecc4a20
description: 'Résumé : Lisez cette rubrique pour savoir comment planifier pour serveur Chat persistant dans Skype Business Server 2015.'
ms.openlocfilehash: 0380b5ebb43e198160faa3e7f10b1563b4def80f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Planifier un serveur de conversation permanente dans Skype Entreprise Server 2015
 
**Résumé :** Lisez cette rubrique pour savoir comment planifier pour serveur Chat persistant dans Skype Business Server 2015.
  
Serveur de conversation permanent est un rôle facultatif qui permet à plusieurs utilisateurs de votre organisation participer aux conversations de salle de conversation qui persistent dans le temps. Même si les utilisateurs peuvent communiquer en temps réel pendant une session - notamment par le biais de texte, de liens et de fichiers - le contenu de chaque session est persistant, ce qui signifie qu’il reste disponible après la fin d’une session.
  
Serveur de Chat persistant peut aider à améliorer la communication au sein de votre organisation par :
  
- Augmentation de la sensibilisation à l’information et à la participation au sein de l’organisation
    
- Facilitation du partage efficace des informations 
    
- Améliorer la communication entre les équipes, y compris les équipes interfonctionnelles et géographiquement dispersés
    
- Réduction de la surcharge d’informations
    
- Suivi de la conformité à la réglementation en déployant facultativement le service de conformité de conversation permanente
    
## <a name="persistent-chat-server-high-level-architecture"></a>Architecture de haut niveau du serveur de conversation permanente

Le diagramme suivant montre une vue d’ensemble de l’architecture de serveur de conversation persistant. 
  
![Architecture de haut niveau du serveur de conversation permanente](../../media/0344f6e2-0c6d-4391-b4b3-ec31062b1576.png)
  
La conversation persistante se compose d’un rôle de serveur frontal qui fournit les services de conversation permanente ainsi qu’un composant de base de données SQL principal. Les deux composants frontal et principal sont inclus dans un pool de conversation permanente dédié. Chaque ordinateur qui héberge le serveur de conversation permanent doit avoir accès à un Skype existant pour la topologie de Business Server 2015. Dans ce diagramme, il existe un pool de serveur de Chat persistant (A), qui dépend de Skype pour un Pool de serveurs d’entreprise pour le routage des messages.
  
Vous pouvez déployer un ou plusieurs pools de serveur de conversation persistant, chacun avec quatre active permanente des serveurs Chat prend en charge jusqu'à 80K d’utilisateurs simultanés.
  
Skype pour Business Server 2015 communique avec le service Chat persistant à l’aide du protocole SIP (Session Initiation) pour l’enregistrement et le protocole Extensible conversation Communication sur SIP (XCCOS) pour une conversation. 
  
## <a name="persistent-chat-services"></a>Services de conversation permanente

Le diagramme suivant illustre les services frontaux persistant Chat Server, et comment ces services communiquent avec les composants de base de données back-end. Les composants frontaux comprennent les services de conversation permanente et le service de conformité. Les composants principaux incluent le magasin de conversation permanente et le magasin de conformité de la conversation permanente.
  
![Services de haut niveau du serveur de conversation permanente](../../media/bcdbadbe-e868-4a46-8a73-36562648fdf7.png)
  
### <a name="chat-service"></a>Service de conversation

Le service Conversation, appelé aussi service Canal, est le service de base responsable du serveur de conversation permanente. Le service de conversation fournit les fonctions suivantes :
  
- acceptation des messages entrants ;
    
- Enregistre et répertorie les participants en ligne au sein d’une salle de conversation permanent
    
- Retransmet les messages vers d’autres abonnés de canal
    
- implémentation de la logique de gestion des canaux, d’invitation aux salles de conversation, de recherche et de notifications de nouveau contenu.
    
Le service de conversation permanente stocke le contenu des salles de conversation et d’autres stores métadonnées (règles d’autorisation, etc.), et y accède, par le biais du magasin de conversation permanente. Le service stocke les fichiers qui sont chargés dans les salles de conversation du magasin de fichiers des conversations permanentes.
  
### <a name="compliance-service"></a>Service de conformité

Si le règlement de votre organisation impose un archivage de l’activité de conversation permanente, vous pouvez déployer le service de conformité de conversation permanente facultatif. Le service de conformité est responsable de l’archivage du contenu des conversation et des événements, comme le fait de rejoindre et de quitter des salles, dans le magasin de fichiers de conformité des conversations permanentes. Le service de mise en conformité est installé sur chaque serveur Chat persistant dans un pool de Chat persistant. 
  
### <a name="web-services"></a>Services web

Les services web de Chat persistant exécutent sur le Skype avant fin des serveurs d’entreprise. Les services web dépendent de IIS (Internet Information Services), et sont implémentés en tant que composants web :
  
- Les services web de conversation permanente pour le chargement et le téléchargement sont responsables de la publication et de la récupération des fichiers à partir des salles de conversation.
    
- Les services web de conversation permanente pour la gestion des salles de conversation sont chargés d’offrir aux utilisateurs la possibilité de gérer leurs salles de conversation et d’en créer des nouvelles.
    
## <a name="defining-requirements-for-your-organization"></a>Définition des exigences pour votre organisation

Si vous décidez de déployer le serveur de conversation persistant, vous devez déterminer les besoins de votre organisation, puis définir la topologie, l’infrastructure et des exigences techniques pour prendre en charge les besoins de votre entreprise. Pour optimiser votre déploiement, vous devez répondre aux questions suivantes :
  
- Vous migrez à partir d’une version précédente du serveur de conversation de groupe, ou une version antérieure du serveur de conversation permanent, ou que vous déployez le serveur de conversation persistant pour la première fois ?
    
- Qui peut utiliser le serveur de conversation permanente ? Vous spécifiez des stratégies de conversation permanente pour déterminer l’accès utilisateur au niveau global, site ou utilisateur.
    
- Combien d’utilisateurs vont avoir besoin de l’accès au serveur de conversation permanente ? Le serveur de conversation permanente prend en charge 150 000 utilisateurs disposant de privilèges d’accès (via une stratégie) et un nombre maximal de 80 000 utilisateurs simultanés. Un seul serveur de conversation permanente peut prendre en charge 20 000 utilisateurs connectés, et un seul pool de serveur de conversation permanente peut comporter jusqu’à 4 serveurs actifs pour un total de 80 000 utilisateurs connectés simultanément.
    
- Comment contrôler les étendues, les limites éthiques et l’accès ? Vous pouvez définir des catégories afin d’établir des limites et choisir les personnes autorisées à être présentes dans les salles créées dans chacune de ces catégories.
    
- Comment voulez-vous déterminer qui peut créer des salles ? Vous pouvez définir des créateurs qui peuvent créer des salles. Les créateurs peuvent affecter d’autres membres en tant que responsables de salles de conversation pour la gestion continue des salles.
    
- Comment créer des salles ? Persistant Chat Server fournit une fonctionnalité basée sur le web pour la création et la gestion de salles. Il peut être lancé depuis la Skype pour client d’entreprise. Vous pouvez choisir de définir une solution client qui implémente vos besoins de l’entreprise et les workflows et configure un serveur de Chat persistant pour diriger les utilisateurs vers votre solution personnalisée.
    
- Quel genre de compléments voulez-vous approvisionner ? Les compléments améliorent l’expérience utilisateur en tirant parti du volet d’extensibilité du client Skype Entreprise afin de fournir un contexte pertinent pour la salle. Vous pouvez choisir les compléments généraux les plus utiles à vos yeux (par exemple, le site de votre entreprise, des documents de collaboration internes, etc.). Les gestionnaires de salles de conversation peuvent choisir l’un des compléments inscrits et l’associer à leurs salles, le cas échéant. 
    
- Quels sont vos besoins en matière de haute disponibilité et de récupération d’urgence ? Serveur de Chat persistant prend en charge la mise en miroir de SQL Server et de SQL Server mise en clusters pour une haute disponibilité. Récupération d’urgence, persistant Chat Server prend en charge jusqu'à 8 serveurs (4 veille active et 4) dans un pool étiré avec SQL Server envoi de journaux. 
    
- Existe-t-il des exigences réglementaires ? Si votre société est dans un pays ou une région où les données doivent rester dans le pays, vous devrez déployer plusieurs pools persistant Chat Server, chaque local à une zone géographique spécifique. Une salle, catégorie ou complément ne couvre pas les pools--il appartient à un seul pool de serveur de Chat persistant. 
    
    > [!NOTE]
    > Ayant plusieurs pools de serveur de conversation permanent ne vous donne pas plus d’évolutivité (vous pouvez toujours avoir uniquement 80 000 utilisateurs simultanés au sein de tous les pools de votre serveur de Chat persistant). La raison principale pour la prise en charge de plusieurs pools de serveur de conversation persistant est à prendre en charge les problèmes de réglementations. 
  
## <a name="for-more-information"></a>Pour plus d’informations

Pour plus d’informations sur l’installation et configuration du serveur de conversation permanente, voir les rubriques suivantes :
  
- Pour plus d’informations sur le déploiement du serveur de conversation persistant, consultez [Déploiement de serveur Chat persistant dans Skype pour Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md). 
    
- Pour plus d’informations sur la façon de configurer les paramètres sur votre déploiement de serveur de conversation persistant, consultez [Gérer serveur Chat persistant dans Skype pour Business Server 2015](../../manage/persistent-chat/persistent-chat.md).
    

