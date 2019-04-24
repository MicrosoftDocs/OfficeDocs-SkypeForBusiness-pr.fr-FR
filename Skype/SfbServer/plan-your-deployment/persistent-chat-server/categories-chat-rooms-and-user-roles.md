---
title: Catégories de conversation permanente, salles de conversation, rôles d’utilisateur dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 343a0563-9ca5-4ad0-b4f3-a72f1d7f1a81
description: 'Résumé : Lisez cette rubrique pour en savoir plus sur les catégories, salles de conversation et les rôles utilisateur et administrateur pour le serveur de conversation permanente dans Skype pour Business Server 2015.'
ms.openlocfilehash: 0a65d5d8944d28ba834fac461051f23fcdd98800
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213780"
---
# <a name="persistent-chat-categories-chat-rooms-and-user-roles-in-skype-for-business-server-2015"></a>Catégories de conversation permanente, salles de conversation, rôles d’utilisateur dans Skype Entreprise Server 2015
 
**Résumé :** Lisez cette rubrique pour en savoir plus sur les catégories, salles de conversation et les rôles utilisateur et administrateur pour le serveur de conversation permanente dans Skype pour Business Server 2015.
  
Vous pouvez contrôler l’accès aux salles de conversation en créant des catégories de salles de conversation, puis en indiquant l’accès aux catégories et aux salles de conversation dans les catégories. Vous pouvez également indiquer différents rôles administrateur. Cette rubrique décrit les ressources suivantes : 
  
- Catégories d’organisation des salles de conversation
    
- Salles de conversation et rôles utilisateur
    
- Rôles d’administrateur

> [!NOTE] 
> Conversation permanente est disponible dans Skype pour Business Server 2015, mais n’est plus pris en charge dans Skype pour Business Server 2019. La même fonctionnalité est disponible dans les équipes. Pour plus d’informations, voir [parcours de Skype pour les entreprises aux équipes de Microsoft](/microsoftteams/journey-skypeforbusiness-teams). Si vous devez utiliser la conversation permanente, vos choix est pour migrer les utilisateurs ayant besoin de cette fonctionnalité aux équipes, ou pour continuer à utiliser Skype pour Business Server 2015. 
    
## <a name="categories-for-organizing-chat-rooms"></a>Catégories d’organisation des salles de conversation

Les catégories permettent d’organiser les salles de conversation et de déterminer quels utilisateurs et groupes sont autorisés à créer les salles de conversation et à s’y joindre dans ces catégories. Chaque catégorie possède des propriétés déterminant les options disponibles pour les salles de conversation dans la catégorie. Vous contrôlez l’accès à une catégorie particulière en indiquant si un utilisateur dispose d’un accès autorisé ou refusé.
  
La logique principale du concept de membres autorisés ou refusés passe par des murs éthiques. Par exemple, il est courant dans les institutions bancaires et financières d’imposer des limites éthiques qui empêchent les courtiers et les analystes de partager des communications quand ils mettent en œuvre des stratégies et des conventions. Pour répondre à cette exigence, un administrateur peut créer des catégories de sorte qu’une seule catégorie autorise la création et l’utilisation des salles par les courtiers, et une autre catégorie autorise la création et l’utilisation des salles par les analystes. Il n’est possible d’ajouter un utilisateur en tant que membre de la salle si la catégorie parente l’en empêche.
  
> [!IMPORTANT]
> Membres autorisés et refusés dans une catégorie ne sont pas les mêmes en tant que **membre du** rôle, qui s’applique à un room.> de conversation permanente affichage recherche tous les ouvrir et de fermeture des salles de conversation pour lequel l’utilisateur qui effectue la recherche est dans l’et liste des membres refusés. Les salles secrètes ne sont pas affichées, sauf si l’utilisateur effectuant la recherche en est membre. L’utilisateur peut rechercher seulement les salles dont il est déjà membre, ou celles pour lesquelles il peut demander son appartenance. 
  
## <a name="chat-rooms-and-user-roles"></a>Salles de conversation et rôles utilisateur

Outre autorisés et membres refusés pour les catégories, vous pouvez contrôler l’accès aux salles de conversation en spécifiant les rôles utilisateur suivants : auteur, responsable, membres et présentateur.
  
- **Créateur** : utilisateurs ayant l’autorisation de créer des salles de conversation. Ces utilisateurs figurent dans la liste de créateurs de certaines catégories : ils peuvent créer des salles de conversation dans cette catégorie et ils peuvent aussi assigner une appartenance selon la catégorie et assigner des responsables pour gérer la salle de conversation. L’utilisateur qui crée une salle de conversation est automatiquement ajouté en tant que responsable de la salle.
    
    > [!NOTE]
    > Le rôle de créateur se limite à disposer du droit de création des salles de conversation. C’est en réalité la promotion automatique au poste de responsable qui permet au créateur de redéfinir les appartenances, les responsables, etc. sur les services de conversation créés. 
  
    Ce rôle existe pour vous donner la possibilité de déterminer qui peut créer des salles de conversation dans votre organisation, en particulier si vous voulez centraliser la gestion de la création de salles de conversation pour appliquer des stratégies et des conventions, et par la suite déléguer la gestion des salles de conversation à d’autres utilisateurs de votre organisation.
    
- **Gestionnaire**: les utilisateurs qui gèrent les propriétés d’une salle de conversation. Les responsables de salle de conversation peuvent modifier la liste des membres (ajouter et supprimer des membres) et modifier la liste de gestionnaires de salle de conversation (ajouter et supprimer des gestionnaires). Gestionnaires de salles de conversation peuvent s’ajouter à la liste des membres ou présentateurs (pour les salles auditorium) afin qu’ils peuvent participer à la salle de conversation. Gestionnaires de salles de conversation peuvent également désactiver les salles de conversation (les administrateurs peuvent interroger des salles de conversation désactivés et peuvent supprimer définitivement les). Les gestionnaires peuvent modifier toutes les propriétés d’une salle de conversation, à l’exception de la catégorie de la salle de conversation. Seul l’administrateur de conversation permanente peut modifier la catégorie après avoir créé la salle de conversation.
    
    > [!IMPORTANT]
    > Si le responsable est aussi le créateur d’une autre catégorie, il peut modifier la catégorie de sorte à pouvoir créer des salles. 
  
- **Membres**: les utilisateurs qui sont membres d’une salle de conversation. Ces utilisateurs peuvent voir les salles de conversation dans le répertoire (même si la salle de conversation est secrète), ainsi que s’abonner à la salle de conversation (y compris les options de métadonnées telles que les messages non lus, filtre ego et des filtres de mot clé) et participer à la salle de conversation (peuvent publier, sauf si la salle est un auditorium où seuls les présentateurs peuvent publier, obtenir le contenu et de recherche). Les utilisateurs qui ne sont pas membres de la salle de conversation, vous pouvant rechercher la salle de conversation si elles se trouvent dans la liste des membres autorisés de la catégorie, mais devez demander l’accès à ces salles de conversation pour accéder au contenu. (Il n’existe aucune demande d’accès ou les approbations intégrées au système ; ces sont effectuées en externe par courrier électronique, le téléphone ou autres formes de contacts).
    
- **Présentateur** : utilisateurs pouvant publier dans un auditorium.
    
## <a name="administrator-roles"></a>Rôles d’administrateur

Rôles d’administrateur pour le serveur de conversation permanente sont les suivantes :
  
- **Administrateur de conversation permanente**: rôle de l’administrateur de conversation permanente peut gérer des salles de conversation (modifier toutes les propriétés, y compris l’appartenance, les responsables, catégories, salles de marquer comme désactivé), ainsi que créer et gérer les catégories de salle de conversation qui définissent les personnes peut créer et accéder aux salles de conversation. Administrators can also mark chat rooms as disabled and clean up chat rooms that are no longer active. Administrators are not subject to the Creators or Allowed Members restrictions. Administrators can create any kind of chat room and add themselves as a member to any chat room. Les administrateurs peuvent également modifier et gérer la configuration de conversation permanente (propriétés du pool, les paramètres globaux et configuration de conformité) et peut également planifier et implémenter migration à partir d’un déploiement de serveur de conversation de groupe antérieur à Skype pour Business Server 2015 Serveur de conversation permanente.
    
    Les administrateurs de conversation permanente sont en mesure d’administrer des serveurs de conversation permanente à l’aide des applets de commande Windows PowerShell à distance (c'est-à-dire, à partir d’un ordinateur autre que le serveur de conversation permanente). Serveur de conversation permanente vérifie que l’administrateur de conversation permanente est un membre du groupe administrateur local RTC Local sur le Persistent Chat Server serveur frontal.
    
- **Skype pour administrateur Business Server 2015**: administrateur de l’entreprise globale pour Skype pour Business Server 2015 responsable du déploiement.
    
- **Responsable des opérations** : utilisateur responsable de la gestion des opérations quotidiennes.
    
- **Développeurs et partenaires tiers** : les développeurs tiers développent le système, en particulier en fournissant une solution de mur éthique pour les conversations de groupe, des outils et un support pour la conformité, des clients web/mobile et une infrastructure pour le développement Bot.
    
## <a name="for-more-information"></a>Pour plus d’informations

Pour plus d’informations sur la configuration et la gestion de salles de conversation et de rôles utilisateur, reportez-vous aux rubriques suivantes :
  
- [Création d’un administrateur de conversation permanente dans Skype Entreprise Server 2015](../../deploy/deploy-persistent-chat-server/create-a-persistent-chat-administrator.md)
    
- [Gestion des catégories sur un serveur de conversation permanente dans Skype Entreprise Server 2015](../../manage/persistent-chat/categories.md)
    
- [Gestion des salles de conversation sur un serveur de conversation permanente dans Skype Entreprise Server 2015](../../manage/persistent-chat/chat-rooms.md)
    

