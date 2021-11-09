---
title: Catégories de conversation permanente, salles de conversation et rôles d’utilisateur dans Skype Entreprise Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 8/17/2015
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 343a0563-9ca5-4ad0-b4f3-a72f1d7f1a81
description: 'Résumé : Consultez cette rubrique pour en savoir plus sur les catégories, les salles de conversation et les rôles d’utilisateur et d’administrateur pour le serveur de conversation permanente Skype Entreprise Server 2015.'
ms.openlocfilehash: 212e731da29bc327487e0e6512db413546d20670
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60857251"
---
# <a name="persistent-chat-categories-chat-rooms-and-user-roles-in-skype-for-business-server-2015"></a>Catégories de conversation permanente, salles de conversation et rôles d’utilisateur dans Skype Entreprise Server 2015
 
**Résumé :** Consultez cette rubrique pour en savoir plus sur les catégories, les salles de conversation et les rôles d’utilisateur et d’administrateur pour le serveur de conversation permanente Skype Entreprise Server 2015.
  
Vous pouvez contrôler l’accès aux salles de conversation en créant des catégories de salles de conversation, puis en spécifiant l’accès aux catégories et salles de conversation au sein de catégories. Vous pouvez également spécifier différents rôles d’administrateur. Cette rubrique décrit : 
  
- Catégories d’organisation des salles de conversation
    
- Salles de conversation et rôles d’utilisateur
    
- Rôles d'administrateur

> [!NOTE] 
> La conversation permanente est disponible Skype Entreprise Server 2015, mais n’est plus prise en charge Skype Entreprise Server 2019. La même fonctionnalité est disponible dans Teams. Pour plus d’informations, voir [Mise en Microsoft Teams mise à niveau.](/microsoftteams/upgrade-start-here) Si vous devez utiliser la conversation permanente, vous pouvez soit migrer des utilisateurs nécessitant cette fonctionnalité vers Teams, soit continuer à utiliser Skype Entreprise Server 2015. 
    
## <a name="categories-for-organizing-chat-rooms"></a>Catégories d’organisation des salles de conversation

Les catégories vous permet d’organiser des salles de conversation et de contrôler quels utilisateurs et groupes sont autorisés à créer ou rejoindre les salles de conversation au sein de ces catégories. Chaque catégorie possède des propriétés associées qui déterminent les options disponibles pour les salles de conversation au sein de la catégorie. Vous contrôlez l’accès à une catégorie particulière en spécifiant si un utilisateur est autorisé ou refusé.
  
La logique principale du concept de membres autorisés et refusés est la cloison déontologique. Par exemple, il est courant dans les institutions bancaires et financières d’imposer des limites éthiques qui empêchent les courtiers et les analystes de partager des communications quand ils mettent en œuvre des stratégies et des conventions. Pour répondre à cette exigence, un administrateur peut créer des catégories de sorte qu’une seule catégorie autorise la création et l’utilisation des salles par les courtiers, et une autre catégorie autorise la création et l’utilisation des salles par les analystes. Les utilisateurs ne peuvent pas être ajoutés en tant que membres d’une salle de conversation si la catégorie parente l’empêche.
  
> [!IMPORTANT]
> Les membres autorisés et refusés d’une  catégorie ne sont pas identiques à un rôle de membre, ce qui s’applique à une salle de conversation permanente.> Les recherches affichent toutes les salles de conversation ouvertes et fermées pour lesquelles l’utilisateur qui effectue la recherche figure dans la liste des membres autorisés et refusés. Les salles secrètes ne sont pas affichées, sauf si l’utilisateur effectuant la recherche en est membre. L’utilisateur peut rechercher seulement les salles dont il est déjà membre, ou celles pour lesquelles il peut demander son appartenance. 
  
## <a name="chat-rooms-and-user-roles"></a>Salles de conversation et rôles d’utilisateur

Outre les membres autorisés et refusés pour les catégories, vous pouvez également contrôler l’accès aux salles de conversation en spécifiant les rôles d’utilisateur suivants : Créateur, Responsable, Membre et Présentateur.
  
- **Créateur**: utilisateurs autorisés à créer des salles de conversation. Ces utilisateurs sont dans la liste créateurs de certaines catégories : ils peuvent créer des salles de conversation dans cette catégorie, et ils peuvent également affecter l’appartenance en fonction de la catégorie et affecter des responsables pour gérer la salle de conversation. L’utilisateur qui crée une salle de conversation est automatiquement ajouté en tant que responsable de la salle.
    
    > [!NOTE]
    > Le rôle de créateur se limite à disposer du droit de création des salles de conversation. C’est en réalité la promotion automatique au poste de responsable qui permet au créateur de redéfinir les appartenances, les responsables, etc. sur les services de conversation créés. 
  
    Ce rôle existe pour vous donner la possibilité de déterminer qui peut créer des salles de conversation dans votre organisation, en particulier si vous voulez centraliser la gestion de la création de salles de conversation pour appliquer des stratégies et des conventions, et par la suite déléguer la gestion des salles de conversation à d’autres utilisateurs de votre organisation.
    
- **Responsable :** utilisateurs qui gèrent les propriétés d’une salle de conversation. Les gestionnaires de salles de conversation peuvent modifier la liste des membres (ajouter et supprimer des membres), et modifier la liste des gestionnaires de salles de conversation (ajouter et supprimer des responsables). Les responsables de salles de conversation peuvent s’ajouter eux-mêmes à la liste des membres ou des présentateurs (pour les salles auditorium) afin de pouvoir participer à la salle de conversation. Les gestionnaires de salles de conversation peuvent également désactiver les salles de conversation (les administrateurs peuvent interroger des salles de conversation désactivées et les supprimer définitivement). Les responsables peuvent modifier toutes les propriétés d’une salle de conversation, à l’exception de la catégorie de la salle de conversation. Seul l’administrateur de conversation permanente peut modifier la catégorie une fois la salle de conversation créée.
    
    > [!IMPORTANT]
    > Si le responsable est aussi le créateur d’une autre catégorie, il peut modifier la catégorie de sorte à pouvoir créer des salles. 
  
- **Membre**: utilisateurs membres d’une salle de conversation. Ces utilisateurs peuvent voir les salles de conversation dans l’annuaire (même si la salle de conversation est secrète), ainsi que s’abonner à la salle de conversation (y compris les options de métadonnées telles que les messages non lus, les filtres ego et les filtres de mots clés) et participer à la salle de conversation (peut publier, sauf si la salle est un auditorium où seuls les présentateurs peuvent publier,  obtenir du contenu et effectuer une recherche). Les utilisateurs qui ne sont pas membres de la salle de conversation peuvent rechercher la salle de conversation s’ils sont dans la liste Des membres autorisés de la catégorie, mais doivent demander l’accès pour rejoindre ces salles de conversation pour accéder au contenu. (Aucune demande d’accès ou approbation n’est intégrée au système ; celles-ci sont réalisées en externe par courrier électronique, par téléphone ou par d’autres formes de contact.)
    
- **Présentateur** : utilisateurs pouvant publier dans un auditorium.
    
## <a name="administrator-roles"></a>Rôles d'administrateur

Les rôles d’administrateur pour le serveur de conversation permanente sont les suivants :
  
- Administrateur de conversation permanente : le rôle Administrateur de conversation permanente peut gérer les salles de conversation (modifier toutes les propriétés, y compris l’appartenance, les responsables, les catégories, marquer les salles comme désactivées), ainsi que créer et gérer des catégories de salles de conversation qui définissent qui peut créer des salles de conversation et y accéder. Les administrateurs peuvent aussi marquer des salles de conversation comme désactivées et effacer celles qui ne sont plus actives. Les administrateurs ne sont pas soumis aux restrictions des créateurs ou des membres autorisés. Ils peuvent créer toutes sortes de salle de conversation et s’ajouter eux-mêmes en tant que membres de n’importe quelle salle de conversation. Les administrateurs peuvent également modifier et gérer la configuration de conversation permanente (propriétés du pool, paramètres globaux et configuration de la conformité), et peuvent également planifier et implémenter la migration d’un ancien déploiement de serveur de conversation de groupe vers Skype Entreprise Server 2015 Persistent Chat Server.
    
    Les administrateurs de conversation permanente peuvent administrer le serveur de conversation permanente à l’aide de Windows PowerShell cmdlets distantes (c’est-à-dire, à partir d’un ordinateur autre que le serveur de conversation permanente). Le serveur de conversation permanente vérifie que l’administrateur de conversation permanente est membre du groupe local Administrateur local RTC sur le serveur frontal du serveur de conversation permanente.
    
- **Skype Entreprise Server 2015 : administrateur** général de l’entreprise Skype Entreprise Server 2015 responsable du déploiement.
    
- **Responsable des opérations** : utilisateur responsable de la gestion des opérations quotidiennes.
    
- **Développeurs et partenaires tiers** : les développeurs tiers développent le système, en particulier en fournissant une solution de mur éthique pour les conversations de groupe, des outils et un support pour la conformité, des clients web/mobile et une infrastructure pour le développement Bot.
    
## <a name="for-more-information"></a>Pour plus d'informations

Pour plus d’informations sur la configuration et la gestion des salles de conversation et des rôles d’utilisateur, consultez les rubriques suivantes :
  
- [Créer un administrateur de conversation permanente dans Skype Entreprise Server 2015](../../deploy/deploy-persistent-chat-server/create-a-persistent-chat-administrator.md)
    
- [Gérer les catégories dans le serveur de conversation permanente dans Skype Entreprise Server 2015](../../manage/persistent-chat/categories.md)
    
- [Gestion des salles de conversation dans le serveur de conversation permanente Skype Entreprise Server 2015](../../manage/persistent-chat/chat-rooms.md)
    

