---
title: Modèles d’identité et authentification
author: MSFTTracyP
ms.author: tracyp
manager: dansimp
ms.date: 09/25/2017
ms.topic: reference
ms.service: msteams
ms.reviewer: anwara
audience: admin
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
description: Learn about the different identity models in Microsoft Teams such as Cloud, Synchronized, and Federated. Also learn about multi-factor authentication.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 330a197f2e042ee8d87e294f9ff822c6bf6d5ac6
ms.sourcegitcommit: 113e3a7314505cf78da57917ff62642125fb11fd
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/14/2020
ms.locfileid: "45121564"
---
<a name="identity-models-and-authentication-in-microsoft-teams"></a>Modèles d’identité et authentification dans Microsoft Teams
==========================================

Microsoft Teams supports all the identity models that are available with Microsoft 365 and Office 365. Supported identity models include:

-   **Identité Cloud**: dans ce modèle, un utilisateur est créé et géré dans Microsoft 365 ou Office 365 et stocké dans Azure Active Directory, et le mot de passe est vérifié par Azure Active Directory.

-   **Synchronized Identity**: In this model, the user identity is managed in an on-premises server, and the accounts and password hashes are synchronized to the cloud. The user enters the same password on-premises as they do in the cloud, and at sign-in the password is verified by Azure Active Directory. This model uses the Microsoft Azure Active Directory Connect Tool.

-   **Federated Identity**: This model requires a synchronized identity with the user password is verified by the on-premises identity provider. With this model, the password hash does not need to be synchronized to Azure AD, and Active Directory Federation Services (ADFS) or a third-party identity provider is used to authenticate users against the on-premises Active Directory.

<a name="configurations"></a>Configurations
--------------

Depending on your organization's decisions of which identity model to implement and use, the implementation requirements may vary. Refer to the requirements table below to ensure that your deployment meets these prerequisites. If you have already deployed Microsoft 365 or Office 365 and have already implemented the identity and authentication method, you may skip these steps.


|Modèle d'identité |Liste de contrôle du déploiement  |Informations complémentaires  |
|---------|---------|---------|
|Tous     |<ol type="1"><li>Comparer les options de plan Microsoft 365 et Office 365 et obtenir un abonnement</li><li>Créer une organisation Microsoft 365 ou Office 365</li><li>Attribution de licences Microsoft 365 ou Office 365 au client</li><li>Configuration des domaines et des administrateurs</li><li>Instructions spécifiques au modèle d'identité</li></ol>          |<ul style="list-style-type:none"><li>[Options de plan Microsoft 365 et Office 365](https://technet.microsoft.com/library/office-365-plan-options.aspx)</li><li>[Comparer les applications 365 Microsoft pour les offres destinées aux entreprises](https://go.microsoft.com/fwlink/?linkid=854617)</li><li>[Gérer les licences d’abonnement](https://support.office.com/article/Buy-licenses-for-your-Office-365-for-business-subscription-36081d8d-b3fa-4948-8c34-e217bba825e1)</li><li>[Ajout de licences à un abonnement](https://support.office.com/article/Add-licenses-to-a-subscription-paid-for-using-a-product-key-4fb4bd7e-3920-4ce0-98fb-0c06e3fedf53)</li><li>[Configurer Microsoft 365 pour les entreprises](https://support.office.com/Article/set-up-Office-365-for-business-6a3a29a0-e616-4713-99d1-15eda62d04fa)</li><li>[Ajout d'utilisateurs et de domaines avec l'assistant de configuration](https://support.office.com/article/Add-users-and-domain-with-the-setup-wizard-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)</li><li>Remarque : Si vous avez besoin d’aide, vous pouvez obtenir de l’aide sur [le Microsoft FastTrack](https://go.microsoft.com/fwlink/?linkid=854618) .</li></ul>          |
|Identité de cloud     |<ol type="1"><li>Créer des utilisateurs à l’aide du centre d’administration Microsoft 365</li></ol>           |<ul style="list-style-type:none"><li>[Ajouter des utilisateurs individuellement ou en bloc](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec)</li></ul>         |
|Identité synchronisée     |<ol type="1"><li>Installation de Azure AD Connect</li><li>Configuration de la synchronisation de répertoires</li><li>Création d'utilisateurs à l'aide d'outils de gestion Active Directory sur site</li></ol>         |<ul style="list-style-type:none"><li>[Configurer la synchronisation d’annuaires](https://support.office.com/article/Set-up-directory-synchronization-for-Office-365-1b3b5318-6977-42ed-b5c7-96fa74b08846)</li><li>Remarque : les hachages de mot de passe doivent être synchronisés pour que Microsoft 365 et Office 365 effectuent l’authentification.</li></ul>         |
|Identité fédérée    |<ol type="1"><li>Installation de Azure AD Connect</li><li>Configuration de la synchronisation de répertoires</li><li>Installation et configuration d'un fournisseur d'identité fédérée (services ADFS recommandés)</li><li>Création d'utilisateurs à l'aide d'outils de gestion Active Directory sur site</li></ol>           |<ul style="list-style-type:none"><li>[Configurer la synchronisation d’annuaires](https://support.office.com/article/Set-up-directory-synchronization-for-Office-365-1b3b5318-6977-42ed-b5c7-96fa74b08846)</li><li>[Planification de votre déploiement AD FS](https://go.microsoft.com/fwlink/?linkid=854619)</li><li>[Liste de vérification : Déploiement de votre batterie de serveurs de fédération](https://go.microsoft.com/fwlink/?linkid=854620)</li><li>[Configuration de l'accès Extranet pour AD FS](https://go.microsoft.com/fwlink/?linkid=854621)</li><li>[Configuration d'une relation d'approbation entre AD FS et Azure AD](https://go.microsoft.com/fwlink/?linkid=854622)</li><li>[Vérification et gestion de l'authentification unique avec ADFS](https://go.microsoft.com/fwlink/?linkid=854624)</li><li>[Liste de compatibilité de fédération Azure AD](https://go.microsoft.com/fwlink/?linkid=854625)</li><li>Note : Il n'est pas nécessaire de synchroniser le hachage de mot de passe avec Azure Active Directory.</li></ul>         |

Pour plus d’informations, reportez-vous à [la rubrique choix d’un modèle de connexion](https://go.microsoft.com/fwlink/?linkid=854626) et [Présentation des modèles d’identité et des guides d’Azure Active Directory](https://support.office.com/article/Understanding-Office-365-identity-and-Azure-Active-Directory-06a189e7-5ec6-4af2-94bf-a22ea225a7a9) .


<a name="multi-factor-authentication"></a>Authentification multifacteur
----------------------------

Microsoft 365 and Office 365 plans support Multi-Factor Authentication (MFA) that increases the security of user logins to services. With MFA, users are required to acknowledge a phone call, text message, or an app notification on their smartphone after correctly entering their password. Only after this second authentication factor has been satisfied, can a user sign in.

Multi Factor authentication is supported with any Microsoft 365 or Office 365 plan that includes Microsoft Teams. The subscription plans that include Microsoft Teams are discussed later in the Licensing section below.

Once the users are enrolled for MFA, the next time a user signs in, they will see a message that asks them to set up their second authentication factor. Supported authentication methods are:


|Type de client  |Options de deuxième facteur de MFA disponibles  |Remarques  |
|---------|---------|---------|
|**Dans le cloud uniquement**     |Authentification multifacteur pour Microsoft 365 ou Office 365 <ul><li>Appel téléphonique</li><li>SMS</li><li>Notification d'application mobile</li><li>Code vérification d'application mobile</li></ul>        | |
|**Configuration hybride (modèle d'identité synchronisée ou fédérée)**     |<ul><li>Authentification multifacteur pour Microsoft 365 ou Office 365</li><li>Module MFA pour Azure (services ADFS intégrés)</li><li>Carte à puce virtuelle ou physique (services ADFS intégrés)</li></ul>         |Remarque : des solutions MFA supplémentaires sont disponibles avec les [documents de compatibilité des fournisseurs d’identité Azure ad](https://www.microsoft.com/download/details.aspx?id=56843)         |
