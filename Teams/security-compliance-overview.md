---
title: Présentation de la sécurité et de la conformité dans Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/11/2018
ms.topic: conceptual
ms.service: msteams
ms.reviewer: anach
description: Vue d’ensemble des fonctionnalités de sécurité et de conformité de Microsoft Teams, y compris l’audit et création de rapports, recherche de contenu de la conformité, eDiscovery et plus.
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 85678529f25e46b7c75c08976d86870fc4566694
ms.sourcegitcommit: cf2cb5b7e03385b33e34a5ff89719adb882525b1
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/06/2019
ms.locfileid: "33632313"
---
<a name="overview-of-security-and-compliance-in-microsoft-teams"></a>Présentation de la sécurité et de la conformité dans Microsoft Teams
======================================================

Microsoft Teams est conçu sur le cloud d'entreprise à très grande échelle Office 365, fournissant à nos clients les fonctionnalités de sécurité avancée et de conformité qu'ils attendent.

Les équipes est compatible avec niveau D. Cela inclut les normes suivantes : ISO 27001, ISO 27018, SSAE16 sociale 1 et 2 de sécurité sociale, HIPAA et Clauses de modèle de l’Union européenne (CMUE). Dans le cadre de conformité de Microsoft, Microsoft classifie les services et applications Office 365 en quatre catégories. Chaque catégorie est définie par les engagements de conformité spécifique qui doivent être remplies pour un service Office 365 ou un service Microsoft associé, répertoriées dans cette catégorie.

Les services qui appartiennent aux catégories de conformité C et D, et qui se soumettent à des conditions de conformité applicables au secteur sont activés par défaut. Les services qui appartiennent aux catégories A et B sont dotés de commandes qui permettent leur activation ou désactivation au niveau de toute l'organisation. Pour obtenir plus d'informations, consultez le document sur le [cadre de conformité aux normes et réglementations du secteur](https://go.microsoft.com/fwlink/?linkid=855777). Teams prend également en charge la conformité à la Cloud Security Alliance.

Les équipes applique également à l’échelle de l’équipe et l’organisation authentification à deux facteurs, authentification unique par le biais de Active Directory et le chiffrement des données en transit et inactives. Les fichiers sont stockés dans SharePoint et sont sauvegardés par le chiffrement de SharePoint. Notes sont stockées dans OneNote et sont sauvegardés par le chiffrement de OneNote. Les données de OneNote sont stockées dans le site d’équipe SharePoint. L’onglet Wiki peut également être utilisé pour la prise de notes et son contenu est également stocké dans le site d’équipe SharePoint.

Nous avons également ajouté la prise en charge de la recherche dans les journaux d'audit, eDiscovery et la conservation légale pour les canaux, les conversations et les fichiers ainsi que la gestion des applications mobiles avec Microsoft Intune. Accédez à la & Office 365 sécurité Centre de conformité pour gérer ces paramètres. 

Pour en savoir plus sur & la conformité de la sécurité Office 365, consultez [configurer votre client Office 365 pour accroître la sécurité](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security)

## <a name="auditing-and-reporting"></a>Audit et rapports

Recherche des journaux d’audit se connecte à droite dans le centre de conformité de & Office 365 sécurité et expose les capacités pour définir des alertes et/ou de créer des rapports sur les événements d’Audit en rendant disponibles, l’exportation de la charge de travail spécifiques ou événement générique définit pour l’utilisation d’administration et d’enquête, sur un chronologie audit illimité. Toutes les données du journal d’Audit est disponibles pour la configuration des alertes dans le centre de conformité de & Office 365 sécurité, ainsi que pour le filtrage et exporter pour une analyse approfondie. Reportez-vous à ce [lien](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security-Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c) pour en savoir plus sur la façon d’effectuer une recherche de journal d’Audit pour les événements Teams Microsoft dans le centre de conformité de & Office 365 sécurité. 

## <a name="compliance-content-search"></a>Recherche de contenu de conformité

Recherche de contenu pouvant être utilisée pour rechercher toutes les données d’équipes par le biais de riches fonctionnalités de filtrage et exportée vers un conteneur spécifique pour la prise en charge pour litige et conformité. Cela peut être effectuée avec ou sans un cas eDiscovery. Cela permet aux administrateurs de conformité recueillir des données d’équipes pour tous les utilisateurs, passez en revue et exportez-le pour un traitement supplémentaire. Reportez-vous à ce [lien](https://support.office.com/article/content-search-in-office-365-53390468-eec6-45cb-b6cd-7511f9c909e4) pour en savoir plus sur la façon d’effectuer une recherche de contenu de conformité pour le contenu Teams Microsoft dans le centre de conformité de & Office 365 sécurité. 

Conseil : Le type Teams Microsoft permettre servir à filtrer par le biais d’à Microsoft Teams contenu uniquement c'est-à-dire conversation et les Messages de canal, les réunions et les appels. 

## <a name="ediscovery"></a>eDiscovery

La découverte électronique représente l'aspect électronique de l'identification, la collecte et la production d'informations stockées électroniquement (ESI) en réponse à une demande dans le cadre d'une action en justice ou d'une enquête judiciaire. Fonctionnalités incluent la gestion, conservation, recherche, l’analyse et exporter des données d’équipes. Cela inclut les résumés de conversation, de messagerie et les fichiers, réunion et appel. Pour les réunions d’équipes et un résumé des événements qui s’est produite dans la réunion et d’appel, les appels sont créés et mis à disposition d’eDiscovery. 

Pour plus d’informations sur la découverte électronique dans sécurité & centre de conformité et exécuter la recherche de contenu de la conformité pour le contenu des équipes, consultez les liens ci-dessous : 

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

Pendant un litige, il est souvent nécessaire que toutes les données associées à un utilisateur (dépositaire) ou une équipe est conservée immuable, donc il peut être utilisé comme preuve pour le cas. Pour cela, vous devez placer un utilisateur (boîte aux lettres de l’utilisateur) ou à une équipe en conservation légale. Lorsqu’une équipe au sein des équipes est placée sur le blocage sur Place (sous-ensemble de la collection de site ou de la boîte aux lettres via des requêtes ciblés ou du contenu filtré) ou litige (toute boîte aux lettres ou site collection), la suspension est placée sur la boîte aux lettres de groupes. Cela garantit que même si les utilisateurs finaux, supprimer ou modifier les messages de canal sont ingérés dans la boîte aux lettres de groupe, immuables copies de ce contenu sont disponibles dans la recherche de découverte électronique et conservées. Les conservations légales sont généralement appliquées dans le contexte d'un cas eDiscovery. Consultez [cette](https://support.office.com/article/overview-of-preservation-policies-9c3b1d52-40ce-4ba3-a520-9ae0be15538a) aide de l’article pour en savoir plus sur la conservation et suspensions dans le centre de conformité de & Office 365 sécurité. 

## <a name="information-protection-architecture-for-microsoft-teams"></a>Architecture de Protection des informations pour les équipes Microsoft. 

La figure suivante indique le flux d’ingestion des données équipes à Exchange et SharePoint pour les équipes de fichiers et des Messages. 

![Diagramme du flux de travail de données Teams vers Exchange et SharePoint.](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1.png)

La figure suivante indique le flux d’ingestion des équipes de réunions et des données appelante à Exchange.

![Diagramme du flux de travail des équipes de réunions et des données appelante à Exchange.](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1a.png)

> [!IMPORTANT]
> Il peut y avoir jusqu'à un délai de 24 heures pour découvrir du contenu des équipes.

<a name="licensing"></a>Licences
---------------

En ce qui concerne les fonctionnalités de protection des informations, les abonnements Office 365 et les licences autonomes associées détermineront l'ensemble de fonctionnalités disponibles.


| Fonctionnalité de protection des informations | Office 365 Business Essentials | Office 365 Business Premium | Office 365 Entreprise E1 | Office 365 Entreprise E3/E4 | Office 365 Entreprise E5 |
|-----------------------------------|--------------------------------|-----------------------------|--------------------------|-----------------------------|--------------------------|
|              Archivage              |               -                |              -              |            -             |             Oui             |           Oui            |
|        eDiscovery en place        |               -                |              -              |            -             |             Oui             |           Oui            |
|        eDiscovery avancée        |               -                |              -              |            -             |              -              |           Oui            |
|            Conservation légale             |               -                |              -              |            -             |             Oui             |           Oui            |
|     Recherche de contenu de conformité     |               -                |             Oui             |           Oui            |             Oui             |           Oui            |
|      Audit et rapports       |              Oui               |             Oui             |           Oui            |             Oui             |           Oui            |
|       Accès conditionnel\*        |              Oui               |             Oui             |           Oui            |             Oui             |           Oui            |

> [!NOTE]
> \*L'accès conditionnel requiert d'autres licences


| |  |  |
|---------|---------|---------|
|![Icône Point de décision.](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image3.png)     |Point de décision         |Votre organisation dispose-t-elle des licences requises pour satisfaire les besoins en matière de sécurité et de conformité ?         |
|![Icône Étapes suivantes.](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image4.png)    |Étapes suivantes         |Passez en revue la licence actuelle de votre organisation et confirmez qu’il répond à tous les besoins de sécurité et de conformité.         |

Avant d’activer une de ces fonctionnalités, assurez-vous de qu'avoir accès à la sécurité de & centre de conformité dans le centre d’administration Microsoft 365. Par défaut, les administrateurs de clients y ont accès.

Contenu de recherche et de découverte électronique ne nécessitent pas d’activation dans le centre de conformité de & sécurité.

<a name="location-of-data-in-teams"></a>Emplacement des données dans Teams
-------------------------

Les données dans Teams résident dans la région géographique associée à votre client Office 365. Actuellement, les équipes prend en charge les régions Australie, Canada, Inde, au Japon, UK, Amérique, APAC et EMEA. 

> [!IMPORTANT]
> Équipes propose actuellement délégation données Australie, Canada, Inde, au Japon et au Royaume-Uni pour les nouveaux clients uniquement. Tout client qui ne possédait pas d'utilisateur unique inscrit dans Teams est considéré comme un nouveau client. Clients existants d’Australie, Inde et Japon continuera à leurs données équipes stocké dans la région APAC. Les clients existants au Canada et au Royaume-Uni auront leurs données stockées en Amérique et la région EMEA, respectivement.

Pour plus d'informations sur le lancement de la résidence des données de Teams au Royaume-Uni et en Inde, lisez l’article de blog d’Ansuman Acharya, [Microsoft Teams launches India Data Residency, other geos coming soon](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-Australia-and-Japan-Data-Residency/ba-p/237827) (Microsoft Teams lance la résidence des données en Inde, d’autres régions géographiques seront couvertes prochainement). 

Pour plus d’informations sur la délégation des données Canada pour les équipes, lisez le billet de blog de Varun Sagar [équipes Microsoft lance la délégation données Canada, Australie et Japon bientôt disponible](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-Canada-Data-Residency-Australia-and/ba-p/227178). 

Pour en savoir plus sur le lancement de la délégation de données Australie et Japon pour les équipes, lisez le billet de blog de Varun Sagar [Microsoft équipes lance Australie et Japon données délégation ](https://go.microsoft.com/fwlink/?linkid=867773). 

Pour afficher la zone contient des données pour votre client, accédez au [Centre d’administration Microsoft 365](https://portal.office.com/adminportal/home) > **paramètres** > **profil d’organisation**. Défilez jusqu’à la section **Emplacement des données**. 

![Capture d’écran de la table de magasin de données, y compris les équipes, dans le centre d’administration d’Office 365.](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image5.png)

<a name="how-do-conditional-access-policies-work-for-teams"></a>Comment les stratégies d’accès conditionnel ne fonctionnent pas pour les équipes ?
-------------------------

Teams Microsoft s’appuie fortement sur Exchange Online, SharePoint Online et Skype pour Business Online pour les scénarios de productivité principaux, tels que des réunions, des calendriers, conversations interopérabilitées et partage de fichiers. Stratégies d’accès conditionnel qui sont définis pour ces applications dans le cloud s’appliquent à Microsoft Teams lorsqu’un utilisateur directement se connecte à Microsoft Teams - sur un client. 

Teams Microsoft est pris en charge séparément comme une application cloud dans les stratégies d’accès conditionnel Azure Active Directory. Stratégies d’accès conditionnel qui sont définis pour l’application du cloud Microsoft Teams s’appliquent à Microsoft Teams lorsqu’un utilisateur se connecte. Toutefois, sans les stratégies appropriées sur les autres applications, telles que Exchange Online et SharePoint Online, les utilisateurs peuvent toujours être en mesure d’accéder directement à ces ressources. Pour plus d’informations sur la configuration d’une stratégie d’accès conditionnel dans le portail azure, accédez à : ()https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal-get-started) 

Clients de bureau Teams Microsoft pour Windows et Mac prend en charge l’authentification moderne. Authentification moderne permet de connexion-basé sur le Azure Active Directory authentification bibliothèque (ADAL) pour les applications clientes Microsoft Office sur plusieurs plates-formes.

Application de bureau Microsoft Teams prend en charge AppLocker.  Pour plus d’informations sur les conditions préalables AppLocker, consultez : configuration requise pour utiliser AppLocker (https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/requirements-to-use-applocker).

<a name="privacy-in-teams"></a>Confidentialité dans Teams
--------------------------

En tant que client Office 365, vous possédez et contrôlez vos données. Microsoft utilise vos données uniquement pour vous fournir le service auquel vous avez souscrit. En tant que fournisseur de services, nous n'analysons pas vos messages électroniques, vos documents ou vos équipes à des fins publicitaires ou non liées au service. Microsoft n'a pas accès au contenu chargé. Tout comme avec OneDrive Entreprise et SharePoint Online, les données des utilisateurs appartiennent au client.

Extraction d’informations sur la sécurité et de confiance des informations à partir du [Centre de gestion de la confidentialité de Microsoft](https://microsoft.com/trustcenter). Les équipes suit les mêmes instructions et principes comme le Center Trust Microsoft.

<a name="related-topics"></a>Voir aussi
----------------------
[Office 365 DAV Safe liens](https://docs.microsoft.com/office365/securitycompliance/atp-safe-links#how-to-get-atp-safe-links-protection)
