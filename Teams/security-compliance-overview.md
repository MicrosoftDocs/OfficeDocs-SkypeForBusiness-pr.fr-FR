---
title: Présentation de la sécurité et de la conformité dans Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/11/2018
ms.topic: article
ms.service: msteams
ms.reviewer: anach
description: Vue d’ensemble des fonctionnalités de sécurité et de conformité de Microsoft Teams, y compris l’audit et création de rapports, recherche de contenu de la conformité, eDiscovery et plus.
localization_priority: Normal
search.appverid: MET150
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: fc686b520c9bd765539ff5fd9f636bc876583a41
ms.sourcegitcommit: 6732f56535d60a46e6998cde64103e8530dd6452
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/11/2018
ms.locfileid: "23937897"
---
<a name="overview-of-security-and-compliance-in-microsoft-teams"></a>Présentation de la sécurité et de la conformité dans Microsoft Teams
======================================================

Microsoft Teams est conçu sur le cloud d'entreprise à très grande échelle Office 365, fournissant à nos clients les fonctionnalités de sécurité avancée et de conformité qu'ils attendent.

Teams est conforme au niveau C à son lancement. Cela comprend les normes suivantes : ISO 27001, ISO 27018, SSAE16 SOC 1 et SOC 2, HIPAA, et les clauses contractuelles types de l'UE (EUMC). Dans son cadre de conformité, Microsoft classe les applications et services Office 365 en quatre catégories. Chaque catégorie est définie par des conditions de conformité spécifiques qui doivent être satisfaites par tout service Office 365, ou tout service Microsoft associé appartenant à ladite catégorie.

Les services qui appartiennent aux catégories de conformité C et D, et qui se soumettent à des conditions de conformité applicables au secteur sont activés par défaut. Les services qui appartiennent aux catégories A et B sont dotés de commandes qui permettent leur activation ou désactivation au niveau de toute l'organisation. Pour obtenir plus d'informations, consultez le document sur le [cadre de conformité aux normes et réglementations du secteur](https://go.microsoft.com/fwlink/?linkid=855777). Teams prend également en charge la conformité à la Cloud Security Alliance.

Les équipes applique également à l’échelle de l’équipe et l’organisation authentification à deux facteurs, authentification unique par le biais de Active Directory et le chiffrement des données en transit et inactives. Les fichiers sont stockés dans SharePoint et sont sauvegardés par le chiffrement de SharePoint. Notes sont stockées dans OneNote et sont sauvegardés par le chiffrement de OneNote. Les données de OneNote sont stockées dans le site d’équipe SharePoint. L’onglet Wiki peut également être utilisé pour la prise de notes et son contenu est également stocké dans le site d’équipe SharePoint.

Nous avons également ajouté la prise en charge de la recherche dans les journaux d'audit, eDiscovery et la conservation légale pour les canaux, les conversations et les fichiers ainsi que la gestion des applications mobiles avec Microsoft Intune. Accédez au centre de sécurité pour Microsoft Office 365 et de la conformité pour gérer ces paramètres. 

## <a name="auditing-and-reporting"></a>Audit et rapports

Recherche des journaux d’audit se connecte à droite dans le centre de conformité et de sécurité pour Microsoft Office 365 et expose les capacités pour définir des alertes et/ou de créer des rapports sur les événements d’Audit en rendant disponibles, l’exportation de la charge de travail spécifiques ou événement générique définit pour l’utilisation d’administration et d’enquête, sur un chronologie audit illimité. Toutes les données du journal d’Audit est disponibles pour la configuration des alertes dans le centre de conformité et de sécurité pour Microsoft Office 365, ainsi que pour le filtrage et exporter pour une analyse approfondie. Reportez-vous à ce [lien](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security-Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c) pour en savoir plus sur la façon d’effectuer une recherche de journal d’Audit pour les événements Teams Microsoft dans le centre de sécurité pour Microsoft Office 365 et de conformité. 

## <a name="compliance-content-search"></a>Recherche de contenu de conformité

Recherche de contenu pouvant être utilisée pour rechercher toutes les données d’équipes par le biais de riches fonctionnalités de filtrage et exportée vers un conteneur spécifique pour la prise en charge pour litige et conformité. Cela peut être effectuée avec ou sans un cas eDiscovery. Cela permet aux administrateurs de conformité recueillir des données d’équipes pour tous les utilisateurs, passez en revue et exportez-le pour un traitement supplémentaire. Reportez-vous à ce [lien](https://support.office.com/article/content-search-in-office-365-53390468-eec6-45cb-b6cd-7511f9c909e4) pour en savoir plus sur la façon d’effectuer une recherche de contenu de conformité pour le contenu Teams Microsoft dans le centre de sécurité pour Microsoft Office 365 et de conformité. 

Conseil : Le type MicrosoftTeams peut servir à filtrer à Microsoft Teams contenu uniquement c'est-à-dire conversation et les Messages de canal, les réunions et les appels. 

## <a name="ediscovery"></a>eDiscovery

La découverte électronique représente l'aspect électronique de l'identification, la collecte et la production d'informations stockées électroniquement (ESI) en réponse à une demande dans le cadre d'une action en justice ou d'une enquête judiciaire. Fonctionnalités incluent la gestion, conservation, recherche, l’analyse et exporter des données d’équipes. Cela inclut les résumés de conversation, de messagerie et les fichiers, réunion et appel. Pour les réunions d’équipes et un résumé des événements qui s’est produite dans la réunion et d’appel, les appels sont créés et mis à disposition d’eDiscovery. 

Pour plus d’informations sur la découverte électronique dans le centre de sécurité et de conformité et de la recherche de contenu d’exécution de la conformité pour le contenu des équipes, consultez les liens ci-dessous : 

[eDiscovery](https://support.office.com/article/manage-legal-investigations-in-office-365-2e5fbe9f-ee4d-4178-8ff8-4356bc1b168e) 

[Recherche de contenu](https://support.office.com/article/search-for-content-in-office-365-df2d1e0f-b476-42c9-aade-4a260b24f193)

Les clients peuvent exploiter la découverte électronique locale ou [eDiscovery avancée] par leurs besoins (https://support.office.com/article/Office-365-Advanced-eDiscovery-fd53438a-a760-45f6-9df4-861b50161ae4). Le tableau suivant présente les différences entre les deux options :


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


## <a name="legal-hold"></a>Conservation légale

Pendant un litige, il est souvent nécessaire que toutes les données associées à un utilisateur (dépositaire) ou une équipe est conservée immuable, donc il peut être utilisé comme preuve pour le cas. Pour cela, vous devez placer un utilisateur (boîte aux lettres de l’utilisateur) ou à une équipe en conservation légale. Lorsqu’une équipe au sein des équipes est placée sur le blocage sur Place (sous-ensemble de la collection de site ou de la boîte aux lettres via des requêtes ciblés ou du contenu filtré) ou litige (toute boîte aux lettres ou site collection), la suspension est placée sur la boîte aux lettres de groupes. Cela garantit que même si les utilisateurs finaux, supprimer ou modifier les messages de canal sont ingérés dans la boîte aux lettres de groupe, immuables copies de ce contenu sont disponibles dans la recherche eDisscovery et conservées. Les conservations légales sont généralement appliquées dans le contexte d'un cas eDiscovery. Consultez [cette](https://support.office.com/article/overview-of-preservation-policies-9c3b1d52-40ce-4ba3-a520-9ae0be15538a) aide de l’article pour en savoir plus sur la conservation et suspensions dans le centre de sécurité pour Microsoft Office 365 et de conformité. 

## <a name="information-protection-architecture-for-microsoft-teams"></a>Architecture de Protection des informations pour les équipes Microsoft. 

La figure suivante indique le flux d’ingestion des données équipes à Exchange et SharePoint pour les équipes de fichiers et des Messages. 

![Diagramme du flux de travail de données Teams vers Exchange et SharePoint.](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1.png)

La figure suivante indique le flux d’ingestion des équipes de réunions et des données appelante à Exchange.

![Diagramme du flux de travail des équipes de réunions et des données appelante à Exchange.](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1a.png)

> [!IMPORTANT]
> Il peut y avoir jusqu'à un délai de 24 heures pour découvrir du contenu des équipes.

## <a name="retention-policies"></a>Stratégies de rétention

Conversations équipes sont persistantes et conservés indéfiniment par défaut. Avec l’introduction des stratégies de rétention, les administrateurs peuvent configurer des stratégies de rétention (conservation et suppression) dans le centre de sécurité et conformité des messages de conversation et de canal équipes. Cela permet aux organisations de conserver les données de conformité (à savoir, stratégie de conservation) pour une période spécifique ou de vous débarrasser de données (à savoir, stratégie de suppression) s’il est considéré comme un passif après une période spécifique. Stratégies de rétention équipes Assurez-vous que lorsque vous supprimez des données, il est supprimé de tous les emplacements de stockage des données permanentes dans le service d’équipes. 

Pour gérer les stratégies de rétention des équipes works utiliser les cmdlets et les paramètres dans le centre de sécurité pour Microsoft Office 365 et de la conformité sous **La gouvernance des données** > **rétention**.

Stratégies de rétention équipes prennent en charge : 
    
- Conservation : Conserver les données d’équipes pour une durée spécifiée et ne fait rien
- Conservation et supprimer puis : conserver les données des équipes pendant une durée spécifiée, puis supprimer
- Suppression : Supprimer des données d’équipes après une durée spécifiée

Stratégies de rétention équipes ne prennent pas encore charge :

- Les stratégies de rétention avancées ne s’appliquent pas conversation équipes et emplacements de message de canal équipes
- Durée de moins de 30 jours

Administrateurs peuvent définir des stratégies de rétention distinct de salles de conversation privées équipes (1:1 ou 1:Many conversations) et les messages de canal équipes. Dans de nombreux cas, aux organisations de considérer les données de conversation privée comme un passif que les messages de canal, qui sont généralement plus conversations liés au projet. Configurer les stratégies suivantes dans le centre de sécurité et de la conformité, **la gouvernance des données** > **rétention**. Activer de **messages du canal équipes** et **équipes conversations** , puis définissez les stratégies de rétention pour ces emplacements (également indiqués dans le diagramme ci-dessous). 

Lorsque vous activez des **messages du canal équipes**, vous pouvez spécifier les équipes auxquels cette stratégie s’applique. Par exemple, pour les équipes X, Y et Z, l’administrateur peut définir les stratégies de suppression pendant 1 an (en sélectionnant individuellement ces équipes) et appliquer une stratégie de suppression de 3 ans pour le reste des équipes. 

Faire la même chose pour **les équipes conversations** sélectionner des utilisateurs spécifiques et appliquer des stratégies de rétention unique. 

![Diagramme du flux de travail de données Teams vers Exchange et SharePoint.](media/Retention-Policies.png)


> [!IMPORTANT]
> Les emplacements de message de canal équipes et les emplacements de conversations équipes adresse uniquement les conversations équipes stockées dans les boîtes aux lettres Exchange Online (boîtes aux lettres utilisateur et de groupe). Les messages sont supprimés de tous les emplacements de stockage appropriées, à savoir les boîtes aux lettres, Network substrate et service de conversation. 
> 
> Pour gérer les stratégies de rétention pour les fichiers d’équipes, qui sont stockés dans OneDrive pour l’activité et de SharePoint, utilisez les stratégies de rétention.




Par leur conception, les stratégies de suppression pour les fichiers d’équipes sont configurés par le biais de SharePoint Online et OneDrive pour des sites. Par conséquent, il est possible qu’une stratégie peut supprimer un fichier référencé dans un message de conversation ou canal équipes avant la suppression d’obtient ces messages. Dans ce cas, le fichier s’afficheront toujours dans le message d’équipes, mais si vous cliquez sur le fichier, vous obtiendrez une erreur « Fichier introuvable » (Cela peut également se produire en l’absence d’une stratégie, si un utilisateur supprime manuellement un fichier à partir de SharePoint Online ou OneDrive entreprise).


Pour plus d’informations sur la configuration des stratégies de rétention pour Office 365, consultez [vue d’ensemble des stratégies de rétention](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423).
 

## <a name="retention-policies-faq"></a>Forum aux questions sur les stratégies de rétention

### <a name="what-types-of-policies-can-i-setup-in-retention-policies-and-how-do-they-work"></a>Quels types de stratégies puis-je installer dans les stratégies de rétention et comment fonctionnent-ils ?

Dans le centre de sécurité et conformité, lorsque vous configurez une stratégie de rétention, des équipes ou pour n’importe quel autre charge de travail, vous pouvez configurer deux principaux types de stratégies : 
- Conservation : Ces stratégies assurer la préservation de vos données pour une période donnée, quel que soit ce qui se passe dans les outils de l’utilisateur final. Elles Vérifiez que les données sont conservées pour des raisons de conformité expire disponibles dans eDiscovery jusqu'à cette date. Après l’expiration du délai, votre stratégie peut indiquer s’il faut ne rien faire ou supprimer les données. Dans les équipes, si vous créez une stratégie de conservation pour 7 ans, même si les utilisateurs finaux suppriment leurs messages équipes, ces messages sont conservées pour la découverte de 7 ans.
- Suppression : Ces stratégies vous assurer que les données ne sont pas un passif pour votre organisation. Après la durée spécifiée, les données sont supprimées à partir du stockage pertinent toutes les équipes. 

### <a name="can-we-include-teams-in-org-wide-policies"></a>Pouvons nous incluons des équipes de stratégies à l’échelle de l’organisation ? 

Non, pas actuellement. Vous devez créer des stratégies spécifiques pour les messages équipes conversation et de canal à l’aide de la ligne d’emplacement équipes ou ces applets de commande équipes : [New-TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancepolicy?view=exchange-ps) & [New-TeamsComplianceRetentionRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancerule?view=exchange-ps). Ces applets de commande ont obtenir et définir les versions.

### <a name="are-these-retention-policies-retroactive"></a>Ces stratégies de rétention sont rétroactif ? 

Oui, ils se trouvent. Si vous créez une stratégie de rétention pour supprimer les données de plus de 60 jours, il supprime les données des équipes créées plus de 60 jours. 

### <a name="what-is-the-default-retention-policy"></a>Qu’est la stratégie de rétention par défaut ? 

Par défaut, équipes conversation, canal et les données de fichiers sont conservées indéfiniment. Un utilisateur peut supprimer un élément, mais en l’absence de stratégies de rétention, données équipes sont toujours archivées dans Exchange online boîtes aux lettres (utilisateur et groupe) et il restent eDiscovery. 

### <a name="can-i-target-sets-of-users-or-teams-in-a-policy"></a>Puis-je cibler des ensembles d’utilisateurs ou des équipes au sein d’une stratégie ? 

Oui, vous le faire. Dans l’Assistant de création de stratégie, dans l’étape d’emplacements, vous pouvez inclure ou exclure des équipes (**équipes channel messages**) ou des utilisateurs (**conversation équipes**) et créer des stratégies cibles pour votre organisation. 

### <a name="what-is-the-main-difference-between-using-the-group-mailbox-location-row-and-teams-channel-messages-location-row-in-retention-policies"></a>Quelle est la différence principale entre l’utilisation de la ligne d’emplacement de boîte aux lettres de groupe et la ligne d’emplacement de messages de canal équipes dans les stratégies de rétention ? 

Si vous utilisez la boîte aux lettres de groupe et les lignes d’emplacement utilisateur boîte aux lettres pour Exchange Online, données équipes seront supprimées de boîtes aux lettres spécifiées. Toutefois, cela supprime uniquement données à partir de la boîte aux lettres. Elle ne supprime pas autres données équipes, telles que les salles de conversation service. Nous vous recommandons d’utiliser des stratégies de rétention équipes pour gérer correctement toutes les données d’équipes. Une stratégie de rétention équipes supprime les données d’équipes de tous les service de la conversation de boîtes aux lettres, des emplacements stockage, clients équipes. 

Remarque : Lancement de la fonctionnalité de stratégies de rétention pour les équipes permet de s’assurer que seules les stratégies équipes supprimer des éléments d’équipes stockées dans les emplacements de boîte aux lettres Exchange (groupe ou utilisateur). Autre programme d’installation de stratégies de boîtes aux lettres ne peut pas avoir une incidence sur les éléments équipes. Il a la valeur true dans le passé, mais a été corrigé avec le lancement de la fonctionnalité de stratégies de rétention. 

### <a name="what-happens-to-skype-for-business-online-and-teams-interop-chats--are-they-affected-by-retention-policies"></a>Que se passe-t-il à Skype pour Business en ligne et les équipes conversations interopérabilitées – ils sont affectés par les stratégies de rétention ?

Oui, Skype pour Business en ligne et conversations interopérabilitées équipes fonctionnent de la même manière. Une fois le Skype pour la conversation en ligne Business entame équipes, il devient un message dans un thread de conversation équipes et obtient ingéré dans la boîte aux lettres appropriée. Afin que les mêmes flux works – stratégies de suppression des équipes supprimera ces messages à partir du thread d’équipes. Toutefois, si l’historique des conversations sont activé pour Skype pour Business Online et de la Skype pour côté client Business Online ceux sont enregistrés dans une boîte aux lettres, ces données de conversation ne sont pas gérées par une stratégie de rétention les équipes.

### <a name="can-i-do-these-through-security--compliance-center-cmdlets-what-should-i-use"></a>Puis-je faire ces via les cmdlets de centre de sécurité et conformité ? Que dois-je utiliser ? 

Absolument. Vous pouvez créer des stratégies de rétention équipes à l’aide des [applets de commande Powershell du centre de conformité et de sécurité]( https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps). N’oubliez pas que ces applets de commande Exchange Online ne sont pas. Voici les applets de commande que nous avons créée pour les équipes. Ils suivent nomenclature existant et le style à partir de la rétention des applets de commande aujourd'hui disponibles dans le centre de sécurité et conformité.

|Stratégie|Règle|
|---|---|
|[Nouvelle TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancepolicy?view=exchange-ps)| [Nouvelle TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-teamsretentioncompliancerule?view=exchange-ps)|
|[Get-TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-teamsretentioncompliancepolicy?view=exchange-ps)| [Get-TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-teamsretentioncompliancerule?view=exchange-ps)|
|[Set-TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-teamsretentioncompliancepolicy?view=exchange-ps)| [Set-TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-teamsretentioncompliancerule?view=exchange-ps)|
|[Remove-TeamsRetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-teamsretentioncompliancepolicy?view=exchange-ps)| [Remove-TeamsRetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-teamsretentioncompliancerule?view=exchange-ps)|

### <a name="if-there-are-multiple-retention-policies-for-teams-with-varying-durations-which-one-wins"></a>S’il existe plusieurs stratégies de rétention pour les équipes avec différentes durées, laquelle wins ?

Nous principes [de stratégies de rétention](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423)et nous vous recommandons de procéder trop. La réponse est simple : 
-   Conservation toujours l’emporte sur suppression
-   Conservation plus longtemps toujours wins
-   Inclusion explicite l’emporte sur l’inclusion implicite en termes d’emplacements
-   Le plus court wins période suppression



## <a name="retention-policies-known-issues"></a>Problèmes connus de stratégies de rétention

1. Sous Choisissez les équipes dans la ligne d’emplacement de messages canal équipes, vous pouvez voir les équipes pas également Office 365 les groupes. Cela sera traité ultérieurement.

1. Sous Choisir les utilisateurs dans la ligne emplacement équipes conversation, vous pouvez voir les invités et les utilisateurs non-mailbox. Stratégies de rétention ne sont pas destinés à définir pour les visiteurs et nous effectuons fonctionne pour les supprimer de la liste. 

1. Assistant de Cycle de vie Exchange (ELC) s’exécute tous les jours, mais il a un SLA de 7 jours. Par conséquent, il est possible que, si vous disposez d’une stratégie de rétention les équipes à supprimer les éléments antérieurs à 60 jours, ces éléments peuvent conserver 67 jours. Ce n’est pas une situation nouvelle : elle suit le modèle Exchange. Bien sûr, dans la plupart des cas, il n’existe aucun délai.


| | | |
|---------|---------|---------|
|![Icône Point de décision.](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image3.png)     |Point de décision         |De quelles fonctionnalités de sécurité et de conformité votre organisation a-t-elle besoin ? Votre organisation dispose-t-elle des licences requises pour satisfaire les besoins en matière de sécurité et de conformité ?         |
|![Icône Étapes suivantes.](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image4.png)     |Étapes suivantes         |Documenter vos fonctionnalités de sécurité et de conformité requises.         |

<a name="licensing"></a>Licences
---------------

En ce qui concerne les fonctionnalités de protection des informations, les abonnements Office 365 et les licences autonomes associées détermineront l'ensemble de fonctionnalités disponibles.

|Fonctionnalité de protection des informations   |Office 365 Business Essentials   |Office 365 Business Premium   |Office 365 Entreprise E1   |Office 365 Entreprise E3/E4   |Office 365 Entreprise E5   |
|---|---|---|---|---|---|
|Archivage|-  |-   |-   |Oui   |Oui   |
|eDiscovery en place|-   |-   |-   |Oui   |Oui   |
|eDiscovery avancée|-   |-   |-   |-   |Oui   |
|Conservation légale|-   |-   |-   |Oui   |Oui   |
|Recherche de contenu de conformité|- |- |- |Oui |Oui |
|Audit et rapports|Oui |Oui |Oui |Oui |Oui |
|Accès conditionnel* |Oui |Oui |Oui |Oui |Oui |
> [!NOTE]
> \*L'accès conditionnel requiert d'autres licences


| |  |  |
|---------|---------|---------|
|![Icône Point de décision.](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image3.png)     |Point de décision         |Votre organisation dispose-t-elle des licences requises pour satisfaire les besoins en matière de sécurité et de conformité ?         |
|![Icône Étapes suivantes.](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image4.png)    |Étapes suivantes         |Passez en revue la licence actuelle de votre organisation et confirmez qu’il répond à tous les besoins de sécurité et de conformité.         |

Avant d'activer ces fonctionnalités, assurez-vous d'avoir accès au Centre de sécurité et de conformité dans le Centre d'administration Office 365. Par défaut, les administrateurs de clients y ont accès.

Contenu de recherche et de découverte électronique ne nécessitent pas de prise en charge de la sécurité et le centre de conformité.

<a name="location-of-data-in-teams"></a>Emplacement des données dans Teams
-------------------------

Les données dans Teams résident dans la région géographique associée à votre client Office 365. Actuellement, les équipes prend en charge les régions Australie, Canada, Inde, au Japon, UK, Amérique, APAC et EMEA. 

> [!IMPORTANT]
> Équipes propose actuellement délégation données Australie, Canada, Inde, au Japon et au Royaume-Uni pour les nouveaux clients uniquement. Tout client qui ne possédait pas d'utilisateur unique inscrit dans Teams est considéré comme un nouveau client. Clients existants d’Australie, Inde et Japon continuera à leurs données équipes stocké dans la région APAC. Les clients existants au Canada et au Royaume-Uni auront leurs données stockées en Amérique et la région EMEA, respectivement.

Pour plus d'informations sur le lancement de la résidence des données de Teams au Royaume-Uni et en Inde, lisez l’article de blog d’Ansuman Acharya, [Microsoft Teams launches India Data Residency, other geos coming soon](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-Australia-and-Japan-Data-Residency/ba-p/237827) (Microsoft Teams lance la résidence des données en Inde, d’autres régions géographiques seront couvertes prochainement). 

Pour plus d’informations sur la délégation des données Canada pour les équipes, lisez le billet de blog de Varun Sagar [équipes Microsoft lance la délégation données Canada, Australie et Japon bientôt disponible](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-Canada-Data-Residency-Australia-and/ba-p/227178). 

Pour en savoir plus sur le lancement de la délégation de données Australie et Japon pour les équipes, lisez le billet de blog de Varun Sagar [Microsoft équipes lance Australie et Japon données délégation ](https://go.microsoft.com/fwlink/?linkid=867773). 

Pour savoir quelle région héberge les données de votre client, accédez au [Centre d’administration Office 365](https://portal.office.com/adminportal/home) > **Paramètres** > **Profil de l’organisation**. Défilez jusqu’à la section **Emplacement des données**. 

![Captures d'écran du tableau de l’emplacement des données, y compris Teams, dans le Centre d'administration Office 365.](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image5.png)

<a name="how-do-conditional-access-policies-work-for-teams"></a>Comment les stratégies d’accès conditionnel ne fonctionnent pas pour les équipes ?
-------------------------

Teams Microsoft s’appuie fortement sur Exchange Online, SharePoint Online et Skype pour Business Online pour les scénarios de productivité principaux, tels que des réunions, des calendriers, conversations interopérabilitées et partage de fichiers. Stratégies d’accès conditionnel qui sont définis pour ces applications dans le cloud s’appliquent à Microsoft Teams lorsqu’un utilisateur directement se connecte à Microsoft Teams - sur un client. 

Teams Microsoft est pris en charge séparément comme une application cloud dans les stratégies d’accès conditionnel Azure Active Directory. Stratégies d’accès conditionnel qui sont définis pour l’application du cloud Microsoft Teams s’appliquent à Microsoft Teams lorsqu’un utilisateur se connecte. Toutefois, sans les stratégies appropriées sur les autres applications, telles que Exchange Online et SharePoint Online, les utilisateurs peuvent toujours être en mesure d’accéder directement à ces ressources. Pour plus d’informations sur la configuration d’une stratégie d’accès conditionnel dans le portail azure, accédez à : ()https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal-get-started) 

Clients de bureau Teams Microsoft pour Windows et Mac prend en charge l’authentification moderne. Authentification moderne permet de connexion-basé sur le Azure Active Directory authentification bibliothèque (ADAL) pour les applications clientes Microsoft Office sur plusieurs plates-formes.

Application de bureau Microsoft Teams prend en charge AppLocker.  Pour plus d’informations sur les conditions préalables AppLocker, consultez : configuration requise pour utiliser AppLocker (https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/requirements-to-use-applocker).

<a name="privacy-in-teams"></a>Confidentialité dans Teams
--------------------------

En tant que client Office 365, vous possédez et contrôlez vos données. Microsoft utilise vos données uniquement pour vous fournir le service auquel vous avez souscrit. En tant que fournisseur de services, nous n'analysons pas vos messages électroniques, vos documents ou vos équipes à des fins publicitaires ou non liées au service. Microsoft n'a pas accès au contenu chargé. Tout comme avec OneDrive Entreprise et SharePoint Online, les données des utilisateurs appartiennent au client.

Obtenez plus d'informations sur la confidentialité et la sécurité dans le [Centre de gestion de la confidentialité Office 365](https://go.microsoft.com/fwlink/?linkid=855779). Teams suit les mêmes recommandations et principes que le Centre de gestion de la confidentialité.
