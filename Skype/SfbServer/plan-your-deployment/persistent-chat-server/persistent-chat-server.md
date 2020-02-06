---
title: Planifier un serveur de conversation permanente dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 8/17/2015
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9e652487-a123-40c0-ae61-47fb8ecc4a20
description: 'Résumé : cette rubrique vous explique comment planifier le fonctionnement du serveur de chat permanent dans Skype entreprise Server 2015.'
ms.openlocfilehash: f2adc5bc9ed23f4ca02843e8c6136c44fca92d6d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815732"
---
# <a name="plan-for-persistent-chat-server-in-skype-for-business-server-2015"></a>Planifier un serveur de conversation permanente dans Skype Entreprise Server 2015
 
**Résumé :** Pour plus d’informations sur la planification du serveur de conversation permanent dans Skype entreprise Server 2015, consultez la rubrique suivante.
  
Le serveur Chat permanent est un rôle facultatif qui permet à plusieurs utilisateurs de votre organisation de participer à des conversations de salles de conversation qui persistent dans le temps. Même si les utilisateurs peuvent communiquer en temps réel pendant une session - notamment par le biais de texte, de liens et de fichiers - le contenu de chaque session est persistant, ce qui signifie qu’il reste disponible après la fin d’une session.
  
Le serveur de chat permanent peut améliorer la communication au sein de votre organisation en procédant comme suit :
  
- Augmentation de la sensibilisation à l’information et à la participation au sein de l’organisation
    
- Facilitation du partage efficace des informations 
    
- Amélioration de la communication entre des équipes géographiquement dispersées et multifonctionnelles
    
- Réduction de la surcharge d’informations
    
- Suivi de la conformité à la réglementation en déployant facultativement le service de conformité de conversation permanente

> [!NOTE] 
> La conversation permanente est disponible dans Skype entreprise Server 2015, mais n’est plus prise en charge dans Skype entreprise Server 2019. La même fonctionnalité est disponible dans Microsoft Teams. Pour plus d’informations, reportez-vous à la rubrique mise [en route de Microsoft teams](/microsoftteams/upgrade-start-here). Si vous avez besoin d’utiliser la conversation permanente, vous pouvez migrer les utilisateurs qui ont besoin de cette fonctionnalité pour teams ou continuer à utiliser Skype entreprise Server 2015. 
    
## <a name="persistent-chat-server-high-level-architecture"></a>Architecture de haut niveau du serveur de conversation permanente

Le diagramme suivant illustre une vue générale de l’architecture serveur de chat permanent. 
  
![Architecture de haut niveau du serveur de conversation permanente](../../media/0344f6e2-0c6d-4391-b4b3-ec31062b1576.png)
  
La conversation persistante se compose d’un rôle de serveur frontal qui fournit les services de conversation permanente ainsi qu’un composant de base de données SQL principal. Les deux composants frontal et principal sont inclus dans un pool de conversation permanente dédié. Chaque ordinateur qui héberge le serveur Chat permanent doit avoir accès à une topologie 2015 Skype entreprise Server. Dans ce diagramme, il existe un pool de serveurs de chat permanent (A), qui dépend de Skype entreprise Server pool A pour le routage de messages.
  
Vous pouvez déployer un ou plusieurs pools de serveurs de chat permanent, chacun avec un maximum de quatre serveurs de chat permanent actifs prenant en charge des utilisateurs simultanés 80K.
  
Skype entreprise Server 2015 communique avec le service de chat permanent en utilisant le protocole SIP (Session Initiation Protocol) pour l’inscription et le protocole de communication de conversation (XCCOS) extensible pour la discussion. 
  
## <a name="persistent-chat-services"></a>Services de conversation permanente

Le diagramme suivant montre les services front-end serveur de chat permanent et la façon dont ces services communiquent avec les composants de la base de données principale. Les composants frontaux comprennent les services de conversation permanente et le service de conformité. Les composants principaux incluent le magasin de conversation permanente et le magasin de conformité de la conversation permanente.
  
![Services de haut niveau du serveur de conversation permanente](../../media/bcdbadbe-e868-4a46-8a73-36562648fdf7.png)
  
### <a name="chat-service"></a>Service de conversation

Le service Conversation, appelé aussi service Canal, est le service de base responsable du serveur de conversation permanente. Le service de conversation fournit les fonctions suivantes :
  
- acceptation des messages entrants ;
    
- inscription et listage des participants en ligne dans une salle de conversation permanente ;
    
- retransmission des messages vers les abonnés à d’autres canaux ;
    
- implémentation de la logique de gestion des canaux, d’invitation aux salles de conversation, de recherche et de notifications de nouveau contenu.
    
Le service de conversation permanente stocke le contenu des salles de conversation et d’autres stores métadonnées (règles d’autorisation, etc.), et y accède, par le biais du magasin de conversation permanente. Le service stocke les fichiers qui sont chargés dans les salles de conversation du magasin de fichiers des conversations permanentes.
  
### <a name="compliance-service"></a>Service de conformité

Si le règlement de votre organisation impose un archivage de l’activité de conversation permanente, vous pouvez déployer le service de conformité de conversation permanente facultatif. Le service de conformité est responsable de l’archivage du contenu des conversation et des événements, comme le fait de rejoindre et de quitter des salles, dans le magasin de fichiers de conformité des conversations permanentes. Le service de conformité est installé sur chaque serveur de chat permanent d’un pool de conversations permanentes. 
  
### <a name="web-services"></a>Services web

Les services Web de chat permanent s’exécutent sur les serveurs front-end Skype entreprise. Les services web dépendent de IIS (Internet Information Services), et sont implémentés en tant que composants web :
  
- Les services web de conversation permanente pour le chargement et le téléchargement sont responsables de la publication et de la récupération des fichiers à partir des salles de conversation.
    
- Les services web de conversation permanente pour la gestion des salles de conversation sont chargés d’offrir aux utilisateurs la possibilité de gérer leurs salles de conversation et d’en créer des nouvelles.
    
## <a name="defining-requirements-for-your-organization"></a>Définition des exigences pour votre organisation

Si vous décidez de déployer le serveur de chat permanent, vous devez déterminer les besoins de votre organisation, puis définir la topologie, l’infrastructure et les exigences techniques pour répondre aux besoins de votre entreprise. Pour optimiser votre déploiement, vous devez répondre aux questions suivantes :
  
- Vous effectuez une migration à partir d’une version précédente du serveur de discussion de groupe ou d’une version antérieure de Chat Server ou vous déployez le serveur de chat permanent pour la première fois ?
    
- Qui peut utiliser le serveur de conversation permanente ? Vous spécifiez des stratégies de conversation permanente pour déterminer l’accès utilisateur au niveau global, site ou utilisateur.
    
- Combien d’utilisateurs vont avoir besoin de l’accès au serveur de conversation permanente ? Le serveur de conversation permanente prend en charge 150 000 utilisateurs disposant de privilèges d’accès (via une stratégie) et un nombre maximal de 80 000 utilisateurs simultanés. Un seul serveur de conversation permanente peut prendre en charge 20 000 utilisateurs connectés, et un seul pool de serveur de conversation permanente peut comporter jusqu’à 4 serveurs actifs pour un total de 80 000 utilisateurs connectés simultanément.
    
- Comment contrôler les étendues, les limites éthiques et l’accès ? Vous pouvez définir des catégories afin d’établir des limites et choisir les personnes autorisées à être présentes dans les salles créées dans chacune de ces catégories.
    
- Comment voulez-vous déterminer qui peut créer des salles ? Vous pouvez définir des créateurs qui peuvent créer des salles. Les créateurs peuvent affecter d’autres membres en tant que responsables de salles de conversation pour la gestion continue des salles.
    
- Comment créer des salles ? Server chat permanent fournit une fonctionnalité basée sur le Web pour la création et la gestion des salles. Ce problème peut être lancé à partir du client Skype entreprise. Vous pouvez choisir de définir une solution destinée aux clients qui implémente vos exigences métiers et vos flux de travail, et configure le serveur de chat permanent pour diriger les utilisateurs vers votre solution personnalisée.
    
- Quel genre de compléments voulez-vous approvisionner ? Les compléments améliorent l’expérience utilisateur en tirant parti du volet d’extensibilité du client Skype Entreprise afin de fournir un contexte pertinent pour la salle. Vous pouvez choisir les compléments généraux les plus utiles à vos yeux (par exemple, le site de votre entreprise, des documents de collaboration internes, etc.). Les gestionnaires de salles de conversation peuvent choisir l’un des compléments inscrits et l’associer à leurs salles, le cas échéant. 
    
- Quels sont vos besoins en matière de haute disponibilité et de récupération d’urgence ? Le serveur Chat permanent prend en charge la mise en miroir SQL Server et SQL Server clustering pour une disponibilité élevée. Dans le cas d’une reprise après sinistre, le serveur de chat permanent prend en charge jusqu’à 8 serveurs (4 de veille active et 4) dans un pool étiré avec l’envoi du journal SQL Server. 
    
- Existe-t-il des exigences réglementaires ? Si votre société se trouve dans un pays ou une région où les données doivent être conservées dans le pays, vous devrez peut-être déployer plusieurs pools de serveurs de chat permanent, chacun d’eux ayant une géographie spécifique. Une salle, une catégorie ou un complément n’étend pas le pool, il n’appartient qu’à un seul pool de serveurs de chat permanent. 
    
    > [!NOTE]
    > Le fait de disposer de plusieurs pools de serveurs de chat permanent ne vous 80 000 permet pas d’effectuer une mise à l’échelle supplémentaire La principale raison de la prise en charge de plusieurs pools de serveurs de chat permanent est de prendre en charge les préoccupations réglementaires. 
  
## <a name="for-more-information"></a>Pour plus d’informations

Pour plus d’informations sur l’installation et configuration du serveur de conversation permanente, voir les rubriques suivantes :
  
- Pour plus d’informations sur le déploiement d’un serveur de chat permanent, voir [déployer un serveur Chat permanent dans Skype entreprise server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md). 
    
- Pour plus d’informations sur la configuration des paramètres du déploiement de votre serveur Chat permanent, voir [gérer le serveur de chat permanent dans Skype entreprise Server 2015](../../manage/persistent-chat/persistent-chat.md).
    

