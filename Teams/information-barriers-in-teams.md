---
title: Obstacles liés à l’information dans Microsoft teams
author: chrfox
ms.author: chrfox
manager: laurawi
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
ms.reviewer: vikramju
f1.keywords:
- NOCSH
description: Cet article décrit les barrières en informations dans Microsoft teams et leur incidence sur Teams.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 519e216a8736ca214f65f11ca5b3509541c09860
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508351"
---
# <a name="information-barriers-in-microsoft-teams"></a>Obstacles liés à l’information dans Microsoft teams

Les barrières d’information (IB) sont des stratégies qu’un administrateur peut configurer pour empêcher des personnes ou des groupes de communiquer entre eux. IB est utile si, par exemple, un service gère des informations qui ne doivent pas être partagées avec d’autres services ou si un groupe doit être empêché ou être isolé de communiquer avec des personnes extérieures à ce groupe.

> [!NOTE]
> - Les groupes de barrière d’information ne peuvent pas être créés entre des clients.
> - L’utilisation de robots pour ajouter des utilisateurs n’est pas prise en charge dans la version 1.
> - Les canaux privés sont conformes aux stratégies de barrière des informations que vous configurez.
> - Nouveau : pour plus d’informations sur la prise en charge des barrières pour un site SharePoint connecté à Teams, cliquez [ici](https://docs.microsoft.com/sharepoint/information-barriers#segments-associated-with-microsoft-teams-sites).

Les stratégies de barrage d’information empêchent également les recherches et la découverte. Si vous essayez de communiquer avec une personne avec laquelle vous ne devez pas communiquer, vous ne trouverez pas cet utilisateur dans le sélecteur de personnes.

## <a name="background"></a>Arrière-plan

Le principal pilote pour les barrières d’information provient du secteur des services financiers. Les autorités compétentes de l’industrie bancaire ([FINRA]( http://www.finra.org)) vérifient les obstacles et conflits d’intérêt dans les entreprises membres et fournissent des instructions sur la gestion de ces conflits (FINRA 2241, [avis de réglementation 15-31](http://www.finra.org/sites/default/files/Regulatory-Notice-15-31_0.pdf).  

Toutefois, dans la mesure où il existe des obstacles d’information, de nombreux autres domaines ont été utiles. Les autres scénarios courants sont les suivants :

- Formation : les étudiants au sein d’une école ne peuvent pas chercher les coordonnées des étudiants de votre établissement scolaire.
- Légal : conservation de la confidentialité des données obtenues par le juriste d’un client par le biais d’un juriste pour la même entreprise représentant un client différent.
- Secteur public : accès et contrôle des informations limités entre les services et les groupes.
- Services professionnels : un groupe de personnes dans une société est uniquement en mesure de dialoguer avec un client ou un client spécifique via une Fédération ou un accès invité lors d’un engagement client.

Par exemple, Enrico appartient au segment bancaire et Pradeep appartient au segment du conseiller financier. Enrico et Pradeep ne peuvent pas communiquer entre eux, car la stratégie IB de l’organisation bloque la communication et la collaboration entre ces deux segments. Toutefois, Enrico et Pradeep peuvent communiquer avec Lee dans HR.

![Exemple montrant les barrières d’information qui empêchent la communication entre les segments](media/information-barriers-example.png)

## <a name="when-to-use-information-barriers"></a>Quand utiliser les barrières d’information

Vous souhaiterez peut-être utiliser les barrières d’information dans les situations suivantes :

- Une équipe doit être empêché de communiquer et de partager des données avec une autre équipe spécifique.
- Une équipe ne doit pas communiquer et partager des données avec une personne en dehors de l’équipe.

Le service d’évaluation de la stratégie d’obstacle des informations détermine si une communication est conforme aux stratégies de cloisonnement des informations.

## <a name="managing-information-barrier-policies"></a>Gestion des stratégies de cloisonnement des informations

Les stratégies de barrière des informations sont gérées dans le centre de conformité Microsoft 365 (SCC) à l’aide des cmdlets PowerShell. Pour plus d’informations, consultez [définir des stratégies pour les barrières d’information](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies).

> [!IMPORTANT]
> Avant de configurer ou de définir des stratégies, **vous devez activer la recherche dans l’annuaire d’étendues dans Microsoft teams**. Patientez au moins quelques heures après l’activation de la recherche dans l’annuaire étendue avant de configurer ou de définir des stratégies pour les barrières d’information. [En savoir plus sur les conditions préalables pour les barrières d’information](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies#prerequisites).

## <a name="information-barriers-administrator-role"></a>Rôles d’administrateur de barrières d’information

Le rôle de gestion de la conformité IB est responsable de la gestion des stratégies de barrière des informations. Pour plus d’informations sur ce rôle, voir [autorisations dans le centre de conformité Microsoft 365](https://docs.microsoft.com/office365/securitycompliance/permissions-in-the-security-and-compliance-center).

## <a name="information-barrier-triggers"></a>Gâchettes de barrière d’information

Les stratégies de barrage d’information sont activées lorsque les événements d’équipe suivants se produisent :

- Les **membres sont ajoutés à une équipe** , chaque fois que vous ajoutez un utilisateur à une équipe, la stratégie de l’utilisateur doit être évaluée par rapport aux stratégies de barrage des informations des autres membres de l’équipe. Une fois que l’utilisateur a été ajouté, l’utilisateur peut exécuter toutes les fonctions de l’équipe sans vérification supplémentaire. Si la stratégie de l’utilisateur les empêche de l’ajouter à l’équipe, l’utilisateur n’affichera pas la recherche.

    ![Capture d’écran montrant une discussion de groupe](media/information-barriers-add-members.png)

- **Une nouvelle conversation est demandée** -chaque fois qu’une nouvelle discussion est demandée entre deux utilisateurs ou plus, la discussion est évaluée pour s’assurer qu’elle ne viole aucune stratégie de barrière des informations. Si la conversation ne respecte aucune stratégie d’obstacle d’information, la conversation n’est pas lancée.

    Voici un exemple de discussion 1:1.

     ![Capture d’écran montrant la communication bloquée dans la conversation 1:1](media/information-barriers-one-one-chat.png)

    Voici un exemple de discussion de groupe.

    ![Capture d’écran montrant une discussion de groupe](media/information-barriers-group-chat.png)

- **Un utilisateur est invité à rejoindre une réunion** : lorsque l’utilisateur est invité à rejoindre une réunion, la stratégie de l’utilisateur est évaluée par rapport aux politiques des autres membres de l’équipe, et en cas de violation, l’utilisateur n’est pas autorisé à rejoindre la réunion.

    ![Capture d’écran montrant l’utilisateur a empêché une réunion](media/information-barriers-meeting.png)

- **Un écran est partagé entre deux utilisateurs ou plus** : lorsqu’un écran est partagé entre plusieurs utilisateurs, le partage d’écran doit être évalué pour veiller à ce qu’il ne soit pas contraire aux stratégies de barrage des informations d’autres utilisateurs. Dans le cas contraire, le partage d’écran ne sera pas autorisé. 
 
    Voici un exemple de partage d’écran avant l’application de la stratégie. 

    ![Capture d’écran montrant une discussion d’utilisateur](media/ib-before-screen-share-policy.png)

    Voici un exemple de partage d’écran après l’application de la stratégie. Les icônes de partage d’écran et d’appel ne sont pas visibles.

    ![Capture d’écran montrant le caractère utilisateur avec les paramètres bloqués](media/ib-after-screen-share-policy.png)

- **Un utilisateur place un appel téléphonique (VoIP) dans teams** : chaque fois qu’un utilisateur est lancé par un utilisateur ou à un groupe d’utilisateurs, l’appel est évalué pour s’assurer qu’il ne respecte pas les stratégies de barrage des informations des autres membres de l’équipe. En cas de violation, l’appel audio est bloqué.
- **Utilisateurs invités dans teams** : les stratégies de barrière des informations s’appliquent également aux utilisateurs invités dans Teams. Si les utilisateurs invités doivent être détectables dans la liste d’adresses globale de votre organisation, voir [gérer l’accès invité dans les groupes Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/create-groups/manage-guest-access-in-groups). Lorsque les utilisateurs invités peuvent être détectables, vous pouvez [définir des politiques de cloisonnement des informations](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies).

## <a name="how-policy-changes-impact-existing-chats"></a>Impact des modifications de la stratégie sur les discussions existantes

Lorsque l’administrateur de la stratégie de protection des informations apporte des modifications à une stratégie ou qu’une modification de la stratégie est en vigueur en raison d’une modification du profil d’un utilisateur (par exemple, pour un changement de poste ou pour une raison similaire), le service d’évaluation de la stratégie d’obstacle des informations recherche automatiquement les membres de l’équipe sans violer une stratégie.

S’il existe une discussion existante ou une autre communication entre les utilisateurs et qu’une nouvelle stratégie est définie ou qu’une stratégie existante est modifiée, le service évalue les communications existantes pour s’assurer que les communications sont toujours autorisées. 

- **chat 1:1** : si la communication entre les deux utilisateurs n’est plus autorisée (si une communication bloquante est appliquée à l’un ou les deux utilisateurs), une communication supplémentaire est bloquée et la conversation par messagerie instantanée devient en lecture seule. 

    Vous trouverez ci-dessous un exemple illustrant la discussion.

    ![Capture d’écran montrant la conversation des utilisateurs est disponible](media/ib-before-1-1chat-policy.png)

    Vous trouverez ci-dessous un exemple illustrant la conversation est désactivée.

    ![Capture d’écran montrant la conversation des utilisateurs est désactivée](media/ib-after-1-1chat-policy.png)

- **Discussions de groupe** : si la communication entre un utilisateur et le groupe n’est plus autorisée (par exemple, si un utilisateur change de travail), l’utilisateur ainsi que les autres utilisateurs qui enfreignent la politique peuvent être supprimés des discussions de groupe et les communications avec le groupe ne sont pas autorisées. L’utilisateur peut toujours voir d’anciennes conversations (lecture seule), mais ne pourra pas voir ou participer à des conversations avec le groupe. Si la stratégie nouvelle ou modifiée qui empêche la communication est appliquée à plusieurs utilisateurs, les utilisateurs concernés par la stratégie peuvent être supprimés de la discussion de groupe. Ils peuvent toujours voir d’anciennes conversations.

Dans cet exemple, Enrico a été déplacé vers un service différent au sein de l’organisation et est supprimé de la discussion de groupe.

  ![Capture d’écran montrant une discussion de groupe](media/information-barriers-user-changes-job.png)

Enrico ne peut plus envoyer de messages à la discussion de groupe.

  ![Capture d’écran montrant une discussion de groupe](media/information-barriers-user-changes-job-2.png)

- **Équipe** : les utilisateurs qui ont été supprimés du groupe sont supprimés de l’équipe et ne seront pas en mesure d’afficher ou de participer à des conversations existantes ou nouvelles.

## <a name="scenario-a-user-in-an-existing-chat-becomes-blocked"></a>Scénario : un utilisateur dans une discussion existante est bloqué

Pour le moment, les utilisateurs peuvent se familiariser avec les scénarios suivants si une stratégie de protection des informations bloque un autre utilisateur :

- **Onglet contacts** : un utilisateur ne peut pas voir les utilisateurs bloqués sous l’onglet **personnes** .
- **Sélecteur de personnes** -les utilisateurs bloqués ne seront pas visibles dans le sélecteur de personnes.

    ![Capture d’écran montrant une discussion de groupe](media/information-barriers-people-picker.png)
    
- **Onglet activité** : si un utilisateur accède à l’onglet **activité** d’un utilisateur bloqué, aucun billet ne s’affiche. (L’onglet **activité** affiche uniquement les billets de canal et il n’y a pas de canaux courants entre les deux utilisateurs.)

    Voici un exemple d’affichage de l’onglet activité qui est bloqué.

    ![Capture d’écran montrant l’onglet activité bloqué](media/ib-after-activity-tab-policy.png)


- **Organigrammes : si** un utilisateur accède à un organigramme sur lequel un utilisateur bloqué apparaît, l’utilisateur bloqué n’apparaît pas dans l’organigramme et un message d’erreur s’affiche à la place.
- **Carte contacts** : si un utilisateur participe à une conversation et que l’utilisateur est bloqué par la suite, les autres utilisateurs verront s’afficher un message d’erreur au lieu de la carte contacts lorsqu’ils placent le pointeur sur le nom de l’utilisateur bloqué. Les actions figurant sur la carte (par exemple, appels et discussions) ne sont pas disponibles.
- **Suggestions de contacts** : les utilisateurs bloqués n’apparaissent pas dans la liste des contacts suggérés (liste de contacts initiale qui s’affiche pour les nouveaux utilisateurs).
- **Contacts de chat** : un utilisateur peut voir les utilisateurs bloqués dans la liste de contacts, mais les utilisateurs bloqués sont identifiés et la seule action que l’utilisateur peut effectuer est de les supprimer. L’utilisateur peut également cliquer dessus pour afficher sa ancienne conversation.
- **Appels** de contact : un utilisateur peut voir les utilisateurs bloqués dans la liste des contacts appels, mais les utilisateurs bloqués seront identifiés et la seule action qu’il peut effectuer est de les supprimer.

    Voici un exemple d’un utilisateur bloqué dans la liste des contacts appels.

    ![Capture d’écran montrant une discussion d’utilisateur](media/ib-before-chat-contacts-policy.png)

    Voici un exemple du message désactivé pour un utilisateur dans la liste de contenu appels.

    ![Capture d’écran montrant que l’utilisateur a bloqué une conversation](media/ib-after-chat-contacts-policy.png)

- **Migration de Skype vers les équipes** : au cours d’une migration Skype entreprise vers Teams, tous les utilisateurs, même ceux qui ont été bloqués par des politiques de barrage d’information, sont migrés vers Teams, puis seront gérés comme décrit ci-dessus.

## <a name="teams-policies-and-sharepoint-sites"></a>Stratégies d’équipe et sites SharePoint

Lors de la création d’une équipe, un site SharePoint est approvisionné et associé à Microsoft teams pour l’interface de fichiers. Par défaut, les stratégies de barrage d’information ne sont pas honorées sur ce site SharePoint et les fichiers. Pour activer les stratégies de cloisonnement des informations, l’administrateur a déjà rempli un formulaire, pour demander l’activation de stratégies IB sur SharePoint et OneDrive (voir la section *conditions préalables* dans la rubrique [barrières d’information](https://docs.microsoft.com/sharepoint/information-barriers#prerequisites)). Si la stratégie de protection des informations est activée dans SharePoint et OneDrive, les stratégies IB fonctionneront sur les sites SharePoint approvisionnés lors de la création d’une équipe à l’aide de Microsoft Teams.

**Exemple de stratégies IB sur le site SharePoint d’une équipe**: dans la Banque bancaire de contoso, l’utilisateur « Sesha@contosobank.onmicrosoft.com » appartient au segment de banque d’investissement et l’utilisateur « Nikita@contosobank.onmicrosoft.com » appartient à la fonction d’avis de segment. La stratégie IB de l’organisation bloque la communication et la collaboration entre ces deux segments.
Lorsque l’utilisateur Sesha crée une équipe pour un segment de services d’investissement, l’équipe et le site SharePoint qui la replaceront ne seront accessibles qu’aux utilisateurs de segments bancaires d’investissement. L’utilisateur Nikita ne peut pas accéder à ce site, même s’il possède le lien de site.

Pour plus d’informations, consultez l’article relatif aux [barrières d’information](https://docs.microsoft.com/sharepoint/information-barriers#segments-associated-with-microsoft-teams-sites) .

## <a name="required-licenses-and-permissions"></a>Licences et autorisations requises

Pour plus d’informations, y compris les offres et les tarifs, voir conseils relatifs aux [licences](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).

## <a name="known-issues"></a>Problèmes connus
- **Les utilisateurs ne peuvent pas participer**à des réunions : si les stratégies IB sont activées, les utilisateurs ne peuvent pas participer à des réunions si la taille de la liste de la réunion ne correspond pas aux [limites d’assiduité](limits-specifications-teams.md)de la réunion. La cause initiale est que le contrôle IB s’appuie sur le fait que les utilisateurs puissent être ajoutés à une liste de discussions et qu’ils le nécessitent pour permettre aux utilisateurs de participer à des réunions. Lorsque vous participez à une réunion, vous ajoutez ce dernier à la liste, par conséquent pour les réunions périodiques, la liste se remplit rapidement. Lorsqu’il atteint les [limites d’assiduité](limits-specifications-teams.md)de la réunion, aucun utilisateur supplémentaire ne peut être ajouté à la liste de conversations de la réunion. Si IB est activé, les utilisateurs ne sont pas autorisés à participer à la réunion, mais si IB n’est pas activé, les utilisateurs sont autorisés à participer à la réunion, mais ils ne sont pas ajoutés à la liste des discussions de la réunion. Une solution courte consiste à supprimer les membres inactifs de la liste de conversations de la réunion afin de libérer de l’espace pour les nouveaux utilisateurs. En revanche, vous augmenterez la taille des listes de discussions de réunion à une date ultérieure.

## <a name="more-information"></a>Plus d’informations

- Pour en savoir plus sur les barrières d’information, voir [barrières d’information](https://docs.microsoft.com/office365/securitycompliance/information-barriers).

- Pour configurer des stratégies de barrière des informations, consultez [définir des stratégies pour les barrières d’information](https://docs.microsoft.com/office365/securitycompliance/information-barriers-policies).

- Pour modifier ou supprimer des stratégies de protection des informations, voir [modifier ou supprimer des stratégies de barrage des informations](https://docs.microsoft.com/microsoft-365/compliance/information-barriers-edit-segments-policies).
