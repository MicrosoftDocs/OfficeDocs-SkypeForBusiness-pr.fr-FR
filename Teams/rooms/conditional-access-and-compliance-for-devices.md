---
title: Meilleures pratiques en matière d’accès conditionnel et de conformité Salles Microsoft Teams
ms.author: czawideh
author: cazawideh
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
description: Découvrez les stratégies d’accès conditionnel et de conformité des appareils Intune recommandées, ainsi que les meilleures pratiques Salles Microsoft Teams.
ms.openlocfilehash: 1f4bec9d47b73be1638b1740afeb879b4dfb4026
ms.sourcegitcommit: dafe48cea1643e1bd79390482da9b002d7e9e0bb
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/16/2022
ms.locfileid: "63689141"
---
# <a name="conditional-access-and-intune-compliance-for-microsoft-teams-rooms"></a>Accès conditionnel et conformité Intune pour les Salles Microsoft Teams

Cet article présente les exigences et les meilleures pratiques en matière d’accès conditionnel et de stratégies de conformité des appareils Intune pour les Salles Microsoft Teams qui sont utilisés dans les espaces partagés.

## <a name="requirements"></a>Conditions requises

salles Teams les stratégies d’accès conditionnel doivent déjà être déployées sur les appareils à qui vous voulez affecter des stratégies d’accès conditionnel. Si vous n’avez pas encore déployé de salles Teams, consultez Créer des comptes de ressources pour des salles, des appareils [Teams partagés](with-office-365.md) et Déployer Salles Microsoft Teams [sur Android](../devices/collab-bar-deploy.md) pour plus d’informations.

Un plan Azure Active Directory service P1 est nécessaire pour utiliser l’accès conditionnel. Elle est incluse dans la licence Salles Microsoft Teams licence.

## <a name="teams-rooms-conditional-access-best-practices"></a>salles Teams meilleures pratiques pour l’accès conditionnel

Les stratégies d’accès conditionnel peuvent sécuriser le processus de inscription sur les appareils qui se trouveraient dans des espaces partagés et utilisés par plusieurs personnes. Pour une vue d’ensemble de l’accès conditionnel dans Azure Active Directory (Azure AD), voir [Qu’est-ce](/azure/active-directory/conditional-access/overview) que l’accès conditionnel Azure Active Directory ?.

Lors de l’utilisation de l’accès conditionnel pour salles Teams données sécurisées, prenons en compte les meilleures pratiques suivantes :

-   Pour simplifier le déploiement et la gestion, incluez tous les Microsoft 365 de ressources de salle associés à salles Teams un seul groupe d’utilisateurs.

-   Avoir une norme d’affectation de noms pour tous salles Teams ressources. Par exemple, les noms de compte « mtr-room1@contoso.com » et « mtr-room2@contoso.com » commencent tous deux par le préfixe « mtr- ».
    Lorsque les noms de compte sont standardisés, vous pouvez utiliser des groupes dynamiques dans Azure AD pour appliquer automatiquement des stratégies d’accès conditionnel à tous ces comptes en même temps. Pour [plus d’informations sur les groupes dynamiques](/azure/active-directory/enterprise-users/groups-dynamic-membership) , voir Règles pour l’appartenance aux groupes de manière dynamique.

Pour obtenir la liste des affectations d’accès conditionnel pour des salles Teams, voir Stratégies [d’accès conditionnel pris en charge](supported-ca-and-compliance-policies.md#supported-conditional-access-policies).

## <a name="example-conditional-access-policy"></a>Exemple de stratégie d’accès conditionnel

Dans l’exemple ci-dessous, la stratégie Accès conditionnel fonctionne comme suit :

1.  Le compte connecté doit être membre d’un groupe d’utilisateurs spécifique ( dans cet exemple, le groupe « Appareils partagés ».

2.  La signature du compte doit uniquement essayer d’accéder à Exchange Online, Microsoft Teams, ou SharePoint Online. Les tentatives de vous connectez à une autre application cliente seront refusées.

3.  Le compte de ressource doit se trouver sur la plateforme Windows appareil mobile.

4.  Le compte de ressource doit également se connecter à partir d’un emplacement connu et approuvé.

Si ces conditions sont remplies correctement et que l’utilisateur entre le nom d’utilisateur et le mot de passe corrects, le compte de ressource se connecte Teams.

## <a name="conditional-access-with-microsoft-intune-compliance-for-teams-rooms"></a>Accès conditionnel avec Microsoft Intune conformité conditionnelle pour les salles Teams

Les exigences de conformité sont des règles définies que les appareils doivent respecter pour être marquées comme conformes, telles que la version minimale du système d’exploitation. Les appareils doivent être considérés comme conformes pour pouvoir être utilisés pour se connecter à un compte de ressource.

Pour obtenir la liste des stratégies de conformité Intune pris en charge pour salles Teams, voir [Stratégies de conformité des appareils pris en charge](supported-ca-and-compliance-policies.md#supported-device-compliance-policies).

Pour plus d’informations sur la configuration d’Intune avec Teams appareils Android, voir Configurer [Intune pour Teams appareils Android](../devices/phones-displays-deploy.md#configure-intune-to-enroll-teams-android-based-devices).

## <a name="example-windows-only-conditional-access-with-intune-device-compliance"></a>Exemple (Windows uniquement) : Accès conditionnel avec la conformité des appareils Intune

Dans cet exemple, pour salles Teams sur Windows

1. Exiger qu’un pare-feu soit en cours d’salles Teams sur Windows.

2. Exiger que Microsoft Defender soit en cours d’exécution salles Teams.

3. Si une salle Teams ne respecte aucune de ces exigences, elle n’est pas marquée comme conforme et les appareils ne se connectent pas.

Cette stratégie de conformité s’applique à tous les utilisateurs, et Teams comptes de ressources.
