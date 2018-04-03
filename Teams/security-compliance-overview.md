---
title: Présentation de la sécurité et de la conformité dans Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
ms.reviewer: anach
description: Ce document présente les fonctionnalités de sécurité et de conformité de Microsoft Teams, notamment les fonctions d'audit, de rapport, de recherche de contenu de conformité, eDiscovery, etc.
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 857e4b691256ff13b6f9308bcd9fb12dfb10297d
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/03/2018
---
<a name="overview-of-security-and-compliance-in-microsoft-teams"></a>Présentation de la sécurité et de la conformité dans Microsoft Teams
======================================================

Microsoft Teams est conçu sur le cloud d'entreprise à très grande échelle Office 365, fournissant à nos clients les fonctionnalités de sécurité avancée et de conformité qu'ils attendent.

Teams est conforme au niveau C à son lancement. Cela comprend les normes suivantes : ISO 27001, ISO 27018, SSAE16 SOC 1 et SOC 2, HIPAA, et les clauses contractuelles types de l'UE (EUMC). Dans son cadre de conformité, Microsoft classe les applications et services Office 365 en quatre catégories. Chaque catégorie est définie par des conditions de conformité spécifiques qui doivent être satisfaites par tout service Office 365, ou tout service Microsoft associé appartenant à ladite catégorie.

Les services qui appartiennent aux catégories de conformité C et D, et qui se soumettent à des conditions de conformité applicables au secteur sont activés par défaut. Les services qui appartiennent aux catégories A et B sont dotés de commandes qui permettent leur activation ou désactivation au niveau de toute l'organisation. Pour obtenir plus d'informations, consultez le document sur le [cadre de conformité aux normes et réglementations du secteur](https://go.microsoft.com/fwlink/?linkid=855777). Teams prend également en charge la conformité à la Cloud Security Alliance.

Teams applique également l'authentification à deux facteurs au niveau de l'équipe et de l'organisation, l'authentification unique via Active Directory et le chiffrement des données en transit ou au repos. Les fichiers sont stockés dans un emplacement SharePoint et protégés par le chiffrement SharePoint. Les notes sont stockées dans un emplacement OneNote et protégées par le chiffrement OneNote.

Nous avons également ajouté la prise en charge de la recherche dans les journaux d'audit, eDiscovery et la conservation légale pour les canaux, les conversations et les fichiers ainsi que la gestion des applications mobiles avec Microsoft Intune. Accédez au centre de sécurité pour Microsoft Office 365 et de la conformité pour gérer ces paramètres. 

## <a name="auditing-and-reporting"></a>Audit et rapports

La recherche dans les journaux d'audit se connecte au Centre de sécurité et de conformité Office 365 et présente les possibilités de définition d'alertes et/ou de génération de rapports sur les événements d'audit, d'exporter des ensembles d'événements spécifiques ou génériques de charges de travail à des fins d'utilisation et de recherche administratives, sur une chronologie d'audit illimitée. Toutes les données des journaux d'audit sont disponibles pour la configuration d'alertes dans le Centre de sécurité et de conformité Office 365, ainsi que le filtrage et l'exportation à des fins d'analyse plus approfondie.

## <a name="compliance-content-search"></a>Recherche de contenu de conformité

La recherche de contenu peut être utilisée pour mener des recherches dans Teams au moyen de fonctionnalités de filtrage enrichies et tout le contenu peut être exporté vers un conteneur spécifique à des fins de conformité et de résolution de litige. Cela peut être effectué avec ou sans cas eDiscovery.

## <a name="ediscovery"></a>eDiscovery

La découverte électronique représente l'aspect électronique de l'identification, la collecte et la production d'informations stockées électroniquement (ESI) en réponse à une demande dans le cadre d'une action en justice ou d'une enquête judiciaire.

Fonctions incluent la gestion, conservation, recherche, analyse et exportation de données d’équipes. Cela inclut les données de chat, de messagerie et de fichiers.

Les clients peuvent utiliser la fonctionnalité eDiscovery en place ou la fonctionnalité [eDiscovery avancée](https://support.office.com/article/Office-365-Advanced-eDiscovery-fd53438a-a760-45f6-9df4-861b50161ae4)

Le tableau suivant présente les différences entre les deux options :


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

Lorsqu'une équipe dans Teams est placée en conservation inaltérable ou en conservation pour litige, cela s'applique à la boîte aux lettres du groupe.

Les conservations légales sont généralement appliquées dans le contexte d'un cas eDiscovery.

La figure ci-après présente le flux de travail de données Teams vers Exchange et SharePoint.

![Diagramme du flux de travail de données Teams vers Exchange et SharePoint.](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1.png)


> [!IMPORTANT]
> La découverte de contenu Teams peut prendre jusqu'à 24 heures.


## <a name="retention-policies"></a>Stratégies de rétention

Conversations des équipes sont persistantes et conservé indéfiniment par défaut. Avec l’introduction de règles de rétention, administrateurs peuvent configurer de rétention (conservation et suppression) dans le centre de sécurité et de conformité pour les messages de conversation et le canal des équipes. Cela aide les entreprises à conserver les données de conformité (à savoir, stratégie de conservation) pour une période spécifique ou de vous débarrasser des données (à savoir, stratégie de suppression) s’il est considéré comme un passif après une période spécifique. Les équipes de rétention Assurez-vous que lorsque vous supprimez des données, il est supprimé de tous les emplacements de stockage des données permanentes sur le service d’équipes. 

Pour gérer les stratégies de rétention des équipes works utilisent les paramètres et les applets de commande dans le centre de sécurité pour Microsoft Office 365 et de la conformité sous la **Gouvernance des données** > **rétention**.

Les équipes de rétention prennent en charge : 
    
- Conservation : Conserver les données des équipes pour une durée spécifiée et ne fait rien
- Conservation et suppression puis : conserver les données des équipes pour une durée spécifiée, puis supprimez
- Suppression : Supprimer les données des équipes après une durée spécifiée

Les équipes de rétention ne ne pas encore prennent en charge :

- Les stratégies de rétention avancées ne s’appliquent pas à la conversation d’équipes et d’emplacements de message de canal équipes
- Durée de moins de 30 jours

Administrateurs pouvez définir des stratégies de rétention distincts pour des conversations privées équipes (1:1 ou 1:Many des chats) et les messages de canaux d’équipes. Dans de nombreux cas, organisations de tenir compte des données de conversation privée comme un passif que les messages de canal qui sont généralement plus de conversations associées au projet. Définir ces stratégies dans le centre de sécurité et de la conformité, de **gouvernance des données** > **rétention**. Allumez **équipes messages du canal** et **les chats des équipes** , puis définissez les stratégies de rétention pour ces emplacements (également indiqués dans le schéma ci-dessous). 

Lorsque vous activez **les équipes messages du canal**, vous pouvez spécifier les équipes auxquels s’applique cette stratégie. Par exemple, des équipes de X, Y et Z, l’administrateur peut définir les règles de suppression pendant un an (en sélectionnant ces équipes individuellement) et appliquer une stratégie de suppression de 3 ans pour le reste de l’équipe. 

Faire la même chose pour **les chats des équipes de** sélection des utilisateurs spécifiques et application de stratégies de rétention unique. 

![Diagramme du flux de travail de données Teams vers Exchange et SharePoint.](media/Retention-Policies.png)


> [!IMPORTANT]
> Les emplacements de message de canal d’équipes et les emplacements des conversations équipes d’adresses uniquement les conversations d’équipes stockées dans les boîtes aux lettres Exchange Online (boîtes aux lettres utilisateur et de groupe). Les messages sont supprimés de tous les emplacements de stockage en cause, à savoir les boîtes aux lettres, substrat et le service chat. 
> 
> Pour gérer les stratégies de rétention pour les fichiers des équipes, qui sont stockés dans OneDrive pour l’entreprise et SharePoint, utilisez leur politique de rétention.




Par conception, les règles de suppression des fichiers d’équipes sont configurés par le biais de SharePoint Online et OneDrive pour des sites. Par conséquent, il est possible qu’une stratégie peut supprimer un fichier référencé dans un message de chat ou canal équipes avant que ces messages sont supprimés. Dans ce cas, le fichier s’afficheront toujours dans le message d’équipes, mais si vous cliquez sur le fichier, vous obtiendrez une erreur « Fichier non trouvé » (Cela peut également se produire en l’absence d’une stratégie, si un utilisateur supprime manuellement un fichier à partir de SharePoint Online ou OneDrive pour les entreprises).


Pour plus d’informations sur la configuration des stratégies de rétention pour Office 365, lisez [la vue d’ensemble des stratégies de rétention](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423).
 

## <a name="retention-policies-faq"></a>Forum aux questions de rétention

### <a name="what-types-of-policies-can-i-setup-in-retention-policies-and-how-do-they-work"></a>Quels sont les types de stratégies puis-je configurer dans les stratégies de rétention et comment fonctionnent-ils ?

Dans le centre de sécurité et de conformité, lorsque vous configurez une stratégie de rétention, d’équipes ou de toute autre charge de travail, vous pouvez configurer deux principaux types de stratégies : 
- Conservation : Ces stratégies garantissent que vos données sont conservées pour une période donnée, indépendamment de ce qui se passe dans les outils de l’utilisateur final. Ils veillent à ce que les données sont conservées pour des raisons de respect de la réglementation et expire disponibles dans e-Discovery jusqu'à ce moment. Après l’expiration du délai, votre stratégie peut indiquer si vous souhaitez ne rien faire ou de supprimer les données. Dans les équipes, si vous créez une stratégie de conservation de sept ans, même si les utilisateurs finaux suppriment les messages de leurs équipes, ces messages sont toujours conservés pour e-Discovery pendant 7 ans.
- Suppression : Ces stratégies garantissent que les données ne sont pas un passif pour votre organisation. Après la durée spécifiée, les données sont supprimées à partir de tout le stockage approprié dans les équipes. 

### <a name="can-we-include-teams-in-org-wide-policies"></a>Pouvons nous incluons des équipes de stratégies à l’échelle de l’organisation ? 

Non, pas actuellement. Vous devez créer des stratégies pour les messages chat et canal équipes à l’aide de la ligne d’emplacement équipes ou ces applets de commande d’équipes spécifiques : New-TeamsRetentionCompliancePolicy & New-TeamsComplianceRetentionRule. Ces applets de commande ont obtenir et définir les versions.

### <a name="are-these-retention-policies-retroactive"></a>Ces stratégies de rétention sont les rétroactif ? 

Oui, ils le sont. Si vous créez une stratégie de rétention pour supprimer les données de plus de 60 jours, il supprime les données des équipes créées il y a plus de 60 jours. 

### <a name="what-is-the-default-retention-policy"></a>Quelle est la stratégie de rétention par défaut ? 

Par défaut, les équipes chat, canaux et les données de fichiers sont conservées indéfiniment. Un utilisateur peut supprimer quelque chose, mais en l’absence de stratégies de rétention, données d’équipes sont toujours archivées dans Exchange en ligne boîtes aux lettres (utilisateur et groupe) et reste à ce niveau d’e-Discovery. 

### <a name="can-i-target-sets-of-users-or-teams-in-a-policy"></a>Puis-je cibler des ensembles d’utilisateurs ou les équipes dans une stratégie ? 

Oui, vous le faites. Dans l’Assistant de création de stratégie, dans l’étape d’emplacements, vous pouvez inclure ou exclure des équipes (**équipes de canal de messages**) ou des utilisateurs (**chat d’équipes**) et créer des stratégies ciblées pour votre organisation. 

### <a name="what-is-the-main-difference-between-using-the-group-mailbox-location-row-and-teams-channel-messages-location-row-in-retention-policies"></a>Quelle est la principale différence entre l’utilisation de la ligne d’emplacement de boîte aux lettres de groupe et de la ligne d’emplacement de messages de canal équipes dans les stratégies de rétention ? 

Si vous utilisez la boîte aux lettres de groupe et les lignes d’emplacement de boîte aux lettres utilisateur pour Exchange Online, données d’équipes seront supprimées à partir de boîtes aux lettres spécifiées. Toutefois, cela ne supprime que données à partir de la boîte aux lettres. Il ne supprime les autres données des équipes, telles que des salles de conversation service. Nous vous conseillons de stratégies de rétention des équipes pour gérer correctement les données de toutes les équipes. Une stratégie de rétention les équipes supprime les données d’équipes à partir de tout stockage emplacements – les boîtes aux lettres, le service Chat, clients d’équipes. 

### <a name="what-happens-to-skype-for-business-online-and-teams-interop-chats--are-they-affected-by-retention-policies"></a>Que se passe-t-il à Skype pour Business Online et les équipes des conversations interopérabilitées – si elles sont concernées par les stratégies de rétention ?

Oui, Skype pour entreprise en ligne et conversations d’interopérabilité équipes fonctionnent de la même manière. Une fois le Skype pour une conversation en ligne Business est fourni en équipes, il devient un message dans une thread de conversation équipes et obtient ingéré dans la boîte aux lettres appropriée. Afin que le même flux de works, règles de suppression d’équipes supprimera ces messages à partir du thread d’équipes. Toutefois, si l’historique des conversations sont activée pour Skype pour entreprise en ligne et de la Skype pour les côté client Business Online ceux sont enregistrées dans une boîte aux lettres, ces données de conversation ne sont pas gérées par une stratégie de rétention les équipes.

### <a name="can-i-do-these-through-security--compliance-center-cmdlets-what-should-i-use"></a>Puis-je faire ces via les cmdlets de centre de sécurité et conformité ? Que dois-je utiliser ? 

Absolument. Vous pouvez créer des règles de rétention des équipes à l’aide des [applets de commande Powershell du centre de conformité et de sécurité]( https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps). N’oubliez pas que ces ne sont pas des applets de commande en ligne Exchange. Voici les applets de commande que nous avons créées pour les équipes. Ils suivent une nomenclature existante et le style de rétention applets de commande disponibles aujourd'hui dans le centre de sécurité et de conformité.

|Stratégie de|Règle|
|---|---|
|Nouvelle-TeamsRetentionCompliancePolicy| Nouvelle-TeamsRetentionComplianceRule|
|Get-TeamsRetentionCompliancePolicy| Get-TeamsRetentionComplianceRule|
|Get - TeamsRetentionCompliancePolicy| Set - TeamsRetentionComplianceRule|
|Supprimer - TeamsRetentionCompliancePolicy| Supprimer - TeamsRetentionComplianceRule|

### <a name="if-there-are-multiple-retention-policies-for-teams-with-varying-durations-which-one-wins"></a>S’il existe plusieurs stratégies de rétention pour les équipes avec des durées différentes, lequel wins ?

Nous suivons les [principes des stratégies de rétention](https://support.office.com/article/overview-of-retention-policies-5e377752-700d-4870-9b6d-12bfc12d2423), et nous vous conseillons trop. La réponse est simple : 
-   Conservation toujours wins sur suppression
-   Période de conservation la plus longue toujours wins
-   Inclusion explicite wins sur l ' inclusion implicite en termes d’emplacements
-   Le plus court wins période de suppression



## <a name="retention-policies-known-issues"></a>Problèmes connus de rétention

1. Sous Choisissez les équipes dans la ligne d’emplacement de messages canal d’équipes, vous pouvez voir les équipes pas également Office 365 les groupes. Cela sera résolu dans le futur.

1. Sous Choisissez les utilisateurs dans la ligne d’emplacement équipes Chat, vous pouvez voir les invités et les utilisateurs de boîtes aux lettres non. Stratégies de rétention ne sont pas destinées à être défini pour les visiteurs, et nous travaillons pour les supprimer de la liste. 

1. Assistant du Cycle de vie d’Exchange (ELC) s’exécute tous les jours, mais il a un SLA de 7 jours. Par conséquent, il est possible que, si vous avez une stratégie de rétention les équipes pour supprimer les articles datant de plus de 60 jours, ces éléments susceptible de se maintenir jusqu'à 67 jours. Ce n’est pas une situation nouvelle, il suit le modèle Exchange. Bien sûr, dans la plupart des cas, il n’existe aucun délai.


| | | |
|---------|---------|---------|
|![Icône Point de décision.](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image3.png)     |Point de décision         |De quelles fonctionnalités de sécurité et de conformité votre organisation a-t-elle besoin ? Votre organisation dispose-t-elle des licences requises pour satisfaire les besoins en matière de sécurité et de conformité ?         |
|![Icône Étapes suivantes.](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image4.png)     |Étapes suivantes         |Documentez vos fonctionnalités de sécurité et de conformité requises.         |

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
|![Icône Étapes suivantes.](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image4.png)    |Étapes suivantes         |Vérifier les licences actuelles de votre entreprise et confirmer qu’il répond à tous les besoins de conformité et de sécurité.         |

Avant d'activer ces fonctionnalités, assurez-vous d'avoir accès au Centre de sécurité et de conformité dans le Centre d'administration Office 365. Par défaut, les administrateurs de clients y ont accès.

Contenu de recherche et d’e-Discovery ne nécessitent pas de prise en charge de la sécurité et le centre de conformité.

<a name="location-of-data-in-teams"></a>Emplacement des données dans Teams
-------------------------

Les données dans Teams résident dans la région géographique associée à votre client Office 365. Actuellement, Teams prend en charge les régions Amériques, EMEA et APAC. 

> [!IMPORTANT]
> Teams fournit la résidence des données au Royaume-Uni et en Inde, pour les nouveaux clients uniquement. Tout client qui ne possédait pas d'utilisateur unique inscrit dans Teams est considéré comme un nouveau client. Les clients existants du Royaume-Uni et en Inde resteront dans les régions EMEA et APAC, respectivement, jusqu'à la publication d'un plan de migration (prévue pour 2018).

Pour plus d'informations sur le lancement de la résidence des données de Teams au Royaume-Uni et en Inde, lisez l’article de blog d’Ansuman Acharya, [Microsoft Teams launches India Data Residency, other geos coming soon](https://go.microsoft.com/fwlink/?linkid=867773) (Microsoft Teams lance la résidence des données en Inde, d’autres régions géographiques seront couvertes prochainement).

Pour savoir quelle région héberge les données de votre client, accédez au [Centre d’administration Office 365](https://portal.office.com/adminportal/home) > **Paramètres** > **Profil de l’organisation**. Défilez jusqu’à la section **Emplacement des données**. 

![Captures d'écran du tableau de l’emplacement des données, y compris Teams, dans le Centre d'administration Office 365.](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image5.png)

<a name="privacy-in-teams"></a>Confidentialité dans Teams
--------------------------

En tant que client Office 365, vous possédez et contrôlez vos données. Microsoft utilise vos données uniquement pour vous fournir le service auquel vous avez souscrit. En tant que fournisseur de services, nous n'analysons pas vos messages électroniques, vos documents ou vos équipes à des fins publicitaires ou non liées au service. Microsoft n'a pas accès au contenu chargé. Tout comme avec OneDrive Entreprise et SharePoint Online, les données des utilisateurs appartiennent au client.

Découvrez plus d’informations sur la confiance et la sécurité des informations à partir du [Centre de confidentialité Office 365](https://go.microsoft.com/fwlink/?linkid=855779). Teams suit les mêmes recommandations et principes que le Centre de gestion de la confidentialité.
