---
title: Catégories de conversation permanente, salles de conversation, rôles d’utilisateur dans Skype Entreprise Server 2015
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
ms.assetid: 343a0563-9ca5-4ad0-b4f3-a72f1d7f1a81
description: 'Résumé : cette rubrique vous explique en plus des catégories, des salles de conversation et des rôles d’utilisateur et d’administrateur pour le serveur de chat permanent dans Skype entreprise Server 2015.'
ms.openlocfilehash: 03a7b68a9728b60ebae25081e3e974bb61b0fc5b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815762"
---
# <a name="persistent-chat-categories-chat-rooms-and-user-roles-in-skype-for-business-server-2015"></a>Catégories de conversation permanente, salles de conversation, rôles d’utilisateur dans Skype Entreprise Server 2015
 
**Résumé :** Consultez cette rubrique pour en savoir plus sur les catégories, les salles de conversation et les rôles d’utilisateur et d’administrateur pour le serveur de chat permanent dans Skype entreprise Server 2015.
  
Vous pouvez contrôler l’accès aux salles de conversation en créant des catégories de salles de conversation, puis en indiquant l’accès aux catégories et aux salles de conversation dans les catégories. Vous pouvez également indiquer différents rôles administrateur. Cette rubrique décrit les ressources suivantes : 
  
- Catégories d’organisation des salles de conversation
    
- Salles de conversation et rôles utilisateur
    
- Rôles d’administrateur

> [!NOTE] 
> La conversation permanente est disponible dans Skype entreprise Server 2015, mais n’est plus prise en charge dans Skype entreprise Server 2019. La même fonctionnalité est disponible dans Microsoft Teams. Pour plus d’informations, reportez-vous à la rubrique mise [en route de Microsoft teams](/microsoftteams/upgrade-start-here). Si vous avez besoin d’utiliser la conversation permanente, vous pouvez migrer les utilisateurs qui ont besoin de cette fonctionnalité pour teams ou continuer à utiliser Skype entreprise Server 2015. 
    
## <a name="categories-for-organizing-chat-rooms"></a>Catégories d’organisation des salles de conversation

Les catégories permettent d’organiser les salles de conversation et de déterminer quels utilisateurs et groupes sont autorisés à créer les salles de conversation et à s’y joindre dans ces catégories. Chaque catégorie possède des propriétés déterminant les options disponibles pour les salles de conversation dans la catégorie. Vous contrôlez l’accès à une catégorie particulière en indiquant si un utilisateur dispose d’un accès autorisé ou refusé.
  
La logique principale du concept de membres autorisés ou refusés passe par des murs éthiques. Par exemple, il est courant dans les institutions bancaires et financières d’imposer des limites éthiques qui empêchent les courtiers et les analystes de partager des communications quand ils mettent en œuvre des stratégies et des conventions. Pour répondre à cette exigence, un administrateur peut créer des catégories de sorte qu’une seule catégorie autorise la création et l’utilisation des salles par les courtiers, et une autre catégorie autorise la création et l’utilisation des salles par les analystes. Il n’est possible d’ajouter un utilisateur en tant que membre de la salle si la catégorie parente l’en empêche.
  
> [!IMPORTANT]
> Les membres autorisés et refusés d’une catégorie ne sont pas les mêmes que les rôles de **membre** qui s’appliquent à une salle de conversation permanente. > recherche affiche toutes les salles de conversation ouvertes et fermées pour lesquelles l’utilisateur exécute la recherche dans la liste des membres autorisés et refusés. Les salles secrètes ne sont pas affichées, sauf si l’utilisateur effectuant la recherche en est membre. L’utilisateur peut rechercher seulement les salles dont il est déjà membre, ou celles pour lesquelles il peut demander son appartenance. 
  
## <a name="chat-rooms-and-user-roles"></a>Salles de conversation et rôles utilisateur

Outre les membres autorisés et refusés pour les catégories, vous pouvez également contrôler l’accès aux salles de conversation en spécifiant les rôles d’utilisateur suivants : créateur, responsable, membre et présentateur.
  
- **Créateur** : utilisateurs ayant l’autorisation de créer des salles de conversation. Ces utilisateurs figurent dans la liste de créateurs de certaines catégories : ils peuvent créer des salles de conversation dans cette catégorie et ils peuvent aussi assigner une appartenance selon la catégorie et assigner des responsables pour gérer la salle de conversation. L’utilisateur qui crée une salle de conversation est automatiquement ajouté en tant que responsable de la salle.
    
    > [!NOTE]
    > Le rôle de créateur se limite à disposer du droit de création des salles de conversation. C’est en réalité la promotion automatique au poste de responsable qui permet au créateur de redéfinir les appartenances, les responsables, etc. sur les services de conversation créés. 
  
    Ce rôle existe pour vous donner la possibilité de déterminer qui peut créer des salles de conversation dans votre organisation, en particulier si vous voulez centraliser la gestion de la création de salles de conversation pour appliquer des stratégies et des conventions, et par la suite déléguer la gestion des salles de conversation à d’autres utilisateurs de votre organisation.
    
- **Responsable**: utilisateurs qui gèrent les propriétés d’une salle de conversation. Les gestionnaires de salle de conversation peuvent modifier la liste des membres (ajouter et supprimer des membres) et modifier la liste des gestionnaires de salle de conversation (ajout et suppression de gestionnaires). Les gestionnaires de salle de conversation peuvent s’ajouter eux-mêmes à la liste membres ou présentateurs (pour les salles d’Auditorium) pour pouvoir participer à la salle de conversation. Les gestionnaires de salle de conversation peuvent également désactiver les salles de conversation (les administrateurs peuvent rechercher des salles de conversation désactivées et pouvoir les supprimer définitivement). Les responsables peuvent modifier toutes les propriétés d’une salle de conversation, à l’exception de la catégorie de la salle de conversation. Seul l’administrateur de chat permanent peut changer la catégorie après la création de la salle de conversation.
    
    > [!IMPORTANT]
    > Si le responsable est aussi le créateur d’une autre catégorie, il peut modifier la catégorie de sorte à pouvoir créer des salles. 
  
- **Membre**: utilisateurs membres d’une salle de conversation. Ces utilisateurs peuvent voir les salles de conversation dans l’annuaire (même si la salle de conversation est secrète), ainsi que s’abonner à la salle de conversation (y compris les options de métadonnées, telles que les messages non lus, les filtres figure et les filtres par Mots clés) et participer à la salle de conversation (peut publier, sauf si la salle est une salle d’Auditorium dans laquelle seuls les présentateurs peuvent publier, obtenir du contenu et effectuer une recherche. Les utilisateurs qui ne sont pas membres de la salle de conversation peuvent rechercher une salle de conversation s’ils figurent dans la liste des membres autorisés de la catégorie, mais doivent demander l’accès pour joindre ces salles de conversation et accéder au contenu. (Il n’y a pas d’accès ou d’approbations de requête intégré au système ; ces opérations sont effectuées en externe par e-mail, par téléphone ou d’autres types de contacts.)
    
- **Présentateur** : utilisateurs pouvant publier dans un auditorium.
    
## <a name="administrator-roles"></a>Rôles d’administrateur

Vous trouverez ci-après les rôles d’administrateur pour le serveur de chat permanent :
  
- **Administrateur de chat permanent**: le rôle d’administrateur de chat permanent peut gérer des salles de conversation (modifier toutes les propriétés, y compris l’appartenance, les responsables, les catégories, marquer des salles comme désactivées), et créer et gérer des catégories de salle de conversation qui définissent les personnes autorisées à créer des salles de conversation. Administrators can also mark chat rooms as disabled and clean up chat rooms that are no longer active. Administrators are not subject to the Creators or Allowed Members restrictions. Administrators can create any kind of chat room and add themselves as a member to any chat room. Les administrateurs peuvent également modifier et gérer la configuration de chat permanent (propriétés du pool, paramètres globaux et configuration de la conformité) et peut également planifier et implémenter une migration à partir d’un ancien déploiement du serveur de discussion de groupe sur Skype entreprise Server 2015 Serveur de chat permanent.
    
    Les administrateurs de chat permanent peuvent administrer le serveur de chat permanent en utilisant des applets de commande Windows PowerShell à distance (à partir d’un ordinateur autre que le serveur de chat permanent). Serveur de chat permanent vérifie que l’administrateur de chat permanent est membre du groupe local de l’administrateur local RTC sur le serveur frontal du serveur Chat permanent.
    
- **Administrateur 2015 de Skype entreprise Server**: administrateur global d’entreprise pour Skype entreprise Server 2015 responsables du déploiement.
    
- **Responsable des opérations** : utilisateur responsable de la gestion des opérations quotidiennes.
    
- **Développeurs et partenaires tiers** : les développeurs tiers développent le système, en particulier en fournissant une solution de mur éthique pour les conversations de groupe, des outils et un support pour la conformité, des clients web/mobile et une infrastructure pour le développement Bot.
    
## <a name="for-more-information"></a>Pour plus d’informations

Pour plus d’informations sur la configuration et la gestion de salles de conversation et de rôles utilisateur, reportez-vous aux rubriques suivantes :
  
- [Création d’un administrateur de conversation permanente dans Skype Entreprise Server 2015](../../deploy/deploy-persistent-chat-server/create-a-persistent-chat-administrator.md)
    
- [Gestion des catégories sur un serveur de conversation permanente dans Skype Entreprise Server 2015](../../manage/persistent-chat/categories.md)
    
- [Gestion des salles de conversation sur un serveur de conversation permanente dans Skype Entreprise Server 2015](../../manage/persistent-chat/chat-rooms.md)
    

