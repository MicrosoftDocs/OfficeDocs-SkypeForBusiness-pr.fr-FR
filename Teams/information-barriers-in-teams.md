---
title: Obstacles à l’information dans Microsoft Teams
description: Cet article explique comment les obstacles à l’information sont pris en charge dans Microsoft Teams.
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
ms.openlocfilehash: e57686e2decb5b2d663f75f1ad7884220a9ff4c2
ms.sourcegitcommit: 1d990582e2deb5f55ba9adada3e17377f792a141
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/19/2022
ms.locfileid: "64922805"
---
# <a name="information-barriers-in-microsoft-teams"></a>Obstacles à l’information dans Microsoft Teams

[Les barrières à l’information (IB) Microsoft Purview](/microsoft-365/compliance/information-barriers) sont des stratégies qu’un administrateur peut configurer pour empêcher des individus ou des groupes de communiquer entre elles. Les E/S sont utiles si, par exemple, un service gère des informations qui ne doivent pas être partagées avec d’autres ministères. Les E/S sont également utiles lorsqu’un groupe doit être isolé ou empêché de communiquer avec quelqu’un en dehors de ce groupe. Les canaux partagés dans Microsoft Teams sont pris en charge par les obstacles à l’information. Selon le type de partage, les stratégies d’obstacle à l’information peuvent restreindre le partage de certaines façons. Pour plus d’informations sur le comportement des canaux partagés et des obstacles à l’information, consultez [Obstacles à l’information et Canaux partagés](information-barriers-shared-channels.md).

Pour Microsoft Teams, les obstacles à l’information peuvent déterminer et empêcher les types de collaboration non autorisés suivants :

- Ajout d’un utilisateur à une équipe ou à un canal
- Accès utilisateur au contenu d’équipe ou de canal
- Accès utilisateur aux conversations de groupe et 1:1
- Accès utilisateur aux réunions
- Empêche les recherches et la découverte, les utilisateurs ne seront pas visibles dans le sélecteur de personnes.

>[!NOTE]
>- Les groupes d’obstacles à l’information ne peuvent pas être créés entre les locataires.
>- L’utilisation de bots, d’applications Azure Active Directory (Azure AD), d’API pour envoyer des notifications de flux d’activité et de certaines API pour ajouter des utilisateurs n’est pas prise en charge dans la version 1.
>- Les canaux privés sont conformes aux stratégies d’obstacles à l’information que vous configurez.
>- Pour plus d’informations sur la prise en charge des obstacles pour les sites SharePoint connectés à Teams, consultez [Segments associés à Microsoft Teams sites](/sharepoint/information-barriers#segments-associated-with-microsoft-teams-sites).

## <a name="background"></a>Arrière-plan

Le principal moteur des E/S provient du secteur des services financiers. L’Autorité de réglementation de l’industrie financière ([FINRA]( https://www.finra.org)) examine les E/S et les conflits d’intérêts au sein des entreprises membres et fournit des conseils sur la gestion de ces conflits (FINRA 2241, Avis réglementaire sur la recherche sur la [dette 15-31](https://www.finra.org/sites/default/files/Regulatory-Notice-15-31_0.pdf).

Toutefois, depuis l’introduction des E/S, de nombreux autres domaines les ont jugés utiles. Voici d’autres scénarios courants :

- **Éducation** : les étudiants d’une école ne peuvent pas rechercher les coordonnées des étudiants d’autres écoles.
- **Juridique** : maintien de la confidentialité des données obtenues par l’avocat d’un client et empêcher l’accès par un avocat du même cabinet qui représente un autre client.
- **Gouvernement** : l’accès et le contrôle de l’information sont limités entre les ministères et les groupes.
- **Professional services** : un groupe de personnes d’une entreprise peut uniquement discuter avec un client ou un client spécifique via un accès invité lors d’un engagement client.

Par exemple, Enrico appartient au segment Banque et Pradeep appartient au segment Conseiller financier. Enrico et Pradeep ne peuvent pas communiquer entre elles, car la stratégie IB de l’organisation bloque la communication et la collaboration entre ces deux segments. Cependant, Enrico et Pradeep peuvent communiquer avec Lee en RH.

![Exemple montrant les obstacles à l’information empêchant la communication entre les segments.](media/information-barriers-example.png)

## <a name="when-to-use-information-barriers"></a>Quand utiliser les obstacles à l’information

Vous souhaiterez peut-être utiliser des E/S dans des situations comme celles-ci :

- Une équipe doit être empêchée de communiquer ou de partager des données avec une autre équipe spécifique.
- Une équipe ne doit pas communiquer ou partager des données avec des personnes extérieures à l’équipe.

Le service d’évaluation des stratégies d’obstacle à l’information détermine si une communication est conforme aux stratégies ib.

## <a name="managing-information-barrier-policies"></a>Gestion des stratégies d’obstacle à l’information

Les stratégies IB sont gérées dans le portail de conformité Microsoft Purview (SCC) à l’aide d’applets de commande PowerShell. Pour plus d’informations, consultez [Définir des stratégies pour les obstacles à l’information](/office365/securitycompliance/information-barriers-policies).

>[!IMPORTANT]
>Avant de configurer ou de définir des stratégies, vous devez activer la recherche d’annuaire délimitée dans Microsoft Teams. Attendez au moins quelques heures après avoir activé la recherche d’annuaires délimités avant de configurer ou de définir des stratégies pour les obstacles à l’information. Pour plus d’informations, consultez [Définir des stratégies d’obstacle à l’information](/office365/securitycompliance/information-barriers-policies#prerequisites).

## <a name="information-barriers-administrator-role"></a>Rôle d’administrateur des obstacles à l’information

Le rôle gestion de la conformité ib est responsable de la gestion des stratégies IB. Pour plus d’informations sur ce rôle, consultez [Autorisations dans le portail de conformité Microsoft Purview](/office365/securitycompliance/permissions-in-the-security-and-compliance-center).

## <a name="information-barrier-triggers"></a>Déclencheurs de barrière d’information

Les stratégies IB sont activées lorsque les événements Teams suivants ont lieu :

- **Les membres sont ajoutés à une équipe** : chaque fois que vous ajoutez un utilisateur à une équipe, la stratégie de l’utilisateur doit être évaluée par rapport aux stratégies IB des autres membres de l’équipe. Une fois l’utilisateur ajouté, l’utilisateur peut effectuer toutes les fonctions de l’équipe sans vérifications supplémentaires. Si la stratégie de l’utilisateur l’empêche d’être ajouté à l’équipe, l’utilisateur ne s’affiche pas dans la recherche.

    ![Capture d’écran de la recherche d’un nouveau membre à ajouter à une équipe et de la recherche d’aucune correspondance.](media/information-barriers-add-members.png)

- **Une nouvelle conversation est demandée** : chaque fois qu’un utilisateur demande une nouvelle conversation avec un ou plusieurs autres utilisateurs, la conversation est évaluée pour s’assurer qu’elle ne viole pas les stratégies IB. Si la conversation viole une stratégie IB, la conversation n’est pas démarrée.

    Voici un exemple de conversation 1:1.

    ![Capture d’écran montrant la communication bloquée dans la conversation 1:1.](media/information-barriers-one-one-chat.png)

    Voici un exemple de conversation de groupe.

    ![Capture d’écran montrant la conversation de groupe.](media/information-barriers-group-chat.png)

- **Un utilisateur est invité à participer à une réunion** : lorsqu’un utilisateur est invité à participer à une réunion, la stratégie IB qui s’applique à l’utilisateur est évaluée par rapport aux stratégies d’ib qui s’appliquent aux autres membres de l’équipe. En cas de violation, l’utilisateur n’est pas autorisé à participer à la réunion.

    ![Capture d’écran montrant l’utilisateur bloqué à la réunion.](media/information-barriers-meeting.png)

- **Un écran est partagé entre deux utilisateurs ou plus** : lorsqu’un utilisateur partage un écran avec d’autres utilisateurs, le partage doit être évalué pour s’assurer qu’il ne viole pas les stratégies IB d’autres utilisateurs. Si une stratégie IB est enfreinte, le partage d’écran n’est pas autorisé.

    Voici un exemple de partage d’écran avant l’application de la stratégie.

    ![Capture d’écran montrant une conversation utilisateur.](media/ib-before-screen-share-policy.png)

    Voici un exemple de partage d’écran après l’application de la stratégie. Les icônes de partage d’écran et d’appel ne sont pas visibles.

    ![Capture d’écran montrant le caractère de l’utilisateur avec des paramètres bloqués.](media/ib-after-screen-share-policy.png)

- **Un utilisateur passe un appel téléphonique dans Teams** : chaque fois qu’un utilisateur lance un appel vocal (via VOIP) à un autre utilisateur ou groupe d’utilisateurs, l’appel est évalué pour s’assurer qu’il ne viole pas les stratégies IB des autres membres de l’équipe. En cas de violation, l’appel vocal est bloqué.

- **Invités dans Teams** : Les stratégies IB s’appliquent également aux invités dans Teams. Si les invités doivent être détectables dans la liste d’adresses globale de votre organisation, consultez [Gérer l’accès invité dans Groupes Microsoft 365](/microsoft-365/admin/create-groups/manage-guest-access-in-groups). Une fois que les invités sont détectables, vous pouvez [définir des stratégies IB](/office365/securitycompliance/information-barriers-policies).

## <a name="how-policy-changes-impact-existing-chats"></a>Impact des modifications de stratégie sur les conversations existantes

Lorsque l’administrateur de stratégie IB apporte des modifications à une stratégie ou lorsqu’une modification de stratégie est activée en raison d’une modification du profil d’un utilisateur (par exemple, pour une modification d’un travail), le service d’évaluation de la stratégie de barrière de l’information recherche automatiquement les membres pour s’assurer que leur appartenance à l’équipe ne viole aucune stratégie.

S’il existe une conversation ou une autre communication entre les utilisateurs et qu’une nouvelle stratégie est définie ou qu’une stratégie existante est modifiée, le service évalue les communications existantes pour s’assurer que les communications sont toujours autorisées. 

- **Conversation 1:1** : Si la communication entre deux utilisateurs n’est plus autorisée (en raison de l’application à un ou les deux utilisateurs d’une stratégie qui bloque la communication), toute communication supplémentaire est bloquée. Leurs conversations de conversation existantes deviennent en lecture seule.

    Voici un exemple montrant que la conversation est visible.

    ![Capture d’écran montrant que la conversation utilisateur est disponible.](media/ib-before-1-1chat-policy.png)

    Voici un exemple montrant que la conversation est désactivée.

    ![Capture d’écran montrant que la conversation utilisateur est désactivée.](media/ib-after-1-1chat-policy.png)

- **Conversation** de groupe : si la communication d’un utilisateur à un groupe n’est plus autorisée (par exemple, parce qu’un utilisateur a modifié des travaux), l’utilisateur, ainsi que les autres utilisateurs dont la participation viole la stratégie, peut être supprimé de la conversation de groupe, et toute communication supplémentaire avec le groupe n’est pas autorisée. L’utilisateur peut toujours voir les anciennes conversations, mais ne pourra pas voir ou participer à de nouvelles conversations avec le groupe. Si la stratégie nouvelle ou modifiée qui empêche la communication est appliquée à plusieurs utilisateurs, les utilisateurs affectés par la stratégie peuvent être supprimés de la conversation de groupe. Ils peuvent toujours voir les anciennes conversations.

  Dans cet exemple, Enrico est passé à un autre service au sein de l’organisation et est supprimé de la conversation de groupe.

  ![Capture d’écran d’une conversation de groupe à partir de laquelle un utilisateur a été supprimé.](media/information-barriers-user-changes-job.png)

  Enrico ne peut plus envoyer de messages à la conversation de groupe.

  ![Capture d’écran de l’impossibilité d’envoyer des messages à une conversation de groupe, car l’utilisateur a été supprimé du groupe.](media/information-barriers-user-changes-job-2.png)

- **Équipe** : tous les utilisateurs qui ont été supprimés du groupe sont supprimés de l’équipe et ne pourront pas voir ou participer à des conversations existantes ou nouvelles.

## <a name="scenario-a-user-in-an-existing-chat-becomes-blocked"></a>Scénario : Un utilisateur dans une conversation existante est bloqué

Actuellement, les utilisateurs rencontrent les scénarios suivants si une stratégie IB bloque un autre utilisateur :

- **Onglet Contacts** : un utilisateur ne peut pas voir les utilisateurs bloqués sous l’onglet **Contacts** .

- **Sélecteur** de personnes : les utilisateurs bloqués ne seront pas visibles dans le sélecteur de personnes.

    ![Capture d’écran de Teams alertant l’utilisateur que la stratégie empêche l’affichage des informations d’un autre utilisateur.](media/information-barriers-people-picker.png)

- **Onglet Activité** : si un utilisateur visite l’onglet **Activité** d’un utilisateur bloqué, aucune publications n’apparaît. ( **L’onglet Activité** affiche uniquement les publications de canal, et il n’y aurait aucun canal commun entre les deux utilisateurs.)

    Voici un exemple d’affichage de l’onglet Activité bloqué.

    ![Capture d’écran montrant l’onglet Activité bloqué.](media/ib-after-activity-tab-policy.png)

- **Organigrammes** : si un utilisateur accède à un organigramme sur lequel un utilisateur bloqué apparaît, l’utilisateur bloqué n’apparaît pas sur le graphique de l’organisation. Au lieu de cela, un message d’erreur s’affiche.

- **Carte contacts** : si un utilisateur participe à une conversation et que l’utilisateur est bloqué par la suite, d’autres utilisateurs voient un message d’erreur au lieu de la carte contacts lorsqu’ils pointent sur le nom de l’utilisateur bloqué. Les actions répertoriées sur la carte (comme l’appel et la conversation) ne seront pas disponibles.

- **Contacts suggérés : les utilisateurs** bloqués n’apparaissent pas dans la liste des contacts suggérés (liste de contacts initiale qui s’affiche pour les nouveaux utilisateurs).

- **Contacts de** conversation : un utilisateur peut voir les utilisateurs bloqués dans la liste des contacts de conversation, mais les utilisateurs bloqués seront identifiés. La seule action que l’utilisateur peut effectuer sur les utilisateurs bloqués consiste à les supprimer. L’utilisateur peut également les sélectionner pour afficher leur conversation passée.

- **Contacts d’appels** : un utilisateur peut voir les utilisateurs bloqués dans la liste des contacts d’appels, mais les utilisateurs bloqués seront identifiés. La seule action que l’utilisateur peut effectuer sur les utilisateurs de bloc consiste à les supprimer.

    Voici un exemple d’utilisateur bloqué dans la liste des contacts d’appels.

    > [!div class="mx-imgBorder"]
    > ![Capture d’écran montrant la conversation utilisateur.](media/ib-before-chat-contacts-policy.png)

    Voici un exemple de la conversation désactivée pour un utilisateur dans la liste de contenu des appels.

    > [!div class="mx-imgBorder"]
    > ![Capture d’écran montrant l’utilisateur bloqué à la conversation.](media/ib-after-chat-contacts-policy.png)

- **Skype à Teams migration** : lors d’une migration de Skype Entreprise vers Teams, tous les utilisateurs, même les utilisateurs bloqués par les stratégies IB, seront migrés vers Teams. Ces utilisateurs sont ensuite gérés comme décrit ci-dessus.

## <a name="teams-policies-and-sharepoint-sites"></a>Teams stratégies et sites SharePoint

Lorsqu’une équipe est créée, un site SharePoint est approvisionné et associé à Microsoft Teams pour l’expérience des fichiers. Les stratégies de barrière d’information ne sont pas respectées par défaut sur ce site et fichiers SharePoint. Pour activer les obstacles à l’information dans SharePoint et OneDrive, suivez les instructions et les étapes décrites dans l’article [Utiliser les obstacles à l’information avec SharePoint](/sharepoint/information-barriers#enable-sharepoint-and-onedrive-information-barriers-in-your-organization) article.

## <a name="information--barrier-modes-and-teams"></a>Modes de barrière de l’information et Teams

Le mode Obstacles à l’information permet de renforcer les personnes qui peuvent être ajoutées ou supprimées d’une équipe. Lorsque vous utilisez des barrières d’information avec Teams, les modes IB suivants sont pris en charge :

- **Ouvert** : cette configuration est le mode IB par défaut pour tous les groupes existants qui ont été approvisionnés avant l’activation des barrières à l’information. Dans ce mode, aucune stratégie IB n’est applicable.
- **Implicite** : cette configuration est le mode IB par défaut lorsqu’une équipe est provisionnée après l’activation des barrières d’informations. Le mode implicite vous permet d’ajouter tous les utilisateurs compatibles dans le groupe.
- **Propriétaire modéré** : ce mode est défini sur une équipe lorsque vous souhaitez autoriser la collaboration entre les utilisateurs de segment incompatibles qui sont modérés par le propriétaire. Le propriétaire de l’équipe peut ajouter de nouveaux membres en fonction de sa stratégie d’IB.

Teams créées avant d’activer une stratégie de cloisonnement des informations dans votre locataire sont automatiquement définies sur *Mode Ouvert* par défaut. Une fois que vous avez activé les stratégies IB sur votre locataire, vous devez mettre à jour le mode de vos équipes existantes vers *Implicite* pour vous assurer que les équipes existantes sont conformes à l’IB.

Utilisez l’applet [de commande Set-UnifiedGroup](/powershell/module/exchange/set-unifiedgroup) avec le paramètre *InformationBarrierMode* qui correspond au mode que vous souhaitez utiliser pour vos segments. La liste des valeurs autorisées pour le paramètre *InformationBarrierMode* est *Open*, *Implicit* et *Owner Moderated*.

Par exemple, pour configurer le mode *implicite* pour un groupe Microsoft 365, vous allez utiliser la commande PowerShell suivante :

```powershell
Set-UnifiedGroup -InformationBarrierMode Implicit
```

Pour mettre à jour le mode d’Open à Implicit pour toutes les équipes existantes, utilisez ce [script PowerShell](information-barriers-mode-script.md).

Si vous modifiez la configuration en mode Ouvert sur des groupes connectés à Teams existants pour répondre aux exigences de conformité de votre organisation, vous devez [mettre à jour les modes IB pour les](/sharepoint/information-barriers#view-and-manage-ib-modes-as-an-administrator-with-sharepoint-powershell) sites SharePoint associés connectés à l’équipe Teams.

## <a name="required-licenses-and-permissions"></a>Licences et autorisations requises

Pour plus d’informations sur les licences et les autorisations, les plans et les tarifs, consultez [Microsoft 365 conseils sur les licences pour la sécurité & la conformité](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).

## <a name="known-issues"></a>Problèmes connus

- **Les utilisateurs ne peuvent pas participer à des réunions ad hoc** : si les stratégies IB sont activées, les utilisateurs ne sont pas autorisés à participer aux réunions si la taille de la liste de réunions est supérieure aux [limites de participation aux réunions](limits-specifications-teams.md). La cause racine est que les vérifications ib reposent sur la possibilité d’ajouter des utilisateurs à une liste de conversation de réunion, et seulement quand ils peuvent être ajoutés à la liste sont autorisés à participer à la réunion. Un utilisateur qui rejoint une réunion ajoute cet utilisateur à la liste ; par conséquent, pour les réunions périodiques, la liste peut se remplir rapidement. Une fois que la liste de conversation a atteint les [limites de participation](limits-specifications-teams.md) à la réunion, les utilisateurs supplémentaires ne peuvent pas être ajoutés à la réunion. Si IB est activé pour l’organisation et que la liste de conversation est complète pour une réunion, les nouveaux utilisateurs (les utilisateurs qui ne figurent pas déjà dans la liste) ne sont pas autorisés à participer à la réunion. Toutefois, si IB n’est pas activé pour l’organisation et que la liste de conversation de la réunion est complète, les nouveaux utilisateurs (ceux qui ne figurent pas déjà dans la liste) sont autorisés à participer à la réunion, bien qu’ils ne voient pas l’option de conversation dans la réunion. Une solution à court terme consiste à supprimer les membres inactifs de la liste de conversation de la réunion afin de faire de l’espace pour les nouveaux utilisateurs. Toutefois, nous augmenterons la taille des listes de conversation de réunion à une date ultérieure.
- **Les utilisateurs ne peuvent pas participer à des réunions de canal** : si les stratégies IB sont activées, les utilisateurs ne sont pas autorisés à participer à des réunions de canal s’ils ne sont pas membres de l’équipe. La cause racine est que les vérifications ib reposent sur la possibilité d’ajouter des utilisateurs à une liste de conversation de réunion, et seulement quand ils peuvent être ajoutés à la liste sont autorisés à participer à la réunion. Le fil de conversation d’une réunion de canal est disponible uniquement pour les membres d’équipe/canal, et les non-membres ne peuvent pas voir ou accéder au fil de conversation. Si IB est activé pour l’organisation et qu’un membre non membre de l’équipe tente de rejoindre une réunion de canal, cet utilisateur n’est pas autorisé à participer à la réunion. Toutefois, si IB n’est pas* activé pour l’organisation et qu’un membre non membre de l’équipe tente de rejoindre une réunion de canal, l’utilisateur est autorisé à participer à la réunion, mais il ne voit pas l’option de conversation dans la réunion.
- **Nombre maximal de segments autorisés dans une organisation** : chaque organisation peut configurer jusqu’à 100 segments lors de la configuration des stratégies IB. Il n’existe aucune limite quant au nombre de stratégies qui peuvent être configurées.
- **Les stratégies IB ne fonctionnent pas pour les utilisateurs fédérés** : si vous autorisez la fédération avec des organisations externes, les utilisateurs de ces organisations ne seront pas limités par les stratégies IB. Si les utilisateurs de votre organisation participent à une conversation ou à une réunion organisée par des utilisateurs fédérés externes, les stratégies ib ne limitent pas non plus la communication entre les utilisateurs de votre organisation.

## <a name="more-information"></a>Plus d’informations

- Pour en savoir plus sur les E/S, consultez [Obstacles à l’information](/office365/securitycompliance/information-barriers).
- Pour configurer des stratégies d’IB, consultez [Démarrage avec des obstacles à l’information](/office365/securitycompliance/information-barriers-policies).
- Pour modifier ou supprimer des stratégies d’ib, consultez [Gérer les stratégies d’obstacle aux informations](/microsoft-365/compliance/information-barriers-edit-segments-policies).
- [Obstacles à l’information et canaux partagés](information-barriers-shared-channels.md)

## <a name="availability"></a>Disponibilité

Les obstacles à l’information dans Teams sont disponibles dans nos clouds publics, Cloud de la communauté du secteur public, Cloud de la communauté du secteur public - Haut et DOD.
