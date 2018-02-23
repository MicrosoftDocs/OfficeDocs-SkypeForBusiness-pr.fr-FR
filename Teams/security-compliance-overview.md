---
title: "Présentation de la sécurité et de la conformité dans Microsoft Teams"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
ms.reviewer: anach
description: "Ce document présente les fonctionnalités de sécurité et de conformité de Microsoft Teams, notamment les fonctions d'audit, de rapport, de recherche de contenu de conformité, eDiscovery, etc."
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1cb2bfe08736f355f01d55d05be7c7091b79f396
ms.sourcegitcommit: ed40dcf28ae72961fb1f23cf72985cef1d145db0
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/11/2018
---
<a name="overview-of-security-and-compliance-in-microsoft-teams"></a>Présentation de la sécurité et de la conformité dans Microsoft Teams
======================================================

Microsoft Teams est conçu sur le cloud d'entreprise à très grande échelle Office 365, fournissant à nos clients les fonctionnalités de sécurité avancée et de conformité qu'ils attendent.

Teams est conforme au niveau C à son lancement. Cela comprend les normes suivantes : ISO 27001, ISO 27018, SSAE16 SOC 1 et SOC 2, HIPAA, et les clauses contractuelles types de l'UE (EUMC). Dans son cadre de conformité, Microsoft classe les applications et services Office 365 en quatre catégories. Chaque catégorie est définie par des conditions de conformité spécifiques qui doivent être satisfaites par tout service Office 365, ou tout service Microsoft associé appartenant à ladite catégorie.

Les services qui appartiennent aux catégories de conformité C et D, et qui se soumettent à des conditions de conformité applicables au secteur sont activés par défaut. Les services qui appartiennent aux catégories A et B sont dotés de commandes qui permettent leur activation ou désactivation au niveau de toute l'organisation. Pour obtenir plus d'informations, consultez le document sur le [cadre de conformité aux normes et réglementations du secteur](https://go.microsoft.com/fwlink/?linkid=855777). Teams prend également en charge la conformité à la Cloud Security Alliance.

Teams applique également l'authentification à deux facteurs au niveau de l'équipe et de l'organisation, l'authentification unique via Active Directory et le chiffrement des données en transit ou au repos. Les fichiers sont stockés dans un emplacement SharePoint et protégés par le chiffrement SharePoint. Les notes sont stockées dans un emplacement OneNote et protégées par le chiffrement OneNote.

Nous avons également ajouté la prise en charge de la recherche dans les journaux d'audit, eDiscovery et la conservation légale pour les canaux, les conversations et les fichiers ainsi que la gestion des applications mobiles avec Microsoft Intune.

Ces outils résident dans le Portail de sécurité et de conformité Office 365 et fournissent les fonctions suivantes :

-   Audit et rapports

    -   La recherche dans les journaux d'audit se connecte au Centre de sécurité et de conformité Office 365 et présente les possibilités de définition d'alertes et/ou de génération de rapports sur les événements d'audit, d'exporter des ensembles d'événements spécifiques ou génériques de charges de travail à des fins d'utilisation et de recherche administratives, sur une chronologie d'audit illimitée. Toutes les données des journaux d'audit sont disponibles pour la configuration d'alertes dans le Centre de sécurité et de conformité Office 365, ainsi que le filtrage et l'exportation à des fins d'analyse plus approfondie.

-   Recherche de contenu de conformité

    -   La recherche de contenu peut être utilisée pour mener des recherches dans Teams au moyen de fonctionnalités de filtrage enrichies et tout le contenu peut être exporté vers un conteneur spécifique à des fins de conformité et de résolution de litige. Cela peut être effectué avec ou sans cas eDiscovery.

-   eDiscovery

    -   La découverte électronique représente l'aspect électronique de l'identification, la collecte et la production d'informations stockées électroniquement (ESI) en réponse à une demande dans le cadre d'une action en justice ou d'une enquête judiciaire.

    -   Les fonctionnalités incluent la gestion des cas, la conservation, la recherche, l'analyse et l'exportation de données Teams. Les données comprennent les conversations, la messagerie et les fichiers.

    -   Les clients peuvent utiliser la fonctionnalité eDiscovery en place ou la fonctionnalité [eDiscovery avancée](https://support.office.com/article/Office-365-Advanced-eDiscovery-fd53438a-a760-45f6-9df4-861b50161ae4)

    -   Le tableau suivant présente les différences entre les deux options :


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


-   Conservation légale

    -   Lorsqu'une équipe dans Teams est placée en conservation inaltérable ou en conservation pour litige, cela s'applique à la boîte aux lettres du groupe.

    -   Les conservations légales sont généralement appliquées dans le contexte d'un cas eDiscovery.

La figure ci-après présente le flux de travail de données Teams vers Exchange et SharePoint.

![Diagramme du flux de travail de données Teams vers Exchange et SharePoint.](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1.png)


> [!IMPORTANT]
> La découverte de contenu Teams peut prendre jusqu'à 24 heures.

De plus, Microsoft envisage de fournir les fonctionnalités de sécurité suivantes pour Teams. Lorsqu'elles seront disponibles, des instructions d'utilisation seront fournies aux clients :

-   Stratégie de rétention en fonction du client

-   Prévention de perte des données (DLP)

-   Référentiel sécurisé du client

-   Gestion des droits


| | | |
|---------|---------|---------|
|![Icône Point de décision.](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image3.png)     |Point de décision         |De quelles fonctionnalités de sécurité et de conformité votre organisation a-t-elle besoin ? Votre organisation dispose-t-elle des licences requises pour satisfaire les besoins en matière de sécurité et de conformité ?         |
|![Icône Étapes suivantes.](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image4.png)     |Étapes suivantes         |Documentez les fonctionnalités de sécurité et de conformité dans le tableau ci-dessous.         |

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
\*L'accès conditionnel requiert d'autres licences


| |  |  |
|---------|---------|---------|
|![Icône Point de décision.](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image3.png)     |Point de décision         |Votre organisation dispose-t-elle des licences requises pour satisfaire les besoins en matière de sécurité et de conformité ?         |
|![Icône Étapes suivantes.](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image4.png)    |Étapes suivantes         |Consultez les licences actuelles de votre organisation pour confirmer que les besoins en matière de sécurité et de conformité sont satisfaits.         |

Avant d'activer ces fonctionnalités, assurez-vous d'avoir accès au Centre de sécurité et de conformité dans le Centre d'administration Office 365. Par défaut, les administrateurs de clients y ont accès.

La recherche de contenu et eDiscovery ne requièrent pas l'activation dans le Centre de sécurité et de conformité.

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

Obtenez plus d'informations sur la confidentialité et la sécurité dans le [*Centre de gestion de la confidentialité Office 365*](https://go.microsoft.com/fwlink/?linkid=855779). Teams suit les mêmes recommandations et principes que le Centre de gestion de la confidentialité.
