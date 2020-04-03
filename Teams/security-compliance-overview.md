---
title: Présentation de la sécurité et de la conformité dans Microsoft Teams
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: anach
audience: admin
description: Vue d’ensemble des fonctionnalités de sécurité et de conformité de Microsoft Teams, notamment l’audit et la création de rapports, la recherche de contenu de conformité, la découverte électronique, etc.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
- remotework
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.securityandcompliance
appliesto:
- Microsoft Teams
ms.openlocfilehash: fbec8f7d246a4acfe241ef4f4d701cc9e1e6b28c
ms.sourcegitcommit: 1bb3df681177db5ecc6afae3d3f3a46c251e5c23
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/02/2020
ms.locfileid: "43117422"
---
# <a name="security-and-compliance-in-microsoft-teams"></a>Sécurité et conformité dans Microsoft teams

> [!IMPORTANT]
> Pour plus d’informations sur la façon de garantir **la sécurité de tous les utilisateurs de chez vous lors de l’épidémie de COVID-19**, lisez les articles suivants :
>  - [12 tâches principales pour que les équipes de sécurité prennent en charge le télétravail de chez vous](https://docs.microsoft.com/microsoft-365/security/top-security-tasks-for-remote-work)
>  - [Optimiser la connectivité d’Office 365 pour les utilisateurs distants à l’aide de la segmentation de tunnel VPN](https://docs.microsoft.com/Office365/Enterprise/office-365-vpn-split-tunnel)
>  - Mise à jour du 2 avril 2020 : Guide sur la [sécurité teams](teams-security-guide.md)


Microsoft Teams est conçu sur le cloud d'entreprise à très grande échelle Office 365, fournissant à nos clients les fonctionnalités de sécurité avancée et de conformité qu'ils attendent. Pour plus d’informations sur la planification de la sécurité dans O365, veuillez consulter notre contenu O365. [Le plan de la sécurité O365 est l'](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-roadmap) endroit idéal pour commencer. Pour plus d’informations sur la planification de la conformité dans O365, vous pouvez commencer avec [l’article planifier pour la sécurité et la conformité](https://docs.microsoft.com/microsoft-365/compliance/plan-for-security-and-compliance) .


Cet article fournit des informations supplémentaires sur la sécurité et la conformité spécifiques aux équipes. Ne manquez pas cette vidéo sur la sécurité et la conformité :

- [Microsoft teams Essentials : sécurité et conformité](https://youtu.be/91lHNKVVvQ4) (12:42 min)
- [Contrôles Microsoft teams pour la sécurité et la conformité](https://www.youtube.com/watch?v=Km4T4hMM__k) (10:54 min)

> [!IMPORTANT]
> En tant que client d’Office 365, vous êtes propriétaire et contrôle de vos données. Microsoft n’utilise pas vos données pour aucune autre action que le service auquel vous êtes abonné. En tant que fournisseur de services, nous ne analyserons pas vos messages électroniques, vos documents ou vos équipes à des fins publicitaires ou à des fins qui ne sont pas liées au service. Microsoft n’a pas accès au contenu téléchargé. Comme OneDrive entreprise et SharePoint Online, les données de clients restent dans le client. Vous pouvez en savoir plus sur les informations relatives à la confidentialité et à la sécurité du centre de gestion de la [confidentialité de Microsoft](https://microsoft.com/trustcenter). Teams suit les mêmes recommandations et principes que le centre de gestion de la confidentialité Microsoft.

## <a name="security"></a>Sécurité

Teams applique l’authentification à deux facteurs à l’échelle de l’organisation et au niveau de l’organisation, de l’authentification unique par le biais d’Active Directory et du chiffrement des données en transit et au repos. Les fichiers sont stockés dans SharePoint et sont sauvegardés par le chiffrement SharePoint. Les notes sont stockées dans OneNote et sont représentées par un chiffrement OneNote. Les données OneNote sont stockées dans le site SharePoint de l’équipe. L’onglet wiki peut également être utilisé pour la prises de notes et son contenu est également stocké dans le site SharePoint de l’équipe.

Lire les [modèles d’identité et l’authentification](identify-models-authentication.md) pour plus d’informations sur l’authentification et les équipes et sur [le fonctionnement de l’authentification moderne](sign-in-teams.md) , notamment sur l’authentification moderne.

Étant donné que teams travaille en partenariat avec SharePoint, OneNote, Exchange, et bien plus encore, vous devez être sûr de la gestion de la sécurité dans O365. Pour en savoir plus sur la sécurité d’Office 365, voir [configurer votre client office 365 pour renforcer la sécurité](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security).

> [!NOTE]
> Actuellement, les [canaux privés](private-channels.md) prennent en charge des fonctionnalités de sécurité et de conformité limitées. La prise en charge de l’ensemble complet des fonctionnalités de sécurité et de conformité dans les canaux privés est disponible prochainement.

### <a name="advance-threat-protection-atp"></a>Advanced Threat Protection (ATP)

L’Advanced Threat Protection (ATP) est disponible pour Microsoft Teams, ainsi que dans SharePoint et OneDrive entreprise, applications intégrées à teams pour la gestion de contenu. ATP vous permet de déterminer si le contenu de ces applications est malveillant et de bloquer ce contenu de l’accès des utilisateurs.

La façon dont le contenu affecté est géré après la détection correspond aux paramètres que vous avez sélectionnés dans O365. Nous vous recommandons vivement de prendre en compte toutes les applications lorsque vous configurez ATP, et pour une lecture plus approfondie, l’article [Office 365 ATP pour SharePoint, OneDrive et Microsoft teams](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-for-spo-odb-and-teams) vous propose des informations détaillées sur la prise en main.

### <a name="safe-links"></a>Liens approuvés

Pour le moment, les liens sécurisés ATP ne sont pas disponibles dans Microsoft Teams, ils sont désormais disponibles dans la version préliminaire publique du programme d’adoption de la technologie (TAP) et, si la date de publication de la disponibilité générale n’est pas définie, nous mettrons à jour cet article lorsque le délai sera écoulé. Pour plus d’informations sur les liens en sécurité d’Office 365, consultez les [liens vers la sécurité Office 365 ATP](https://docs.microsoft.com/office365/securitycompliance/atp-safe-links#how-to-get-atp-safe-links-protection).

### <a name="how-conditional-access-policies-work-for-teams"></a>Fonctionnement des stratégies d’accès conditionnel pour les équipes

Microsoft teams repose essentiellement sur Exchange Online, SharePoint Online et Skype entreprise Online pour les scénarios de productivité de base, tels que les réunions, les calendriers, les discussions d’interopérabilité et le partage de fichiers. Les stratégies d’accès conditionnel définies pour ces applications Cloud s’appliquent à Microsoft teams lorsqu’un utilisateur se connecte directement à Microsoft Teams, quel que soit le client.

Microsoft teams est pris en charge séparément en tant qu’application Cloud dans des stratégies d’accès conditionnel Azure Active Directory. Les stratégies d’accès conditionnel définies pour l’application Cloud de Microsoft teams s’appliquent à Microsoft teams lorsqu’un utilisateur se connecte. Toutefois, sans les stratégies appropriées sur d’autres applications telles qu’Exchange Online et SharePoint Online, les utilisateurs peuvent toujours accéder directement à ces ressources. Pour plus d’informations sur la configuration d’une stratégie d’accès conditionnel dans le portail Azure, voir [démarrage rapide d’Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal-get-started).

Les clients de bureau Microsoft teams pour Windows et Mac prennent en charge l’authentification moderne. L’authentification moderne fournit la connexion en fonction de la bibliothèque d’authentification Azure Active Directory (ADAL) pour les applications clientes Microsoft Office sur différentes plateformes.

L’application de bureau Microsoft teams prend en charge AppLocker.  Pour plus d’informations sur les conditions préalables pour AppLocker, voir : configuration requise pour utiliser [AppLocker](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/requirements-to-use-applocker).

## <a name="compliance"></a>Conformément

Teams dispose d’une large gamme d’informations pour vous aider à utiliser les zones de conformité, y compris la conformité des communications pour les canaux, les conversations et les pièces jointes, les stratégies de rétention, la recherche de perte de données (DLP), la découverte électronique et la gestion des applications mobiles avec Microsoft Intune. Nous avons mis à votre disposition des informations sur ces rubriques ci-dessous, et vous pouvez accéder au [Centre de conformité microsoft 365](https://compliance.microsoft.com) ou au [centre de sécurité & conformité Office 365](https://protection.microsoft.com) pour gérer ces paramètres.

### <a name="communication-compliance"></a>Conformité des communications

La conformité de la communication dans Microsoft 365 vous permet d’ajouter des utilisateurs à des stratégies dans le cadre qui peuvent être configurées de manière à examiner les communications de Microsoft teams pour le langage injurieux, les informations sensibles et les informations relatives aux normes internes et réglementaires. Les communications de conversation et les pièces jointes associées dans les canaux d’équipe publique et privée, les discussions individuelles et les pièces jointes peuvent être analysées pour réduire les risques de communication au sein de votre organisation. Pour plus d’informations sur la configuration des stratégies permettant de détecter, de capturer et de prendre des mesures pour les communications d’équipes inappropriées, voir [conformité de la communication dans Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/communication-compliance).

### <a name="retention-policies"></a>Stratégies de rétention

Les stratégies de rétention de Microsoft teams vous permettent de conserver les données importantes pour les exigences de votre organisation, pour des raisons réglementaires, juridiques, professionnelles ou autres, ainsi que pour supprimer du contenu et des communications dont la conservation n’est pas pertinente. Vous pouvez également utiliser des stratégies de rétention pour conserver les données pendant un laps de temps, puis les supprimer. Pour plus d’informations, consultez l’article [stratégies de rétention dans Microsoft teams](retention-policies.md) .

### <a name="data-loss-prevention-dlp"></a>Protection contre la perte de données (DLP)

La protection contre la perte de données (DLP) dans Microsoft Teams, ainsi que l’histoire DLP plus grande pour O365, tourne autour de la préparation de l’entreprise en matière de protection des documents et données sensibles dans O365. Que vous ayez des inquiétudes sur des informations sensibles dans des messages ou des documents, les stratégies DLP seront en mesure de garantir que vos utilisateurs ne partageront pas ces données sensibles avec les personnes inappropriées.

Pour plus d’informations sur la protection contre la perte de données dans Teams, voir [DLP pour Microsoft teams](https://docs.microsoft.com/microsoft-365/compliance/dlp-microsoft-teams). Un article idéal pour les inquiétudes de O36 [https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)DLP est.

### <a name="ediscovery"></a>eDiscovery

La découverte électronique (eDiscovery) est l’aspect électronique d’identification, de collecte et de production d’informations stockées par voie électronique (ESI) en réponse à une demande de production dans une action ou une enquête en vigueur. Les fonctionnalités incluent la gestion des cas, la conservation, la recherche, l’analyse et l’exportation des données d’équipe. Il s’agit de messages instantanés, de messages et de dossiers, de réunions et d’appels. Pour les réunions et les appels en équipe, un résumé des événements qui se sont produits lors de la réunion et de l’appel sont créés et rendus disponibles dans eDiscovery.

Pour plus d’informations sur la façon d’effectuer une découverte électronique O365 dans le centre de sécurité & conformité et de vérifier le contenu de la recherche de contenu d’équipe, consultez les liens ci-dessous :

[eDiscovery](https://docs.microsoft.com/microsoft-365/compliance/manage-legal-investigations)

[Recherche de contenu](https://docs.microsoft.com/microsoft-365/compliance/search-for-content)

Nous avons un article spécifique à teams pour plus d’informations, EDiscovery concernant les [discussions invité-à-invité](eDiscovery-investigation.md).

Les clients peuvent tirer parti d’une découverte électronique inaltérable ou [Advanced eDiscovery] selon leurs [besoins](https://docs.microsoft.com/microsoft-365/compliance/office-365-advanced-ediscovery). Le tableau suivant présente les différences entre les deux options :

| |eDiscovery en place  |eDiscovery avancée  |
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

Au cours d’un litige, il est possible que vous ayez besoin de toutes les données associées à un utilisateur ou à une équipe dont la conservation est inaltérable, afin qu’elle puisse être utilisée comme preuve pour le cas. Pour ce faire, vous devez placer un utilisateur (boîte aux lettres d’utilisateur) ou une équipe en attente de conservation légale. Pour une attente légale d’équipe, la boîte aux lettres de l’équipe peut être placée sur les éléments suivants :

- Blocage sur place (un sous-ensemble de la boîte aux lettres ou de la collection de sites par le biais de requêtes ciblées ou de contenu filtré est mis en attente), ou
- Conservation pour litige (la boîte aux lettres ou la collection de sites entière est mise en attente).

Dans les deux cas, une fois la conservation définie, elle garantit que, même si les utilisateurs finaux suppriment ou modifient des messages de canal qui se trouvent dans la boîte aux lettres de groupe, les copies immuables de ce contenu sont conservées et disponibles par le biais de la recherche eDiscovery. Les conservations juridiques sont généralement appliquées dans le cadre d’un cas de découverte électronique.

Reportez-vous à l’article [vue d’ensemble des stratégies de rétention](https://docs.microsoft.com/microsoft-365/compliance/retention-policies) pour en savoir plus sur la conservation et la conservation dans le centre de sécurité & conformité Office 365. Pour plus d’informations spécifiques aux équipes en matière de conservation légale, nous avons également [placé une équipe Microsoft teams pour un utilisateur ou une équipe sur le holding légal](legal-hold.md) pour en savoir plus.

### <a name="compliance-content-search"></a>Recherche de contenu de conformité

La recherche de contenu peut être utilisée pour rechercher toutes les données de l’équipe grâce aux fonctionnalités de filtrage enrichies. Les données obtenues peuvent être exportées vers un conteneur spécifique à des fins de compatibilité et de litige. Cette opération peut être réalisée avec ou sans cas de découverte électronique. Cela permet aux administrateurs de la conformité de recueillir des données d’équipe auprès de tous les utilisateurs, de les réviser et de les exporter pour plus de traitement. Pour en savoir plus sur la réalisation d’une recherche de contenu de conformité pour Microsoft teams et d’autres contenus O365 dans le centre de sécurité & conformité Office 365, consultez la [recherche de contenu dans](https://docs.microsoft.com/microsoft-365/compliance/content-search) l’article o365.

> [!TIP]
> À l’aide de la recherche de contenu, vous pouvez filtrer uniquement le contenu de Microsoft Teams, par exemple, les conversations et les messages de canal, les réunions et les appels, si nécessaire.

Pour obtenir d’autres informations spécifiques aux équipes sur la configuration de la recherche de contenu, consultez l’article [recherche de contenu dans Microsoft teams](content-search.md) .

### <a name="auditing-and-reporting"></a>Audit et rapports

La recherche dans le journal d’audit s’ouvre directement dans le centre de sécurité & de conformité Office 365 et vous permet de définir des alertes, ainsi que de signaler des événements d’audit, en autorisant l’exportation des jeux d’événements spécifiques ou génériques de charge de travail pour l’utilisation d’administration au sein d’une timeline d’audit illimité. Vous pouvez configurer des alertes pour toutes les données du journal d’audit au sein du centre de & sécurité et de la conformité Office 365, et filtrer et exporter ces données pour une analyse plus approfondie. Reportez-vous à la rubrique [Rechercher dans le journal d’audit](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance) pour en savoir plus sur la réalisation d’un journal d’audit pour O365. Pour en savoir plus sur la recherche d’événements Microsoft teams dans le centre de & sécurité et conformité Office 365, nous avons également la [fonction d’audit dans teams](audit-log-events.md) .

## <a name="information-protection-architecture"></a>Architecture de protection des informations

La figure suivante indique le flux de réception des données d’équipe à la fois pour les fichiers et les messages teams dans Exchange et SharePoint.

![Diagramme du flux de travail des données d’équipes dans Exchange et SharePoint](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1.png)

La figure suivante indique le flux d’intégration des réunions teams et des données d’appel vers Exchange.

![Diagramme illustrant le flux de travail des réunions d’équipe et des données d’appel vers Exchange](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1a.png)

> [!IMPORTANT]
> Un délai de 24 heures peut être nécessaire pour détecter du contenu d’équipes.

## <a name="licensing"></a>Licence

En ce qui concerne les capacités de protection des informations, les abonnements Office 365 et les licences autonomes associées déterminent l’ensemble des fonctionnalités disponibles.

Pour plus d’informations sur la façon de déterminer les fonctionnalités de gestion des licences requises en matière de sécurité et de conformité, reportez-vous à la rubrique [licences pour Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center).

> [!NOTE]
> La recherche de contenu et eDiscovery n’ont pas besoin d’être activées dans le centre de sécurité & conformité pour fonctionner.

## <a name="location-of-data-in-teams"></a>Emplacement des données dans Teams

Les données dans Teams résident dans la région géographique associée à votre client Office 365. Pour connaître les régions prises en charge pour le moment, veuillez vérifier [l’emplacement des données dans Microsoft teams](location-of-data-in-teams.md).

Si vous avez besoin de voir la région qui abrite les données pour votre client, accédez au**profil d’organisation****paramètres** > du centre > d' [administration 365 Microsoft](https://portal.office.com/adminportal/home). Défilez jusqu’à la section **Emplacement des données**.

![Capture d’écran de la table d’emplacements des données, y compris équipes dans le centre d’administration](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image5.png)

## <a name="compliance-standards"></a>Normes de conformité

Teams est conforme à la norme de niveau D. Cela inclut les normes suivantes : [iso 27001](https://docs.microsoft.com/microsoft-365/compliance/offering-iso-27001), [ISO 27018](https://docs.microsoft.com/microsoft-365/compliance/offering-iso-27018), [SSAE16 SOC 1 et SOC 2](https://docs.microsoft.com/microsoft-365/compliance/offering-soc), [HIPAA](https://docs.microsoft.com/microsoft-365/compliance/offering-hipaa-hitech)et des [clauses de modèle européen (CMUE)](https://docs.microsoft.com/microsoft-365/compliance/offering-eu-model-clauses). Dans l’infrastructure de conformité Microsoft, Microsoft classifie les applications et services Office 365 en quatre catégories. Chaque catégorie est définie par des engagements de conformité spécifiques qui doivent être satisfaits pour un service Office 365 ou un service Microsoft associé qui doit être répertorié dans cette catégorie.

Les services qui appartiennent aux catégories de conformité C et D, et qui se soumettent à des conditions de conformité applicables au secteur sont activés par défaut. Les services qui appartiennent aux catégories A et B sont dotés de commandes qui permettent leur activation ou désactivation au niveau de toute l'organisation. Pour obtenir plus d'informations, consultez le document sur le [cadre de conformité aux normes et réglementations du secteur](https://download.microsoft.com/download/1/4/3/1434ABAB-B8E9-412D-8C3A-187B5FCB7A2F/Compliance%20Framework%20document.pdf). Teams prend également en charge la conformité à la Cloud Security Alliance.

## <a name="related-topics"></a>Voir aussi

[Microsoft 365 sécurité](https://docs.microsoft.com/microsoft-365/security/)
Microsoft[365 conformité](https://docs.microsoft.com/microsoft-365/compliance/)
Microsoft[Compliance](https://docs.microsoft.com/microsoft-365/compliance/offering-home)
