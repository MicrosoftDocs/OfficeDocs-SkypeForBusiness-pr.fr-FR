---
title: Gérez l’accès externe (fédération) dans Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.reviewer: vinbel
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.externalaccess.overview
description: Votre administrateur Teams ou informatique peut configurer l’accès externe pour les autres domaines (Fédération) pour permettre aux utilisateurs de ces domaines de participer à Teams.
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: b354172e5a60e3c6f9df5d74c5d16731fdac0bf8
ms.sourcegitcommit: 4ee9835282e1440d03abc6dbcd172bc20c5b3015
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/01/2020
ms.locfileid: "43096859"
---
<a name="manage-external-access-in-microsoft-teams"></a>Gérer l’accès externe dans Microsoft Teams
======================================================

L’accès externe permet aux utilisateurs de Microsoft teams de rechercher, appeler, discuter et organiser des réunions en équipe. Vous pouvez également utiliser l’accès externe pour communiquer avec des utilisateurs externes qui utilisent encore Skype entreprise (en ligne et sur site) et Skype (en version préliminaire).

Si vous voulez que les utilisateurs externes aient accès aux équipes et aux canaux, l’accès invité sera sans doute préférable. Pour plus d’informations sur les différences entre l’accès externe et l’accès invité, voir [Comparer les accès externe et invité](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access). 

Utilisez l’accès externe dans les situations suivantes :
  
- Vous avez des utilisateurs dans différents domaines qui doivent collaborer. Par exemple, Rob@contoso.com et Ann@northwindtraders.com travaillent ensemble sur un projet en même temps que d’autres personnes dans les domaines contoso.com et northwindtraders.com.

- Vous souhaitez que les membres de votre organisation utilisent Teams pour contacter des personnes appartenant à des entreprises spécifiques extérieures à votre organisation.

- Ou vous souhaitez que tous les utilisateurs de Teams à travers le monde puissent vous contacter, à l'aide de votre adresse électronique. 

> [!IMPORTANT]
> Pour l’instant, pour fédérer au sein de l’application Microsoft Teams auprès d’un utilisateur externe à votre organisation qui n’est pas actuellement un invité de votre client Azure Active Directory (Azure AD) ou de votre client, vous devez être correctement configuré pour hybride et déplacé vers Skype Entreprise Online. Depuis le 25 février 2019, Teams ne prend pas en charge la Fédération native sans que l’utilisateur du profil SIP ne soit hébergé dans Skype Entreprise Online. Pour plus d’informations sur la configuration de votre compte en vue d’un déploiement hybride, puis la migration vers Teams, voir [Mettre à niveau le déploiement hybride Skype Entreprise vers Teams](https://docs.microsoft.com/microsoftteams/upgrade-to-teams-execute-skypeforbusinesshybrid).

## <a name="plan-for-external-access"></a>Plan pour l’accès externe

Par défaut, l’accès externe est activé dans Teams, ce qui signifie que votre organisation peut communiquer avec tous les domaines externes. Si vous ajoutez des domaines bloqués, tous les autres domaines sont autorisés. Si vous ajoutez des domaines autorisés, tous les autres domaines sont bloqués. Trois scénarios permettent de configurer l’accès externe dans le centre d’administration de Teams (**Paramètres à l’échelle de l’organisation** > **Accès externe**) :

- **Fédération ouverte**: il s’agit du paramètre par défaut dans Teams, qui permet aux membres de votre organisation de rechercher, d’appeler, d’envoyer des messages instantanés/conversations et de configurer des réunions avec des personnes extérieures à votre organisation.

    Lorsque vous optez pour cette configuration, vos utilisateurs peuvent communiquer avec tous les domaines externes exécutant Teams ou Skype Entreprise et utilisant la Fédération ouverte OU ayant ajouté votre domaine à leur liste Autoriser.

- **Autoriser des domaines spécifiques**: en ajoutant des domaines à une liste**Autoriser**, vous limitez l’accès externe uniquement aux domaines autorisés. Une fois que vous avez configuré la liste des domaines autorisés, tous les autres domaines sont bloqués. Pour autoriser certains domaines, cliquez sur **Ajouter un domaine**, ajoutez le nom de domaine, cliquez sur **Action à effectuer sur ce domaine**, puis sélectionnez **Autorisé**.

- **Bloquez des domaines spécifiques**-en ajoutant des domaines à une liste **Bloquer**, vous pouvez communiquer avec tous les domaines externes *à l’exception de* ceux que vous avez bloqués. Pour bloquer certains domaines, cliquez sur **Ajouter un domaine**, ajoutez le nom de domaine, cliquez sur **Action à effectuer sur ce domaine**, puis sélectionnez **Bloqué**. Une fois que vous avez configuré la liste des domaines bloqués, tous les autres domaines sont autorisés.

## <a name="allow-or-block-domains"></a>Autoriser ou bloquer des domaines

### <a name="step-1---enable-your-organization-to-communicate-with-another-teams-organization"></a>Étape 1 : permettre aux membres de votre organisation de communiquer avec d’autres organisations Teams

![Icône affichant le logo Microsoft Teams](media/teams-logo-30x30.png) **Utilisation du centre d’administration Microsoft Teams** :

1. Dans le volet de navigation gauche, accédez à **Paramètres à l’échelle de l’organisation** > **Accès externe**.

2. Activez le paramètre**Les utilisateurs peuvent communiquer avec d’autres utilisateurs de Skype Entreprise et de Teams**.

     ![Capture d’écran de Les utilisateurs peuvent communiquer avec d’autres utilisateurs de Skype Entreprise et de Teams activé.](media/manage-external-access-2.png).

3. Si vous voulez autoriser toutes les organisations Teams à communiquer avec des utilisateurs au sein de votre organisation, passez à l’étape 5.

4. Si vous voulez limiter les organisations pouvant communiquer avec les utilisateurs de votre organisation, vous pouvez autoriser tous les domaines sauf certains, ou autoriser uniquement certains domaines. 

    - Pour autoriser tous les domaines sauf certains, ajoutez les domaines que vous voulez bloquer en cliquant sur **Ajouter un domaine**. Dans le volet **Ajouter un domaine**, tapez le nom de domaine, cliquez sur **Bloqué**, puis sur **Terminé**. 
    - Pour limiter les communications à des organisations spécifiques, ajoutez ces domaines à la liste en définissant l’état **Autorisé**. Une fois que vous avez ajouté un domaine à la liste Autoriser, les communications avec d’autres organisations sont limitées aux seules organisations dont les domaines figurent dans la liste Autoriser. 

5. Cliquez sur **Enregistrer**.

6. Assurez-vous que l’administrateur de l’autre organisation Teams effectue les mêmes étapes. Par exemple, dans leur **liste de domaines autorisée**, leur administrateur doit entrer dans le domaine de votre entreprise s’ils limitent les organisations pouvant communiquer avec leurs utilisateurs.

### <a name="step-2---test-it"></a>Étape 2 : tester

Pour tester votre configuration, vous devez disposer d’un contact Teams qui ne soit pas derrière votre pare-feu.
  
1. Une fois que vous et l’administrateur de l’organisation avez modifié les paramètres d’**Accès externe**, vous devriez être prêt.

2. Dans l’application Teams, recherchez la personne par adresse de messagerie et envoyez une demande de conversation.

3. Demandez à votre contact Teams de vous envoyer une demande de discussion. Si vous ne recevez pas leur demande, le problème est lié aux paramètres de votre pare-feu (en supposant qu’ils aient déjà vérifié que les paramètres de leur pare-feu sont corrects).

4. Une autre méthode pour tester si le problème est lié à votre pare-feu consiste à utiliser un emplacement WiFi non protégé par votre pare-feu. par exemple, un cybercafé, et vous pouvez utiliser Teams pour envoyer une demande de conversation à votre contact. Si le message a pu être envoyé depuis l’emplacement WiFi et non depuis votre bureau, vous savez alors que le problème est lié à votre pare-feu.

> [!NOTE]
> Si vous et un autre utilisateur activez l’accès externe et autorisez les domaines d’un autre utilisateur, cela fonctionnera. Si cela ne fonctionne pas, l’autre utilisateur doit s’assurer que sa configuration ne bloque pas votre domaine.

## <a name="communicate-with-users-in-a-skype-for-business-online-organization"></a>Communiquez avec des utilisateurs dans une organisation Skype Entreprise Online

Si vous configurez un accès externe pour permettre à vos utilisateurs Teams de rechercher et de contacter des utilisateurs dans une organisation Skype Entreprise qui limite les personnes qui peuvent contacter leurs utilisateurs, suivez les étapes de configuration de l’accès externe à partir de votre domaine vers le domaine de l’autre organisation. Demandez ensuite à l’administrateur de l’autre organisation de suivre les étapes ci-dessous pour configurer l’accès externe pour Skype Entreprise online.

Pour obtenir des instructions spécifiques sur les scénarios de Skype Entreprise Online courants, voir [Scénarios d’accès externe courants](#common-external-access-scenarios) ci-dessous.

![Icône affichant le logo Skype Entreprise](media/sfb-logo-30x30.png) **Utiliser le Centre d’administration Skype Entreprise**

Demandez à l’administrateur de cette organisation de procéder comme suit :

1. Dans le Centre d’administration Microsoft 365, accédez à **Centres d’administration**  > **Teams & Skype** > **> Portail hérité**.
  
2. Dans la **Centre d’administration Skype Entreprise**, sélectionnez **Organisation** > **Communications externes**.

3. Pour configurer une communication avec une entreprise particulière ou avec des utilisateurs ayant un autre domaine, dans le menu déroulant, choisissez **Activé uniquement pour les domaines autorisés**.

    Ou, s’ils souhaitent activer les communications avec toute personne disposant de stratégies Skype Entreprise ouvertes, sélectionnez **Activer sauf pour les domaines bloqués**. Il s’agit du paramètre par défaut.

4. Sous **Domaines bloqués ou autorisés**, choisissez **+** et ajoutez le nom du domaine que vous voulez autoriser.

## <a name="communicate-with-skype-users-in-preview"></a>Communiquer avec les utilisateurs de Skype (en version d’évaluation)

Pour permettre aux membres Teams de votre organisation de discuter avec et d’appeler des utilisateurs de Skype, procédez comme suit. Les membres de Teams peuvent ensuite rechercher et démarrer une conversation texte privée ou un appel audio/vidéo avec des utilisateurs de Skype, et vice-versa.

![Icône affichant le logo Microsoft Teams](media/teams-logo-30x30.png) **Utilisation du centre d’administration Microsoft Teams** :

1. Dans le volet de navigation gauche, accédez à **Paramètres à l’échelle de l’organisation** > **Accès externe**.

2. Activez le paramètre**Les utilisateurs peuvent communiquer avec les utilisateurs de Skype**.

    ![La capture d’écran du paramètre Les utilisateurs peut communiquer avec Skype activé](media/manage-external-access-5.png).

Pour en savoir plus sur la manière dont les utilisateurs de Teams et les utilisateurs de Skype peuvent communiquer, y compris les limitations qui s’appliquent, voir [Interopérabilité Skype et Teams](teams-skype-interop.md).

## <a name="common-external-access-scenarios"></a>Scénarios d’accès externe courants

|**Si vous souhaitez ...**  |**Procédez comme suit…**  |
|---------|-----------------------|
|Autoriser les**utilisateurs Teams** membres de votre organisation à communiquer avec les **utilisateurs Teams** dans une autre organisation (externe).|Dans Accès externe, ajoutez le domaine externe à la Liste autorisée ou utilisez la Fédération ouverte. Demandez ensuite à l’administrateur de l’autre organisation Teams de faire la même chose.      |
|Autoriser les**utilisateurs Teams** membres de votre organisation à communiquer avec les **utilisateurs Skype Entreprise Online** dans la même organisation.  |Activer le mode de Coexistence ou choisir le Mode de mise à niveau des îlots pour prendre en charge les utilisateurs de Skype Entreprise au sein de votre organisation.   |
|Autoriser les**utilisateurs Teams** membres de votre organisation à communiquer avec les **utilisateurs Skype Entreprise Online** dans une autre organisation (externe).      |Dans Accès externe, ajoutez le domaine externe à la Liste autorisée ou utilisez la Fédération ouverte. <br><br>Activez le paramètre**Les utilisateurs peuvent communiquer avec d’autres utilisateurs de Skype Entreprise et de Teams** sous Accès externe. Demandez ensuite à l’administrateur de l’autre organisation Teams de faire la même chose. <br><br>**Remarque**: le domaine externe avec les utilisateurs de Skype Entreprise doit activer le mode de Coexistence ou choisir le mode de Mise à niveau des îlots pour prendre en charge les utilisateurs de Skype Entreprise au sein de cette organisation.|
|Autoriser les**utilisateurs Teams** membres de votre organisation à communiquer avec les **utilisateurs Skype**.<br> (version d’évaluation)  |Activez le paramètre**Les utilisateurs peuvent communiquer avec les utilisateurs de Skype**sous Accès externe. |
|Autoriser les**utilisateurs Skype Entreprise Online** à communiquer avec les **utilisateurs Teams** dans une autre organisation Office 365.| Vos utilisateurs de Skype Entreprise Online peuvent communiquer avec les utilisateurs Teams d’une autre organisation si vos utilisateurs se trouvent dans l’un des modes de mise à niveau suivants : îlots, SfBOnly, SfBWIthTeamsCollab, SfBWithTeamsCollabAndMeetings ; et les utilisateurs de Teams de l’autre organisation sont en mode TeamsOnly. <br><br>Activez le paramètre**Les utilisateurs peuvent communiquer avec d’autres utilisateurs de Skype Entreprise et de Teams** sous Accès externe. Demandez ensuite à l’administrateur de l’autre organisation Teams de faire la même chose.|
|Autoriser les**utilisateurs Skype Entreprise Online** à communiquer avec les **utilisateurs Skype Entreprise Online** d’une autre organisation Office 365.    | Vos utilisateurs de Skype Entreprise Online peuvent communiquer avec les utilisateurs Skype Entreprise Online d’une autre organisation si vos utilisateurs se trouvent dans l’un des modes de mise à niveau suivants : îlots, SfBOnly, SfBWIthTeamsCollab, SfBWithTeamsCollabAndMeetings ; et les utilisateurs de Skype Entreprise Online de l’autre organisation sont dans l’un des modes suivants : îlots, SfBOnly, SfBWIthTeamsCollab, SfBWithTeamsCollabAndMeetings.<br><br>Activez le paramètre**Les utilisateurs peuvent communiquer avec d’autres utilisateurs de Skype Entreprise et de Teams** sous Accès externe. Demandez ensuite à l’administrateur de l’autre organisation Teams de faire la même chose.|
|Autoriser vos**utilisateurs Skype Entreprise Online** à communiquer avec les **utilisateurs Skype Entreprise** d’une autre organisation locale.     |Vos utilisateurs de Skype Entreprise Online peuvent communiquer avec les utilisateurs Skype Entreprise d’une autre organisation locale si vos utilisateurs se trouvent dans l’un des modes de mise à niveau suivants : îlots, SfBOnly, SfBWIthTeamsCollab, SfBWithTeamsCollabAndMeetings ; et les utilisateurs de Skype Entreprise Online de l’autre organisation sont dans l’un des modes suivants : îlots, SfBOnly, SfBWIthTeamsCollab, SfBWithTeamsCollabAndMeetings.<br><br>Activez le paramètre**Les utilisateurs peuvent communiquer avec d’autres utilisateurs de Skype Entreprise et de Teams** sous Accès externe. Demandez ensuite à l’administrateur de l’autre organisation Teams de faire la même chose.|
|Autoriser les**utilisateurs Skype Entreprise Online** à communiquer avec les **utilisateurs Skype** (dans et hors votre organisation).   |Activez le paramètre**Les utilisateurs peuvent communiquer avec les utilisateurs de Skype**sous Accès externe.|

> [!IMPORTANT]
> Vous n’êtes pas obligé d’ajouter des **domaines Skype** comme domaines autorisés pour permettre aux utilisateurs Teams ou Skype Entreprise Online de communiquer avec des utilisateurs de Skype à l’intérieur ou à l’extérieur de votre organisation. Tous les **domaines Skype**sont des éléments approuvés, ce qui signifie que tous ces domaines sont considérés comme AUTORISÉS.

## <a name="how-does-external-access-compare-with-guest-access"></a>Qu’est-ce que l’accès externe par rapport à l’accès invité ?

Pour en savoir plus sur la différence entre l’accès externe et l’accès invité, consultez [Communiquer avec des utilisateurs d’autres organisations](communicate-with-users-from-other-organizations.md).

## <a name="related-topics"></a>Sujets associés

- [Expérience de conversation native pour les utilisateurs externes (fédérés)](native-chat-for-external-users.md)
