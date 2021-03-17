---
title: Vue d’ensemble de la sécurité et de la conformité
author: laurawi
ms.author: laurawi
manager: laurawi
ms.topic: conceptual
ms.service: msteams
ms.reviewer: anwara
audience: admin
description: Vue d’ensemble des fonctionnalités de sécurité et de conformité de Microsoft Teams, notamment la confidentialité et le chiffrement, l’audit et les rapports, etc.
localization_priority: Normal
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
ms.openlocfilehash: 36cb67dc73177678206e5d5865ba145414ae37a9
ms.sourcegitcommit: 360c78c66386fe00afe535681f51254eda886edf
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/17/2021
ms.locfileid: "50836921"
---
# <a name="security-and-compliance-in-microsoft-teams"></a>Sécurité et conformité dans Microsoft Teams

> [!IMPORTANT]
> Pour découvrir comment garantir au mieux la sécurité pendant que tout le monde travaille à domicile en cas **d’épidémie de COVID-19,** lisez les articles suivants :
>  - [12 premières tâches pour les équipes de sécurité qui prennent en charge le travail à domicile](https://docs.microsoft.com/microsoft-365/security/top-security-tasks-for-remote-work)
>  - [Optimiser la connectivité de Microsoft 365 ou Office 365 pour les utilisateurs à distance à l’aide de la segmentation de tunnel VPN](https://docs.microsoft.com/Office365/Enterprise/office-365-vpn-split-tunnel)
>  - Mise à jour : 2 avril 2020 : [Guide de sécurité de Teams](teams-security-guide.md)


Microsoft Teams est intégré à l’échelle hypertexte de Microsoft 365 et Office 365 cloud de qualité entreprise, et offre aux clients les fonctionnalités avancées de sécurité et de conformité que nos clients attendent. Pour plus d’informations sur la planification de la sécurité [](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-roadmap) dans Microsoft 365 ou Office 365, la feuille de route de sécurité est un bon point de départ. Pour plus d’informations sur la planification de la conformité dans Microsoft 365 ou Office 365, vous pouvez commencer par planifier la conformité des produits [& sécurité.](https://docs.microsoft.com/microsoft-365/compliance/plan-for-security-and-compliance)


Cet article vous fournira des informations supplémentaires sur la sécurité et la conformité spécifiques de Teams. Ne manquez pas ces vidéos sur la sécurité et la conformité de Microsoft Mechanics :

- [Microsoft Teams Essentials pour les services informatiques :](https://youtu.be/91lHNKVVvQ4) Sécurité et conformité (12:42 min)
- [Contrôles Microsoft Teams pour la sécurité et la conformité](https://www.youtube.com/watch?v=Km4T4hMM__k) (10:54 min)

> [!IMPORTANT]
> En tant que client de Microsoft 365 ou Office 365, vous possédez et contrôlez vos données. Microsoft n’utilise vos données que pour vous fournir le service à qui vous êtes abonné. En tant que fournisseur de services, nous n’analyserons pas vos messages électroniques, vos documents ou vos équipes à des fins publicitaires ou non liées au service. Microsoft n’a pas accès au contenu téléchargé. Comme OneDrive et SharePoint dans Microsoft 365, les données client restent au sein du client. Pour plus d’informations sur la sécurité et la confiance, consultez le Centre de sécurité [Microsoft.](https://microsoft.com/trustcenter) Teams suit les mêmes recommandations et principes que le Centre de trust Microsoft.

## <a name="security"></a>Sécurité

Teams applique l’authentification à deux facteurs à l’échelle de l’équipe et de l’organisation, l’authentification unique via Active Directory et le chiffrement des données en transit et au repos. Les fichiers sont stockés dans SharePoint et sont sécurisés par chiffrement SharePoint. Les notes sont stockées dans OneNote et sont chiffrées par OneNote. Les données OneNote sont stockées dans le site d’équipe SharePoint. L’onglet Wiki peut également être utilisé pour la prise de notes et son contenu est également stocké dans le site SharePoint de l’équipe.

Lisez les modèles d’identité et [](sign-in-teams.md) [l’authentification](identify-models-authentication.md) pour plus d’informations sur l’authentification et Teams, et le fonctionnement de l’authentification moderne vous sera utile dans le cas de l’authentification moderne en particulier.

Teams fonctionne en partenariat avec SharePoint, OneNote, Exchange et bien plus encore. Vous devez être à l’aise pour gérer la sécurité dans la suite Microsoft 365 ou Office 365. Pour en savoir plus, découvrez comment configurer votre organisation [Microsoft 365 ou Office 365](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security)pour une sécurité accrue.

> [!NOTE]
> Actuellement, les [canaux privés prend](private-channels.md) en charge des fonctionnalités limitées de sécurité et de conformité. La prise en charge de l’ensemble complet des fonctionnalités de sécurité et de conformité dans les canaux privés sera prochainement prise en charge.

### <a name="advanced-threat-protection-atp"></a>Protection avancée contre les menaces

La protection avancée contre les menaces est disponible pour Microsoft Teams, ainsi que pour SharePoint et OneDrive, les applications qui s’intègrent à Teams pour la gestion de contenu. AtP vous permet de déterminer si le contenu de ces applications est malveillant et de bloquer l’accès des utilisateurs.

La manière dont le contenu affecté est géré après la détection se limite aux paramètres que vous avez sélectionnés dans Microsoft 365 ou Office 365. Nous vous recommandons vivement de prendre en considération toutes les applications lorsqu’il s’agit de configurer la fonction ATP et, pour une lecture plus détaillée, la fonction ATP pour [SharePoint, OneDrive](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-for-spo-odb-and-teams) et Microsoft Teams vous permettra d’obtenir des informations détaillées sur la façon de commencer.

### <a name="safe-links"></a>Liens sécurisés

Si, pour l’instant, les liens sécurisés de protection avancée contre les [](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links-for-teams?view=o365-worldwide) menaces ne sont pas disponibles dans Microsoft Teams, ils sont désormais en prévisualisation via notre Programme d’adoption des technologies (TAP), et alors qu’une date de publication pour la disponibilité générale n’est pas définie, nous actualiserons cet article lorsque cette date sera disponible. En attendant, pour plus d’informations sur les liens sécurisés Microsoft 365 ou Office 365, consultez liens sécurisés [ATP.](https://docs.microsoft.com/office365/securitycompliance/atp-safe-links#how-to-get-atp-safe-links-protection) Des liens sécurisés atp sont disponibles dans [atp plan 1 et ATP plan 2.](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide)

### <a name="safe-attachments"></a>Pièces jointes sécurisées

La fonctionnalité Pièces jointes sécurisées est conçue pour renforcer la sécurité des utilisateurs en vérifiant et en détectant des pièces jointes malveillantes. Les administrateurs globaux [](https://docs.microsoft.com/microsoft-365/security/office-365-security/set-up-atp-safe-attachments-policies?view=o365-worldwide) ou de sécurité créent des stratégies pour gérer ces pièces jointes malveillantes suspectées afin d’empêcher leur envoi à des utilisateurs, de cliquer dessus et d’agir dessus. La protection contre les pièces jointes sécurisées est disponible pour SharePoint, OneDrive et Microsoft Teams, et Microsoft 365 ou Office 365 [Advanced Threat Protection Plan 1](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide) et 2 disposent de cette fonctionnalité. En savoir plus sur les pièces jointes sécurisées et la manière dont elles peuvent contribuer à protéger votre organisation dans les pièces [jointes sécurisées dans Microsoft Defender pour Office 365.](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-attachments?view=o365-worldwide)

### <a name="secure-score"></a>Secure Score

Microsoft Secure Score est une mesure de la sécurité d’une organisation, avec un nombre plus élevé indiquant des actions d’amélioration apportées. Il est possible de le trouver dans le [Centre de sécurité Microsoft 365.](https://security.microsoft.com/securescore) La suite des recommandations sur le score de sécurité permet de protéger votre organisation contre les menaces. À partir d’un tableau de bord centralisé dans le Centre de sécurité Microsoft 365, les organisations peuvent surveiller et travailler sur la sécurité de leurs identités, applications et appareils Microsoft 365. Microsoft Teams propose désormais des recommandations sur Secure Score et les administrateurs sont invités à surveiller leur sécurité sur la plateforme.

Secure Score aide les organisations :
- État de l’état actuel de la sécurité de l’organisation.
- Améliorez leur sécurité en fournissant une visibilité, une visibilité, des conseils et un contrôle.
- Comparez avec les références et établissez des indicateurs de performance clés.


### <a name="how-conditional-access-policies-work-for-teams"></a>Fonctionnement des stratégies d’accès conditionnel pour Teams

Microsoft Teams repose largement sur Exchange Online, SharePoint et Skype Entreprise Online pour les principaux scénarios de productivité, tels que les réunions, les calendriers, les conversations interop et le partage de fichiers. Les stratégies d’accès conditionnel définies pour ces applications cloud s’appliquent à Microsoft Teams lorsqu’un utilisateur se signe directement à Microsoft Teams, sur n’importe quel client.

Microsoft Teams est pris en charge séparément en tant qu’application cloud dans les stratégies d’accès conditionnel Azure Active Directory. Les stratégies d’accès conditionnel définies pour l’application cloud Microsoft Teams s’appliquent à Microsoft Teams lorsqu’un utilisateur se signe. Toutefois, sans les stratégies appropriées sur d’autres applications telles qu’Exchange Online et SharePoint, les utilisateurs pourront toujours accéder à ces ressources directement. Pour plus d’informations sur la configuration d’une stratégie d’accès conditionnel dans le portail Azure, voir Le démarrage rapide [d’Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal-get-started)

Les clients de bureau Microsoft Teams pour Windows et Mac supportent l’authentification moderne. L’authentification moderne apporte une authentification basée sur la bibliothèque d’authentification Azure Active Directory (ADAL) Microsoft Office applications clientes sur toutes les plateformes.

L’application de bureau Microsoft Teams prend en charge AppLocker.  Pour plus d’informations sur les conditions préalables pour AppLocker, voir : Conditions requises pour utiliser [AppLocker.](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/requirements-to-use-applocker)

## <a name="compliance"></a>Conformité

Teams dispose d’un large éventail d’informations pour vous aider dans les domaines de conformité, y compris la conformité des communications pour les canaux, conversations et pièces jointes, stratégies de rétention, protection contre la perte de données, eDiscovery et conservation légale pour les canaux, conversations et fichiers, recherche dans le journal d’audit, ainsi que la gestion des applications mobiles avec Microsoft Intune. Nous avons fourni des informations sur ces rubriques ci-dessous et vous pouvez vous rendre dans le Centre de conformité [Microsoft 365](https://compliance.microsoft.com) pour gérer ces paramètres.

### <a name="information-barriers"></a>Barrières de l’information

Les obstacles à l’information sont des stratégies mises en place par les administrateurs Teams pour empêcher les personnes ou les groupes de communiquer entre eux (lorsqu’ils n’ont pas besoin d’une entreprise pour le faire ou pour une raison réglementaire les empêcher de le faire), et elles vous permettent également de définir des stratégies liées à des éléments tels que la recherche et la découverte électronique (voir ci-dessous). Ces stratégies peuvent avoir un impact sur les utilisateurs dans les conversations en tête-à-tête, les conversations de groupe ou au niveau d’une équipe. La fonctionnalité Barrière des informations est disponible dans le cloud public et, depuis le mois de janvier 2021, elle a été déployée dans le cloud gcc.

Pour lire davantage d’informations sur ce sujet, voir [Barrières de l’information dans Microsoft Teams.](information-barriers-in-teams.md)

### <a name="communication-compliance"></a>Conformité des communications

La conformité des communications dans Microsoft 365 vous permet d’ajouter des utilisateurs à des stratégies internes qui peuvent être configurées pour examiner les communications Microsoft Teams en relation avec du langage choquant, des informations sensibles et des informations liées aux normes internes et réglementaires. Les communications de conversation et les pièces jointes associées dans les canaux Teams publics et privés, les conversations individuelles et les pièces jointes peuvent être numérisées pour réduire les risques de communication dans votre organisation. Pour plus d’informations sur la configuration des stratégies pour vous aider à détecter, capturer et prendre des mesures pour les communications Teams inappropriées, voir Conformité des communications dans [Microsoft 365.](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance)

### <a name="retention-policies"></a>Stratégies de rétention

Les stratégies de rétention dans Microsoft Teams vous permettent de conserver des données qui sont importantes pour votre organisation, pour des raisons réglementaires, juridiques, professionnelles ou autres, et de supprimer du contenu et des communications qui ne sont pas pertinents pour être conservés. Vous pouvez également utiliser des stratégies de rétention pour conserver des données pendant une période donnée, puis les supprimer. Pour plus d’informations, [examinez les stratégies de rétention dans Microsoft Teams.](retention-policies.md)

## <a name="sensitivity-labels"></a>Étiquettes de confidentialité

Appliquez [des étiquettes de sensibilité](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels) pour protéger et réguler l’accès au contenu d’organisation sensible créé lors de la collaboration au sein d’équipes. Par exemple, appliquez des étiquettes qui configurent la confidentialité (publique ou privée) des équipes, contrôlent l’accès invité et le partage externe, et gèrent l’accès à partir d’appareils non utilisés. Pour plus d’informations, [examinez les étiquettes de sensibilité dans Microsoft Teams.](sensitivity-labels.md)

### <a name="data-loss-prevention-dlp"></a>Protection contre la perte de données (DLP)

Dans Microsoft Teams, la protection contre la perte de données (DLP), ainsi que les informations relatives à la protection contre la perte de données (DLP) pour Microsoft 365 ou Office 365, se basent sur la préparation professionnelle pour la protection des documents et données sensibles. Que vous soyez préoccupé par des informations sensibles dans des messages ou des documents, les stratégies DLP seront en mesure de s’assurer que vos utilisateurs ne partagent pas ces données sensibles avec des personnes erronées.

Pour plus d’informations sur la protection contre la perte de données dans Teams, consultez [la DLP pour Microsoft Teams.](https://docs.microsoft.com/microsoft-365/compliance/dlp-microsoft-teams) Un bon article concernant les problèmes DLP dans O365 est une vue d’ensemble de [la protection contre la perte de données.](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)

### <a name="ediscovery"></a>eDiscovery

La découverte électronique, ou eDiscovery, est l’aspect électronique de l’identification, de la collecte et de la production d’informations stockées électroniquement à la suite d’une demande de production dans une enquête ou une enquête juridique. Les fonctionnalités incluent la gestion de cas, la conservation, la recherche, l’analyse et l’exportation de données Teams. Cela inclut les discussions, la messagerie et les fichiers, les résumés de réunion et d’appel. Pour les réunions et appels Teams, un résumé des événements survenus au cours de la réunion et de l’appel est créé et mis à disposition dans eDiscovery.

Pour plus d’informations sur la manière d’effectuer la découverte électronique Microsoft 365 ou Office 365 dans le Centre de sécurité et le Centre de conformité et d’exécuter la recherche de contenu de conformité pour du contenu Teams, consultez les liens ci-dessous :

 - [eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/manage-legal-investigations)

 - [Recherche de contenu](https://docs.microsoft.com/microsoft-365/compliance/search-for-content)

Nous avons un article spécifique de Teams pour plus d’informations, [eDiscovery des](eDiscovery-investigation.md)conversations entre invités.

Les clients peuvent tirer parti d’eDiscovery ou [advanced eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/office-365-advanced-ediscovery) selon leurs besoins. Le tableau suivant présente les différences entre les deux options :

| |eDiscovery  |eDiscovery avancée  |
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

Consultez la [vue d’ensemble](https://docs.microsoft.com/microsoft-365/compliance/retention-policies) des stratégies de rétention pour mieux comprendre la conservation et les conservations dans le Centre de conformité Microsoft 365. Pour plus d’informations spécifiques à Teams sur la attente légale, nous avons également placez un utilisateur ou une équipe [Microsoft Teams](legal-hold.md) en attente légale pour vous afin d’en savoir plus.

### <a name="compliance-content-search"></a>Recherche de contenu de conformité

La recherche de contenu peut être utilisée pour rechercher toutes les données Teams par le biais de fonctionnalités de filtrage enrichies. Les données résultantes peuvent être exportées vers un conteneur spécifique à des fins de conformité et d’appui pour les litiges. Cela peut être fait avec ou sans cas de découverte électronique. Cela permet aux administrateurs de conformité de recueillir des données Teams sur tous les utilisateurs, de les consulter et de les exporter pour un traitement approfondi. Reportez-vous à la recherche de contenu pour en savoir plus sur la façon d’effectuer une recherche de contenu de conformité pour Microsoft Teams et d’autres contenus Microsoft 365 ou Office 365 dans le Centre de conformité Microsoft 365. [](https://docs.microsoft.com/microsoft-365/compliance/content-search)

> [!TIP]
> La recherche de contenu vous permet de filtrer jusqu’au contenu de Microsoft Teams uniquement, tel que les messages de conversation et de canal, les réunions et les appels, si nécessaire.

Si vous souhaitez consulter des informations spécifiques à Teams sur la configuration de la recherche de contenu, examinez la recherche [de contenu dans Microsoft Teams.](content-search.md)

### <a name="auditing-and-reporting"></a>Audit et rapports

La recherche dans le journal d’audit se branche directement dans le Centre de conformité Microsoft 365 et vous permet de définir des alertes, ainsi que des rapports sur des événements d’audit, en permettant l’exportation de jeux d’événements spécifiques ou génériques de charge de travail à des fin d’utilisation et d’examen par l’administrateur dans le cadre d’une chronologie d’audit illimitée. Vous pouvez configurer des alertes pour toutes les données du journal d’audit dans le Centre de conformité Microsoft 365, et filtrer et exporter ces données pour une analyse approfondie. Reportez-vous [à la recherche dans](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance) le journal d’audit pour en savoir plus sur la façon d’effectuer une recherche dans le journal d’audit pour Microsoft 365 ou Office 365. Pour en savoir plus sur la recherche d’événements Microsoft Teams dans le Centre de conformité Microsoft 365, nous avons également activer [l’audit](audit-log-events.md) dans Teams pour vous aider à le vérifier.

## <a name="customer-key"></a>Clé client

Microsoft 365 offre une couche supplémentaire de chiffrement par-dessus le chiffrement du service pour votre contenu. À l’aide des clés que vous fournissez, la clé client chiffre différents types de données dans Microsoft Teams. À l’aide de la clé client au niveau de l’application, la clé client chiffre les fichiers Teams stockés dans SharePoint Online. Pour plus d’informations, voir [Chiffrement du service avec la clé client.](https://docs.microsoft.com/microsoft-365/compliance/customer-key-overview) 

À l’aide de la clé client au niveau du client, la clé client chiffre :
- Messages de conversation Teams (conversations en tête-à-tête, conversations de groupe, conversations de réunion et conversations de canal)
- Messages multimédias Teams (images, extraits de code, vidéos et images Wiki)
- Enregistrements des appels et des réunions Teams stockés dans le stockage Teams
- Notifications de conversation Teams
- Suggestions de conversation Teams par Cortana
- Messages de statut Teams Pour plus d’informations, voir Vue d’ensemble de la clé client pour [Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/customer-key-tenant-level) au niveau du client et lisez le blog Microsoft Teams sur la prise en charge de la clé client [pour Microsoft Teams](https://techcommunity.microsoft.com/t5/microsoft-teams-blog/customer-key-support-for-microsoft-teams-now-in-public-preview/ba-p/1999893)désormais en prévisualisation publique. Pour plus d’informations sur la publication Microsoft Information Protection qui incluait la clé Client au niveau du client, lisez Annonce des nouvelles fonctionnalités de Protection des informations Microsoft pour connaître et protéger [vos données sensibles.](https://techcommunity.microsoft.com/t5/microsoft-security-and/announcing-new-microsoft-information-protection-capabilities-to/ba-p/1999692)

## <a name="privacy"></a>Confidentialité

Chez Microsoft, la protection de vos données est la priorité la plus élevée. Pour en savoir plus sur nos pratiques en matière de confidentialité, voir :  

- [Confidentialité chez Microsoft](https://www.microsoft.com/trust-center/privacy)
- [Notre engagement en matière de confidentialité et de sécurité dans Microsoft Teams](https://www.microsoft.com/en-us/microsoft-365/blog/2020/04/06/microsofts-commitment-privacy-security-microsoft-teams/)
- [Pour les professionnels de l’informatique : Confidentialité et sécurité dans Microsoft Teams](https://www.microsoft.com/en-us/microsoft-365/blog/2020/04/06/it-professionals-privacy-security-microsoft-teams/#:~:text=We%20safeguard%20your%20privacy%20by,and%20distribution%20of%20your%20data.)

## <a name="information-protection-architecture"></a>Architecture de la protection des informations

La figure suivante indique le flux de données Teams vers Exchange et SharePoint pour les fichiers et messages Teams.

> [!div class="mx-imgBorder"]
> ![Diagramme du flux de travail de données Teams vers Exchange et SharePoint](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1.png)

La figure suivante indique le flux d’ingestion de réunions Teams et d’appels de données vers Exchange.

> [!div class="mx-imgBorder"]
> ![Diagramme du flux de travail des réunions Teams et des données d’appel à Exchange](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1a.png)

> [!IMPORTANT]
> Il peut y avoir un délai de 24 heures pour découvrir le contenu de Teams.

## <a name="licensing"></a>Gestion des licences

En ce qui concerne les fonctionnalités de protection des informations, les abonnements Microsoft 365, les abonnements Office 365 et les licences autonomes associées déterminent l’ensemble de fonctionnalités disponible.

Pour plus d’informations sur la détermination des besoins en [](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance) matière de gestion des licences afin d’implémenter des fonctionnalités à des fin de sécurité et de conformité, consultez les exigences en matière de gestion des licences pour les fonctionnalités de sécurité et de conformité.

> [!NOTE]
> La recherche de contenu et la découverte électronique n’ont pas besoin d’être activées dans le Centre & conformité pour fonctionner.

## <a name="location-of-data-in-teams"></a>Emplacement des données dans Teams

Les données dans Teams se situent dans la région géographique associée à votre organisation Microsoft 365 ou Office 365. Pour savoir quelles régions sont actuellement pris en charge, consultez [l’emplacement des données dans Microsoft Teams.](location-of-data-in-teams.md)

Si vous voulez voir quelle région héberge les données de votre client, consultez le profil de l’organisation du Centre d’administration [Microsoft 365.](https://portal.office.com/adminportal/home)  >    >   Faites défiler vers le bas jusqu’à **Emplacement des données**.

> [!div class="mx-imgBorder"]
> ![Capture d’écran de la table Emplacement de données incluant Teams dans le Centre d’administration](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image5.png)

## <a name="compliance-standards"></a>Normes de conformité

Teams utilise les normes suivantes : [ISO 27001,](https://docs.microsoft.com/microsoft-365/compliance/offering-iso-27001) [ISO 27018,](https://docs.microsoft.com/microsoft-365/compliance/offering-iso-27018) [SSAE18 SOC 1 et SOC 2,](https://docs.microsoft.com/microsoft-365/compliance/offering-soc) [HIPAA](https://docs.microsoft.com/microsoft-365/compliance/offering-hipaa-hitech)et les clauses contractuelles de l’UE [(EUMC).](https://docs.microsoft.com/microsoft-365/compliance/offering-eu-model-clauses) Dans le cadre de conformité Microsoft, Microsoft classe les applications et services Microsoft 365 et Office 365 en quatre catégories. Chaque catégorie est définie par des engagements de conformité spécifiques qui doivent être satisfaits pour qu’un service Microsoft 365, Office 365 ou un service Microsoft associé figure dans cette catégorie.

Vous pouvez en savoir plus dans les ressources [de protection des données.](https://servicetrust.microsoft.com/ViewPage/TrustDocumentsV3?command=Download&downloadType=Document&downloadId=b7d05b86-c69b-41ba-8245-21161b9febf9&tab=7f51cb60-3d6c-11e9-b2af-7bb9f5d2d913&docTab=7f51cb60-3d6c-11e9-b2af-7bb9f5d2d913_Compliance_Guides) Teams prend également en charge la conformité à la Cloud Security Alliance.

## <a name="related-topics"></a>Rubriques connexes

[Sécurité Microsoft 365](https://docs.microsoft.com/microsoft-365/security/)

[Conformité à Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/)

[Offres de conformité Microsoft](https://docs.microsoft.com/microsoft-365/compliance/offering-home)
