---
title: Catégories de conversation permanente, salles de conversation, rôles d’utilisateur dans Skype Entreprise Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 343a0563-9ca5-4ad0-b4f3-a72f1d7f1a81
description: 'Résumé : Lisez cette rubrique pour en savoir plus sur les catégories, les salles de conversation et les rôles utilisateur et administrateur pour le serveur de conversation permanents dans Skype pour Business Server 2015.'
ms.openlocfilehash: 73c7bd8863ba9560b8ef7d79b3e5dce1fbd797a1
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="persistent-chat-categories-chat-rooms-and-user-roles-in-skype-for-business-server-2015"></a>Catégories de conversation permanente, salles de conversation, rôles d’utilisateur dans Skype Entreprise Server 2015
 
**Résumé :** Lisez cette rubrique pour en savoir plus sur les catégories, les salles de conversation et les rôles utilisateur et administrateur pour le serveur de conversation permanents dans Skype pour Business Server 2015.
  
Vous pouvez contrôler l’accès aux salles de conversation en créant des catégories de salles de conversation, puis en indiquant l’accès aux catégories et aux salles de conversation dans les catégories. Vous pouvez également indiquer différents rôles administrateur. Cette rubrique décrit les ressources suivantes : 
  
- Catégories d’organisation des salles de conversation
    
- Salles de conversation et rôles utilisateur
    
- Rôles d’administrateur
    
## <a name="categories-for-organizing-chat-rooms"></a>Catégories d’organisation des salles de conversation

Les catégories permettent d’organiser les salles de conversation et de déterminer quels utilisateurs et groupes sont autorisés à créer les salles de conversation et à s’y joindre dans ces catégories. Chaque catégorie possède des propriétés déterminant les options disponibles pour les salles de conversation dans la catégorie. Vous contrôlez l’accès à une catégorie particulière en indiquant si un utilisateur dispose d’un accès autorisé ou refusé.
  
La logique principale du concept de membres autorisés ou refusés passe par des murs éthiques. Par exemple, il est courant dans les institutions bancaires et financières d’imposer des limites éthiques qui empêchent les courtiers et les analystes de partager des communications quand ils mettent en œuvre des stratégies et des conventions. Pour répondre à cette exigence, un administrateur peut créer des catégories de sorte qu’une seule catégorie autorise la création et l’utilisation des salles par les courtiers, et une autre catégorie autorise la création et l’utilisation des salles par les analystes. Il n’est possible d’ajouter un utilisateur en tant que membre de la salle si la catégorie parente l’en empêche.
  
> [!IMPORTANT]
> Membres autorisé et refusé dans une catégorie ne sont pas identique à un rôle de **membre** , qui s’applique à une salle de conversation permanents. > recherches affichent toutes les salles de conversation ouvertes et fermées pour lesquels l’utilisateur effectuant la recherche figure dans la liste de membres autorisé et refusé. Les salles secrètes ne sont pas affichées, sauf si l’utilisateur effectuant la recherche en est membre. L’utilisateur peut rechercher seulement les salles dont il est déjà membre, ou celles pour lesquelles il peut demander son appartenance. 
  
## <a name="chat-rooms-and-user-roles"></a>Salles de conversation et rôles utilisateur

En plus d’autorisés et membres refusés pour les catégories, vous pouvez également contrôler l’accès aux salles de conversation en spécifiant les rôles utilisateur suivants : auteur, responsable, membres et présentateur.
  
- **Créateur** : utilisateurs ayant l’autorisation de créer des salles de conversation. Ces utilisateurs figurent dans la liste de créateurs de certaines catégories : ils peuvent créer des salles de conversation dans cette catégorie et ils peuvent aussi assigner une appartenance selon la catégorie et assigner des responsables pour gérer la salle de conversation. L’utilisateur qui crée une salle de conversation est automatiquement ajouté en tant que responsable de la salle.
    
    > [!NOTE]
    > Le rôle de créateur se limite à disposer du droit de création des salles de conversation. C’est en réalité la promotion automatique au poste de responsable qui permet au créateur de redéfinir les appartenances, les responsables, etc. sur les services de conversation créés. 
  
    Ce rôle existe pour vous donner la possibilité de déterminer qui peut créer des salles de conversation dans votre organisation, en particulier si vous voulez centraliser la gestion de la création de salles de conversation pour appliquer des stratégies et des conventions, et par la suite déléguer la gestion des salles de conversation à d’autres utilisateurs de votre organisation.
    
- **Manager**: les utilisateurs qui gèrent les propriétés d’une salle de conversation. Les responsables de salle de conversation peuvent modifier la liste des membres (ajouter et supprimer des membres) et de modifier la liste des responsables de la salle de conversation (ajouter et supprimer des gestionnaires). Responsables de la salle de conversation peuvent s’ajouter à la liste des membres ou des présentateurs (pour les salles de l’auditorium) afin qu’ils puissent participer dans la salle de conversation. Responsables de la salle de conversation peuvent également désactiver les salles de conversation (les administrateurs peuvent interroger pour les salles de conversation désactivés et peuvent les supprimer définitivement). Les responsables peuvent modifier toutes les propriétés d’une salle de conversation, à l’exception de la catégorie de la salle de conversation. Seul l’administrateur de Chat persistante peut modifier la catégorie après que la salle de conversation a été créée.
    
    > [!IMPORTANT]
    > Si le responsable est aussi le créateur d’une autre catégorie, il peut modifier la catégorie de sorte à pouvoir créer des salles. 
  
- **Membres**: les utilisateurs qui sont membres d’une salle de conversation. Ces utilisateurs peuvent voir les salles de chat dans le répertoire (même si la salle de conversation est secrète), ainsi que s’abonner à la salle de conversation (y compris les options de métadonnées telles que les messages non lus, des filtres de leur ego et des filtres de mots clés) et participer à la salle de conversation (valider, à moins que la pièce est un espace auditorium où uniquement les présentateurs peuvent valider, obtenir du contenu et de rechercher.) Les utilisateurs qui ne sont pas membres de la salle de conversation, vous peuvent rechercher la salle de conversation si elles figurent dans la liste de membres autorisés de la catégorie, mais est nécessaire demander l’accès à rejoindre ces salles de conversation pour accéder au contenu. (Il n’y a aucune demande d’accès ou les approbations intégrées dans le système ; ils sont faits à l’extérieur par courrier électronique, téléphone ou autres formes de contacts).
    
- **Présentateur** : utilisateurs pouvant publier dans un auditorium.
    
## <a name="administrator-roles"></a>Rôles d’administrateur

Rôles d’administrateur pour le serveur de conversation permanent sont les suivantes :
  
- **Administrateur de Chat persistant**: rôle de l’administrateur de Chat persistants peut gérer les salles de conversation (modifier toutes les propriétés, y compris l’appartenance, les responsables, les catégories, salles de marque comme désactivé), ainsi que créer et gérer des catégories de salles de conversation qui définissent qui peut créer et accéder aux salles de conversation. Les administrateurs peuvent également marquer des salles de conversation comme étant désactivés et nettoyer les salles de conversation qui ne sont plus actifs. Les administrateurs ne sont pas soumis aux restrictions créateurs ou des membres autorisés. Les administrateurs peuvent créer n’importe quel type de salle de conversation et ajouter eux-mêmes en tant que membre d’une salle de conversation. Les administrateurs peuvent également modifier et gérer la configuration Chat persistant (propriétés du pool, les paramètres globaux et la configuration de la conformité) et peut également planifier et mettre en œuvre la migration à partir d’un déploiement de groupe Chat Server antérieure à Skype pour Business Server 2015 Serveur de conversation permanent.
    
    Administrateurs de Chat persistants sont en mesure d’administrer le serveur de Chat persistant à distance à l’aide des applets de commande Windows PowerShell (c'est-à-dire, à partir d’un autre ordinateur que le serveur Chat persistant). Serveur de Chat persistant vérifie que l’administrateur de Chat persistant est un membre du groupe administrateur local RTC Local sur le persistant Chat Server serveur frontal.
    
- **Skype pour Business Server 2015 Administrator**: administrateur de l’entreprise globale pour Skype pour 2015 de serveur d’entreprise responsable du déploiement.
    
- **Responsable des opérations** : utilisateur responsable de la gestion des opérations quotidiennes.
    
- **Développeurs et partenaires tiers** : les développeurs tiers développent le système, en particulier en fournissant une solution de mur éthique pour les conversations de groupe, des outils et un support pour la conformité, des clients web/mobile et une infrastructure pour le développement Bot.
    
## <a name="for-more-information"></a>Pour plus d’informations

Pour plus d’informations sur la configuration et la gestion de salles de conversation et de rôles utilisateur, reportez-vous aux rubriques suivantes :
  
- [Créer un administrateur de Chat persistant dans Skype pour Business Server 2015](../../deploy/deploy-persistent-chat-server/create-a-persistent-chat-administrator.md)
    
- [Gérer les catégories dans le serveur Chat persistant dans Skype pour Business Server 2015](../../manage/persistent-chat/categories.md)
    
- [Gérer les salles de conversation dans un serveur de conversation permanent dans Skype pour Business Server 2015](../../manage/persistent-chat/chat-rooms.md)
    

