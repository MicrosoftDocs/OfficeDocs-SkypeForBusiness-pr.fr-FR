---
title: Planifier la gestion du cycle de vie
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: reference
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: Dans cet article, vous allez découvrir comment planifier l’implémentation des fonctionnalités de gestion du cycle de vie dans Teams.
ms.localizationpriority: high
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 082657f5d114a7228f5b95e39390a87ccf6d0dcb
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58727823"
---
# <a name="plan-for-lifecycle-management-in-teams"></a>Planifier la gestion du cycle de vie dans Teams

Teams fournit un ensemble complet d’outils pour implémenter les processus de gestion du cycle de vie de la collaboration de votre organisation. Cet article expose aux spécialistes des technologies de l’information les éléments à prendre en compte pour déterminer leurs besoins en matière de gestion du cycle de vie, ainsi que les outils à utiliser pour y répondre. 

La planification du cycle de vie est importante, car cela signifie que vous établissez un plan pour accomplir vos tâches efficacement. La plupart des projets s’articulent autour d’un début, d’un milieu et d'une fin. Teams également, mais elle peut être constituée et utilisée de manière tellement différente qu’il n’est pas toujours facile de savoir à quelle étape de son cycle de vie elle correspond. Avoir un plan de gestion du cycle de vie vous permettra de suivre les projets de votre organisation au fur et à mesure qu’elle franchi ces étapes.

> [!Tip]
> Regardez la session suivante pour en savoir plus sur le cycle de vie dans Microsoft Teams : [Gouvernance, gestion et cycle de vie dans Microsoft Teams](https://aka.ms/teams-governance)


## <a name="lifecycle-concepts"></a>Concepts de cycle de vie

Les concepts et définitions suivants ont tous une incidence sur les décisions que vous prenez concernant la gestion du cycle de vie.

**Teams**

Une _équipe_ est un regroupement de personnes, de contenu et d'outils qui facilitent la collaboration. Une équipe définit qui sont ses membres, ainsi que les autorisations et stratégies qui s’appliquent à ces membres. Les équipes sont centrées autour de groupes Microsoft 365, et les modifications apportées à l’appartenance à un groupe Microsoft 365 sont synchronisées avec l’équipe. Comme les autres groupes Microsoft 365, une boîte de messagerie Exchange, un site SharePoint, un bloc-notes OneNote ainsi que d’autres ressources dans Microsoft 365 ou Office 365 sont mis à disposition automatiquement dans Teams. [En savoir plus sur les groupes Microsoft 365](https://support.office.com/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2).

**Canaux**

Les canaux sont les espaces de collaboration au sein desquels les tâches réelles sont effectuées. Chaque canal représente un thème ou un flux de travail différent dans l’équipe globale. Pour chaque canal, un dossier est créé automatiquement sur le site SharePoint pour stocker tous les fichiers partagés dans ce canal, ce qui permet aux utilisateurs de trouver et travailler facilement sur les documents qui les concernent. Les canaux peuvent également être complétés d’applications correspondant au flux de travail spécifique. Par exemple, vous pouvez ajouter un tableau de bord Power BI à un canal pour suivre la réussite d’un aspect de votre projet.

**Types d’accès à l’équipe**

Les types d’accès suivants déterminent qui peut rejoindre l’équipe :

-   Les équipes _privées_ sont restreintes aux membres de l’équipe approuvés par le ou les propriétaire(s) de celle-ci. Il s’agit du paramètre le plus courant pour les équipes de projet et les équipes virtuelles dans une grande organisation.
-   Les équipes _publiques_ sont ouvertes à tous les utilisateurs au sein de l'organisation, qui peuvent les rejoindre directement. Elles sont utiles pour la collaboration sur des thèmes d’intérêt général pour les personnes de services différents qui travaillent sur des projets distincts. Ce paramètre par défaut est idéal pour les organisations plus petites.

**Types d’utilisateurs de l’équipe et rôles d’administration** 

Les types d’utilisateurs de l’équipe déterminent le niveau de contrôle dont dispose un membre :

-   Le *créateur de l’équipe* dispose d’autorisations pour créer un groupe ou une équipe dans le répertoire. L’administrateur peut restreindre ce type d’utilisateurs à un sous-ensemble d’administrateurs ou utilisateurs. Si vous souhaitez en savoir plus, consultez l’article [Gérer qui peut créer des groupes Microsoft 365](https://support.office.com/article/Manage-who-can-create-Office-365-Groups-4c46c8cb-17d0-44b5-9776-005fced8e618). Les créateurs d’équipe deviennent automatiquement propriétaires d’équipe.
-   Un *propriétaire d’équipe* gère l’appartenance et les paramètres de l’équipe. Une équipe peut comporter jusqu’à 100 propriétaires.
-   Un *membre de l'équipe* est un membre de votre organisation qui participe à une équipe.
-   Un *invité* est un utilisateur qui est externe à votre organisation. N’importe quelle personne ayant une adresse de messagerie peut être invitée si votre organisation a activé l’[accès invité](guest-access.md).

> [!Note]
> Vous trouverez des informations supplémentaires sur les fonctionnalités de propriétaire d’équipe et de membre d’équipe dans l’article [Attribuer le rôle et les autorisations dans Microsoft Teams](assign-roles-permissions.md).

Les rôles d’administration des équipes déterminent les fonctionnalités auxquelles chaque détenteur du rôle d’administrateur a accès. Elles sont décrites dans le tableau suivant.

<table>
 <thead>
  <tr>
    <th width="0.5%"></th>
    <th width="15.5%">Rôle&nbsp;&nbsp;</th>
    <th width="25%">Description</th>
    <th width="60%">Peut effectuer les tâches suivantes, en utilisant les outils indiqués</th>
  </tr>
</thead>
<tbody>
   <tr>
    <td valign="top" colspan="2">Administrateur Teams</td>
    <td valign="top">Gérer le service Teams, et créer et gérer des groupes Microsoft 365</td>
    <td valign="top">Gérer les réunions, y compris les stratégies de réunion, les configurations et les ponts de conférence<sup>1</sup><br><br>Gérer les appels vocaux, y compris les stratégies d’appels, l'inventaire et l’attribution des numéros de téléphone, les files d’attente d’appels et les répondeurs automatiques<sup>1</sup><br><br>Gérer la messagerie, y compris les stratégies de messagerie<sup>1</sup><br><br>Gérer tous les paramètres à l’échelle de l’organisation, notamment la fédération, la mise à niveau de Teams et les paramètres du client Teams<sup>1</sup><br><br>Gérer les équipes de l’organisation et leurs paramètres associés, y compris l’appartenance<sup>2</sup><br><br>Afficher la page de profil des utilisateurs et résoudre les problèmes de qualité des appels à l’aide d’un ensemble avancé d'outils de résolution des problèmes<sup>3</sup></td>
</tr>
<tr>
<td valign="top" colspan="2">Administrateur des communications Teams</td>
<td valign="top">Gérer les fonctionnalités d’appels et de réunions au sein du service Microsoft Teams</td>
<td valign="top">Gérer les réunions, y compris les stratégies de réunion, les configurations et les ponts de conférence<sup>1</sup><br><br>Gérer les appels vocaux, y compris les stratégies d’appels, l'inventaire et l’attribution des numéros de téléphone, les files d’attente d’appels et les répondeurs automatiques<sup>1</sup><br><br>Afficher la page de profil des utilisateurs et résoudre les problèmes de qualité des appels à aide d’un ensemble avancé d'outils de résolution des problèmes<sup>1</sup></td>
</tr>
<tr>
<td valign="top" colspan="2">Spécialiste des communications Teams</td>
<td valign="top">Résoudre les problèmes de communications au sein de Teams en utilisant des outils de base</td>
<td valign="top">Accéder à la page de profil des utilisateurs pour résoudre les problèmes relatifs aux appels dans les données d’analyse des appels. Peut afficher uniquement les informations de l’utilisateur spécifique recherché.<sup>3</sup></td>
</tr>
<tr>
<td valign="top" colspan="2">Ingénieur du support technique pour les communications Teams</td>
<td valign="top">Résoudre les problèmes de communications au sein de Teams en utilisant des outils avancés</td>
<td valign="top">Accéder à la page de profil des utilisateurs pour résoudre les problèmes relatifs aux appels dans les données d’analyse des appels. Peut afficher l’intégralité du journal des appels.<sup>3</sup></td>
</tr>
<tr>
</tbody>
<tfoot>
<tr><td align="right"><sup>1</sup></td><td colspan="3"><a href="/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell
">Module PowerShell- Skype Entreprise</a> ou <a href="/microsoftteams/manage-teams-skypeforbusiness-admin-center">Centre d’administration Microsoft Teams</a></td></tr>
<tr><td align="right"><sup>2</sup></td><td colspan="3"><a href="https://www.powershellgallery.com/packages/MicrosoftTeams/0.9.3">Module PowerShell- Microsoft Teams</a> ou <a href="/microsoftteams/manage-teams-skypeforbusiness-admin-center">Centre d’administration Microsoft Teams</a></td></tr>
<tr><td align="right"><sup>3</sup></td><td colspan="3"><a href="/microsoftteams/manage-teams-skypeforbusiness-admin-center">Centre d’administration de Microsoft Teams</a> uniquement</td>
</tr>
</tfoot>
</table>


## <a name="it-decisions-to-make-before-getting-started"></a>Décisions à prendre en matière de technologies de l'information avant de commencer

Avant de déployer Teams dans votre organisation, implémentez les stratégies de gouvernance que votre organisation a déterminé être nécessaires. Elles peuvent inclure des éléments tels que des conventions d’affectation de noms, des stratégies d’expiration, des stratégies de conservation, etc. De manière générale, il est beaucoup plus simple d’implémenter ces exigences avant de mettre à l’échelle votre déploiement dans votre organisation.

Pour pour plus d’informations, reportez-vous à l’article [Planifier la gouvernance dans Teams](plan-teams-governance.md).

## <a name="teams-lifecycle-stages"></a>Stades de cycle de vie des équipes

De manière générale, une équipe a une finalité qui correspond à un projet ou à la réalisation d’un objectif. Même si une équipe a été constituée sur la base d'un intérêt partagé, l’appartenance à l’équipe changera probablement au fil du temps et la discussion peut perdre en efficacité - pour ne resurgir que d'une façon légèrement différente dans une équipe distincte.

Chaque équipe a un début - lorsque qu’elle est créée et que les canaux sont configurés ; un milieu - lorsqu’elle est utilisée et que la collaboration a lieu pour s’accorder au rythme du flux de travail ; et - parfois - une fin, lorsqu’elle a atteint son objectif et est arrivée à la fin de sa durée de vie utile. 

Pour plus d'informations, reportez-vous à l'article [Gérer les équipes dans le centre d’administration Microsoft Teams](manage-teams-in-modern-portal.md).

### <a name="stage-1-beginning"></a>Stade 1: début

#### <a name="create-the-team"></a>Créer l’équipe

La première étape consiste à définir l’objectif de l’équipe (qui peut aller des processus d’entreprise à la structure d’organisation de projets, ou être simplement la création d'une plate-forme de collaboration ouverte et non structurée). La définition de l'objectif de l’équipe va de pair avec l’identification des personnes concernées. Dans la mesure du possible, il est judicieux de favoriser une collaboration ouverte en visant une appartenance large. 

Les propriétaires de l’équipe invitent les membres, définissent la représentation et la description de l’équipe et peuvent définir les autorisations pour les membres individuels. 

> [!Tip]
>  L’idéal est d’identifier au moins deux propriétaires de l’équipe, pour tenir compte de l’absence ou de la réaffectation.

#### <a name="team-origins"></a>Origines de l’équipe

Les équipes peuvent être issues de différentes méthodes, notamment :

-   Créez l’équipe à partir de zéro. Ajoutez les membres en utilisant les alias de messagerie ou noms d’utilisateur ou développez une liste de distribution.
-   Créer l’équipe à partir d’une équipe existante, et utiliser sa configuration de canal et d’application à partir d'un modèle. Vous pouvez aussi utiliser sa liste d’appartenance.
-   Ajouter une équipe à un groupe Microsoft 365 existant, qui donne également accès à l’équipe à sa boîte aux lettres et à son site SharePoint.
-   Utiliser les API Teams Microsoft Graph ou des applets de commande PowerShell pour créer des équipes. Les API peuvent créer des équipes par programmation en fonction des attributs du carnet d’adresses global (tels que la région ou le département) ou des processus d’entreprise (engagements clients ou listes de classes par exemple).

Utilisez ces liens pour obtenir plus d’informations sur l'organisation de vos équipes.

-   [Meilleurs pratiques d'organisation d'équipe dans Teams](best-practices-organizing.md)
-   [Déployer conversation, les équipes, les canaux et les applications](deploy-chat-teams-channels-microsoft-teams-landing-page.md)
-   [Déployer des réunions et des conférences](deploy-meetings-microsoft-teams-landing-page.md)
-   [Déployer les appels vocaux dans le nuage](cloud-voice-landing-page.md)


|    |     |
|-----------|------------|
| ![Icône montrant les points de décision.](media/audio_conferencing_image7.png) <br/>Points de décision|<ul><li>Quelle est la finalité de l’équipe ?</li><li>Qui fait partie de l’équipe ?</li><li>L’équipe sera-t-elle privée ou publique ?</li><li>Les nouveaux membres peuvent-ils s’ajouter eux-mêmes ou les propriétaires de l’équipe les ajoutent-ils ?</li><li>Qui aura l’autorisation de créer des canaux ou d’ajouter des onglets, des bots et des connecteurs ?</li></ul> |
| ![Icône montrant les étapes suivantes.](media/audio_conferencing_image9.png)<br/>Étapes suivantes|<ul><li>Créez l’équipe.</li><li>Planifiez les canaux.</li></ul>|


#### <a name="set-up-channels"></a>Configurer les canaux

Tous les propriétaires ou membres d’une équipe ayant les autorisations appropriées peuvent créer des canaux dans l’équipe Il est important de prendre en compte l’objectif de chaque canal : les options incluent la collaboration autour de projets, les discussions sur des thèmes ou des domaines d’intérêt commun. Par défaut, chaque équipe inclut un canal Général. La plupart des équipes ont besoin de davantage de canaux, et les membres créeront des canaux supplémentaires. Il est probable que l’ensemble de canaux se développera de manière organique au fur et à mesure que de nouveaux thèmes ou projets apparaîtront, et les discussions peuvent dépasser le canal dans lequel elles ont commencé.

Pour susciter l’intérêt, le propriétaire du canal peut publier un message de bienvenue, charger des documents pertinents dans l'onglet **Fichiers** ou ajouter des onglets ou connecteurs au canal. Le propriétaire définit également la description du canal, et peut « ajouter aux favoris automatiquement » les canaux importants afin qu’ils soient répertoriés par défaut pour tous les membres de l’équipe.

Envisagez des noms des canaux avant de les créer, car si vous renommez un canal dans l’équipe, le dossier correspondant n’est pas renommé dans la bibliothèque de documents SharePoint, ce qui peut être une source de confusion pour l’utilisateur final. 

|    |     |
|-----------|------------|
| ![Icône montrant les points de décision.](media/audio_conferencing_image7.png) <br/>Points de décision|<ul><li>Quels sont les canaux initiaux qui seront ajoutés à l’équipe ?</li><li>Quelles indications, le cas échéant, seront-elles fournies pour l’ajout de nouveaux canaux ? (Seront-ils configurés par projet, thème, ou...?)</li></ul> |
| ![Icône montrant les étapes suivantes.](media/audio_conferencing_image9.png)<br/>Étapes suivantes|<ul><li>Créez les canaux initiaux.</li><li>Publiez un message de bienvenue.</li><li>Commencez la collaboration.</li></ul>|

### <a name="stage-2-middle"></a>Stade 2: milieu

Lorsque le travail en équipe commence, l’appartenance à l’équipe commence probablement à évoluer avec la hiérarchie du canal. Sauf si l’équipe doit être strictement contrôlée et verrouillée, il est judicieux d’encourager l’exploration même si cela conduit à une impasse. Lorsque les utilisateurs se sentent plus à l’aise, ils peuvent expérimenter les mentions de l’équipe \@, ajouter les canaux à leurs favoris et utiliser l’onglet Général pour se familiariser avec la publication. Chaque équipe est différente : laissez la pratique guider l’évolution de la conception. Contrôlez l’utilisation et l'intégrité de l’équipe via les fonctionnalités de rapports de Teams.

La confiance, la tolérance et l’esprit de collaboration se développent de manière organique au fur et à mesure que les communications de groupe sont engagées et maintenues dans Teams. Les membres de l’équipe constatent l’utilité des conversations de groupe par rapport aux conversations à deux. Les équipes individuelles ont tendance à développer leur propre personnalité, soutenue par des fonctionnalités amusantes comme les images Giphy et les autocollants. En même temps, il est important que les comportements non autorisés ou impolis soient découragés.

Les équipes étant des organismes vivants, elles peuvent avoir parfois besoin d’être contrôlées ou aidées. Voici quelques bonnes pratiques :

- Utilisez des ambassadeurs pour entretenir l’utilisation si elle commence à décliner, et également pour détecter et diffuser les nouveaux comportements créatifs. 
- Gérez les invités de manière judicieuse, en vous assurant que leur accès se termine lorsque le besoin de l’entreprise prend fin.
- Encouragez les membres à utiliser des conversations à thread avec des lignes d’objet pour améliorer la visibilité et l’attention lors du défilement dans un canal.
- Laissez les canaux évoluer avec les besoins de l’entreprise, en ajoutant de nouveaux canaux si nécessaire et en permettant aux anciens de disparaître (ou envisagez leur archivage ou leur suppression s’ils contiennent des données sensibles ou éphémères, en fonction de vos exigences de rétention).
- Répartissez de nouvelles équipes au fur et à mesure que des groupes plus larges ou domaines d’intérêt apparaissent.
- Essayez différentes collaborations de canal, comme des réunions de canal ou des conversations dans un onglet autour des documents.
- Utilisez l’application mobile Microsoft Teams pour accroître l’engagement.

|    |     |
|-----------|------------|
| ![Icône montrant les points de décision.](media/audio_conferencing_image7.png) <br/>Points de décision|<ul><li>Qui contrôlera l’utilisation pour identifier les problèmes ?</li><li>Quelles sont les mesures qui seront utilisées pour déterminer si une équipe est intègre ?</li><li>Identifiez les équipes qui sont arrivées à la fin de leur durée de vie utile.</li><li>Identifiez les équipes non intègres qui servent toujours un objectif mais qui ont besoin d’être dynamisées.</li></ul> |
| ![Icône montrant l’étape suivante.](media/audio_conferencing_image9.png)<br/>Étape suivante|<ul><li>Implémentez un processus pour contrôler l’intégrité des équipes individuelles.</li></ul>|

### <a name="stage-3-end"></a>Stade 3: fin

Lorsque le travail d'une équipe est arrivé à son terme, il est important de prendre officiellement acte qu'il est terminé. Cela donnera aux membres de l’équipe un sentiment de bouclage et empêchera également l’accès à des informations obsolètes et périmées. Vous pouvez utiliser l’équipe elle-même pour effectuer les rituels de clôture comme les analyses rétrospectives et les rapports de synthèse.

Vous pouvez supprimer les équipes que vous n’avez plus besoin de conserver (une équipe créée exclusivement à des fins de test ou contenant des données sensibles par exemple). Les équipes sont ainsi supprimées avec une « suppression réversible » durant une durée de 30 jours, permettant au service Informatique de le récupérer.  La suppression d’une équipe n’a pas d’incidence sur les conversations ou contenus qui ont été conservés conformément aux stratégies de conformité. Les canaux ont également une « suppression réversible » et peuvent être rétablis jusqu’à 21 jours après la suppression. La suppression d’un canal ne supprimera pas le dossier ou son contenu de la bibliothèque de documents SharePoint.

Vous pouvez aussi utiliser des stratégies d’expiration et de rétention, en plus des fonctionnalités d’archivage pour réduire l’exposition aux équipes qui ne sont plus actives ou aux propriétaires qui ont quitté l'organisation.

Les stratégies de rétention appliquées à Teams ou aux services associés tels que SharePoint peuvent interdire la suppression d’équipes. En outre, tenez compte du fait que le contenu d’une équipe est souvent bien plus que de simples fichiers dans la bibliothèque de documents SharePoint. Il s’agit de conversations, de tableaux du Planificateur, de wikis, de résultats de formulaires, de réunions enregistrées, de blocs-notes OneNote et bien d’autres.

Pour obtenir des informations sur la configuration des stratégies d’expiration et de rétention, reportez-vous à l’article [Présentation de la sécurité et de la conformité dans Microsoft Teams](security-compliance-overview.md).

|    |     |
|-----------|------------|
| ![Icône montrant les points de décision.](media/audio_conferencing_image7.png) <br/>Points de décision|<ul><li>Définissez à quoi ressemble la fin de la durée de vie d’une équipe.</li><li>Décidez si le contenu de l’équipe doit rester disponible ou non, et pendant combien de temps.</li></ul> |
| ![Icône montrant les étapes suivantes.](media/audio_conferencing_image9.png)<br/>Étapes suivantes|<ul><li>Documentez les meilleures pratiques et les leçons apprises.</li><li>Archivez les données si nécessaire.</li></ul>|

## <a name="related-topics"></a>Rubriques connexes

[Démarrage rapide de la gouvernance pour Teams](teams-adoption-governance-quick-start.md)
