---
title: Description de l’appartenance à la conversation permanente
TOCTitle: Description de l’appartenance à la conversation permanente
ms:assetid: 900392d6-6e9f-4dae-93d6-39d7474409ef
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398730(v=OCS.15)
ms:contentKeyID: 49298065
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Description de l’appartenance à la conversation permanente

 

_**Dernière rubrique modifiée :** 2013-02-22_

L’accès des utilisateurs aux salles de conversation permanente est géré par l’appartenance ; les utilisateurs doivent être membres d’une salle de conversation pour être en mesure de publier et de lire des messages. Seuls les **Présentateurs** qui ont une affiliation aux salles de conversation sont autorisés à utiliser la **publication dans des auditoriums**. Un auditorium est un type de salle de conversation (l’autre type est **Normal**), dans lequel seuls les présentateurs peuvent publier et tout le monde peut lire.

De plus, les salles de conversation permanente suivent les règles de catégorie. Pour plus d’informations sur les catégories, reportez-vous à [Gestion des catégories, des salles et des compléments dans Lync Server 2013](lync-server-2013-managing-categories-rooms-and-add-ins.md), et les sections « Fonctionnement de l’étendue des catégories » et « Stratégies de catégorie de salle » dans la suite de cette rubrique.

Un administrateur de conversation permanente peut créer et gérer des catégories de salle de conversation. Dans le cadre de la création et de la gestion des catégories de salle de conversation, l’administrateur de conversation permanente peut configurer des principaux ( services de domaine Active Directory groupes, conteneurs et utilisateurs) qui sont membres ou créateurs des salles de conversation d’une catégorie donnée et y ont accès.

## Services de domaine Active Directory et conversation permanente

serveur de conversations permanentes repose sur Active Directory pour le pool d’utilisateurs de conversation permanente internes. Après avoir installé conversation permanente, vous pouvez ajouter les domaines et groupes d’utilisateurs à la catégorie de la salle. Vous pouvez ensuite ajouter ces utilisateurs et groupes à l’appartenance de vos catégories de salles.

> [!IMPORTANT]  
> Vous devez vérifier qu’aucun doublon de noms n’existe pour les utilisateurs souhaitant modifier leur(s) salle(s) conversation permanente. Si des doublons de noms existent, modifiez-les pour débloquer les utilisateurs afin qu’ils puissent apporter certaines modifications. Si un utilisateur présente des doublons de noms dans Active Directory et qu’il tente d’effectuer plusieurs modifications dans sa ou ses salles, un message d’erreur l’invitant à contacter l’administrateur pour résoudre ce problème s’affiche.

## Fonctionnement de l’étendue des catégories

Une catégorie spécifie tous les utilisateurs et les groupes qui peuvent être membres dans une liste d’appartenance d’une salle de conversation permanente de cette catégorie, en fonction de la propriété **AllowedMembers**. Par exemple, si vous définissez la propriété **AllowedMembers** de la catégorie à contoso.com, vous pouvez ajouter n’importe quel groupe ou utilisateur à *Contoso* en tant que membre des salles de conversation de cette catégorie. Si vous définissez **AllowedMembers** d’une catégorie à *Ventes* , seuls les groupes et utilisateurs de cette liste de distribution peuvent être ajoutés en tant que membre des salles de conversation de cette catégorie. De la même façon, la propriété **Créateurs** vous permet de contrôler qui peut créer des salles de conversation dans la catégorie. Une fois la salle de conversation créée, toute personne membre du groupe **AllowedMembers** peut être désignée en tant que **Gestionnaire** pour les opérations de gestion courantes des salles (par exemple, modifications des membres et approbations).

La définition de **AllowedMembers** et **Créateurs** pour une catégorie comporte les avantages suivants :

  - Toutes les salles de conversation de cette catégorie sont liées par des limitations définies au niveau de la catégorie. Vous pouvez utiliser cela pour isoler des salles de conversation en fonction des besoins et des stratégies d’accès.

  - Un utilisateur qui se trouve dans la liste **Créateurs** peut créer des salles de conversation dans cette catégorie. Si vous voulez mettre en place un système qui limite le nombre de personnes de votre organisation ayant la possibilité de créer des salles de conversation, ce contrôle peut être utilisé.

## Stratégies de catégorie de salle

Une propriété **AllowedMembers** de catégorie doit inclure tous les utilisateurs qui participeront aux salles de conversation permanente de cette catégorie. En fonction des besoins de protection de vos données et pour contrôler les niveaux d’accès, vous pouvez définir une ou plusieurs catégories pour spécifier qui peut effectuer des recherches dans les salles et y participer. Si vous ne voulez autoriser qu’un groupe d’utilisateurs donnés (support technique ou employés à plein temps) à créer des salles, vous pouvez définir l’étendue de **Créateurs** d’une catégorie pour répondre à ce besoin.

Les catégories peuvent également être utilisées pour créer des séparations déontologiques. Les séparations déontologiques permettent d’éviter les conflits d’intérêts dans votre organisation. Par exemple, un administrateur peut créer des salles de conversation dans une catégorie uniquement pour les opérateurs en bourse, et d’autres salles dans une autre catégorie pour les analystes.

> [!NOTE]  
> Les utilisateurs fédérés ne sont pas pris en charge sur un serveur de conversations permanentesLync Server 2013. Les conversations d’utilisateurs fédérés des anciennes versions du serveur de conversations permanentes seront migrées. Les utilisateurs fédérés sont ajoutés en tant que principaux désactivés.

## Limitation des membres aux groupes d’utilisateurs

Lorsque vous ajoutez un domaine à une catégorie, les groupes d’utilisateurs dont les objets de groupe sont contenus dans ce domaine sont mis à votre disposition pour que vous les définissiez en tant que membres des salles de cette catégorie.

En règle générale, nous recommandons d’utiliser les conteneurs Active Directory, tels que des domaines et des unités d’organisation, pour définir les propriétés **AllowedMembers** et **Créateurs** d’une catégorie. Vous pouvez ajouter des objets d’un domaine à une liste **AllowedMembers** ou **Créateurs**. Seuls les objets de ces listes **AllowedMembers** ou **Créateurs** peuvent être ajoutés aux salles de cette catégorie.

