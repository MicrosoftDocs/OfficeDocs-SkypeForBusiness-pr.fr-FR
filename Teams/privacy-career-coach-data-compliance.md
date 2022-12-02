---
title: Données et informations de conformité de Career Coach
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: ''
search.appverid: MET150
f1keywords: ''
description: Découvrez les mesures de confidentialité, de conformité et de contrôle prises par Microsoft en ce qui concerne l’éducation ou l’coach de carrière de l’ÉDUCATION.
appliesto:
- Microsoft Teams
ms.localizationpriority: high
ms.openlocfilehash: 1a21f3337ca9255572c25fd152f928c6444dc317
ms.sourcegitcommit: aef1ab47fb9cb4502cb49bc3c7ffafcd62e54c82
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/02/2022
ms.locfileid: "69242488"
---
# <a name="career-coach-data-and-compliance"></a>Conformité et données Career Coach

Cet article explique comment utiliser les fonctionnalités intégrées à l’application ainsi que d’autres outils pour vous aider à rechercher et à agir sur des données personnelles ou des informations personnelles pour répondre à la demande de la personne concernée (DSR) conformément à vos obligations rgpd. Career Coach classifie largement les données en deux catégories : le contenu client et les journaux générés par le système. Dans Career Coach, le contenu client inclut des données utilisateur, des données de configuration de locataire et des données d’activité des étudiants, tandis que les journaux générés par le système incluent des journaux et des données associées générées par Microsoft qui aident Microsoft fournir des services d’entreprise aux utilisateurs.

## <a name="customer-content"></a>Contenu client

### <a name="user-data"></a>Données utilisateur

Les données utilisateur collectées par Career Coach incluent des informations de profil telles que la progression des objectifs et des activités, le domaine d’études, l’année scolaire, les compétences enregistrées, les carrières enregistrées, les CV téléchargés et les relevés de notes.

#### <a name="deleting-user-data"></a>Suppression des données utilisateur

Procédez comme suit pour supprimer les données utilisateur de Career Coach :

1. Un administrateur général doit [ouvrir un ticket](https://edusupport.microsoft.com/support?product_id=career_coach) de support qui indique clairement la demande d’une opération de suppression DSR (demandes de la personne concernée) de suppression RGPD. ** Il n’est pas possible de limiter le jeu de données ou la fenêtre de temps de la suppression**.
2. La requête doit indiquer clairement le type de données qui doivent être supprimées :
    1. Toutes les données utilisateur du locataire.
    2. Données utilisateur pour un utilisateur spécifique. Incluez l’OID (identificateurs d’objet) de l’utilisateur dans le cadre de la demande de suppression.
3. Une fois déposé, le ticket de support sera traité après une semaine pour respecter la stratégie de rétention minimale de la conformité. Vous pouvez annuler l’opération pendant cette période.
4. Après une semaine, l’équipe Career Coach supprime toutes les données relatives au locataire. Microsoft support surveille le ticket et vous avertit une fois le processus de suppression terminé **, dans un délai de 30 jours** maximum.

#### <a name="exporting-user-data"></a>Exportation de données utilisateur

Procédez comme suit pour exporter des données utilisateur à partir de Career Coach :

1. [Ouvrir l’assistant carrière](https://aka.ms/Career_Coach_App)  et affichez votre profil.
1. Faites défiler jusqu’à la section Confidentialité et sécurité.
1. Sélectionnez « Télécharger » pour exporter toutes les données client de votre compte.

### <a name="tenant-configuration-data"></a>Données de configuration du locataire

Les données client incluent des informations chargées ou générées dans le cadre de la configuration de l’application Career Coach. Ces données incluent les informations de marque d’un locataire, le logo et l’icône d’apprentissage, le catalogue de cours, l’URL LinkedIn de l’établissement scolaire, la liste des champs d’étude et toutes les autres données ajoutées lors de la configuration du locataire Career Coach dans le Centre d’administration Teams.

#### <a name="deleting-tenant-configuration-data"></a>Suppression des données de configuration de locataire

Procédez comme suit pour supprimer les données de configuration de locataire de Career Coach :

1. Un administrateur général doit [ouvrir un ticket de support](https://edusupport.microsoft.com/support?product_id=career_coach) indiquant clairement la demande de suppression des données de configuration de votre locataire.  **Il n’est pas possible de limiter le jeu de données ou la fenêtre de temps de la suppression**.
1. Une fois déposé, le ticket de support sera traité après une semaine pour respecter la stratégie de rétention minimale de la conformité. Vous pouvez annuler l’opération pendant cette période.
1. Après une semaine, l’équipe Career Coach supprime toutes les données relatives au locataire. Microsoft support surveille le ticket et vous avertit une fois le processus de suppression terminé **, dans un délai de 30 jours** maximum.

### <a name="student-activity-data"></a>Données d’activité des étudiants

Career Coach stocke les données d’activité des étudiants au même emplacement que  [Éducation Insights](class-insights.md). Les données agrégées sont exposées dans l’expérience d’informations sur l’activité des étudiants Career Coach. Les données d’utilisation des étudiants capturées pour alimenter cette fonctionnalité sont stockées et conservées pendant un an.

#### <a name="deleting-student-activity-data"></a>Suppression des données d’activité des étudiants

Pour supprimer les données d’activité des étudiants d’un individu ou d’un locataire, suivez les étapes décrites dans [Comment supprimer des données utilisateur d’Insights Éducation](class-insights.md#how-to-delete-user-data-from-education-insights).

## <a name="system-generated-logs"></a>Journaux générés par le système

Les journaux générés par le système incluent des journaux et des données associées générées par Microsoft qui aident Microsoft fournir des services d’entreprise aux utilisateurs. Les journaux générés par le système contiennent principalement des données pseudonymes, telles que des identificateurs uniques (généralement un nombre généré par le système) qui ne peuvent pas identifier une personne individuelle, mais sont utilisés pour fournir les services d’entreprise aux utilisateurs. Voici quelques exemples de ces données :

- Données d’utilisation des produits et des services, telles que les journaux d’activité des utilisateurs.
- Demandes de recherche utilisateur et données de requête.
- Données générées par les produits et services en tant que produit de la fonctionnalité système et de l’interaction des utilisateurs ou d’autres systèmes.

> [!NOTE]
> La possibilité de restreindre ou de rectifier les données dans les journaux générés par le système n’est pas prise en charge. Les données des journaux générés par le système constituent des actions factuelles effectuées dans le Microsoft données cloud et de diagnostic, et les modifications apportées à ces données compromettraient l’historique des actions et augmenteraient les risques de fraude et de sécurité. Career Coach conserve les journaux générés par le système pendant 30 jours.

### <a name="exporting-and-deleting-system-generated-logs"></a>Exportation et suppression des journaux générés par le système

L’administrateur général du locataire est la seule personne au sein de votre organisation qui peut accéder aux journaux générés par le système associés à l’utilisation par un utilisateur particulier des services et applications Office 365. Career Coach s’aligne sur [le processus d’accès et d’exportation des journaux générés par le système fournis par Office 365](/compliance/regulatory/gdpr-dsr-Office365#accessing-and-exporting-system-generated-logs).

## <a name="more-information"></a>Plus d’informations

- [Prise en main de Career Coach pour Microsoft Teams](career-coach.md)
- [Questions fréquentes (FAQ) sur la confidentialité](https://privacy.microsoft.com/faq)
- [Microsoft produits et vos données - Microsoft Confidentialité](https://privacy.microsoft.com/privacy-in-our-products)
- [Paramètres de confidentialité du compte Microsoft](https://account.microsoft.com/account/privacy?refd=privacy.microsoft.com&ru=https%3A%2F%2Faccount.microsoft.com%2Fprivacy%2F%3Frefd%3Dprivacy.microsoft.com&destrt=privacy-dashboard)
