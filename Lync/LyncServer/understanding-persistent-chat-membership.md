---
title: Présentation de l’appartenance à la conversation permanente
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Understanding Persistent Chat membership
ms:assetid: 900392d6-6e9f-4dae-93d6-39d7474409ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398730(v=OCS.15)
ms:contentKeyID: 48184781
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dfed05d4cb2ce55971a9964d5360002599d0fe0c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527181"
---
# <a name="understanding-persistent-chat-membership"></a>Présentation de l’appartenance à la conversation permanente

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-22_

L’accès des utilisateurs aux salles de conversation permanente est géré par l’appartenance ; les utilisateurs doivent être membres d’une salle de conversation pour pouvoir publier et lire des messages. Seuls les **Présentateurs** qui ont une affiliation aux salles de conversation sont autorisés à utiliser la **publication dans des auditoriums**. Un auditorium est un type de salle de conversation (l’autre type est **Normal**), dans lequel seuls les présentateurs peuvent publier et tout le monde peut lire.

En outre, les salles de conversation permanente fonctionnent sous les règles d’une catégorie. Pour plus d’informations sur les catégories, voir [Managing Categories, rooms, and Add-ins in Lync Server 2013](lync-server-2013-managing-categories-rooms-and-add-ins.md), ainsi que les sections « fonctionnement de la portée des catégories » et « stratégies de catégorie de salle » plus loin dans cette rubrique.

Un administrateur de conversation permanente peut créer et gérer des catégories de salles de conversation. Dans le cadre de la création et de la gestion des catégories de salles de conversation, l’administrateur de conversation permanente peut configurer les principaux (groupes, conteneurs et utilisateurs des services de domaine Active Directory) qui ont accès aux membres ou aux créateurs des salles de conversation d’une catégorie particulière.

<div>

## <a name="active-directory-domain-services-and-persistent-chat"></a>Services de domaine Active Directory et conversation permanente

Le serveur de conversation permanente s’appuie sur Active Directory pour le pool d’utilisateurs de conversation permanente interne. Après avoir installé la conversation permanente (client), vous pouvez ajouter des domaines d’utilisateurs et de groupes d’utilisateurs à la catégorie de salle. Vous pouvez ensuite ajouter ces utilisateurs et groupes à l’appartenance de vos catégories de salles.

<div>


> [!IMPORTANT]  
> Vous devez vous assurer qu’il n’existe aucun nom en double pour les utilisateurs qui souhaitent modifier leurs salles de conversation permanente. Si des noms d’utilisateurs en double existent, modifiez-les pour débloquer les utilisateurs afin qu’ils puissent apporter des modifications. Si un utilisateur a des noms en double dans Active Directory et tente d’y effectuer des modifications, un message d’erreur s’affiche pour demander à l’utilisateur de contacter l’administrateur pour résoudre le problème.



</div>

</div>

<div>

## <a name="how-category-scoping-works"></a>Fonctionnement de l’étendue des catégories

Une catégorie spécifie tous les utilisateurs et les groupes qui peuvent être membres d’une liste d’appartenance d’une salle de conversation permanente de cette catégorie, en fonction de sa propriété **AllowedMembers** . Par exemple, si vous définissez le **AllowedMembers** de la catégorie sur contoso.com, vous pouvez ajouter un groupe ou un utilisateur de *contoso* en tant que membre aux salles de conversation de cette catégorie. Si vous définissez **AllowedMembers** d’une catégorie à *Ventes*, seuls les groupes et utilisateurs de cette liste de distribution peuvent être ajoutés en tant que membre des salles de conversation de cette catégorie. De la même façon, la propriété **Créateurs** vous permet de contrôler qui peut créer des salles de conversation dans la catégorie. Une fois la salle de conversation créée, toute personne membre du groupe **AllowedMembers** peut être désignée en tant que **Gestionnaire** pour les opérations de gestion courantes des salles (par exemple, modifications des membres et approbations).

La définition de **AllowedMembers** et **Créateurs** pour une catégorie comporte les avantages suivants :

  - Toutes les salles de conversation de cette catégorie sont liées par des limitations définies au niveau de la catégorie. Vous pouvez utiliser cela pour isoler des salles de conversation en fonction des besoins et des stratégies d’accès.

  - Un utilisateur qui se trouve dans la liste **Créateurs** peut créer des salles de conversation dans cette catégorie. Si vous voulez mettre en place un système qui limite le nombre de personnes de votre organisation ayant la possibilité de créer des salles de conversation, ce contrôle peut être utilisé.

</div>

<div>

## <a name="room-category-strategies"></a>Stratégies de catégorie de salle

Le **AllowedMembers** d’une catégorie doit inclure tous les utilisateurs qui utiliseront toute salle de conversation permanente de cette catégorie. En fonction des besoins de protection de vos données et pour contrôler les niveaux d’accès, vous pouvez définir une ou plusieurs catégories pour spécifier qui peut effectuer des recherches dans les salles et y participer. Si vous ne voulez autoriser qu’un groupe d’utilisateurs donnés (support technique ou employés à plein temps) à créer des salles, vous pouvez définir l’étendue de **Créateurs** d’une catégorie pour répondre à ce besoin.

Les catégories peuvent également être utilisées pour créer des séparations déontologiques. Les séparations déontologiques permettent d’éviter les conflits d’intérêts dans votre organisation. Par exemple, un administrateur peut créer des salles de conversation dans une catégorie uniquement pour les opérateurs en bourse, et d’autres salles dans une autre catégorie pour les analystes.

<div>


> [!NOTE]  
> Dans Lync Server 2013, serveur de conversation permanente, nous ne prenons pas en charge l’accès aux utilisateurs fédérés. S’il existe des conversations d’utilisateurs fédérés dans les versions précédentes du serveur de conversation permanente, elles sont migrées. Les utilisateurs fédérés sont ajoutés en tant que principaux désactivés.



</div>

</div>

<div>

## <a name="narrowing-the-members-to-user-groups"></a>Limitation des membres aux groupes d’utilisateurs

Lorsque vous ajoutez un domaine à une catégorie, les groupes d’utilisateurs dont les objets de groupe sont contenus dans ce domaine sont mis à votre disposition pour que vous les définissiez en tant que membres des salles de cette catégorie.

Nous vous recommandons, en règle générale, d’utiliser des conteneurs Active Directory, tels que des domaines et des unités d’organisation, pour définir le **AllowedMembers** et les **créateurs**d’une catégorie. Vous pouvez ajouter des objets d’un domaine à une liste **AllowedMembers** ou **Créateurs**. Seuls les objets de ces listes **AllowedMembers** ou **Créateurs** peuvent être ajoutés aux salles de cette catégorie.

</div>

</div>

<span> </span>

</div>

</div>

</div>

