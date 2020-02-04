---
title: Description de l’appartenance à la conversation permanente
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Understanding Persistent Chat membership
ms:assetid: 900392d6-6e9f-4dae-93d6-39d7474409ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398730(v=OCS.15)
ms:contentKeyID: 48184781
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c2b4eb5fbe4342c1bd6bcb3bbb842e076e5863ad
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741944"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="understanding-persistent-chat-membership"></a>Description de l’appartenance à la conversation permanente

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-22_

L’accès des utilisateurs aux salles de conversation permanentes est géré par l’appartenance ; les utilisateurs doivent être membres d’une salle de conversation pour pouvoir publier et lire des messages. Seuls les **présentateurs** disposant d’une affiliation désignée avec des salles de conversation peuvent utiliser la **publication sur les salles d’Auditorium**. Un auditorium est un type de salle de conversation (l’autre est **normal**), dans lequel seuls les présentateurs peuvent publier et tout le monde peut lire.

De plus, les salles de conversation permanente fonctionnent conformément aux règles d’une catégorie. Pour plus d’informations sur les catégories, voir [gérer des catégories, des salles et des compléments dans Lync Server 2013](lync-server-2013-managing-categories-rooms-and-add-ins.md), ainsi que les sections « fonctionnement de la portée de la catégorie » et « stratégies de catégorie de salle » plus loin dans cette rubrique.

Un administrateur de chat permanent peut créer et gérer des catégories de salle de conversation. Dans le cadre de la création et de la gestion des catégories de salle de conversation, l’administrateur de chat permanent peut configurer des principales (services de domaine Active Directory) qui peuvent être membres ou créateurs de salles de conversation d’une catégorie spécifique.

<div>

## <a name="active-directory-domain-services-and-persistent-chat"></a>Services de domaine Active Directory et conversation permanente

Le serveur Chat permanent s’appuie sur Active Directory pour le pool d’utilisateurs de chat permanents internes. Après l’installation d’une conversation permanente (client), vous pouvez ajouter des domaines d’utilisateurs et de groupes d’utilisateurs à la catégorie salle. Vous pouvez ensuite ajouter ces utilisateurs et groupes à l’appartenance aux catégories de votre salle.

<div>


> [!IMPORTANT]  
> Vous devez vérifier qu’il n’y a aucun doublon pour les utilisateurs qui souhaitent apporter des modifications à leurs salles de conversation permanentes. S’il existe des noms d’utilisateur en double, remplacez-les par d’autres noms pour autoriser les utilisateurs à y apporter des modifications. Si un utilisateur a des noms dupliqués dans Active Directory et tente d’y apporter des modifications, un message d’erreur s’affiche pour inviter l’utilisateur à contacter l’administrateur pour résoudre le problème.



</div>

</div>

<div>

## <a name="how-category-scoping-works"></a>Fonctionnement de la portée de la catégorie

Une catégorie spécifie tous les utilisateurs et groupes qui peuvent être membres d’une liste d’appartenance d’une salle de conversation permanente de cette catégorie en fonction de la propriété **AllowedMembers** . Par exemple, si vous définissez le **AllowedMembers** de la catégorie sur contoso.com, vous pouvez ajouter un groupe ou un utilisateur de *contoso* en tant que membre aux salles de conversation de cette catégorie. Si vous définissez **AllowedMembers** sur une catégorie sur *ventes*, seuls les groupes et les utilisateurs de cette liste de distribution peuvent être ajoutés en tant que membres à des salles de conversation dans cette catégorie. De même, la propriété **créateurs** vous permet de contrôler qui peut créer des salles de conversation dans cette catégorie. Après la création d’une salle de conversation, tous les membres du groupe **AllowedMembers** peuvent être désignés en tant que **responsable** pour les opérations de gestion en cours sur les salles (par exemple, modifications d’appartenance et approbations).

La définition de **AllowedMembers** et de **créateurs** pour une catégorie offre les avantages suivants :

  - Toutes les salles de conversation de cette catégorie sont liées par des limitations définies au niveau de la catégorie. Vous pouvez utiliser cela pour isoler des salles de conversation en fonction des besoins et des stratégies d’accès.

  - Les utilisateurs qui se trouvent dans la liste de **créateurs** peuvent créer de nouvelles salles de conversation dans cette catégorie. Si vous voulez implémenter un système dans lequel un nombre restreint de membres du personnel de l’organisation peut créer des salles de conversation, ce contrôle peut être utilisé pour respecter cette exigence.

</div>

<div>

## <a name="room-category-strategies"></a>Stratégies de catégorie de salle

Le **AllowedMembers** d’une catégorie doit inclure tous les utilisateurs qui utiliseront toute salle de conversation permanente de cette catégorie. En fonction de vos besoins en matière de protection des données d’entreprise et de garantir le niveau d’accès approprié, vous pouvez définir une ou plusieurs catégories pour spécifier qui peut rechercher et participer à des salles. Si vous ne souhaitez autoriser qu’un ensemble spécifique d’utilisateurs (un support technique central ou uniquement des employés à plein temps) à créer des salles, vous pouvez définir la portée des **créateurs** d’une catégorie pour ce faire.

Les catégories peuvent également être utilisées pour créer des murs éthiques. Les murs éthiques empêchent tout conflit d’intérêt au sein d’une organisation. Par exemple, un administrateur peut créer des salles de conversation dans une catégorie uniquement pour les commerçants, alors qu’il n’est pas possible d’utiliser les analystes dans une autre catégorie.

<div>


> [!NOTE]  
> Dans Lync Server 2013, serveur de chat permanent, nous ne prenons pas en charge l’accès aux utilisateurs fédérés. S’il existe des discussions des utilisateurs fédérés dans les versions précédentes du serveur de chat permanent, celles-ci sont déplacées. Les utilisateurs fédérés sont ajoutés comme principaux désactivés.



</div>

</div>

<div>

## <a name="narrowing-the-members-to-user-groups"></a>Réduction des membres à des groupes d’utilisateurs

Lorsque vous ajoutez un domaine à une catégorie, il est possible d’accéder aux groupes d’utilisateurs dont les objets de groupe sont contenus dans ce domaine, afin que vous puissiez les spécifier en tant que membres de salles de la catégorie.

En règle générale, nous vous conseillons d’utiliser les conteneurs Active Directory, tels que les domaines et les unités d’organisation, pour définir les **AllowedMembers** et **créateurs**d’une catégorie. Vous pouvez ajouter des objets de n’importe quel domaine à une liste de **AllowedMembers** ou de **créateurs** . Seuls les objets figurant dans la liste **AllowedMembers** ou **Creators** peuvent être ajoutés aux salles de la catégorie.

</div>

</div>

<span> </span>

</div>

</div>

</div>

