---
title: Vue d’ensemble de la sécurité et de la conformité
author: laurawi
ms.author: laurawi
manager: laurawi
ms.topic: conceptual
ms.service: msteams
ms.reviewer: anwara
audience: admin
description: Une vue d’Microsoft Teams fonctionnalités de sécurité et de conformité telles que la confidentialité et le chiffrement, l’audit et les rapports, etc.
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
- remotework
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.securityandcompliance
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: e653e10dbaa0d8211fd10ca6b0f4b8507e748f7d
ms.sourcegitcommit: c7904086e6956ad8d0e5544530bcc90d608b6e6a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/14/2022
ms.locfileid: "62039917"
---
# <a name="security-and-compliance-in-microsoft-teams"></a>Sécurité et conformité dans Microsoft Teams

> [!IMPORTANT]
> Pour découvrir comment garantir au mieux la sécurité pendant que tout le monde travaille à domicile en cas **d’épidémie de COVID-19,** lisez les articles suivants :
>  - [12 premières tâches pour les équipes de sécurité qui prennent en charge le travail à domicile](/microsoft-365/security/top-security-tasks-for-remote-work)
>  - [Optimiser la connectivité de Microsoft 365 ou Office 365 pour les utilisateurs à distance à l’aide de la segmentation de tunnel VPN](/Office365/Enterprise/office-365-vpn-split-tunnel)
>  - Mise à jour : 2 avril 2020 : [guide Teams sécurité des données](teams-security-guide.md)


Microsoft Teams est intégré à la technologie Microsoft 365 et Office 365 cloud à l’échelle hypertexte et de qualité entreprise, qui fournit les fonctionnalités avancées de sécurité et de conformité que nos clients attendent. Pour plus d’informations sur la planification de la sécurité dans Microsoft 365 ou [Office 365,](/microsoft-365/security/office-365-security/security-roadmap) la feuille de route de sécurité est un bon point de départ. Pour plus d’informations sur la planification de la conformité dans Microsoft 365 ou Office 365, vous pouvez commencer avec l’aide du plan de sécurité [et & conformité.](/microsoft-365/compliance/plan-for-security-and-compliance)


Cet article vous fournira des informations supplémentaires sur Teams sécurité et conformité spécifiques. Ne manquez pas ces vidéos sur la sécurité et la conformité de Microsoft Mechanics :

- [Microsoft Teams essentials pour les services informatiques :](https://youtu.be/91lHNKVVvQ4) sécurité et conformité (12:42 min)
- [Microsoft Teams Contrôles de sécurité et conformité](https://www.youtube.com/watch?v=Km4T4hMM__k) (10:54 min)

> [!IMPORTANT]
> En tant que client de Microsoft 365 ou Office 365, vous possédez et contrôlez vos données. Microsoft n’utilise vos données que pour vous fournir le service à qui vous êtes abonné. En tant que fournisseur de services, nous n’analyserons pas vos messages électroniques, vos documents ou vos équipes à des fins publicitaires ou non liées au service. Microsoft n’a pas accès au contenu téléchargé. Comme OneDrive et SharePoint dans Microsoft 365, les données client restent au sein du client. Pour plus d’informations sur la sécurité et la confiance, consultez le Centre de sécurité [Microsoft.](https://microsoft.com/trustcenter) Teams suit les mêmes recommandations et principes que le Centre de trust Microsoft.

## <a name="security"></a>Sécurité

Teams applique l’authentification à deux facteurs à l’échelle de l’équipe et de l’organisation, l’authentification unique via Active Directory et le chiffrement des données en transit et au repos. Les fichiers sont stockés dans SharePoint et sont sécurisés par SharePoint chiffrement. Les notes sont stockées dans OneNote et sont enregistrées à l’OneNote chiffrement. Les OneNote sont stockées dans le site d’équipe SharePoint site. L’onglet Wiki peut également être utilisé pour la prise de notes, et son contenu est également stocké dans le site d SharePoint é team.

Lisez [les](identify-models-authentication.md) modèles d’identité et l’authentification pour obtenir des informations plus complètes sur l’authentification et la Teams, et le fonctionnement de l’authentification moderne vous sera utile dans le domaine de l’authentification moderne en particulier. [](sign-in-teams.md)

Étant donné Teams en partenariat avec SharePoint, OneNote, Exchange, etc., vous devez être à l’aise pour gérer la sécurité au niveau Microsoft 365 ou Office 365 niveau général. Pour en savoir plus, découvrez comment configurer votre organisation pour [Microsoft 365 ou Office 365 sécurité accrue.](/office365/securitycompliance/tenant-wide-setup-for-increased-security)

> [!NOTE]
> Actuellement, les [canaux privés prend](private-channels.md) en charge des fonctionnalités limitées de sécurité et de conformité. La prise en charge de l’ensemble complet des fonctionnalités de sécurité et de conformité dans les canaux privés sera prochainement prise en charge.

### <a name="advanced-threat-protection-atp"></a>Protection avancée contre les menaces

La protection avancée contre les menaces est disponible pour les Microsoft Teams, ainsi que pour les applications SharePoint et OneDrive qui s’intègrent avec les Teams pour la gestion de contenu. AtP vous permet de déterminer si le contenu de ces applications est malveillant et de bloquer l’accès des utilisateurs.

La manière dont le contenu affecté est géré après la détection se limite aux paramètres que vous avez sélectionnés dans Microsoft 365 ou Office 365. Nous vous recommandons vivement de prendre en considération toutes les applications lorsqu’il s’agit de configurer la fonction ATP. Pour plus d’informations sur la mise en place de la mise en place d’un atp, nous vous recommandons d’étudier en détail les applications pour [SharePoint, OneDrive](/microsoft-365/security/office-365-security/atp-for-spo-odb-and-teams) et Microsoft Teams.

### <a name="safe-links"></a>Coffre liens

Pour l’instant, les liens sécurisés de la protection avancée contre les menaces [](/microsoft-365/security/office-365-security/atp-safe-links-for-teams) ne sont pas disponibles dans Microsoft Teams, mais ils sont désormais en prévisualisation via notre programme d’adoption des technologies (TAP), et bien qu’une date de publication pour la disponibilité générale ne soit pas définie, nous actualiserons cet article lorsque cette date sera disponible. Entre-temps, pour plus d’informations sur Microsoft 365 liens Office 365 Coffre recherche, consultez les liens d’accès [ATP Coffre la recherche.](/office365/securitycompliance/atp-safe-links#how-to-get-atp-safe-links-protection) Des liens de Coffre ATP sont disponibles dans [atp plan 1 et ATP (plan 2).](/microsoft-365/security/office-365-security/office-365-atp)

### <a name="safe-attachments"></a>Coffre pièces jointes

Coffre pièces jointes est une fonctionnalité conçue pour renforcer la sécurité des utilisateurs en vérifiant et en détectant des pièces jointes malveillantes. Les administrateurs globaux [](/microsoft-365/security/office-365-security/set-up-atp-safe-attachments-policies) ou de sécurité créent des stratégies pour gérer ces pièces jointes malveillantes suspectées afin d’empêcher leur envoi à des utilisateurs, de cliquer dessus et d’agir dessus. Coffre protection des pièces jointes est disponible pour les SharePoint, OneDrive et Microsoft Teams, ainsi qu’Microsoft 365 ou Office 365 Advanced Threat Protection Plan 1 et [2.](/microsoft-365/security/office-365-security/office-365-atp) En savoir plus sur Coffre pièces jointes et la manière dont elles peuvent contribuer à protéger votre organisation dans [Coffre pièces jointes dans Microsoft Defender pour Office 365.](/microsoft-365/security/office-365-security/atp-safe-attachments)

### <a name="secure-score"></a>Secure Score

Microsoft Secure Score est une mesure de la sécurité d’une organisation, avec un nombre plus élevé indiquant des actions d’amélioration apportées. Il est également possible de le trouver dans [le Microsoft 365 de sécurité de l’équipe.](https://security.microsoft.com/securescore) La suite des recommandations sur le score de sécurité permet de protéger votre organisation contre les menaces. À partir d’un tableau de bord centralisé dans le Microsoft 365 de sécurité, les organisations peuvent surveiller et travailler sur la sécurité de leurs identités, applications et appareils Microsoft 365 de sécurité. Microsoft Teams à présent des recommandations sur Secure Score et les administrateurs sont invités à surveiller leur sécurité sur la plateforme.

Secure Score aide les organisations :
- État de l’état actuel de la sécurité de l’organisation.
- Améliorez leur sécurité en fournissant une visibilité, une visibilité, des conseils et un contrôle.
- Comparez avec les références et établissez des indicateurs de performance clés.

### <a name="how-conditional-access-policies-work-for-teams"></a>Fonctionnement des stratégies d’accès conditionnel pour les Teams

Microsoft Teams repose largement sur Exchange Online, SharePoint et Skype Entreprise Online pour les principaux scénarios de productivité, tels que les réunions, les calendriers, les conversations interop et le partage de fichiers. Les stratégies d’accès conditionnel définies pour ces applications cloud s’appliquent aux Microsoft Teams utilisateurs qui se Microsoft Teams directement sur n’importe quel client.

Microsoft Teams est pris en charge séparément en tant qu’application cloud dans Azure Active Directory d’accès conditionnel. Les stratégies d’accès conditionnel définies pour l’Microsoft Teams cloud s’appliquent Microsoft Teams utilisateur lorsqu’un utilisateur se signe. Toutefois, sans les stratégies appropriées sur d’autres applications telles que Exchange Online et SharePoint, les utilisateurs peuvent toujours accéder directement à ces ressources. Pour plus d’informations sur la configuration d’une stratégie d’accès conditionnel dans le portail Azure, voir [Azure Active Directory démarrage rapide.](/azure/active-directory/active-directory-conditional-access-azure-portal-get-started)

Microsoft Teams clients de bureau pour Windows mac prise en charge l’authentification moderne. L’authentification moderne apporte une authentification basée sur Azure Active Directory d’authentification unique (ADAL) aux applications clientes Microsoft Office différentes plateformes.

Microsoft Teams application de bureau prend en charge AppLocker.  Pour plus d’informations sur les conditions préalables pour AppLocker, voir : Conditions requises pour utiliser [AppLocker.](/windows/security/threat-protection/windows-defender-application-control/applocker/requirements-to-use-applocker)

## <a name="compliance"></a>Conformité

Teams dispose d’un large éventail d’informations pour vous aider dans les domaines de conformité, notamment la conformité des communications pour les canaux, les conversations et les pièces jointes, les stratégies de rétention, la protection contre la perte de données, la découverte électronique et la conservation légale pour les canaux, les conversations et les fichiers, la recherche dans le journal d’audit, ainsi que la gestion des applications mobiles avec Microsoft Intune. Nous vous proposons des informations sur toutes ces rubriques ci-dessous, et vous pouvez vous rendre sur le Centre de conformité Microsoft 365 [pour](https://compliance.microsoft.com) gérer ces paramètres.

### <a name="information-barriers"></a>Barrières de l’information

Les barrières de l’information sont des stratégies mises en place par les administrateurs Teams pour empêcher les personnes ou les groupes de communiquer entre eux (lorsqu’ils n’ont pas besoin d’une entreprise pour le faire ou pour une raison réglementaire les empêcher de le faire), et elles vous permettent également de définir des stratégies liées à des éléments tels que la recherche et la découverte électronique (voir ci-dessous). Ces stratégies peuvent avoir un impact sur les utilisateurs dans les conversations en tête-à-tête, les conversations de groupe ou au niveau d’une équipe. La fonctionnalité Barrière des informations est disponible dans le cloud public et depuis janvier 2021, elle est déployée dans le cloud Cloud de la communauté du secteur public cloud.

Pour lire davantage d’informations sur ce sujet, voir [Barrières de](information-barriers-in-teams.md)l’information Microsoft Teams.

### <a name="communication-compliance"></a>Conformité des communications

La conformité des communications dans Microsoft 365 vous permet d’ajouter des utilisateurs à des stratégies internes qui peuvent être configurées pour examiner les communications Microsoft Teams en relation avec du langage choquant, des informations sensibles et des informations liées aux normes internes et réglementaires. Les communications de conversation et les pièces jointes associées dans les canaux d’Teams publics et privés, les conversations individuelles et les pièces jointes peuvent être analysées pour réduire les risques de communication dans votre organisation. Pour plus d’informations sur la configuration des stratégies pour vous aider à détecter, capturer et prendre des mesures pour les communications Teams inappropriées, voir Conformité des communications [dans Microsoft 365.](/microsoft-365/compliance/communication-compliance)

### <a name="sensitivity-labels"></a>Étiquettes de confidentialité

Appliquez [des étiquettes de sensibilité](/microsoft-365/compliance/sensitivity-labels) pour protéger et réguler l’accès au contenu d’organisation sensible créé lors de la collaboration au sein d’équipes. Par exemple, appliquez des étiquettes qui configurent la confidentialité (publique ou privée) des équipes, contrôlent l’accès invité et le partage externe, et gèrent l’accès à partir d’appareils non utilisés. Pour plus d’informations, [examinez les étiquettes de sensibilité dans Microsoft Teams.](sensitivity-labels.md)

### <a name="data-loss-prevention-dlp"></a>Protection contre la perte de données (DLP)

Dans Microsoft Teams, la protection contre la perte de données (DLP), ainsi que les informations plus volumineuses relatives à la protection DLP pour Microsoft 365 ou Office 365, concernent la préparation professionnelle pour la protection des documents et des données sensibles. Que vous soyez préoccupé par des informations sensibles dans des messages ou des documents, les stratégies DLP seront en mesure de s’assurer que vos utilisateurs ne partagent pas ces données sensibles avec des personnes erronées.

Pour plus d’informations sur la protection contre la perte de Teams données, consultez la protection contre la [perte de données pour Microsoft Teams.](/microsoft-365/compliance/dlp-microsoft-teams) Un bon article concernant les problèmes DLP dans O365 est une vue d’ensemble de [la protection contre la perte de données.](/microsoft-365/compliance/data-loss-prevention-policies)

### <a name="customer-key"></a>Clé client

Microsoft 365 supplémentaire une couche de chiffrement par-dessus le chiffrement du service pour votre contenu. À l’aide des clés que vous fournissez, la clé client chiffre différents types de données dans Microsoft Teams. À l’aide de la clé client au niveau de l’application, la clé client chiffre Teams fichiers stockés dans SharePoint Online. Pour plus d’informations, voir [Chiffrement du service avec la clé client.](/microsoft-365/compliance/customer-key-overview) 

À l’aide de la clé client au niveau du client, la clé client chiffre :
- Teams (conversations en tête-à-tête, conversations de groupe, conversations de réunion et conversations de canal)
- Teams messages multimédias (images, extraits de code, vidéos et images Wiki)
- Teams enregistrements d’appel et de réunion stockés dans Teams stockage
- Teams notifications de conversation instantanée
- Teams suggestions de conversation Cortana
- Teams d’état pour plus d’informations, voir Vue d’ensemble de la clé client [pour Microsoft 365](/microsoft-365/compliance/customer-key-tenant-level) au niveau du client et lisez le blog Microsoft Teams qui traite du support de la clé client pour [Microsoft Teams](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/customer-key-support-for-microsoft-teams-now-in-public-preview/ba-p/1999893)désormais en prévisualisation publique. Pour plus d’informations sur la version Protection des données Microsoft qui incluait la clé client au niveau du client, lisez Annoncer les nouvelles fonctionnalités de Protection des données Microsoft pour connaître et [protéger vos données sensibles.](https://techcommunity.microsoft.com/t5/microsoft-security-and/announcing-new-microsoft-information-protection-capabilities-to/ba-p/1999692)

### <a name="retention-policies"></a>Stratégies de rétention

Les stratégies de rétention dans Microsoft Teams vous permettent de conserver des données qui sont importantes pour votre organisation, pour des raisons réglementaires, juridiques, professionnelles ou autres, et de supprimer du contenu et des communications qui ne sont pas pertinents pour être conservés. Vous pouvez également utiliser des stratégies de rétention pour conserver des données pendant une période donnée, puis les supprimer. Pour plus d’informations, [examinez les stratégies de rétention Microsoft Teams.](retention-policies.md)

### <a name="ediscovery"></a>eDiscovery

La découverte électronique, ou eDiscovery, est l’aspect électronique de l’identification, de la collecte et de la production d’informations stockées électroniquement à la suite d’une demande de production dans une enquête ou une enquête juridique. Ces fonctionnalités incluent la gestion de cas, la conservation, la recherche, l’analyse et l’exportation Teams données. Cela inclut les discussions, la messagerie et les fichiers, les résumés de réunion et d’appel. Pour Teams réunions et appels, un résumé des événements survenus au cours de la réunion et de l’appel est créé et mis à disposition dans eDiscovery.

Pour plus d’informations sur l’utilisation des outils de découverte électronique dans le Centre de conformité Microsoft 365 pour rechercher du contenu Teams, consultez les liens ci-dessous :

- [eDiscovery](/microsoft-365/compliance/manage-legal-investigations)

- [Recherche de contenu](/microsoft-365/compliance/search-for-content)

Nous avons un Teams spécifique pour plus d’informations sur la direction [d’une découverte](eDiscovery-investigation.md)électronique de contenu dans Microsoft Teams.

Les clients peuvent tirer parti d’eDiscovery [Advanced eDiscovery](/microsoft-365/compliance/office-365-advanced-ediscovery) selon leurs besoins. Le tableau suivant présente les différences entre les deux options :

|&nbsp; |eDiscovery  |eDiscovery avancée  |
|---------|---------|---------|
|Gestion des cas     |X        |X         |
|Contrôle d'accès  |X         |X         |
|Recherches de contenu     |X         | X        |
|Conservation(s)   |X         | X        |
|Exportation     |X         |X         |
|Détection de duplication     |-         |X         |
|Recherches de pertinence avec Machine Learning    |-         |X         |
|Analyse de données non structurées      |-         |X         |

### <a name="legal-hold"></a>Conservation légale

En cas de litige, il est possible que toutes les données associées à un utilisateur (collecte) ou à une équipe soient conservées comme immutables, afin qu’elles soient utilisées comme preuves pour le cas. Pour ce faire, placez un utilisateur (boîte aux lettres utilisateur) ou une équipe en attente légale. Pour une réserve légale d’équipe, la boîte aux lettres de l’équipe peut être placé dans les limites suivantes :

- In-Place mise en attente (un sous-ensemble de la boîte aux lettres ou de la collection de sites via des requêtes ciblées ou du contenu filtré est mis en attente) ou
- Mise en attente pour litige (l’intégralité de la boîte aux lettres ou de la collection de sites est mise en attente).

Dans les deux cas, une fois la mise en attente définie, elle garantit que, même si les utilisateurs finaux suppriment ou modifient les messages de canal présents dans la boîte aux lettres de groupe, les copies immutables de ce contenu sont conservées et disponibles via la recherche eDiscovery. Les valeurs légales sont généralement appliquées dans le contexte d’un cas de découverte électronique.

Consultez la [vue d’ensemble des stratégies de rétention](/microsoft-365/compliance/retention-policies) pour mieux comprendre la conservation et les conservations dans le Centre de conformité Microsoft 365. Pour plus Teams d’informations spécifiques sur la [](legal-hold.md) attente légale, nous avons également pour vous Microsoft Teams un utilisateur ou une équipe en attente d’action légale.

### <a name="content-search"></a>Recherche de contenu

La recherche de contenu permet de rechercher toutes les Teams via des fonctionnalités de filtrage enrichies. Les données résultantes peuvent être exportées vers un conteneur spécifique à des fins de conformité et d’appui pour les litiges. Cela peut être fait avec ou sans cas de découverte électronique. Cela permet aux administrateurs de conformité de collecter Teams données à tous les utilisateurs, de les consulter et de les exporter pour un traitement approfondi. Reportez-vous [](/microsoft-365/compliance/content-search) à la recherche de contenu pour en savoir plus sur la façon d’effectuer une recherche de contenu de conformité pour des Microsoft Teams et d’autres Microsoft 365 ou contenu Office 365 dans le Centre de conformité Microsoft 365.

> [!TIP]
> Si vous utilisez la recherche de contenu, vous pouvez filtrer vers le bas jusqu’Microsoft Teams contenu uniquement, tel que les messages de conversation et de canal, les réunions et les appels, si nécessaire.

Si vous souhaitez consulter davantage d’Teams spécifiques sur la configuration de la recherche de contenu, examinez la recherche [de contenu dans Microsoft Teams.](content-search.md)

### <a name="auditing"></a>Audit

La recherche dans le journal d’audit se branche directement dans le Centre de conformité Microsoft 365 et vous permet de définir des alertes, ainsi que de créer des rapports sur des événements d’audit, en permettant l’exportation d’ensembles d’événements spécifiques ou génériques de charge de travail à des fin d’utilisation et d’examen par l’administrateur dans le cadre d’une chronologie d’audit illimitée. Vous pouvez configurer des alertes pour toutes les données du journal d’audit au sein du Centre de conformité Microsoft 365, et filtrer et exporter ces données pour une analyse approfondie. Pour en savoir plus sur la recherche d’Microsoft Teams dans le Centre de conformité Microsoft 365, consultez Rechercher des événements dans le journal [d’audit Microsoft Teams.](audit-log-events.md)

## <a name="privacy"></a>Confidentialité

Chez Microsoft, la protection de vos données est la priorité la plus élevée. Pour en savoir plus sur nos pratiques en matière de confidentialité, voir :  

- [Confidentialité chez Microsoft](https://www.microsoft.com/trust-center/privacy)
- [Notre engagement en matière de confidentialité et de sécurité dans Microsoft Teams](https://www.microsoft.com/en-us/microsoft-365/blog/2020/04/06/microsofts-commitment-privacy-security-microsoft-teams/)
- [Pour les professionnels de l’informatique : confidentialité et sécurité dans Microsoft Teams](https://www.microsoft.com/en-us/microsoft-365/blog/2020/04/06/it-professionals-privacy-security-microsoft-teams/#:~:text=We%20safeguard%20your%20privacy%20by,and%20distribution%20of%20your%20data.)

## <a name="information-protection-architecture"></a>Architecture de la protection des informations

La figure suivante indique le flux d’ingestion de données Teams vers les Exchange et les SharePoint pour les Teams et les messages.

> [!div class="mx-imgBorder"]
> ![Diagramme du flux de travail de données Teams vers Exchange et SharePoint.](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1.png)

La figure suivante indique le flux d’ingestion d Teams des réunions et des appels de données vers Exchange.

> [!div class="mx-imgBorder"]
> ![Diagramme du flux de travail de Teams réunions et d’appels de données à Exchange.](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1a.png)

> [!IMPORTANT]
> Il peut y avoir un délai de 24 heures pour découvrir Teams contenu.

## <a name="licensing"></a>Gestion des licences

En ce qui concerne les fonctionnalités de protection des informations, les abonnements Microsoft 365, les abonnements Office 365 abonnements autonomes et les licences autonomes associées déterminent l’ensemble de fonctionnalités disponible.

Pour plus d’informations sur la détermination des besoins en [](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance) matière de gestion des licences afin d’implémenter des fonctionnalités à des fin de sécurité et de conformité, consultez les exigences en matière de gestion des licences pour les fonctionnalités de sécurité et de conformité.

> [!NOTE]
> La recherche de contenu, la découverte électronique principale et les Advanced eDiscovery ne doivent pas être activés dans le Centre de conformité Microsoft 365 pour fonctionner. Pour plus d’informations, [voir Microsoft 365 solutions eDiscovery.](/microsoft-365/compliance/ediscovery)

## <a name="location-of-data-in-teams"></a>Emplacement des données dans Teams

Les données dans Teams se situent dans la région géographique associée à votre organisation Microsoft 365 ou Office 365. Pour savoir quelles régions sont actuellement pris en charge, consultez [l’emplacement](location-of-data-in-teams.md)des données dans Microsoft Teams.

Si vous voulez voir quelle région héberge les [](https://portal.office.com/adminportal/home)données de votre client, Centre d'administration Microsoft 365  >  **Paramètres**  >  **de votre organisation.** Faites défiler vers le bas jusqu’à **Emplacement des données**.

> [!div class="mx-imgBorder"]
> ![Capture d’écran de la table Emplacement des Teams dans le Centre d’administration.](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image5.png)

## <a name="compliance-standards"></a>Normes de conformité

Teams utilise les normes suivantes : [ISO 27001,](/microsoft-365/compliance/offering-iso-27001) [ISO 27018,](/microsoft-365/compliance/offering-iso-27018) [SSAE18 SOC 1 et SOC 2,](/microsoft-365/compliance/offering-soc) [HIPAA](/microsoft-365/compliance/offering-hipaa-hitech)et les clauses contractuelles de l’UE [(EUMC).](/microsoft-365/compliance/offering-eu-model-clauses) Dans le cadre de la conformité Microsoft, Microsoft classe les applications et services Microsoft 365 et Office 365 applications et services en quatre catégories. Chaque catégorie est définie par des engagements de conformité spécifiques qui doivent être satisfaits pour qu’un service Microsoft 365 ou Office 365 ou un service Microsoft associé soit répertorié dans cette catégorie.

Vous pouvez en savoir plus dans les ressources [de protection des données.](https://servicetrust.microsoft.com/ViewPage/TrustDocumentsV3?command=Download&downloadType=Document&downloadId=b7d05b86-c69b-41ba-8245-21161b9febf9&tab=7f51cb60-3d6c-11e9-b2af-7bb9f5d2d913&docTab=7f51cb60-3d6c-11e9-b2af-7bb9f5d2d913_Compliance_Guides) Teams prend également en charge la conformité à la Cloud Security Alliance.

## <a name="related-topics"></a>Sujets associés

[Microsoft 365 sécurité des données](/microsoft-365/security/)

[Microsoft 365 conformité](/microsoft-365/compliance/)

[Offres de conformité Microsoft](/microsoft-365/compliance/offering-home)
