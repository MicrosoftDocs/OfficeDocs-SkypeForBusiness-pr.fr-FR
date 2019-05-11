---
title: Planifier un serveur de conversation permanente dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9e652487-a123-40c0-ae61-47fb8ecc4a20
description: 'Résumé : Lisez cette rubrique pour savoir comment planifier des serveurs de conversation permanente dans Skype pour Business Server 2015.'
ms.openlocfilehash: b3ca8125a69a94da3e0c707456d695c31eaf8c47
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33910804"
---
# <a name="plan-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Planifier un serveur de conversation permanente dans Skype Entreprise Server 2015
 
**Résumé :** Lisez cette rubrique pour savoir comment planifier des serveurs de conversation permanente dans Skype pour Business Server 2015.
  
Serveur de conversation permanente est un rôle facultatif qui permet à plusieurs utilisateurs dans votre organisation participer à des conversations de salle de conversation persistant. Même si les utilisateurs peuvent communiquer en temps réel pendant une session - notamment par le biais de texte, de liens et de fichiers - le contenu de chaque session est persistant, ce qui signifie qu’il reste disponible après la fin d’une session.
  
Serveur de conversation permanente peuvent aider à améliorer la communication au sein de votre organisation par :
  
- Augmentation de la sensibilisation à l’information et à la participation au sein de l’organisation
    
- Facilitation du partage efficace des informations 
    
- Amélioration de la communication entre des équipes géographiquement dispersées et multifonctionnelles
    
- Réduction de la surcharge d’informations
    
- Suivi de la conformité à la réglementation en déployant facultativement le service de conformité de conversation permanente

> [!NOTE] 
> Conversation permanente est disponible dans Skype pour Business Server 2015, mais n’est plus pris en charge dans Skype pour Business Server 2019. La même fonctionnalité est disponible dans les équipes. Pour plus d’informations, voir [parcours de Skype pour les entreprises aux équipes de Microsoft](/microsoftteams/journey-skypeforbusiness-teams). Si vous devez utiliser la conversation permanente, vos choix est pour migrer les utilisateurs ayant besoin de cette fonctionnalité aux équipes, ou pour continuer à utiliser Skype pour Business Server 2015. 
    
## <a name="persistent-chat-server-high-level-architecture"></a>Architecture de haut niveau du serveur de conversation permanente

Le diagramme suivant illustre une vue de haut niveau de l’architecture du serveur de conversation permanente. 
  
![Architecture de haut niveau du serveur de conversation permanente](../../media/0344f6e2-0c6d-4391-b4b3-ec31062b1576.png)
  
La conversation persistante se compose d’un rôle de serveur frontal qui fournit les services de conversation permanente ainsi qu’un composant de base de données SQL principal. Les deux composants frontal et principal sont inclus dans un pool de conversation permanente dédié. Chaque ordinateur qui héberge le serveur de conversation permanente doit avoir accès à un Skype existant pour la topologie Business Server 2015. Dans ce diagramme, il existe un pool de serveurs de conversation permanente (A), qui est tributaire Skype pour un Pool de serveurs d’entreprise pour le routage des messages.
  
Vous pouvez déployer un ou plusieurs pools de serveurs de conversation permanente, chacun avec jusqu'à quatre active des serveurs de conversation permanente prend en charge jusqu'à 80K d’utilisateurs simultanés.
  
Skype pour Business Server 2015 communique avec le service de conversation permanente à l’aide du protocole SIP (Session Initiation) pour l’enregistrement et le protocole Extensible conversation Communication sur SIP (XCCOS) pour la conversation. 
  
## <a name="persistent-chat-services"></a>Services de conversation permanente

Le diagramme suivant illustre les services frontaux Persistent Chat Server et comment ces services communiquent avec les composants de base de données principale. Les composants frontaux comprennent les services de conversation permanente et le service de conformité. Les composants principaux incluent le magasin de conversation permanente et le magasin de conformité de la conversation permanente.
  
![Services de haut niveau du serveur de conversation permanente](../../media/bcdbadbe-e868-4a46-8a73-36562648fdf7.png)
  
### <a name="chat-service"></a>Service de conversation

Le service Conversation, appelé aussi service Canal, est le service de base responsable du serveur de conversation permanente. Le service de conversation fournit les fonctions suivantes :
  
- acceptation des messages entrants ;
    
- inscription et listage des participants en ligne dans une salle de conversation permanente ;
    
- retransmission des messages vers les abonnés à d’autres canaux ;
    
- implémentation de la logique de gestion des canaux, d’invitation aux salles de conversation, de recherche et de notifications de nouveau contenu.
    
Le service de conversation permanente stocke le contenu des salles de conversation et d’autres stores métadonnées (règles d’autorisation, etc.), et y accède, par le biais du magasin de conversation permanente. Le service stocke les fichiers qui sont chargés dans les salles de conversation du magasin de fichiers des conversations permanentes.
  
### <a name="compliance-service"></a>Service de conformité

Si le règlement de votre organisation impose un archivage de l’activité de conversation permanente, vous pouvez déployer le service de conformité de conversation permanente facultatif. Le service de conformité est responsable de l’archivage du contenu des conversation et des événements, comme le fait de rejoindre et de quitter des salles, dans le magasin de fichiers de conformité des conversations permanentes. Le service de conformité est installé sur chaque serveur de conversation permanente dans un pool de conversation permanente. 
  
### <a name="web-services"></a>Services web

Les services web de conversation permanente exécutent sur le Skype pour les serveurs frontaux Business. Les services web dépendent de IIS (Internet Information Services), et sont implémentés en tant que composants web :
  
- Les services web de conversation permanente pour le chargement et le téléchargement sont responsables de la publication et de la récupération des fichiers à partir des salles de conversation.
    
- Les services web de conversation permanente pour la gestion des salles de conversation sont chargés d’offrir aux utilisateurs la possibilité de gérer leurs salles de conversation et d’en créer des nouvelles.
    
## <a name="defining-requirements-for-your-organization"></a>Définition des exigences pour votre organisation

Si vous décidez de déployer des serveurs de conversation permanente, vous devez déterminer les besoins de votre organisation, puis définir la topologie, l’infrastructure et des conditions techniques requises pour prendre en charge les besoins de votre entreprise. Pour optimiser votre déploiement, vous devez répondre aux questions suivantes :
  
- Vous migrez depuis une version antérieure du serveur de conversation de groupe, ou une version antérieure du serveur de conversation permanente, ou que vous déployez le serveur de conversation permanente pour la première fois ?
    
- Qui peut utiliser le serveur de conversation permanente ? Vous spécifiez des stratégies de conversation permanente pour déterminer l’accès utilisateur au niveau global, site ou utilisateur.
    
- Combien d’utilisateurs vont avoir besoin de l’accès au serveur de conversation permanente ? Le serveur de conversation permanente prend en charge 150 000 utilisateurs disposant de privilèges d’accès (via une stratégie) et un nombre maximal de 80 000 utilisateurs simultanés. Un seul serveur de conversation permanente peut prendre en charge 20 000 utilisateurs connectés, et un seul pool de serveur de conversation permanente peut comporter jusqu’à 4 serveurs actifs pour un total de 80 000 utilisateurs connectés simultanément.
    
- Comment contrôler les étendues, les limites éthiques et l’accès ? Vous pouvez définir des catégories afin d’établir des limites et choisir les personnes autorisées à être présentes dans les salles créées dans chacune de ces catégories.
    
- Comment voulez-vous déterminer qui peut créer des salles ? Vous pouvez définir des créateurs qui peuvent créer des salles. Les créateurs peuvent affecter d’autres membres en tant que responsables de salles de conversation pour la gestion continue des salles.
    
- Comment créer des salles ? Serveur de conversation permanente fournit une fonctionnalité basée sur le web pour la création et la gestion des salles. Cela peut être lancé depuis la Skype pour client d’entreprise. Vous pouvez choisir de définir une solution personnalisée qui implémente vos impératifs d’entreprise et les flux de travail et configure Persistent Chat Server pour rediriger les utilisateurs vers votre solution personnalisée.
    
- Quel genre de compléments voulez-vous approvisionner ? Les compléments améliorent l’expérience utilisateur en tirant parti du volet d’extensibilité du client Skype Entreprise afin de fournir un contexte pertinent pour la salle. Vous pouvez choisir les compléments généraux les plus utiles à vos yeux (par exemple, le site de votre entreprise, des documents de collaboration internes, etc.). Les gestionnaires de salles de conversation peuvent choisir l’un des compléments inscrits et l’associer à leurs salles, le cas échéant. 
    
- Quels sont vos besoins en matière de haute disponibilité et de récupération d’urgence ? Persistent Chat Server prend en charge la mise en miroir SQL Server et le clustering SQL Server pour une haute disponibilité. La récupération d’urgence, Persistent Chat Server prend en charge jusqu'à 8 serveurs (4 de secours actif et 4) dans un pool étiré avec SQL Server envoi de journaux. 
    
- Existe-t-il des exigences réglementaires ? Si votre société est dans votre pays ou région dans lequel les données doivent être conservées à l’intérieur du pays, vous devrez déployer plusieurs pools de serveurs de conversation permanente, chaque local à une zone géographique spécifique. Une salle, catégorie ou complément ne couvre pas les pools--il appartient à un seul pool de serveurs de conversation permanente. 
    
    > [!NOTE]
    > Ayant plusieurs pools de serveurs de conversation permanente ne donne pas l’échelle (vous pouvez toujours avoir seulement 80 000 utilisateurs simultanés dans tous les pools de votre serveur de conversation permanente). La raison principale pour la prise en charge de plusieurs pools de serveurs de conversation permanente est pour prendre en charge de la réglementation. 
  
## <a name="for-more-information"></a>Pour plus d’informations

Pour plus d’informations sur l’installation et configuration du serveur de conversation permanente, voir les rubriques suivantes :
  
- Pour plus d’informations sur le déploiement des serveurs de conversation permanente, voir [Déployer un serveur de conversation permanente dans Skype pour Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md). 
    
- Pour plus d’informations sur la façon de configurer les paramètres de votre déploiement de serveurs de conversation permanente, voir [Gérer les serveurs de conversation permanente dans Skype pour Business Server 2015](../../manage/persistent-chat/persistent-chat.md).
    

