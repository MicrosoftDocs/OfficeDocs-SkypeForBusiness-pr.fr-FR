---
title: Meilleures pratiques en matière d’accès conditionnel et de conformité pour Salles Microsoft Teams
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
description: Découvrez les stratégies de conformité des appareils et les meilleures pratiques recommandées en matière d’accès conditionnel et de Intune pour les Salles Microsoft Teams.
ms.openlocfilehash: 1221060121f47154549c6c6fc926415f4feabbe5
ms.sourcegitcommit: 726df9ecac561bda18e349a5adab9bc85e52844d
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/27/2022
ms.locfileid: "65761306"
---
# <a name="conditional-access-and-intune-compliance-for-microsoft-teams-rooms"></a>Accès conditionnel et conformité Intune pour Salles Microsoft Teams

Cet article fournit les conditions requises et les meilleures pratiques pour l’accès conditionnel et Intune stratégies de conformité des appareils pour les Salles Microsoft Teams qui sont utilisées dans les espaces partagés.

## <a name="requirements"></a>Conditions requises

salles Teams doit déjà être déployé sur les appareils auxquels vous souhaitez affecter des stratégies d’accès conditionnel. Si vous n’avez pas encore déployé salles Teams, consultez [Créer des comptes de ressources pour les salles et les appareils Teams partagés](with-office-365.md) et [Déployer Salles Microsoft Teams sur Android](../devices/collab-bar-deploy.md) pour plus d’informations.

Un Azure Active Directory plan de service P1 est nécessaire pour utiliser l’accès conditionnel. Il est inclus dans la licence Salles Microsoft Teams.

## <a name="teams-rooms-conditional-access-best-practices"></a>salles Teams meilleures pratiques en matière d’accès conditionnel

Les stratégies d’accès conditionnel peuvent sécuriser le processus de connexion sur les appareils qui se trouvent dans des espaces partagés et qui sont utilisés par plusieurs personnes. Pour obtenir une vue d’ensemble de l’accès conditionnel dans Azure Active Directory (Azure AD), consultez [Qu’est-ce que l’accès conditionnel dans Azure Active Directory ?](/azure/active-directory/conditional-access/overview).

Lorsque vous utilisez l’accès conditionnel pour sécuriser salles Teams, tenez compte des meilleures pratiques suivantes :

-   Pour simplifier le déploiement et la gestion, incluez tous les comptes de ressources de salle Microsoft 365 associés à salles Teams dans un groupe d’utilisateurs.

-   Disposez d’une norme d’affectation de noms pour tous les comptes de ressources salles Teams. Par exemple, les noms de compte « mtr-room1@contoso.com » et « mtr-room2@contoso.com » commencent tous les deux par le préfixe « mtr- ».
    Lorsque les noms de comptes sont normalisés, vous pouvez utiliser des groupes dynamiques dans Azure AD pour appliquer automatiquement des stratégies d’accès conditionnel à tous ces comptes en même temps. Pour plus d’informations sur [les groupes dynamiques, consultez Règles pour l’appartenance aux groupes dynamiquement remplis](/azure/active-directory/enterprise-users/groups-dynamic-membership) .

Pour obtenir la liste des affectations d’accès conditionnel prises en charge pour salles Teams, consultez Stratégies [d’accès conditionnel prises en charge](supported-ca-and-compliance-policies.md#supported-conditional-access-policies).

## <a name="example-conditional-access-policy"></a>Exemple de stratégie d’accès conditionnel

Dans l’exemple ci-dessous, la stratégie d’accès conditionnel fonctionne comme suit :

1.  La connexion au compte doit être membre d’un groupe d’utilisateurs spécifique, dans cet exemple, le groupe « Appareils partagés ».

2.  Le compte qui se connecte doit uniquement essayer d’accéder à Exchange Online, Microsoft Teams ou SharePoint Online. Les tentatives de connexion à n’importe quelle autre application cliente sont rejetées.

3.  Le compte de ressource doit se connecter à la plateforme d’appareil Windows.

4.  Le compte de ressource doit également se connecter à partir d’un emplacement connu et approuvé.

Si ces conditions sont remplies avec succès et que l’utilisateur entre le nom d’utilisateur et le mot de passe appropriés, le compte de ressource se connecte à Teams.

## <a name="conditional-access-with-microsoft-intune-compliance-for-teams-rooms"></a>Accès conditionnel avec conformité Microsoft Intune pour salles Teams

Les exigences de conformité sont des règles définies que les appareils doivent respecter pour être marqués comme conformes, telles que la version minimale du système d’exploitation. Les appareils doivent être considérés comme conformes avant de pouvoir être utilisés pour se connecter à un compte de ressource.

Pour obtenir la liste des stratégies de conformité Intune prises en charge pour salles Teams, consultez Stratégies [de conformité des appareils prises en charge](supported-ca-and-compliance-policies.md#supported-device-compliance-policies).

Pour plus d’informations sur la configuration de Intune avec des appareils Teams Android, consultez [Configurer les Intune pour inscrire des appareils basés sur Teams Android](../devices/phones-displays-deploy.md#configure-intune-to-enroll-teams-android-based-devices).

## <a name="example-windows-only-conditional-access-with-intune-device-compliance"></a>Exemple (Windows uniquement) : accès conditionnel avec Intune conformité de l’appareil

Dans cet exemple, pour salles Teams sur Windows

1. Exiger qu’un pare-feu s’exécute sur salles Teams sur Windows.

2. Exiger que Microsoft Defender s’exécute sur salles Teams.

3. Si une Teams Room ne répond à aucune de ces exigences, elle n’est pas marquée comme conforme et les appareils ne se connectent pas.

Cette stratégie de conformité s’applique à tous les utilisateurs, et pas seulement aux comptes de ressources Teams.
