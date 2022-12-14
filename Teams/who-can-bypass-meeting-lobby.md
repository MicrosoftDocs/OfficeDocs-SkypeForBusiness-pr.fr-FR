---
title: Contrôler qui peut contourner la salle d’attente de la réunion dans Microsoft Teams
ms.author: mikeplum
author: MikePlumleyMSFT
ms.reviewer: rbronisevsky
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Apprenez à utiliser la salle d’attente de la réunion dans Microsoft Teams pour autoriser uniquement certains participants à participer directement à la réunion.
ms.openlocfilehash: c9073209a329c0d97c7d1951c02194d9924eea76
ms.sourcegitcommit: 0d97dc6616b3d633564409e39c08311af1522705
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/14/2022
ms.locfileid: "69392714"
---
# <a name="control-who-can-bypass-the-meeting-lobby-in-microsoft-teams"></a>Contrôler qui peut contourner la salle d’attente de la réunion dans Microsoft Teams

La salle d’attente de réunion Teams est un moyen d’empêcher certains types de participants à une réunion de rejoindre une réunion jusqu’à ce qu’un organisateur, co-organisateur ou présentateur de réunion les admette. Lorsqu’un participant se rend dans la salle d’attente, les organisateurs, les co-organisateurs et les présentateurs sont avertis et peuvent choisir de les admettre à la réunion ou non.

À l’aide des paramètres de salle d’attente dans le Centre d’administration Teams, vous pouvez créer des valeurs par défaut pour les types de participants à la réunion qui sont en mesure de contourner la salle d’attente et quels participants doivent y attendre jusqu’à ce qu’ils soient admis à la réunion. Vous pouvez contrôler la façon dont les types de participants suivants interagissent avec la salle d’attente :

- Organisateur et co-organisateurs de la réunion
- Personnes dans votre organisation
- Invités
- Personnes dans les organisations approuvées
- Participants anonymes

Les identités des personnes qui rejoignent des réunions sont vérifiées par Microsoft 365, sauf si le participant est anonyme. Les participants anonymes ne peuvent pas être vérifiés.

## <a name="prerequisites-for-meeting-with-people-outside-your-organization"></a>Conditions préalables à la réunion avec des personnes extérieures à votre organisation

Il existe plusieurs paramètres dans Teams qui contrôlent si des personnes extérieures à l’organisation peuvent interagir avec Teams. Les paramètres suivants doivent être activés pour permettre aux personnes extérieures à l’organisation de rejoindre des réunions :

- [L’accès invité dans Teams](guest-access.md) doit être activé pour que les invités puissent participer à des réunions.
- [L’accès externe](manage-external-access.md) doit être activé pour que les membres d’organisations approuvées puissent participer aux réunions. Une confiance mutuelle entre votre organisation et l’organisation externe doit être configurée et l’organisateur de la réunion de votre organisation ainsi que tous les participants de l’organisation externe doivent être activés pour l’accès externe.
- Les **utilisateurs anonymes peuvent rejoindre un** paramètre de réunion (au niveau de l’organisation) et la stratégie de réunion (pour l’organisateur qui crée la réunion) doit être **Activée** pour que les participants anonymes puissent participer à des réunions.

Si l’un de ces paramètres est désactivé, ce type de participant externe ne pourra pas participer à des réunions, quels que soient les paramètres de la salle d’attente.

## <a name="overview-of-lobby-settings-and-policies"></a>Vue d’ensemble des paramètres et stratégies de salle d’attente

Le tableau suivant présente les stratégies de réunion Teams qui affectent la façon dont les participants à la réunion interagissent avec la salle d’attente.

|Paramètres|Description|
|:------|:----------|
|**Les utilisateurs anonymes et les appelants rendez-vous peuvent démarrer une réunion**|Il s’agit d’une stratégie par organisateur qui autorise les réunions sans leader. Ce paramètre contrôle si les participants anonymes et les utilisateurs rendez-vous peuvent rejoindre la réunion sans qu’un participant vérifié ne soit présent. Ce paramètre s’applique uniquement lorsque **Qui peut contourner la salle d’attente** est défini sur **Tout le monde**. Si les **utilisateurs anonymes peuvent rejoindre une** organisation de réunion ou le paramètre de réunion est **Désactivé**, ce paramètre s’applique uniquement aux appelants rendez-vous. Par défaut, ce paramètre est désactivé pour éviter tout abus potentiel de vos liens de réunion par des utilisateurs anonymes. <br><br> Si cette option est **désactivée**, les participants anonymes et les utilisateurs connectés attendent dans la salle d’attente jusqu’à ce qu’un participant vérifié (y compris un organisateur de rendez-vous) rejoigne la réunion, auquel cas ils seront automatiquement admis. Une fois la réunion démarrée, les participants anonymes et les utilisateurs rendez-vous rejoignent automatiquement l’appel, même si l’organisateur part. <br><br> Si ce paramètre est **Activé**, les participants anonymes et rendez-vous peuvent démarrer et rejoindre la réunion sans qu’un participant vérifié ne soit présent.|
|**Personnes la numérotation peut contourner la salle d’attente**|Il s’agit d’une stratégie par organisateur. Ce paramètre détermine si les personnes qui composent par téléphone rejoignent directement la réunion ou attendent dans la salle d’attente. Lorsque ce paramètre est **Désactivé**, les utilisateurs rendez-vous attendent dans la salle d’attente jusqu’à ce qu’un organisateur, un co-organisateur ou un présentateur rejoigne la réunion et les admette. Lorsque ce paramètre est **Activé**, les utilisateurs rendez-vous rejoignent automatiquement la réunion sans passer par la salle d’attente. (Si **les utilisateurs anonymes et les appelants rendez-vous peuvent démarrer une réunion** est **désactivé**, ils attendront dans la salle d’attente jusqu’au début de la réunion.)|
|**Qui peut contourner la salle d’attente**|Il s’agit d’une stratégie par organisateur. Ce paramètre contrôle les types de participants (à l’exception de ceux qui se composent directement par téléphone) qui rejoignent une réunion et les types de participants qui attendent dans la salle d’attente jusqu’à ce qu’ils soient admis par un organisateur, un co-organisateur ou un présentateur.|

Le tableau suivant montre comment chaque option de la stratégie **Qui peut contourner la salle d’attente** affecte chaque *type de participant à la réunion*.

|Valeur de stratégie :|Tout le monde|Membres de mon organisation, organisations de confiance et invités|Membres de mon organisation et invités|Membres de mon organisation|Seules les personnes qui ont été invitées|Seuls les organisateurs et les co-organisateurs|
|:--------|:------|:-----|:-----|:------|:-------|:---------------|
|*Organisateur et co-organisateurs*|Contourner|Contourner|Contourner|Contourner|Contourner|Contourner|
|*Personnes dans l’organisation*|Contourner|Contourner|Contourner|Contourner|Personnes qui ont été envoyés ou transférés une invitation contourneront ; d’autres attendent dans la salle d’attente|Hall|
|*Invités*|Contourner|Contourner|Contourner|Hall|Personnes qui ont été envoyés ou transférés une invitation contourneront ; d’autres attendent dans la salle d’attente|Hall|
|*Personnes dans les organisations approuvées*|Contourner|Contourner|Hall|Hall|Personnes qui ont été envoyés ou transférés une invitation contourneront ; d’autres attendent dans la salle d’attente|Hall|
|*Participants anonymes*|Contourner|Hall|Hall|Hall|Hall|Hall|

**Seules les personnes qui ont été invitées** s’appliquent uniquement aux participants vérifiés qui ont reçu une invitation ou auxquels une invitation a été transmise. Les utilisateurs ajoutés dans le cadre d’un groupe de distribution attendront dans la salle d’attente.

## <a name="choose-who-can-bypass-the-lobby-in-meetings-hosted-by-your-organization"></a>Choisir qui peut contourner la salle d’attente dans les réunions hébergées par votre organisation

Vous pouvez configurer les paramètres et les stratégies décrits ci-dessus dans le Centre d’administration Teams. Consultez les sections ci-dessous pour obtenir des conseils sur le paramètre à choisir dans différentes circonstances. Pour plus d’informations sur le fonctionnement des stratégies de réunion, consultez [Gérer les stratégies de réunion dans Microsoft Teams](/microsoftteams/meeting-policies-overview).

> [!Important]
> Les organisateurs de la réunion peuvent modifier les valeurs par défaut que vous choisissez pour la **Personnes la numérotation peut contourner la salle d’attente** et **Qui peut contourner les paramètres de la salle d’attente**. Si vous devez appliquer ces paramètres à une valeur particulière, vous pouvez utiliser un modèle de réunion ou une étiquette de confidentialité (Teams Premium requis).  Pour plus d’informations, consultez [Configurer la salle d’attente de réunion Microsoft Teams pour les réunions sensibles](configure-lobby-sensitive-meetings.md).

Pour définir des stratégies de participation aux réunions et de lobbying
1. Dans le Centre d’administration Teams, développez **Réunions** , puis sélectionnez **Stratégies de réunion**.
1. Sélectionnez la stratégie à mettre à jour.
1. Dans les sections **Participants & invités** , mettez à jour les paramètres que vous souhaitez modifier :
   - **Permettre à des personnes anonymes de rejoindre une réunion**
   - **Autoriser les personnes anonymes à démarrer une réunion**
   - **Admettre automatiquement les personnes** (qui peut contourner la salle d’attente)
   - **Les utilisateurs rendez-vous peuvent contourner la salle d’attente**

    ![Capture d’écran montrant la stratégie de participation à la réunion et de salle d’attente dans le Centre d’administration Teams.](media/meeting-join-and-lobby-tac-settings.png)
1. Sélectionnez **Enregistrer**.

Notez que l’application des modifications peut prendre jusqu’à vingt-quatre heures.

Si vous souhaitez autoriser l’accès anonyme aux réunions, assurez-vous que le paramètre **Utilisateurs anonymes peuvent participer à une réunion** est également activé.

Pour définir le paramètre de réunion à l’échelle de l’organisation pour la participation anonyme à une réunion
1. Dans le Centre d’administration Teams, développez **Réunions** , puis sélectionnez **Paramètres de réunion**.
1. Dans la section **Participants** , définissez **Les utilisateurs anonymes peuvent rejoindre une réunion** sur **Activé** ou **Désactivé**.
    ![Capture d’écran montrant les paramètres de participation à la réunion et de salle d’attente dans le Centre d’administration Teams.](media/anonymous-users-can-join-meetings-org-setting.png)
1. Sélectionnez **Enregistrer**.

## <a name="control-access-to-meetings-by-anonymous-participants"></a>Contrôler l’accès aux réunions par des participants anonymes

Les participants anonymes sont anonymes, car ils ne sont pas connectés à un compte qui peut être vérifié par Microsoft 365. Il peut s’agir des éléments suivants :

- Personnes qui ne sont pas connectés à Microsoft 365 avec un compte professionnel ou scolaire 
- Personnes d’organisations non approuvées (comme configuré dans [l’accès externe](manage-external-access.md)).
- Personnes d’organisations auxquelles vous faites confiance, mais qui ne font pas confiance à votre organisation

Si vous souhaitez empêcher les participants anonymes de participer complètement à une réunion, vous pouvez désactiver le paramètre **Les utilisateurs anonymes peuvent rejoindre une réunion** à l’échelle de l’organisation. Vous pouvez également désactiver la participation anonyme pour des organisateurs de réunion spécifiques à l’aide de la stratégie **Les utilisateurs anonymes peuvent participer à une réunion** .

Si vous souhaitez que les personnes qui rejoignent anonymement attendent dans la salle d’attente, vous pouvez définir la stratégie **de réunion Qui peut contourner la salle d’attente** sur n’importe quel paramètre, sauf **Tout le monde**. (Ce paramètre n’affecte pas les personnes qui composent par téléphone.)

Par défaut, les **utilisateurs anonymes et les appelants rendez-vous peuvent démarrer une stratégie de réunion** est **Désactivée**. Cela signifie que les participants anonymes et les personnes appelant par téléphone attendent toujours dans la salle d’attente si un participant vérifié n’a pas encore commencé la réunion. Bien que vous puissiez activer ce paramètre s’il existe des circonstances où vous souhaitez autoriser des participants anonymes et des personnes appelant par téléphone à démarrer des réunions, nous vous recommandons de le laisser désactivé.  Lorsque le paramètre est activé, les personnes disposant de comptes non vérifiés peuvent démarrer des réunions, notamment en utilisant le lien de réunion pour avoir des réunions à des heures non planifiées.

## <a name="control-access-to-meetings-by-people-dialing-in-by-phone"></a>Contrôler l’accès aux réunions par les personnes qui se composent par téléphone

Par défaut, la **Personnes la connexion à distance peut contourner la stratégie de salle d’attente** est **Désactivée**, mais les organisateurs de la réunion peuvent modifier cela lorsqu’ils configurent la réunion. Vous pouvez modifier la valeur par défaut en mettant à jour la **Personnes la numérotation peut contourner la stratégie de salle d’attente** ou vous pouvez appliquer une valeur particulière à l’aide d’un modèle de réunion.

## <a name="control-access-to-meetings-by-guests-and-people-from-trusted-organizations"></a>Contrôler l’accès aux réunions par les invités et les personnes d’organisations approuvées

Il existe deux types de personnes extérieures à votre organisation qui peuvent participer à des réunions en tant que participants vérifiés :

- Invités : personnes disposant d’un [compte de collaboration B2B Azure Active Directory (Azure AD)](/azure/active-directory/external-identities/what-is-b2b) dans votre organisation
- Utilisateurs d’accès externe : personnes disposant de comptes Azure AD dans une organisation approuvée définie dans [l’accès externe](manage-external-access.md) Teams

Si vous souhaitez que tous les participants vérifiés à la réunion de l’extérieur de votre organisation attendent dans la salle d’attente, vous pouvez définir la stratégie Qui peut contourner la salle d’attente **sur Personnes dans mon organisation** ou **Uniquement les organisateurs et co-organisateurs** (tant qu’un invité n’est pas l’organisateur ou le co-organisateur). Si vous souhaitez que seules les personnes d’organisations approuvées (utilisateurs d’accès externe) attendent dans la salle d’attente, vous pouvez choisir **Personnes dans mon organisation et mes invités**.

## <a name="control-access-to-meetings-by-people-without-invitations"></a>Contrôler l’accès aux réunions par les personnes sans invitation

Si vous souhaitez autoriser uniquement les personnes qui ont des invitations à participer directement aux réunions et que tous les autres participants attendent dans la salle d’attente, définissez **Qui peut contourner la salle d’attente** sur **Uniquement les personnes qui ont été invitées**. (Personnes invités via la liste de distribution ne sont pas inclus.)

Le paramètre **Uniquement les personnes invitées** inclut les participants vérifiés auxquels l’invitation a été transmise, et pas seulement ceux invités directement par l’organisateur. Il n’inclut pas les personnes qui ont le lien de participation à la réunion, mais pas l’invitation elle-même et les participants non vérifiés (anonymes). Ils doivent attendre dans le hall.

Notez que les organisateurs de la réunion peuvent désactiver le transfert de l’invitation à la réunion s’ils souhaitent uniquement que des personnes directement invitées par eux à participer à la réunion.

## <a name="control-access-to-meetings-by-non-organizers"></a>Contrôler l’accès aux réunions par les non-organisateurs

Si vous avez des réunions où des informations sensibles sont partagées ou qui sont soumises à des exigences réglementaires, vous souhaiterez peut-être que tous les participants attendent dans la salle d’attente jusqu’à ce qu’ils soient admis par un organisateur ou des co-organisateurs de la réunion. Dans ce cas, vous pouvez définir **Qui peut contourner la salle d’attente** sur **Uniquement organisateurs et co-organisateurs**.

Étant donné que **qui peut contourner la salle d’attente** définit uniquement une valeur par défaut que les organisateurs de réunion peuvent modifier, envisagez d’appliquer la valeur avec une étiquette de confidentialité ou un modèle de réunion si vous avez des exigences de conformité dans ce domaine. Pour plus d’informations, consultez [Configurer la salle d’attente de réunion Microsoft Teams pour les réunions sensibles](configure-lobby-sensitive-meetings.md).

## <a name="set-meeting-policies-by-using-powershell"></a>Définir des stratégies de réunion à l’aide de PowerShell

Vous pouvez définir les stratégies de réunion décrites dans cet article à l’aide de l’applet de commande PowerShell [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) avec les paramètres suivants :

- [-AllowAnonymousUsersToJoinMeeting](/powershell/module/skype/set-csteamsmeetingpolicy?#-allowanonymoususerstojoinmeeting) pour contrôler si les utilisateurs anonymes peuvent rejoindre des réunions
- [-AllowPSTNUsersToBypassLobby](/powershell/module/skype/set-csteamsmeetingpolicy#-allowpstnuserstobypasslobby) pour contrôler si les personnes qui composent par téléphone peuvent contourner la salle d’attente
- [-AutoAdmittedUsers](/powershell/module/skype/set-csteamsmeetingpolicy?#-autoadmittedusers) pour contrôler qui peut contourner la salle d’attente

## <a name="related-topics"></a>Rubriques connexes

[Participer à une réunion sans compte Teams](https://support.microsoft.com/office/c6efc38f-4e03-4e79-b28f-e65a4c039508)

[Utilisation du Centre d’administration Microsoft Teams pour configurer la stratégie à l’échelle de l’organisation](meeting-settings-in-teams.md#allow-anonymous-users-to-join-meetings)

[Les participants externes reçoivent « Se connecter à Teams pour participer ou contacter l’organisateur de la réunion »](/microsoftteams/troubleshoot/meetings/external-participants-join-meeting-blocked)
