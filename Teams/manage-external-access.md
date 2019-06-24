---
title: Gérez l’accès externe (fédération) dans Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 06/19/2019
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
ms.reviewer: karvell
search.appverid: MET150
description: Votre administrateur informatique peut configurer l’accès externe pour les autres domaines (Fédération) pour permettre aux utilisateurs de ces domaines de participer aux équipes.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 43e4153959a4d444a81f4769daf69976af018c4d
ms.sourcegitcommit: 2af4c9e3a8374d9a6995e36604d8b0b8eff23b34
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/22/2019
ms.locfileid: "35133922"
---
<a name="manage-external-access-federation-in-microsoft-teams"></a>Gérez l’accès externe (fédération) dans Microsoft Teams
======================================================

L’accès externe de Microsoft teams permet aux utilisateurs d’autres domaines de participer à vos conversations et appels. Vous pouvez également autoriser les utilisateurs externes qui utilisent encore Skype entreprise Online ou Skype entreprise sur locaux.

Suivez la procédure décrite dans cet article lorsque :
  
- Vous avez des utilisateurs dans différents domaines dans votre entreprise: par exemple, Rob@ContosoEast.com et Ann@ContosoWest.com.

- Vous voulez que les membres de votre organisation puissent utiliser teams pour contacter des personnes dans des entreprises spécifiques en dehors de votre organisation.

- Vous voulez que les autres personnes qui utilisent des équipes puissent vous trouver et vous contacter à l’aide de votre adresse de messagerie. Par ailleurs, si vous et un autre utilisateur autorisez l’accès externe et autorisez les domaines de chacun d’eux, cela va fonctionner. Si ce n’est pas le cas, l’autre utilisateur doit veiller à ce qu’il ne bloque pas votre domaine.

L’accès externe permet aux utilisateurs externes de rechercher, appeler et envoyer des messages instantanés, ainsi que de configurer des réunions avec vous. Toutefois, si vous souhaitez que les utilisateurs externes aient accès à des équipes et des canaux, l’accès invité peut être une meilleure solution. Pour plus d’informations sur les différences entre l’accès externe et l’accès invité, voir [accès externe et accès invité.](#external-access-vs-guest-access) Pour activer l’accès invité, voir [activer l’accès invité](set-up-guests.md) pour permettre aux utilisateurs de communiquer.

> [!IMPORTANT]
> Pour l’instant, pour fédérer le client Microsoft teams avec un utilisateur externe extérieur à votre organisation qui ne fait pas partie d’un invité de votre Azure Active Directory (Azure AD) ou d’un client, vous devez être correctement configuré pour une utilisation hybride et déplacée vers Skype entreprise online. À partir de 2/25/2019, Teams ne prend pas en charge la Fédération native sans que l’utilisateur du profil SIP soit hébergé dans Skype entreprise online. Pour plus d’informations sur la configuration de votre compte pour l’environnement hybride, puis pour le déplacement vers Teams, voir [mise à niveau de déploiement hybride de Skype entreprise vers teams](https://docs.microsoft.com/en-us/microsoftteams/upgrade-to-teams-execute-skypeforbusinesshybrid).

## <a name="external-access-vs-guest-access"></a>Accès externe et accès invité

L’accès externe (Fédération) et l’accès invité sont différents:

- L’accès invité accorde une autorisation d’accès à une personne. L’accès externe accorde l’autorisation d’accès à l’intégralité d’un domaine.

- Un accès invité, une fois accordé par le propriétaire d’une équipe, permet à un invité d' [accéder aux ressources](guest-experience.md), telles que les discussions de canal et les fichiers, à une équipe spécifique et à discuter avec d’autres utilisateurs de l’équipe auxquelles ils ont été invités. Avec l’accès externe (discussion fédérée), les participants à la conversation externe ne peuvent pas accéder aux équipes ou ressources de l’équipe de l’organisation. Les utilisateurs peuvent participer à une conversation fédérée unique. Les administrateurs de clients peuvent choisir entre les deux options de communication en fonction du niveau de collaboration souhaité avec la partie externe. Les administrateurs peuvent opter pour une approche ou les deux, en fonction des besoins de votre organisation, mais nous vous recommandons d’activer l’accès invité pour une connaissance plus complète et collaborative des équipes. 

Consultez le tableau ci-dessous pour obtenir une comparaison des fonctionnalités d’accès externe et invités.

| Fonctionnalité | Utilisateurs d’Access externe | Utilisateurs de l’accès invité |
|---------|-----------------------|--------------------|
| Les utilisateurs peuvent dialoguer avec une personne d’une autre société | Oui |Oui |
| Un utilisateur peut appeler quelqu’un d’une autre société | Oui | Oui |
| Un utilisateur peut voir si une personne d’une autre société est disponible pour les appels ou les discussions | Oui | Oui<sup>1</sup> |
| Les utilisateurs peuvent rechercher des utilisateurs sur des clients externes | Oui<sup>2</sup> | Non |
| L’utilisateur peut partager des fichiers | Non | Oui |
| L’utilisateur peut accéder aux ressources de l’équipe | Non | Oui |
| L’utilisateur peut être ajouté à une conversation de groupe | Non | Oui |
| L’utilisateur peut être ajouté à une réunion | Oui | Oui |
| D’autres utilisateurs peuvent être ajoutés à une discussion avec un utilisateur externe | No<sup>3</sup> | S/O |
| L’utilisateur est identifié comme partie externe. | Oui | Oui |
| La présence est affichée | Oui | Oui |
| Le message d’absence du Bureau s’affiche | Non | Oui |
| Il est possible de bloquer l’utilisateur individuel. | Non | Oui |
| @mentions prises en charge | Non | Oui |
| Passer des appels privés | Oui | Oui |
| Autoriser la vidéo IP | Oui | Oui |
| Mode de partage d’écran | Oui | Oui |
| Autoriser la Conférence maintenant | Non | Oui |
| Modifier les messages envoyés | Oui | Oui |
| Peut supprimer les messages envoyés | Oui | Oui |
| Utiliser Giphy dans une conversation | Oui | Oui |
| Utiliser mèmes dans une conversation | Oui | Oui |
| Utiliser les autocollants dans les conversations | Oui | Oui |
||||

<sup>1</sup> si l’utilisateur a été ajouté en tant qu’invité et est connecté en tant qu’invité au client invité.<br>
<sup>2</sup> uniquement par courrier électronique ou adresse SIP (Session Initiation Protocol).<br>
<sup>3</sup> les discussions externes (fédérées) sont 1:1 uniquement.

> [!NOTE]
> Pour plus d’informations sur les fonctionnalités invité et l’interface utilisateur, voir [activation ou désactivation de l’accès invité à Microsoft teams](https://docs.microsoft.com/microsoftteams/set-up-guests) , ainsi [que de l’interface utilisateur](https://docs.microsoft.com/microsoftteams/guest-experience).

## <a name="let-your-teams-users-chat-and-communicate-with-users-in-another-organization"></a>Permettre aux utilisateurs d’équipes de discuter et de communiquer avec les utilisateurs d’une autre organisation

L’accès externe permet aux équipes et aux utilisateurs Skype entreprise de communiquer avec d’autres utilisateurs en dehors de votre organisation. Par défaut, votre organisation peut communiquer avec tous les domaines externes. Si vous ajoutez des domaines bloqués, tous les autres domaines seront autorisés, mais si vous ajoutez des domaines autorisés, tous les autres domaines seront bloqués. Vous pouvez facilement configurer l’accès externe pour votre organisation. Il existe trois scénarios pour la configuration:

- **Scénario 1** -vous pouvez utiliser la **Fédération ouverte**. Il s’agit du paramètre par défaut, qui permet aux membres de votre organisation de rechercher, appeler et envoyer des messages instantanés, ainsi que de configurer des réunions avec des personnes extérieures à votre organisation.

    Lorsque vous utilisez cette configuration, vos utilisateurs peuvent communiquer avec tous les domaines externes exécutant Teams, mais ils ont configuré leur domaine/Organisation pour autoriser votre domaine.

- **Scénario 2** -vous pouvez ajouter un ou des domaines à la liste **verte** . Pour cela, cliquez sur **Ajouter un domaine**, ajoutez le nom de domaine, cliquez sur **action à entreprendre sur ce domaine**, puis sélectionnez **autorisé**. Il est important de savoir que, si vous procédez ainsi **** , tous les autres domaines sont bloqués.

- **Scénario 3** : vous pouvez ajouter un ou des domaines à la liste **rouge** . Pour cela, cliquez sur **Ajouter un domaine**, ajoutez le nom de domaine, cliquez sur **action à entreprendre sur ce domaine**, puis sélectionnez **bloqué**. Il est important de savoir que, si vous effectuez cette opération, tous les autres domaines seront **autorisés** .

Pour autoriser ou bloquer des domaines, procédez comme suit.

### <a name="step-1---enable-your-organization-to-communicate-with-another-teams-organization"></a>Étape 1: permettre à votre organisation de communiquer avec d’autres organisations teams

![Icône illustrant le logo](media/teams-logo-30x30.png) de Microsoft teams à l' **aide du centre d’administration Microsoft teams**

1. Dans le volet de navigation de gauche, accédez à**accès externe aux** **paramètres** > à l’échelle de l’organisation.

2. Activez le bouton bascule permettre aux utilisateurs de **communiquer avec les utilisateurs de Skype entreprise et teams** . ****

     ![Capture d’écran du commutateur d’accès externe activé](media/manage-external-access-2.png).

3. Si vous voulez autoriser toutes les organisations teams à communiquer avec les utilisateurs de votre organisation, passez à l’étape 5.

4. Si vous souhaitez limiter les organisations qui peuvent communiquer avec des utilisateurs au sein de votre organisation, vous pouvez autoriser uniquement certains domaines, ou vous pouvez autoriser uniquement des domaines spécifiques. 

    - Pour autoriser tout sauf certains domaines, ajoutez les domaines que vous voulez bloquer en cliquant sur **Ajouter un domaine**. Dans le volet **Ajouter un domaine** , tapez le nom de domaine, cliquez sur **bloqué**, puis **** sur Clik. 
    - Pour limiter les communications à des organisations spécifiques, ajoutez ces domaines à la liste avec l’état **autorisé**. Une fois que vous avez ajouté un domaine à la liste verte, les communications avec d’autres organisations sont limitées uniquement aux organisations dont le domaine figure dans la liste verte. 

5. Cliquez sur **Enregistrer**.

6. Assurez-vous que l’administrateur de la société autres équipes effectue les mêmes étapes. Par exemple, dans la liste des **domaines autorisés** , l’administrateur doit entrer le domaine de votre entreprise s’il limite les organisations qui peuvent communiquer avec leurs utilisateurs.

### <a name="step-2---test-it"></a>Étape 2: testez-le

Pour tester votre configuration, vous avez besoin d’un utilisateur d’équipe qui ne se trouve pas derrière votre pare-feu.
  
1. Lorsque votre administrateur et vous-même avez modifié les paramètres d' **accès externe** , il est conseillé de procéder comme suit.

2. Dans l’application Teams, recherchez la personne par adresse de messagerie et envoyez une demande de discussion.

3. Demandez à votre contact teams de vous envoyer une demande de discussion. Si vous ne la recevez pas, le problème se situe au niveau de vos paramètres de pare-feu (en supposant que votre contact a confirmé que ses paramètres sont corrects).

4. Un autre moyen de tester s’il s’agit d’un problème lié à votre pare-feu consiste à accéder à un emplacement WiFi qui n’est pas situé derrière le pare-feu. par exemple, un café et utiliser teams pour envoyer une demande de discussion à votre contact. Si le message est transmis à l’emplacement WiFi, mais pas quand vous n’êtes pas au bureau, alors cela signifie que le problème provient de votre pare-feu.

## <a name="communicate-with-users-in-a-skype-for-business-online-organization"></a>Communiquer avec des utilisateurs dans une organisation Skype entreprise Online

Si vous configurez l’accès externe pour permettre aux utilisateurs de teams de rechercher et de contacter les utilisateurs qui se trouvent dans une organisation Skype entreprise qui limitent les personnes qui peuvent contacter leurs utilisateurs, procédez comme suit pour configurer l’accès externe de votre domaine au domaine de l’autre organisation. Demandez ensuite à l’administrateur de votre organisation de suivre les étapes ci-dessous pour configurer l’accès externe pour Skype entreprise online.

![Icône illustrant le logo](media/sfb-logo-30x30.png) Skype entreprise **dans le centre d’administration Skype entreprise**

Demandez à l’administrateur de l’organisation de procéder comme suit:

1. Dans le centre d’administration 365 de Microsoft, accédez à **Centre** > d’administration**teams &** > **portail hérité**de Skype.
  
2. Dans le **centre d'administration de Skype Entreprise**, sélectionnez **Organisation** > **Communications externes**.

3. Pour configurer une communication avec une entreprise particulière ou avec des utilisateurs d’un autre domaine, dans la liste déroulante, choisissez **activé uniquement pour les domaines autorisés**.

    Pour permettre à tous les utilisateurs du monde entier de communiquer entre eux, choisissez **activé sauf pour les domaines bloqués**. Il s’agit du paramètre par défaut.

4. Sous **domaines bloqués ou autorisés**, **+** choisissez, puis ajoutez le nom du domaine que vous voulez autoriser.

## <a name="more-information"></a>Plus d’informations

Pour plus d’informations sur l’accès invité dans Microsoft Teams, voir [gérer l’accès invité dans Microsoft teams](manage-guests.md).
