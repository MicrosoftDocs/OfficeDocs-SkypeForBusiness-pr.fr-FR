---
title: Présentation de la sécurité et de la conformité dans Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/11/2018
ms.topic: conceptual
ms.service: msteams
ms.reviewer: anach
audience: admin
description: Vue d’ensemble des fonctionnalités de sécurité et de conformité de Microsoft Teams, notamment l’audit et la création de rapports, la recherche de contenu de conformité, la découverte électronique, etc.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d9e9b07ed1ca995d673ef6ea79652cb880c4dff6
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36242782"
---
<a name="overview-of-security-and-compliance-in-microsoft-teams"></a>Présentation de la sécurité et de la conformité dans Microsoft Teams
======================================================

Microsoft Teams est conçu sur le cloud d'entreprise à très grande échelle Office 365, fournissant à nos clients les fonctionnalités de sécurité avancée et de conformité qu'ils attendent.

Teams est conforme à la norme de niveau D. Cela inclut les normes suivantes: ISO 27001, ISO 27018, SSAE16 SOC 1 et SOC 2, HIPAA et des clauses de modèle européen (CMUE). Dans l’infrastructure de conformité Microsoft, Microsoft classifie les applications et services Office 365 en quatre catégories. Chaque catégorie est définie par des engagements de conformité spécifiques qui doivent être satisfaits pour un service Office 365 ou un service Microsoft associé qui doit être répertorié dans cette catégorie.

Les services qui appartiennent aux catégories de conformité C et D, et qui se soumettent à des conditions de conformité applicables au secteur sont activés par défaut. Les services qui appartiennent aux catégories A et B sont dotés de commandes qui permettent leur activation ou désactivation au niveau de toute l'organisation. Pour obtenir plus d'informations, consultez le document sur le [cadre de conformité aux normes et réglementations du secteur](https://download.microsoft.com/download/B/2/7/B27B3EF3-8849-4C18-8BA4-5AD755728620/Compliance%20Framework_customer%20guidance.pdf). Teams prend également en charge la conformité à la Cloud Security Alliance.

Teams applique également l’authentification à deux facteurs à l’échelle de l’organisation et au niveau de l’organisation, de l’authentification unique via Active Directory et du chiffrement des données en transit et au repos. Les fichiers sont stockés dans SharePoint et sont sauvegardés par le chiffrement SharePoint. Les notes sont stockées dans OneNote et sont représentées par un chiffrement OneNote. Les données OneNote sont stockées dans le site SharePoint de l’équipe. L’onglet wiki peut également être utilisé pour la capture d’une note et son contenu est également stocké dans le site SharePoint de l’équipe.

Nous avons également ajouté la prise en charge de la recherche dans les journaux d'audit, eDiscovery et la conservation légale pour les canaux, les conversations et les fichiers ainsi que la gestion des applications mobiles avec Microsoft Intune. Accédez au centre de sécurité & conformité d’Office 365 pour gérer ces paramètres. 

Pour en savoir plus sur la & sécurité dans Office 365, voir [configurer votre client office 365 pour renforcer la sécurité](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security) .

## <a name="auditing-and-reporting"></a>Audit et rapports

La recherche dans le journal d’audit s’ouvre directement dans la & Centre de sécurité et de conformité Office 365 et expose les capacités de définir des alertes et/ou de signaler un événement d’audit en mettant à disposition les informations d’identification et/ou de rapport sur l’événement de charge de travail d’administration barre d’audit illimitée. Toutes les données du journal d’audit sont disponibles pour la configuration des alertes dans le centre de sécurité & conformité Office 365, ainsi que pour le filtrage et l’exportation pour une analyse plus approfondie. Pour en savoir plus sur la façon d’effectuer une recherche dans le journal d’audit dans le centre de sécurité & conformité Office 365, consultez le [lien](https://support.office.com/article/Search-the-audit-log-in-the-Office-365-Security-Compliance-Center-0d4d0f35-390b-4518-800e-0c7ec95e946c) suivant. 

## <a name="compliance-content-search"></a>Recherche de contenu de conformité

La recherche de contenu peut être utilisée pour rechercher toutes les données de teams grâce à des fonctionnalités de filtrage enrichies et exportées vers un conteneur spécifique pour la prise en charge de la conformité et du litige. Cette opération peut être réalisée avec ou sans cas de découverte électronique. Cela permet aux administrateurs de la conformité de recueillir des données d’équipe auprès de tous les utilisateurs, de les réviser et de les exporter pour plus de traitement. Pour en savoir plus sur la réalisation d’une recherche de contenu de conformité pour le contenu de Microsoft teams dans le centre de sécurité & conformité Office 365, consultez le [lien](https://support.office.com/article/content-search-in-office-365-53390468-eec6-45cb-b6cd-7511f9c909e4) ci-dessous. 

Astuce: le type Microsoft teams peut être utilisé pour filtrer le contenu de Microsoft teams uniquement (par exemple, les conversations et les messages de canal, les réunions et les appels). 

## <a name="ediscovery"></a>eDiscovery

La découverte électronique représente l'aspect électronique de l'identification, la collecte et la production d'informations stockées électroniquement (ESI) en réponse à une demande dans le cadre d'une action en justice ou d'une enquête judiciaire. Les fonctionnalités incluent la gestion des cas, la conservation, la recherche, l’analyse et l’exportation des données d’équipe. Il s’agit de messages instantanés, de messages et de dossiers, de réunions et d’appels. Pour les réunions et les appels en équipe, un résumé des événements qui se sont produits lors de la réunion et de l’appel sont créés et rendus disponibles dans eDiscovery. 

Pour plus d’informations sur la façon d’effectuer une découverte électronique dans le centre de sécurité & conformité et de procéder à la recherche du contenu d’équipes, accédez aux liens ci-dessous: 

[eDiscovery](https://support.office.com/article/manage-legal-investigations-in-office-365-2e5fbe9f-ee4d-4178-8ff8-4356bc1b168e) 

[Recherche de contenu](https://support.office.com/article/search-for-content-in-office-365-df2d1e0f-b476-42c9-aade-4a260b24f193)

Les clients peuvent tirer parti d’une découverte électronique inaltérable ou [Advanced eDiscovery] selon leurshttps://support.office.com/article/Office-365-Advanced-eDiscovery-fd53438a-a760-45f6-9df4-861b50161ae4)besoins (. Le tableau suivant présente les différences entre les deux options :


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

Au cours d’un litige, il est souvent nécessaire que toutes les données associées à un utilisateur ou à une équipe soient conservées sauvegardé manière inaltérable pour pouvoir être utilisées comme preuves du cas. Pour cela, il suffit de placer un utilisateur (boîte aux lettres d’utilisateur) ou une équipe en attente de conservation légale. Lorsqu’une équipe au sein de teams est placée sur place (sous-ensemble de la boîte aux lettres ou de la collection de sites par le biais de requêtes ciblées ou de contenu filtré) ou de conservation de litige (boîte aux lettres entière ou collection de sites), la conservation est placée sur la boîte aux lettres du groupe. Ainsi, même si les utilisateurs finaux suppriment ou modifient des messages de canal qui sont intégrés à la boîte aux lettres de groupe, les copies immuables de ce contenu sont conservées et disponibles dans la recherche eDiscovery. Les conservations légales sont généralement appliquées dans le contexte d'un cas eDiscovery. Consultez [cet](https://support.office.com/article/overview-of-preservation-policies-9c3b1d52-40ce-4ba3-a520-9ae0be15538a) article d’aide pour en savoir plus sur la conservation et la conservation dans le centre de sécurité & conformité Office 365. 

## <a name="information-protection-architecture-for-microsoft-teams"></a>Architecture de protection des informations de Microsoft Teams. 

La figure suivante indique le flux de réception des données d’équipe à la fois pour les fichiers et les messages teams dans Exchange et SharePoint. 

![Diagramme du flux de travail des données d’équipes dans Exchange et SharePoint](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1.png)

La figure suivante indique le flux d’intégration des réunions teams et des données d’appel vers Exchange.

![Diagramme illustrant le flux de travail des réunions d’équipe et des données d’appel vers Exchange](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image1a.png)

> [!IMPORTANT]
> Un délai de 24 heures peut être nécessaire pour détecter du contenu d’équipes.

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
|![Icône représentant un point de décision](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image3.png)     |Point de décision         |Votre organisation dispose-t-elle des licences requises pour satisfaire les besoins en matière de sécurité et de conformité ?         |
|![Icône représentant les étapes suivantes](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image4.png)    |Étapes suivantes         |Passez en revue le contrat de licence actuel de votre organisation et confirmez qu’il remplit toutes les exigences métiers en matière de conformité et de sécurité.         |

Avant d’activer l’une de ces fonctionnalités, assurez-vous d’avoir accès au centre de sécurité & conformité dans le centre d’administration Microsoft 365. Par défaut, les administrateurs de clients y ont accès.

La recherche de contenu et eDiscovery ne nécessitent aucune activation dans le centre de sécurité & conformité.

<a name="location-of-data-in-teams"></a>Emplacement des données dans Teams
-------------------------

Les données dans Teams résident dans la région géographique associée à votre client Office 365. Actuellement, teams prend en charge l’Australie, le Canada, la France, l’Inde, le Japon, le Royaume-Uni, la Corée du Sud, l’Afrique du Sud 

> [!IMPORTANT]
> Pour le moment, les équipes disposent d’une résidence de données en Australie, au Canada, en France, en Inde, au Japon, au Royaume-Uni, en Corée du Sud et en Afrique du Sud uniquement pour les nouveaux clients. Tout client qui ne possédait pas d'utilisateur unique inscrit dans Teams est considéré comme un nouveau client. Les clients existants tirés de l’Australie, de l’Inde, du Japon et de la Corée du Sud continuent d’avoir leurs données en équipe stockées dans la région sud-est. Les clients existants au Canada continuent d’avoir leurs données stockées dans le continent américain. Les clients existants en France, au Royaume-Uni et en Afrique du Sud continuent d’avoir leurs données stockées dans la région EMEA.

Pour plus d’informations sur la résidence des données sud-africains pour Teams, reportez-vous à la publication de blog d’Varun Sagar de [Microsoft teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-South-Africa-Data-Residency/ba-p/776611).

Pour plus d’informations sur les données de résidence du sud-coréen sur les équipes sont fournies par le billet de blog d’Varun Sagar, [Microsoft teams lance la résidence des données du sud-coréen](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-South-Korea-Data-Residency/ba-p/789171).

Pour plus d'informations sur le lancement de la résidence des données de Teams au Royaume-Uni et en Inde, lisez l’article de blog d’Ansuman Acharya, [Microsoft Teams launches India Data Residency, other geos coming soon](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-Australia-and-Japan-Data-Residency/ba-p/237827) (Microsoft Teams lance la résidence des données en Inde, d’autres régions géographiques seront couvertes prochainement). 

Pour plus d’informations sur la fonction de données du Canada pour Teams, voir le billet de blog de Varun Sagar, Microsoft teams: délégation des données du Canada sur les [données, l’Australie et le Japon bientôt disponible](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-Launches-Canada-Data-Residency-Australia-and/ba-p/227178). 

Pour en savoir plus sur le lancement d’Australie et de résidence sur les données du Japon pour Teams, voir le billet de blog de Varun Sagar de [Microsoft teams](https://go.microsoft.com/fwlink/?linkid=867773). 

Pour en savoir plus sur le lancement de la résidence des données de la France pour Teams, voir le billet de blog de Varun Sagar de [Microsoft teams](https://techcommunity.microsoft.com/t5/Microsoft-Teams-Blog/Microsoft-Teams-launches-France-Data-Residency/ba-p/364466).

Pour afficher la région qui abrite les données pour votre client, accédez au**profil d’organisation****paramètres** > du centre > d' [administration 365 Microsoft](https://portal.office.com/adminportal/home). Défilez jusqu’à la section **Emplacement des données**. 

![Capture d’écran de la table d’emplacements des données, y compris équipes dans le centre d’administration](media/Overview_of_security_and_compliance_in_Microsoft_Teams_image5.png)

<a name="how-do-conditional-access-policies-work-for-teams"></a>Fonctionnement des stratégies d’accès conditionnel pour Microsoft teams
-------------------------

Microsoft teams repose essentiellement sur Exchange Online, SharePoint Online et Skype entreprise Online pour les scénarios de productivité de base, tels que les réunions, les calendriers, les discussions d’interopérabilité et le partage de fichiers. Les stratégies d’accès conditionnel définies pour ces applications Cloud s’appliquent à Microsoft teams lorsqu’un utilisateur se connecte directement à Microsoft Teams, quel que soit le client. 

Microsoft teams est pris en charge séparément en tant qu’application Cloud dans des stratégies d’accès conditionnel Azure Active Directory. Les stratégies d’accès conditionnel définies pour l’application Cloud de Microsoft teams s’appliquent à Microsoft teams lorsqu’un utilisateur se connecte. Toutefois, sans les stratégies appropriées sur d’autres applications telles qu’Exchange Online et SharePoint Online, les utilisateurs peuvent toujours accéder directement à ces ressources. Pour plus d’informations sur la configuration d’une stratégie d’accès conditionnel dans le portail Azure, voir: (https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal-get-started) 

Les clients de bureau Microsoft teams pour Windows et Mac prennent en charge l’authentification moderne. L’authentification moderne fournit la connexion en fonction de la bibliothèque d’authentification Azure Active Directory (ADAL) pour les applications clientes Microsoft Office sur différentes plateformes.

L’application de bureau Microsoft teams prend en charge AppLocker.  Pour plus d’informations sur les conditions préalables pour AppLocker, voir: configuration requise pourhttps://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/requirements-to-use-applocker)utiliser AppLocker (.

<a name="privacy-in-teams"></a>Confidentialité dans Teams
--------------------------

En tant que client Office 365, vous possédez et contrôlez vos données. Microsoft utilise vos données uniquement pour vous fournir le service auquel vous avez souscrit. En tant que fournisseur de services, nous n'analysons pas vos messages électroniques, vos documents ou vos équipes à des fins publicitaires ou non liées au service. Microsoft n'a pas accès au contenu chargé. Tout comme avec OneDrive Entreprise et SharePoint Online, les données des utilisateurs appartiennent au client.

Pour en savoir plus sur nos informations de confiance et de sécurité, consultez le centre de gestion de la [confidentialité de Microsoft](https://microsoft.com/trustcenter). Teams suit les mêmes recommandations et principes que le centre de gestion de la confidentialité Microsoft.

<a name="related-topics"></a>Voir aussi
----------------------
[Liens de sécurité Office 365 ATP](https://docs.microsoft.com/office365/securitycompliance/atp-safe-links#how-to-get-atp-safe-links-protection)
