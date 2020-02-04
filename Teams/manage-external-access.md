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
- ms.teamsadmincenter.externalaccess.overview
description: Votre équipe ou administrateur informatique peut configurer l’accès externe pour les autres domaines (Fédération) pour permettre aux utilisateurs de ces domaines de participer aux équipes.
appliesto:
- Microsoft Teams
localization_priority: Normal
ms.openlocfilehash: a04a5547e13b8b93864b1b23dc598b08877c745a
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41707289"
---
<a name="manage-external-access-in-microsoft-teams"></a>Gérer les accès externes dans Microsoft teams
======================================================

L’accès externe permet aux utilisateurs d’équipes externes d’un domaine entier de rechercher, appeler, discuter et organiser des réunions en équipe. Vous pouvez également utiliser l’accès externe pour communiquer avec des utilisateurs externes qui continuent à utiliser Skype entreprise (en ligne ou en local) et Skype (disponible en première 2020).

Si vous voulez que les utilisateurs externes aient accès aux équipes et aux canaux, l’accès invité sera sans doute préférable. Pour plus d’informations sur les différences entre accès externe et accès invité, voir [comparaison des accès externes et invités](communicate-with-users-from-other-organizations.md#compare-external-and-guest-access). 

Utilisez les accès externes dans les cas suivants :
  
- Vous avez des utilisateurs dans différents domaines qui doivent collaborer. Par exemple, Rob@contoso.com et Ann@northwindtraders.com travaillent ensemble sur un projet avec d’autres personnes dans les domaines contoso.com et northwindtraders.com.

- Vous voulez que les membres de votre organisation puissent utiliser teams pour contacter des personnes dans des entreprises spécifiques en dehors de votre organisation.

- Vous voulez que les autres personnes qui utilisent des équipes puissent vous trouver et vous contacter à l’aide de votre adresse de messagerie. 




> [!IMPORTANT]
> Pour le moment, pour fédérer dans l’application Microsoft teams à un utilisateur externe extérieur à votre organisation qui ne fait pas partie d’un invité de votre Azure Active Directory (Azure AD) ou d’un client, vous devez être correctement configuré pour hybride et déplacé vers Skype entreprise online. À compter du 25 février 2019, Teams ne prend pas en charge la Fédération native sans que l’utilisateur du profil SIP ne soit hébergé dans Skype entreprise online. Pour plus d’informations sur la configuration de votre compte pour l’environnement hybride, puis pour le déplacement vers Teams, voir [mise à niveau de déploiement hybride de Skype entreprise vers teams](https://docs.microsoft.com/microsoftteams/upgrade-to-teams-execute-skypeforbusinesshybrid).






## <a name="plan-for-external-access"></a>Planifier l’accès externe

Par défaut, l’accès externe est activé dans Teams, ce qui signifie que votre organisation peut communiquer avec tous les domaines externes. Si vous ajoutez des domaines bloqués, tous les autres domaines seront autorisés ; et si vous ajoutez des domaines autorisés, tous les autres domaines sont bloqués. Il existe trois scénarios pour configurer l’accès externe dans le centre d’administration Teams (**paramètres** > **à**l’échelle de l’organisation) :

- **Ouvrir la Fédération**: il s’agit du paramètre par défaut dans Teams, qui permet aux membres de votre organisation de rechercher, appeler, discuter et organiser des réunions avec des personnes extérieures à votre organisation dans n’importe quel domaine.

    Dans ce scénario, vos utilisateurs peuvent communiquer avec tous les domaines externes exécutant teams ou Skype entreprise et utiliser la Fédération ouverte ou avoir ajouté votre domaine à leur liste verte.

- **Autoriser des domaines spécifiques**: en ajoutant des domaines à une liste **verte** , vous limitez l’accès externe uniquement aux domaines autorisés. Dès lors que vous avez configuré une liste des domaines autorisés, tous les autres domaines sont bloqués. Pour autoriser des domaines spécifiques, cliquez sur **Ajouter un domaine**, ajoutez le nom de domaine, cliquez sur **action à entreprendre sur ce domaine**, puis sélectionnez **autorisé**.

- **Bloquer des domaines spécifiques** : en ajoutant des domaines à une liste **rouge** , vous pouvez communiquer avec tous les domaines externes, *à l’exception* de ceux que vous avez bloqués. Pour bloquer des domaines spécifiques, cliquez sur **Ajouter un domaine**, ajoutez le nom de domaine, cliquez sur **action à entreprendre sur ce domaine**, puis sélectionnez **bloqué**. Dès lors que vous avez configuré une liste des domaines bloqués, tous les autres domaines sont autorisés.

## <a name="allow-or-block-domains"></a>Autoriser ou bloquer des domaines

### <a name="step-1---enable-your-organization-to-communicate-with-another-teams-organization"></a>Étape 1 : permettre à votre organisation de communiquer avec d’autres organisations teams

![Icône illustrant le logo](media/teams-logo-30x30.png)de Microsoft teams à l'**aide du centre d’administration Microsoft teams**  

1. Dans le volet de navigation de gauche, accédez à**accès externe aux** **paramètres** > à l’échelle de l’organisation.

2. Activez le bouton bascule permettre aux utilisateurs de **communiquer avec les utilisateurs de Skype entreprise et teams** **.**

     ![Capture d’écran du commutateur d’accès externe activé](media/manage-external-access-2.png).

3. Si vous voulez autoriser toutes les organisations teams à communiquer avec les utilisateurs de votre organisation, passez à l’étape 5.

4. Si vous souhaitez limiter les organisations qui peuvent communiquer avec des utilisateurs au sein de votre organisation, vous pouvez autoriser uniquement certains domaines, ou vous pouvez autoriser uniquement des domaines spécifiques. 

    - Pour autoriser tout sauf certains domaines, ajoutez les domaines que vous voulez bloquer en cliquant sur **Ajouter un domaine**. Dans le volet **Ajouter un domaine** , tapez le nom de domaine, cliquez sur **bloqué**, puis cliquez sur **Terminer**. 
    - Pour limiter les communications à des organisations spécifiques, ajoutez ces domaines à la liste avec l’état **autorisé**. Une fois que vous avez ajouté un domaine à la liste verte, les communications avec d’autres organisations sont limitées uniquement aux organisations dont le domaine figure dans la liste verte. 

5. Cliquez sur **Enregistrer**.

6. Assurez-vous que l’administrateur de la société autres équipes effectue les mêmes étapes. Par exemple, dans la liste des **domaines autorisés** , l’administrateur doit entrer le domaine de votre entreprise s’il limite les organisations qui peuvent communiquer avec leurs utilisateurs.

### <a name="step-2---test-it"></a>Étape 2 : testez-le

Pour tester votre configuration, vous avez besoin d’un utilisateur d’équipe qui ne se trouve pas derrière votre pare-feu.
  
1. Lorsque votre administrateur et vous-même avez modifié les paramètres d' **accès externe** , il est conseillé de procéder comme suit.

2. Dans l’application Teams, recherchez la personne par adresse de messagerie et envoyez une demande de discussion.

3. Demandez à votre contact teams de vous envoyer une demande de discussion. Si vous ne la recevez pas, le problème se situe au niveau de vos paramètres de pare-feu (en supposant que votre contact a confirmé que ses paramètres sont corrects).

4. Un autre moyen de tester s’il s’agit d’un problème lié à votre pare-feu consiste à accéder à un emplacement WiFi qui n’est pas situé derrière le pare-feu. par exemple, un café et utiliser teams pour envoyer une demande de discussion à votre contact. Si le message est transmis à l’emplacement WiFi, mais pas quand vous n’êtes pas au bureau, alors cela signifie que le problème provient de votre pare-feu.

> [!NOTE]
> Si vous et un autre utilisateur activez l’accès externe et autorisez l’un des domaines de l’un des domaines, cela fonctionnera. Si ce n’est pas le cas, l’utilisateur doit veiller à ce qu’il ne bloque pas votre domaine.

## <a name="communicate-with-users-in-a-skype-for-business-online-organization"></a>Communiquer avec des utilisateurs dans une organisation Skype entreprise Online

Si vous configurez l’accès externe pour permettre aux utilisateurs d’équipes de rechercher et de contacter des utilisateurs dans une organisation Skype entreprise qui limite les personnes qui peuvent contacter leurs utilisateurs, procédez comme suit pour configurer l’accès externe de votre domaine au domaine de l’autre organisation. Demandez ensuite à l’administrateur de votre organisation de suivre les étapes ci-dessous pour configurer l’accès externe pour Skype entreprise online. 

Pour obtenir des instructions spécifiques sur les scénarios courants de Skype entreprise Online, voir [scénarios d’accès externe courants](#common-external-access-scenarios) ci-dessous.

![Icône illustrant le logo](media/sfb-logo-30x30.png) Skype entreprise **dans le centre d’administration Skype entreprise**

Demandez à l’administrateur de l’organisation de procéder comme suit :

1. Dans le centre d’administration 365 de Microsoft, accédez à **Centre** > d’administration**teams &** > **portail hérité**de Skype.
  
2. Dans le **centre d'administration de Skype Entreprise**, sélectionnez **Organisation** > **Communications externes**.

3. Pour configurer une communication avec une entreprise particulière ou avec des utilisateurs d’un autre domaine, dans la liste déroulante, choisissez **activé uniquement pour les domaines autorisés**.

    Pour permettre à tous les utilisateurs du monde entier de communiquer entre eux, choisissez **activé sauf pour les domaines bloqués**. Il s’agit du paramètre par défaut.

4. Sous **domaines bloqués ou autorisés**, **+** choisissez, puis ajoutez le nom du domaine que vous voulez autoriser.

## <a name="common-external-access-scenarios"></a>Scénarios d’accès externes courants

|**Si vous souhaitez....**  |**Procédez comme suit**  |
|---------|-----------------------|
|Permettre **aux utilisateurs** de votre organisation de communiquer avec des **utilisateurs teams** dans une autre organisation (externe).|Dans accès externe, ajoutez le domaine externe à la liste autorisée ou utilisez la Fédération ouverte. Ensuite, demandez à l’administrateur au sein de l’organisation d’autres équipes de faire la même chose.      |
|Permettre **aux utilisateurs** de votre organisation de communiquer avec des **utilisateurs de Skype entreprise Online** au sein de la même organisation.  |Activez le mode de coexistence ou sélectionnez le mode de mise à niveau des îlots pour prendre en charge les utilisateurs Skype entreprise de votre organisation.   |
|Permettre **aux utilisateurs** de votre organisation de communiquer avec des **utilisateurs de Skype entreprise Online** à l’aide d’une autre organisation (externe).      |Dans accès externe, ajoutez le domaine externe à la liste autorisée ou utilisez la Fédération ouverte. <br><br>Activez l’option **les utilisateurs peuvent communiquer avec les utilisateurs de Skype entreprise et équipes** dans l’accès externe. Ensuite, demandez à l’administrateur au sein de l’organisation d’autres équipes de faire la même chose. <br><br>**Remarque**: le domaine externe avec les utilisateurs Skype entreprise doit activer le mode de coexistence ou choisir le mode de mise à niveau des îlots pour prendre en charge les utilisateurs Skype entreprise de cette organisation.|
|Permettre **aux utilisateurs** de votre organisation de communiquer avec des utilisateurs de **Skype** à l’intérieur ou à l’extérieur de votre organisation.   | Ce scénario sera disponible prochainement. <br><br>**Important**: les utilisateurs de Teams ne peuvent pas encore communiquer avec des utilisateurs Skype, mais vos utilisateurs Skype entreprise peuvent continuer à communiquer avec des utilisateurs de Skype à l’intérieur ou à l’extérieur de votre organisation. Activez la fonction permettre aux utilisateurs de **communiquer avec les utilisateurs de Skype entreprise et équipes** , et les utilisateurs de **Skype entreprise peuvent communiquer avec les paramètres d’utilisateurs Skype** dans un accès externe. |
|Autoriser vos **utilisateurs de Skype entreprise Online** à communiquer avec **les utilisateurs de teams** dans une autre organisation Office 365.| Vos utilisateurs de Skype entreprise Online peuvent communiquer avec des utilisateurs de teams dans une autre organisation si vos utilisateurs sont dans l’un des modes de mise à niveau suivants : îles, SfBOnly, SfBWIthTeamsCollab, SfBWithTeamsCollabAndMeetings ; les utilisateurs teams de l’autre organisation sont en mode TeamsOnly. <br><br>Activez l’option les **utilisateurs peuvent communiquer avec les utilisateurs de Skype entreprise et équipes** dans l’accès externe. Par ailleurs, l’administrateur de l’organisation d’autres équipes effectue les mêmes opérations.|
|Autorisez les **utilisateurs de Skype entreprise Online** à communiquer avec des **utilisateurs de Skype entreprise Online** à partir d’une autre organisation Office 365.    | Vos utilisateurs de Skype entreprise Online peuvent communiquer avec des utilisateurs de Skype entreprise Online au sein d’une autre organisation si vos utilisateurs sont dans l’un des modes de mise à niveau suivants : îles, SfBOnly, SfBWIthTeamsCollab, SfBWithTeamsCollabAndMeetings ; les utilisateurs de Skype entreprise Online de l’organisation se trouvent dans l’un des modes de mise à niveau suivants : îles, SfBOnly, SfBWIthTeamsCollab, SfBWithTeamsCollabAndMeetings.<br><br>Activez l’option les **utilisateurs peuvent communiquer avec les utilisateurs de Skype entreprise et équipes** dans l’accès externe. Par ailleurs, l’administrateur de l’organisation d’autres équipes effectue les mêmes opérations.|
|Autoriser vos **utilisateurs de Skype entreprise Online** à communiquer avec des **utilisateurs de Skype entreprise** à partir d’une organisation locale.     |Vos utilisateurs de Skype entreprise Online peuvent communiquer avec des utilisateurs de Skype entreprise à partir d’une organisation locale si vos utilisateurs sont dans l’un des modes de mise à niveau suivants : îles, SfBOnly, SfBWIthTeamsCollab, SfBWithTeamsCollabAndMeetings ; les utilisateurs de Skype entreprise Online de l’organisation se trouvent dans l’un des modes de mise à niveau suivants : îles, SfBOnly, SfBWIthTeamsCollab, SfBWithTeamsCollabAndMeetings.<br><br>Activez l’option les **utilisateurs peuvent communiquer avec les utilisateurs de Skype entreprise et équipes** dans l’accès externe. Par ailleurs, l’administrateur de l’organisation d’autres équipes effectue les mêmes opérations.|
|Autoriser vos **utilisateurs de Skype entreprise Online** à communiquer avec des **utilisateurs de Skype** (à l’intérieur ou à l’extérieur de votre organisation).   |Activez les **utilisateurs de Skype entreprise pour communiquer avec les utilisateurs de Skype** à l’aide d’un paramètre d’accès externe.|

> [!IMPORTANT]
> Vous n’avez pas besoin d’ajouter des **domaines Skype** comme domaines autorisés pour permettre aux utilisateurs d’équipes ou de Skype entreprise Online de communiquer avec des utilisateurs de Skype à l’intérieur ou à l’extérieur de votre organisation. Tous les **domaines Skype** sont autorisés, ce qui signifie que tous les domaines sont considérés comme autorisés.



## <a name="how-does-external-access-compare-with-guest-access"></a>Comment est-ce que l’accès externe est comparé avec l’accès invité ?

Pour en savoir plus sur la différence entre accès externe et accès invité, voir [communiquer avec des utilisateurs d’autres organisations](communicate-with-users-from-other-organizations.md).

## <a name="related-topics"></a>Rubriques connexes

[Interface de conversation native pour les utilisateurs externes (fédérés)](native-chat-for-external-users.md)
