---
title: Modèles d’identité et authentification dans Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: reference
ms.service: msteams
ms.reviewer: anach
localization_priority: Normal
search.appverid: MET150
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
description: Découvrez les différents modèles d'identité dans Microsoft Teams tels que Identité de cloud, Identité synchronisée, et Identité fédérée. Ce document contient également des informations sur l'authentification multifacteur.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 34e70313d83bfa7873e990a2d77bc165dfd8dfbe
ms.sourcegitcommit: 3014331fff89a0842c4db0b9adf0ef32f9728ade
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/15/2019
ms.locfileid: "30640721"
---
<a name="identity-models-and-authentication-in-microsoft-teams"></a>Modèles d’identité et authentification dans Microsoft Teams
==========================================

Microsoft Teams prend en charge tous les modèles d'identité disponibles avec Office 365. Les modèles d'identité pris en charge sont les suivants :

-   **Identité de cloud** : Dans ce modèle, un utilisateur est créé et géré dans Office 365 et stocké dans Azure Active Directory, et le mot de passe est vérifié par Azure Active Directory.

-   **Identité synchronisée** : Dans ce modèle, l'identité de l'utilisateur est gérée sur un serveur sur site, et les hachages de compte et mot de passe sont synchronisés dans le cloud. L'utilisateur saisit le même mot de passe sur site que celui du cloud, et lors de la connexion, le mot de passe est vérifié par Azure Active Directory. Ce modèle utilise l'outil Azure Active Directory Connect de Microsoft.

-   **Identité fédérée** : Ce modèle requiert une identité synchronisée et le mot de passe utilisateur est vérifié par le fournisseur d'identité sur site. Avec ce modèle, il n'est pas nécessaire de synchroniser le hachage de mot de passe avec Azure AD, et les services ADSF (Active Directory Federation Services) ou un fournisseur d'identité tiers sont utilisés pour authentifier les utilisateurs au niveau de Active Directory sur site.

<a name="configurations"></a>Configurations
--------------

En fonction des décisions de votre organisation concernant l'implémentation et l'utilisation du modèle d'identité, la configuration requise peut varier. Consultez le tableau des configurations requises ci-après pour vous assurer que votre déploiement respecte ces conditions. Si vous avez déjà déployé Office 365 et implémenté la méthode d'identité et d'authentification, vous pouvez ignorer ces étapes.


|Modèle d'identité |Liste de contrôle du déploiement  |Informations complémentaires  |
|---------|---------|---------|
|Tous     |<ol type="1"><li>Comparaison des options de plan Office 365 et obtention d'un abonnement</li><li>Création d'un client Office 365</li><li>Affectation de licences Office 365 au client</li><li>Configuration des domaines et des administrateurs</li><li>Instructions spécifiques au modèle d'identité</li></ol>          |<ul style="list-style-type:none"><li>[Options de plan Office 365](https://technet.microsoft.com/library/office-365-plan-options.aspx)</li><li>[Comparaison des plans Office 365 Business](https://go.microsoft.com/fwlink/?linkid=854617)</li><li>[Achat de licences pour votre abonnement Office 365 Business](https://support.office.com/article/Buy-licenses-for-your-Office-365-for-business-subscription-36081d8d-b3fa-4948-8c34-e217bba825e1)</li><li>[Ajout de licences à un abonnement](https://support.office.com/article/Add-licenses-to-a-subscription-paid-for-using-a-product-key-4fb4bd7e-3920-4ce0-98fb-0c06e3fedf53)</li><li>[Configuration de Office 365 Business](https://support.office.com/Article/set-up-Office-365-for-business-6a3a29a0-e616-4713-99d1-15eda62d04fa)</li><li>[Ajout d'utilisateurs et de domaines avec l'assistant de configuration](https://support.office.com/article/Add-users-and-domain-with-the-setup-wizard-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)</li><li>Note : Si vous avez besoin d'aide, l'[équipe Microsoft FastTrack pour Office 365](https://go.microsoft.com/fwlink/?linkid=854618) est disponible.</li></ul>          |
|Identité de cloud     |<ol type="1"><li>Création d'utilisateurs à l'aide du Portail d'administration Office 365</li></ol>           |<ul style="list-style-type:none"><li>[Ajout d'utilisateurs individuellement ou en bloc dans Office 365](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec)</li></ul>         |
|Identité synchronisée     |<ol type="1"><li>Installation de Azure AD Connect</li><li>Configuration de la synchronisation de répertoires</li><li>Création d'utilisateurs à l'aide d'outils de gestion Active Directory sur site</li></ol>         |<ul style="list-style-type:none"><li>[Configuration de la synchronisation de répertoires pour Office 365](https://support.office.com/article/Set-up-directory-synchronization-for-Office-365-1b3b5318-6977-42ed-b5c7-96fa74b08846)</li><li>Note : Les hachages de mot de passe doivent être synchronisés pour Office 365 pour effectuer l'authentification.</li></ul>         |
|Identité fédérée    |<ol type="1"><li>Installation de Azure AD Connect</li><li>Configuration de la synchronisation de répertoires</li><li>Installation et configuration d'un fournisseur d'identité fédérée (services ADFS recommandés)</li><li>Création d'utilisateurs à l'aide d'outils de gestion Active Directory sur site</li></ol>           |<ul style="list-style-type:none"><li>[Configuration de la synchronisation de répertoires pour Office 365](https://support.office.com/article/Set-up-directory-synchronization-for-Office-365-1b3b5318-6977-42ed-b5c7-96fa74b08846)</li><li>[Planification de votre déploiement AD FS](https://go.microsoft.com/fwlink/?linkid=854619)</li><li>[Liste de vérification : Déploiement de votre batterie de serveurs de fédération](https://go.microsoft.com/fwlink/?linkid=854620)</li><li>[Configuration de l'accès Extranet pour AD FS](https://go.microsoft.com/fwlink/?linkid=854621)</li><li>[Configuration d'une relation d'approbation entre AD FS et Azure AD](https://go.microsoft.com/fwlink/?linkid=854622)</li><li>[Vérification et gestion de l'authentification unique avec ADFS](https://go.microsoft.com/fwlink/?linkid=854624)</li><li>[Liste de compatibilité de fédération Azure AD](https://go.microsoft.com/fwlink/?linkid=854625)</li><li>Note : Il n'est pas nécessaire de synchroniser le hachage de mot de passe avec Azure Active Directory.</li></ul>         |

Reportez-vous aux guides [Choosing a sign-in model for Office 365 (Sélection d'un modèle d'authentification pour Office 365)](https://go.microsoft.com/fwlink/?linkid=854626) et [Présentation de l'identité Office 365 et d'Azure Active Directory](https://support.office.com/article/Understanding-Office-365-identity-and-Azure-Active-Directory-06a189e7-5ec6-4af2-94bf-a22ea225a7a9) pour plus d'informations.

<a name="multi-factor-authentication"></a>Authentification multifacteur
----------------------------

Les plans Office 365 prennent en charge l'authentification multifacteur (MFA) qui renforce la sécurité des connexions des utilisateurs aux services Office 365. Avec la MFA pour Office 365, les  utilisateurs doivent confirmer un appel téléphonique, un SMS ou une notification d'application sur leur smartphone après avoir saisi leur mot de passe. Ils pourront se connecter uniquement après avoir rempli ce second facteur d'authentification.

Authentification à plusieurs facteurs est pris en charge avec n’importe quel plan Office 365 qui inclut Microsoft Teams. Les plans d’abonnement Office 365 comprenant Microsoft Teams présentés plus loin dans la section Gestion des licences ci-dessous.

Une fois les utilisateurs inscrits pour la MFA, lors de leur prochaine connexion, un message les invitera à configurer leur deuxième facteur d'authentification. Méthodes d'authentification prises en charge :


|Type de client  |Options de deuxième facteur de MFA disponibles  |Remarques  |
|---------|---------|---------|
|**Dans le cloud uniquement**     |MFA pour Office 365 <ul><li>Appel téléphonique</li><li>SMS</li><li>Notification d'application mobile</li><li>Code vérification d'application mobile</li></ul>        |[Planification de l'authentification multifacteur pour les déploiements Office 365](https://support.office.com/article/Plan-for-multi-factor-authentication-for-Office-365-Deployments-043807b2-21db-4d5c-b430-c8a6dee0e6ba)         |
|**Configuration hybride (modèle d'identité synchronisée ou fédérée)**     |<ul><li>MFA pour Office 365</li><li>Module MFA pour Azure (services ADFS intégrés)</li><li>Carte à puce virtuelle ou physique (services ADFS intégrés)</li></ul>         |Note : D'autres solutions MFA sont disponibles auprès des [fournisseurs d'identité compatibles avec la fédération Azure AD](https://go.microsoft.com/fwlink/p/?LinkId=510953)         |
