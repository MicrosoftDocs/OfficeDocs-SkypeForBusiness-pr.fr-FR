---
title: Modèles d’identité et authentification
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: reference
ms.service: msteams
ms.reviewer: anach
audience: admin
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
description: Découvrez les différents modèles d'identité dans Microsoft Teams tels que Identité de cloud, Identité synchronisée, et Identité fédérée. Ce document contient également des informations sur l'authentification multifacteur.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 1ccddd3bacdd495fb6febb11871d6d501f0a666b
ms.sourcegitcommit: 3323c86f31c5ab304944a34892601fcc7b448025
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/09/2020
ms.locfileid: "44637203"
---
<a name="identity-models-and-authentication-in-microsoft-teams"></a>Modèles d’identité et authentification dans Microsoft Teams
==========================================

Microsoft teams prend en charge tous les modèles d’identité disponibles avec Microsoft 365 et Office 365. Les modèles d’identité pris en charge sont les suivants :

-   **Identité Cloud**: dans ce modèle, un utilisateur est créé et géré dans Microsoft 365 ou Office 365 et stocké dans Azure Active Directory, et le mot de passe est vérifié par Azure Active Directory.

-   **Identité synchronisée** : Dans ce modèle, l'identité de l'utilisateur est gérée sur un serveur sur site, et les hachages de compte et mot de passe sont synchronisés dans le cloud. L'utilisateur saisit le même mot de passe sur site que celui du cloud, et lors de la connexion, le mot de passe est vérifié par Azure Active Directory. Ce modèle utilise l'outil Azure Active Directory Connect de Microsoft.

-   **Identité fédérée** : Ce modèle requiert une identité synchronisée et le mot de passe utilisateur est vérifié par le fournisseur d'identité sur site. Avec ce modèle, il n'est pas nécessaire de synchroniser le hachage de mot de passe avec Azure AD, et les services ADSF (Active Directory Federation Services) ou un fournisseur d'identité tiers sont utilisés pour authentifier les utilisateurs au niveau de Active Directory sur site.

<a name="configurations"></a>Configurations
--------------

En fonction des décisions de votre organisation relatives au modèle d’identité à implémenter et à utiliser, les exigences en matière d’implémentation peuvent varier. Référez-vous au tableau exigences ci-dessous pour vous assurer que votre déploiement répond aux conditions préalables suivantes. Si vous avez déjà déployé Microsoft 365 ou Office 365 et avez déjà implémenté la méthode d’identité et d’authentification, vous pouvez ignorer ces étapes.


|Modèle d'identité |Liste de contrôle du déploiement  |Informations complémentaires  |
|---------|---------|---------|
|Tous     |<ol type="1"><li>Comparer les options de plan Microsoft 365 et Office 365 et obtenir un abonnement</li><li>Créer une organisation Microsoft 365 ou Office 365</li><li>Attribution de licences Microsoft 365 ou Office 365 au client</li><li>Configuration des domaines et des administrateurs</li><li>Instructions spécifiques au modèle d'identité</li></ol>          |<ul style="list-style-type:none"><li>[Options de plan Microsoft 365 et Office 365](https://technet.microsoft.com/library/office-365-plan-options.aspx)</li><li>[Comparer les applications 365 Microsoft pour les offres destinées aux entreprises](https://go.microsoft.com/fwlink/?linkid=854617)</li><li>[Gérer les licences d’abonnement](https://support.office.com/article/Buy-licenses-for-your-Office-365-for-business-subscription-36081d8d-b3fa-4948-8c34-e217bba825e1)</li><li>[Ajout de licences à un abonnement](https://support.office.com/article/Add-licenses-to-a-subscription-paid-for-using-a-product-key-4fb4bd7e-3920-4ce0-98fb-0c06e3fedf53)</li><li>[Configurer Microsoft 365 pour les entreprises](https://support.office.com/Article/set-up-Office-365-for-business-6a3a29a0-e616-4713-99d1-15eda62d04fa)</li><li>[Ajout d'utilisateurs et de domaines avec l'assistant de configuration](https://support.office.com/article/Add-users-and-domain-with-the-setup-wizard-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)</li><li>Remarque : Si vous avez besoin d’aide, vous pouvez obtenir de l’aide sur [le Microsoft FastTrack](https://go.microsoft.com/fwlink/?linkid=854618) .</li></ul>          |
|Identité de cloud     |<ol type="1"><li>Créer des utilisateurs à l’aide du centre d’administration Microsoft 365</li></ol>           |<ul style="list-style-type:none"><li>[Ajouter des utilisateurs individuellement ou en bloc](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec)</li></ul>         |
|Identité synchronisée     |<ol type="1"><li>Installation de Azure AD Connect</li><li>Configuration de la synchronisation de répertoires</li><li>Création d'utilisateurs à l'aide d'outils de gestion Active Directory sur site</li></ol>         |<ul style="list-style-type:none"><li>[Configurer la synchronisation d’annuaires](https://support.office.com/article/Set-up-directory-synchronization-for-Office-365-1b3b5318-6977-42ed-b5c7-96fa74b08846)</li><li>Remarque : les hachages de mot de passe doivent être synchronisés pour que Microsoft 365 et Office 365 effectuent l’authentification.</li></ul>         |
|Identité fédérée    |<ol type="1"><li>Installation de Azure AD Connect</li><li>Configuration de la synchronisation de répertoires</li><li>Installation et configuration d'un fournisseur d'identité fédérée (services ADFS recommandés)</li><li>Création d'utilisateurs à l'aide d'outils de gestion Active Directory sur site</li></ol>           |<ul style="list-style-type:none"><li>[Configurer la synchronisation d’annuaires](https://support.office.com/article/Set-up-directory-synchronization-for-Office-365-1b3b5318-6977-42ed-b5c7-96fa74b08846)</li><li>[Planification de votre déploiement AD FS](https://go.microsoft.com/fwlink/?linkid=854619)</li><li>[Liste de vérification : Déploiement de votre batterie de serveurs de fédération](https://go.microsoft.com/fwlink/?linkid=854620)</li><li>[Configuration de l'accès Extranet pour AD FS](https://go.microsoft.com/fwlink/?linkid=854621)</li><li>[Configuration d'une relation d'approbation entre AD FS et Azure AD](https://go.microsoft.com/fwlink/?linkid=854622)</li><li>[Vérification et gestion de l'authentification unique avec ADFS](https://go.microsoft.com/fwlink/?linkid=854624)</li><li>[Liste de compatibilité de fédération Azure AD](https://go.microsoft.com/fwlink/?linkid=854625)</li><li>Note : Il n'est pas nécessaire de synchroniser le hachage de mot de passe avec Azure Active Directory.</li></ul>         |

Pour plus d’informations, reportez-vous à [la rubrique choix d’un modèle de connexion](https://go.microsoft.com/fwlink/?linkid=854626) et [Présentation des modèles d’identité et des guides d’Azure Active Directory](https://support.office.com/article/Understanding-Office-365-identity-and-Azure-Active-Directory-06a189e7-5ec6-4af2-94bf-a22ea225a7a9) .

<a name="multi-factor-authentication"></a>Authentification multifacteur
----------------------------

Les offres Microsoft 365 et Office 365 prennent en charge l’authentification multifacteur (MFA) qui renforce la sécurité des connexions utilisateur aux services. Avec l’authentification multifacteur, les utilisateurs doivent accuser réception d’un appel téléphonique, d’un SMS ou d’une notification d’application sur son smartphone après avoir entré correctement son mot de passe. Un utilisateur ne peut se connecter qu’après avoir satisfait ce deuxième facteur d’authentification.

L’authentification multifacteur est prise en charge avec n’importe quel plan Microsoft 365 ou Office 365 incluant Microsoft Teams. Les offres d’abonnement qui incluent Microsoft teams sont décrites plus loin dans la section gestion des licences ci-dessous.

Lorsque les utilisateurs sont inscrits pour l’authentification multifacteur, la prochaine fois qu’un utilisateur se connecte, il verra un message lui demandant de configurer son deuxième facteur d’authentification. Les méthodes d’authentification prises en charge sont les suivantes :


|Type de client  |Options de deuxième facteur de MFA disponibles  |Remarques  |
|---------|---------|---------|
|**Dans le cloud uniquement**     |Authentification multifacteur pour Microsoft 365 et Office 365 <ul><li>Appel téléphonique</li><li>SMS</li><li>Notification d'application mobile</li><li>Code vérification d'application mobile</li></ul>        |[Plan pour l’authentification multifacteur pour les déploiements de Microsoft 365](https://support.office.com/article/Plan-for-multi-factor-authentication-for-Office-365-Deployments-043807b2-21db-4d5c-b430-c8a6dee0e6ba)         |
|**Configuration hybride (modèle d'identité synchronisée ou fédérée)**     |<ul><li>Authentification multifacteur pour Microsoft 365 et Office 365</li><li>Module MFA pour Azure (services ADFS intégrés)</li><li>Carte à puce virtuelle ou physique (services ADFS intégrés)</li></ul>         |Remarque : des solutions MFA supplémentaires sont disponibles avec les [documents de compatibilité des fournisseurs d’identité Azure ad](https://www.microsoft.com/download/details.aspx?id=56843)         |
