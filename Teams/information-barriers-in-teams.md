---
title: Barrières de l’information au Microsoft Teams
description: Cet article explique comment les obstacles à la protection des informations sont pris en charge dans Microsoft Teams.
author: robmazz
ms.author: robmazz
manager: laurawi
ms.reviewer: smahadevan
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 41d5cf86085c944e414e1c78e3160f8f2678d0d1
ms.sourcegitcommit: 2388838163812eeabcbd5331aaf680b79da3ccba
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/31/2022
ms.locfileid: "64592939"
---
# <a name="information-barriers-in-microsoft-teams"></a>Barrières de l’information au Microsoft Teams

[Les barrières à l’information](/microsoft-365/compliance/information-barriers) sont les stratégies qu’un administrateur peut configurer pour empêcher des individus ou des groupes de communiquer entre eux. LesB sont utiles si, par exemple, un service gère des informations qui ne doivent pas être partagées avec d’autres services. Les IB sont également utiles lorsqu’un groupe doit être isolé ou empêché de communiquer avec des personnes extérieures à ce groupe. Les canaux partagés dans Microsoft Teams sont pris en charge par des barrières d’informations. Selon le type de partage, les stratégies de barrière des informations peuvent restreindre le partage de certaines façons. Pour plus d’informations sur le comportement des canaux partagés et les barrières de l’information, voir [Les barrières de l’information et les canaux partagés](information-barriers-shared-channels.md).

Par Microsoft Teams, des barrières de l’information peuvent déterminer et empêcher les types suivants de collaboration non autorisée :

- Ajout d’un utilisateur à une équipe ou un canal
- Accès utilisateur au contenu d’une équipe ou d’un canal
- Accès utilisateur aux conversations 1:1 et de groupe
- Accès utilisateur aux réunions
- Empêche les recherches et la découverte, les utilisateurs ne seront pas visibles dans le s sélectionneur de personnes.

>[!NOTE]
>- Les groupes de barrière de l’information ne peuvent pas être créés entre des locataires.
>- L’utilisation de bots, Azure Active Directory (Azure AD), d’API pour envoyer des notifications de flux d’activité et de certains API pour ajouter des utilisateurs n’est pas prise en charge dans la version 1.
>- Les canaux privés respectent les stratégies de protection des informations que vous configurez.
>- Pour plus d’informations sur la prise en charge des barrières SharePoint sites connectés à Teams, voir [Segments associés à Microsoft Teams sites web](/sharepoint/information-barriers#segments-associated-with-microsoft-teams-sites).

## <a name="background"></a>Arrière-plan

Le principal moteur des IB provient du secteur des services financiers. L’Autorité de réglementation du secteur financier ([FINRA]( https://www.finra.org)) examine les B/S et les conflits d’intérêts au sein des entreprises membres et fournit des conseils sur la gestion de ces conflits (FINRA 2241, Avis de réglementation en matière de recherche sur le crédit [15-31](https://www.finra.org/sites/default/files/Regulatory-Notice-15-31_0.pdf)).

Toutefois, depuis l’introduction des IB, de nombreux autres domaines les ont trouvés utiles. Les autres scénarios courants sont les suivants :

- **Éducation** : Les étudiants d’une école ne peuvent pas rechercher les coordonnées des étudiants d’autres écoles.
- **Juridique** : préserver la confidentialité des données obtenues par l’entreprise d’un client et empêcher qu’elles ne sont accessibles par une personne de la même entreprise qui représente un autre client.
- **Gouvernement :** L’accès et le contrôle des informations sont limités entre les départements et les groupes.
- **Professional services aux** invités : un groupe de personnes dans une entreprise peut uniquement discuter avec un client ou un client spécifique via l’accès invité pendant un engagement client.

Par exemple, Enric appartient au segment Banque et Ppep au segment Conseiller financier. Enrico et Ppep ne peuvent pas communiquer entre eux, car la stratégie de l’organisation L’ORGANISATION bloque la communication et la collaboration entre ces deux segments. Cependant, Enrico et P matièreep peuvent communiquer avec Lee dans les ressources humaines.

![Exemple montrant les barrières de l’information qui empêchent la communication entre segments.](media/information-barriers-example.png)

## <a name="when-to-use-information-barriers"></a>Quand utiliser les barrières de l’information

Vous souhaitez peut-être utiliser des IB dans les situations comme celles-ci :

- Une équipe doit être empêchée de communiquer ou de partager des données avec une autre équipe spécifique.
- Une équipe ne doit pas communiquer ou partager des données avec des personnes extérieures à l’équipe.

Le service d’évaluation des stratégies de barrière des informations détermine si une communication est conforme aux stratégies de l’organisation.

## <a name="managing-information-barrier-policies"></a>Gestion des stratégies de barrière de l’information

Les stratégies DE l’organisation sont gérées dans le Centre Microsoft 365 conformité de l’entreprise à l’aide des cmdlets PowerShell. Pour plus d’informations, voir [Définir les stratégies en matière d’obstacles à l’information](/office365/securitycompliance/information-barriers-policies).

>[!IMPORTANT]
>Avant de configurer ou de définir des stratégies, vous devez activer la recherche dans l’annuaire dans Microsoft Teams. Patientez au moins quelques heures après avoir mis en place la recherche étendue dans l’annuaire avant de définir ou de définir des stratégies pour les barrières de l’information. Pour plus d’informations, voir [Définir les stratégies de barrière de l’information](/office365/securitycompliance/information-barriers-policies#prerequisites).

## <a name="information-barriers-administrator-role"></a>Rôle d’administrateur de barrière de l’information

Le rôle de gestion de la conformité de l’organisation est responsable de la gestion des stratégies de l’organisation. Pour plus d’informations sur ce rôle, voir [Autorisations dans le Centre Microsoft 365 conformité.](/office365/securitycompliance/permissions-in-the-security-and-compliance-center)

## <a name="information-barrier-triggers"></a>Déclencheurs de barrière de l’information

Les stratégies DE L’ORGANISATION sont activées lorsque les événements Teams événements suivants sont activés :

- **Les membres sont ajoutés** à une équipe : Chaque fois que vous ajoutez un utilisateur à une équipe, sa stratégie doit être évaluée par rapport aux stratégies DE l’organisation des autres membres de l’équipe. Une fois l’utilisateur ajouté, il peut effectuer toutes les fonctions de l’équipe sans autres vérifications. Si la stratégie de l’utilisateur empêche son ajout à l’équipe, l’utilisateur n’est pas dans la recherche.

    ![Capture d’écran de la recherche d’un nouveau membre à ajouter à une équipe et de la recherche de correspondances.](media/information-barriers-add-members.png)

- **Une** nouvelle conversation est demandée : chaque fois qu’un utilisateur demande une nouvelle conversation avec un ou plusieurs autres utilisateurs, la conversation est évaluée pour s’assurer qu’elle n’enfreinait aucune stratégie de l’organisation. Si la conversation ne respecte pas la stratégie de l’organisation, la conversation n’est pas démarrée.

    Voici un exemple de conversation en deux:

    ![Capture d’écran montrant la communication bloquée dans une conversation à deux.](media/information-barriers-one-one-chat.png)

    Voici un exemple de conversation de groupe.

    ![Capture d’écran montrant une conversation de groupe.](media/information-barriers-group-chat.png)

- Un utilisateur est invité à participer à une réunion : Lorsqu’un utilisateur est invité à participer à une réunion, la stratégie DE l’organisation qui s’applique à l’utilisateur est évaluée par rapport aux stratégies DEXT qui s’appliquent aux autres membres de l’équipe. En cas de violation, l’utilisateur n’est pas autorisé à participer à la réunion.

    ![Capture d’écran montrant un utilisateur bloqué d’une réunion.](media/information-barriers-meeting.png)

- Un écran est partagé entre deux utilisateurs ou plus : lorsqu’un utilisateur partage un écran avec d’autres utilisateurs, le partage doit être évalué afin de s’assurer qu’il ne constitue pas une violation des stratégies DE l’organisation. En cas de violation d’une stratégie de l’organisation, le partage d’écran n’est pas autorisé.

    Voici un exemple de partage d’écran avant l’application de la stratégie.

    ![Capture d’écran montrant une conversation utilisateur.](media/ib-before-screen-share-policy.png)

    Voici un exemple de partage d’écran après l’application de la stratégie. Les icônes de partage d’écran et d’appel ne sont pas visibles.

    ![Capture d’écran montrant un char d’utilisateur avec des paramètres bloqués.](media/ib-after-screen-share-policy.png)

- Un utilisateur passe un appel téléphonique dans **Teams** : chaque fois qu’un utilisateur passe un appel vocal (via VOIP) à un autre utilisateur ou groupe d’utilisateurs, l’appel est évalué pour s’assurer qu’il ne enfreint pas les stratégies de l’organisation. En cas de violation, l’appel vocal est bloqué.

- **Invités dans Teams** : Les stratégies DE l’organisation d’organisation de groupe s’appliquent également aux Teams invités. Si les invités doivent être utilisables dans la liste d’adresses globale de votre organisation, voir Gérer l’accès [invité dans Groupes Microsoft 365](/microsoft-365/admin/create-groups/manage-guest-access-in-groups). Une fois que les invités sont découvables, vous pouvez [définir les stratégies de l’organisation](/office365/securitycompliance/information-barriers-policies).

## <a name="how-policy-changes-impact-existing-chats"></a>Impact des modifications de stratégie sur les conversations existantes

Lorsque l’administrateur de stratégie de l’organisation modifie une stratégie ou lorsqu’une modification de stratégie est activée en raison d’une modification du profil d’un utilisateur (par exemple pour un changement de poste), le service d’évaluation de la stratégie de barrière des informations effectue automatiquement une recherche dans les membres pour s’assurer que leur appartenance à l’équipe n’enfreigne aucune stratégie.

S’il existe une conversation ou une autre communication existante entre les utilisateurs, et qu’une nouvelle stratégie est définie ou qu’une stratégie existante est modifiée, le service évalue les communications existantes pour s’assurer que les communications sont toujours autorisées à se produire. 

- **Conversation 1:1** : si la communication entre deux utilisateurs n’est plus autorisée (en raison de l’application à l’un ou aux deux utilisateurs d’une stratégie qui bloque la communication), toute communication supplémentaire est bloquée. Leurs conversations de conversation existantes deviennent en lecture seule.

    Voici un exemple qui montre que la conversation est visible.

    ![Capture d’écran montrant que la conversation utilisateur est disponible.](media/ib-before-1-1chat-policy.png)

    Voici un exemple qui montre que la conversation est désactivée.

    ![Capture d’écran montrant que la conversation utilisateur est désactivée.](media/ib-after-1-1chat-policy.png)

- Conversation de groupe : si la communication d’un utilisateur à un groupe n’est plus autorisée (par exemple, en raison de la changement de tâches d’un utilisateur), l’utilisateur, ainsi que les autres utilisateurs dont la participation ne respecte pas la stratégie, peut être supprimé de la conversation de groupe et les communications avec le groupe ne seront pas autorisées. L’utilisateur peut toujours voir les anciennes conversations, mais ne peut pas voir et participer à de nouvelles conversations avec le groupe. Si la stratégie nouvelle ou modifiée qui empêche la communication est appliquée à plusieurs utilisateurs, les utilisateurs concernés par la stratégie peuvent être supprimés de la conversation de groupe. Ils peuvent toujours voir les anciennes conversations.

  Dans cet exemple, Enric a été déplacé vers un autre service au sein de l’organisation et retiré de la conversation de groupe.

  ![Capture d’écran d’une conversation de groupe à partir de laquelle un utilisateur a été supprimé.](media/information-barriers-user-changes-job.png)

  Enrico ne peut plus envoyer de messages à la conversation de groupe.

  ![Capture d’écran du fait que l’utilisateur n’a pas pu envoyer de messages à une conversation de groupe, car l’utilisateur a été supprimé du groupe.](media/information-barriers-user-changes-job-2.png)

- **Équipe** : Tous les utilisateurs supprimés du groupe sont supprimés de l’équipe et ne peuvent pas voir et participer à des conversations existantes ou nouvelles.

## <a name="scenario-a-user-in-an-existing-chat-becomes-blocked"></a>Scénario : Un utilisateur dans une conversation existante devient bloqué

Actuellement, les utilisateurs sont les scénarios suivants si une stratégie DE L’organisation bloque un autre utilisateur :

- **Onglet Personnes :** Un utilisateur ne peut pas voir les utilisateurs bloqués sous **l’onglet** Personnes.

- **S sélectionneur de personnes** : les utilisateurs bloqués ne seront pas visibles dans le s sélectionneur de personnes.

    ![Capture d’Teams d’alerte à l’utilisateur que la stratégie empêche l’affichage des informations d’un autre utilisateur.](media/information-barriers-people-picker.png)

- **Onglet Activité :** Si un utilisateur visite l’onglet **Activité** d’un utilisateur bloqué, aucune billet n’apparaît. ( **L’onglet** Activité affiche uniquement les publications de canal et il n’existe aucun canal commun entre les deux utilisateurs.)

    Voici un exemple d’affichage de l’onglet Activité bloqué.

    ![Capture d’écran montrant l’onglet Activité bloqué.](media/ib-after-activity-tab-policy.png)

- **Organigrammes** : si un utilisateur accède à un organigramme sur lequel un utilisateur bloqué apparaît, l’utilisateur bloqué n’apparaîtra pas dans l’organigramme. Un message d’erreur s’affiche à la place.

- **Carte personnes** : si un utilisateur participe à une conversation et qu’il est bloqué par la suite, les autres utilisateurs voient un message d’erreur au lieu de la carte de la personne lorsqu’ils pointent sur le nom de l’utilisateur bloqué. Les actions répertoriées sur la carte (telles que les appels et les discussions) ne seront pas disponibles.

- **Contacts suggérés :** Les utilisateurs bloqués n’apparaissent pas dans la liste des contacts suggérés (liste de contacts initiale qui s’affiche pour les nouveaux utilisateurs).

- **Contacts de conversation** : un utilisateur peut voir les utilisateurs bloqués dans la liste de contacts des conversations, mais les utilisateurs bloqués seront identifiés. La seule action que l’utilisateur peut effectuer sur les utilisateurs bloqués consiste à les supprimer. L’utilisateur peut également le sélectionner pour afficher son passé.

- **Appels :** un utilisateur peut voir les utilisateurs bloqués dans la liste de contacts d’appels, mais les utilisateurs bloqués seront identifiés. La seule action que l’utilisateur peut effectuer sur le blocage des utilisateurs consiste à les supprimer.

    Voici un exemple d’utilisateur bloqué dans la liste de contacts d’appels.

    > [!div class="mx-imgBorder"]
    > ![Capture d’écran montrant la conversation de l’utilisateur.](media/ib-before-chat-contacts-policy.png)

    Voici un exemple de conversation désactivée pour un utilisateur dans la liste de contenu appels.

    > [!div class="mx-imgBorder"]
    > ![Capture d’écran montrant un utilisateur bloqué d’une conversation.](media/ib-after-chat-contacts-policy.png)

- **Skype** migration vers Teams : lors d’une migration de Skype Entreprise vers Teams, tous les utilisateurs, même les utilisateurs bloqués par les stratégies de l’organisation, sont migrés vers Teams. Ces utilisateurs sont ensuite gérés comme décrit ci-dessus.

## <a name="teams-policies-and-sharepoint-sites"></a>Teams stratégies et sites SharePoint sites

Lorsqu’une équipe est créée, un site SharePoint est mis en service et associé à Microsoft Teams de l’expérience de fichiers. Les stratégies de barrière de l’information ne sont pas respecter sur SharePoint site et fichiers par défaut. Pour faire tomber les barrières de l’information SharePoint en OneDrive, suivez les [recommandations et les étapes](/sharepoint/information-barriers#enable-sharepoint-and-onedrive-information-barriers-in-your-organization) qui permettent d’utiliser les barrières de l’information grâce SharePoint’article.

## <a name="information--barrier-modes-and-teams"></a>Modes de barrière de l’information et Teams

Le mode Barrières de l’information permet d’renforcer les personnes qui peuvent être ajoutées ou supprimées d’une équipe. Lors de l’utilisation des barrières d’Teams, les modes de l’organisation sont pris en charge :

- **Ouvert** : Cette configuration est le mode IB par défaut pour tous les groupes existants qui ont été provisionés avant l’ouverture d’une barrière de l’information. Dans ce mode, aucune stratégie DE l’organisation n’est applicable.
- **Implicite** : cette configuration est le mode IB par défaut lorsqu’une équipe est mise en service après l’activation des barrières de l’information. Le mode implicite vous permet d’ajouter tous les utilisateurs compatibles du groupe.
- **Propriétaire modéré :** Ce mode est définie pour une équipe lorsque vous voulez autoriser la collaboration entre les utilisateurs de segments incompatibles modérés par le propriétaire. Le propriétaire de l’équipe peut ajouter de nouveaux membres selon sa stratégie DNS.

Teams création avant l’activation d’une stratégie de barrière des informations dans votre client sont automatiquement définies sur *le* mode Ouvrir par défaut. Une fois les stratégies IB activées sur votre client, vous devez mettre à jour le mode de vos équipes existantes vers *Implicite* pour vous assurer que les équipes existantes respectent la conformité de l’organisation.

Utilisez [l’cmdlet Set-UnifiedGroup](/powershell/module/exchange/set-unifiedgroup) avec le paramètre *InformationBarrierMode* correspondant au mode que vous voulez utiliser pour vos segments. La liste des valeurs autorisées pour le paramètre *InformationBarrierMode* *est Ouverte*, *Implicite* et *Modérer par le propriétaire*.

Par exemple, pour configurer *le mode implicite* pour un groupe Microsoft 365, vous devez utiliser la commande PowerShell suivante :

```powershell
Set-UnifiedGroup -InformationBarrierMode Implicit
```

Pour mettre à jour le mode d’Ouverture à Implicite pour toutes les équipes existantes, utilisez ce [script PowerShell](information-barriers-mode-script.md).

Si vous modifiez la configuration du mode Ouvrir sur les groupes connectés à Teams existants afin de respecter les exigences de conformité de votre organisation, vous devez mettre à jour les [modes IB](/sharepoint/information-barriers#view-and-manage-ib-modes-as-an-administrator-with-sharepoint-powershell) pour les sites SharePoint associés connectés à l’équipe Teams web.

## <a name="required-licenses-and-permissions"></a>Licences et autorisations requises

Pour plus d’informations sur les licences et les autorisations, les plans et les prix, voir Microsoft 365 [d’aide](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance) en matière de licences & conformité.

## <a name="known-issues"></a>Problèmes connus

- Les utilisateurs ne peuvent pas participer à des réunions **ad hoc : si les stratégies de l’organisation sont activées**, les utilisateurs ne sont pas autorisés à participer à des réunions si la taille de la liste de réunions est supérieure aux [limites](limits-specifications-teams.md) de participation aux réunions. La raison principale est que les vérifications de l’organisation de l’organisation dépendent du fait que les utilisateurs peuvent être ajoutés à une liste de conversation de réunion et que, lorsqu’ils peuvent être ajoutés à la liste, ils sont autorisés à participer à la réunion. Un utilisateur rejoignant une réunion l’ajoute à la liste ; par conséquent, pour les réunions périodiques, la liste peut se remplir rapidement. Une fois que la liste de conversation a atteint les [limites](limits-specifications-teams.md) de participation à la réunion, d’autres utilisateurs ne peuvent pas être ajoutés à la réunion. Si l’offre IB est activée pour l’organisation et que la liste de discussion est pleine pour une réunion, les nouveaux utilisateurs (ces utilisateurs qui ne sont pas déjà dans la liste) ne sont pas autorisés à participer à la réunion. Toutefois, si l’organisation n’est pas activée et que la liste de discussion de la réunion est pleine, les nouveaux utilisateurs (utilisateurs qui ne sont pas déjà dans la liste) sont autorisés à participer à la réunion, même s’ils ne voient pas l’option de conversation dans la réunion. Une solution à court terme consiste à supprimer les membres inactifs de la liste de conversation de réunion afin de faire de l’espace pour les nouveaux utilisateurs. Nous augmenterons toutefois la taille des listes de conversation de réunion à une date ultérieure.
- **Les utilisateurs ne peuvent** pas participer aux réunions de canal : si les stratégies de l’organisation sont activées, les utilisateurs ne sont pas autorisés à participer aux réunions de canal si ils ne sont pas membres de l’équipe. La raison principale est que les vérifications de l’organisation de l’organisation dépendent du fait que les utilisateurs peuvent être ajoutés à une liste de conversation de réunion et que, lorsqu’ils peuvent être ajoutés à la liste, ils sont autorisés à participer à la réunion. Le thread de conversation dans une réunion de canal est disponible uniquement pour les membres de l’équipe/canal, et les non-membres ne peuvent pas voir ou accéder au fil de conversation. Si l’organisation est activée et qu’un membre non-équipe tente de rejoindre une réunion de canal, cet utilisateur n’est pas autorisé à participer à la réunion. Toutefois, si l’organisation n’est pas* activée et qu’un membre autre qu’un membre de l’équipe tente de participer à une réunion de canal, l’utilisateur est autorisé à participer à la réunion, mais il ne verra pas l’option de conversation pendant la réunion.
- **Nombre maximal de segments autorisés dans** une organisation : chaque organisation peut configurer jusqu’à 100 segments lors de la configuration des stratégies de l’organisation. Le nombre de stratégies configurables n’est pas limité.
- Les **stratégies DE l’ORGANISATION** ne fonctionnent pas pour les utilisateurs fédérés : si vous autorisez la fédération avec des organisations externes, les utilisateurs de ces organisations ne seront pas limités par les stratégies de l’organisation. Si les utilisateurs de votre organisation participent à une conversation ou à une réunion organisée par des utilisateurs fédérés externes, les stratégies DE l’organisation ne limitent pas non plus la communication entre les utilisateurs de votre organisation.

## <a name="more-information"></a>Plus d’informations

- Pour en savoir plus sur les IB, consultez la [barrière des informations](/office365/securitycompliance/information-barriers).
- Pour configurer les stratégies de l’organisation, voir [Démarrage les barrières à l’information](/office365/securitycompliance/information-barriers-policies).
- Pour modifier ou supprimer des stratégies d’ING, voir [Gérer les stratégies de protection contre la barrière des informations](/microsoft-365/compliance/information-barriers-edit-segments-policies).
- [Barrières de l’information et canaux partagés](information-barriers-shared-channels.md)

## <a name="availability"></a>Disponibilité

Les barrières de l’Teams sont disponibles dans les nuages publics, Cloud de la communauté du secteur public, Cloud de la communauté du secteur public- haut et DOD.
