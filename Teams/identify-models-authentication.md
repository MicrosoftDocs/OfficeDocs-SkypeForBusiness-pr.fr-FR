---
title: Modèles d’identité et authentification pour Microsoft teams
author: MSFTTracyP
ms.author: tracyp
manager: dansimp
ms.date: 09/25/2020
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
description: Découvrez les différents modèles d’identité de Microsoft Teams, tels que Cloud-only et hybride. En savoir plus sur l’authentification multifacteur.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 40a06ce75c3ae7a4f85eb1c93064ba3d80c13fc0
ms.sourcegitcommit: a28232f16bfefe6414d1f5a54d5f8c8665eb0e23
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/25/2020
ms.locfileid: "48277114"
---
# <a name="identity-models-and-authentication-for-microsoft-teams"></a>Modèles d’identité et authentification pour Microsoft teams

Microsoft teams prend en charge tous les modèles d’identité disponibles avec Microsoft 365 et Office 365, notamment :

- **Cloud-only**: les comptes d’utilisateurs sont créés et gérés dans Microsoft 365 ou Office 365 et stockés dans Azure Active Directory (Azure AD). Les informations d’identification de l’utilisateur (nom du compte et mot de passe) sont validées par Azure AD.

- **Hybride**: les comptes d’utilisateurs sont généralement gérés dans une forêt AD DS (Active Directory Domain Services) locale. En fonction de la configuration, il est possible de valider les informations d’identification à l’aide d’Azure AD, de AD DS ou d’un fournisseur d’identité fédéré. Ce modèle utilise la synchronisation d’annuaires entre les services de domaine Active Directory et Azure AD.

Pour plus d’informations, reportez-vous à la rubrique [modèles d’identité Microsoft 365 et Azure ad](https://docs.microsoft.com/microsoft-365/enterprise/about-microsoft-365-identity).

## <a name="configurations"></a>Configurations

En fonction des décisions de votre organisation relatives au modèle d’identité et à la configuration que vous utilisez, les étapes d’implémentation peuvent varier.

Si vous n’avez pas encore déployé Microsoft 365 ou Office 365 et un modèle d’identité, utilisez ce tableau. 

|Modèle d'identité |Liste de contrôle du déploiement  |Informations supplémentaires  |
|---------|---------|---------|
|Tout     |<ol type="1"><li>Comparez les options de plan Microsoft 365 et Office 365 et obtenez un abonnement et un client.</li><li>Créez une organisation Microsoft 365 ou Office 365 pour votre client.</li><li>Acheter des licences Microsoft 365 ou Office 365 pour le client</li><li>Configurer les comptes d’utilisateurs et les domaines.</li></ol>  |<ul><li>[Options de plan dans Office 365](https://technet.microsoft.com/library/office-365-plan-options.aspx)</li><li>[Comparer les offres Microsoft 365 pour les entreprises](https://go.microsoft.com/fwlink/?linkid=854617)</li><li>[Acheter ou supprimer des licences d’abonnement](https://support.office.com/article/Buy-licenses-for-your-Office-365-for-business-subscription-36081d8d-b3fa-4948-8c34-e217bba825e1)</li><li>[Ajout de licences à un abonnement](https://support.office.com/article/Add-licenses-to-a-subscription-paid-for-using-a-product-key-4fb4bd7e-3920-4ce0-98fb-0c06e3fedf53)</li><li>[Configurer Microsoft 365 pour les entreprises](https://support.office.com/Article/set-up-Office-365-for-business-6a3a29a0-e616-4713-99d1-15eda62d04fa)</li><li>[Ajouter un domaine à l’aide de l’Assistant Configuration](https://support.office.com/article/Add-users-and-domain-with-the-setup-wizard-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)</li></ul><br>[Microsoft FastTrack](https://www.microsoft.com/fasttrack/microsoft-365) est disponible pour vous aider.  |
|Identité Cloud     |<ul><li>Créer des comptes d’utilisateurs à l’aide du centre d’administration 365 Microsoft</li></ul> |<ul style="list-style-type:none"><li>[Ajouter des utilisateurs et attribuer des licences](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec)</li></ul> |
|Identité hybride     |<ol type="1"><li>Installez Azure AD Connect.</li><li>Configurer la synchronisation d’annuaires.</li><li>Gérer les utilisateurs et les groupes avec les outils AD DS.</li></ol> |<ul style="list-style-type:none"><li>[Configurer la synchronisation d’annuaires](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization)</li></ul> |
|Identité hybride avec authentification fédérée    |<ol type="1"><li>Installez et configurez un fournisseur d’identité fédéré tel qu’AD FS.</li><li>Installez Azure AD Connect et configurez la synchronisation d’annuaires et l’authentification fédérée.</li><li>Gérer les utilisateurs et les groupes avec les outils AD DS.</li></ol> |<ul><li>[Planification de votre déploiement AD FS](https://go.microsoft.com/fwlink/?linkid=854619)</li><li>[Liste de vérification : Déploiement de votre batterie de serveurs de fédération](https://go.microsoft.com/fwlink/?linkid=854620)</li><li>[Configuration de l'accès Extranet pour AD FS](https://go.microsoft.com/fwlink/?linkid=854621)</li><li>[Configuration d'une relation d'approbation entre AD FS et Azure AD](https://go.microsoft.com/fwlink/?linkid=854622)</li><li>[Vérification et gestion de l'authentification unique avec ADFS](https://go.microsoft.com/fwlink/?linkid=854624)</li><li>[Configurer la synchronisation d’annuaires](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization)</li></ul> |
||||

## <a name="multi-factor-authentication"></a>Authentification multifacteur

Les mots de passe sont la méthode d’authentification la plus courante pour la connexion à un ordinateur ou un service en ligne, mais qui sont également les plus vulnérables. Les utilisateurs peuvent choisir des mots de passe simples et utiliser le même mot de passe pour plusieurs connexions sur des ordinateurs et services différents. 

Pour fournir un niveau de sécurité supplémentaire pour les connexions, utilisez l’authentification multifacteur (MFA), qui nécessite un mot de passe et une méthode de vérification supplémentaire telle que :

- Un message texte envoyé à un téléphone qui demande à l’utilisateur de taper un code de vérification.
- Un appel téléphonique.
- Application de téléphone intelligent Microsoft Authenticator.
- D’autres méthodes d’identité et d’authentification hybrides sont disponibles.

MFA est pris en charge avec n’importe quel plan Microsoft 365 ou Office 365 incluant Microsoft Teams. Il est vivement recommandé d’utiliser une authentification multifacteur pour les comptes auxquels des [rôles d’administrateur sont attribués](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide), tels que l’administrateur de service Teams.

Vous devez également déployer l’authentification multifacteur pour les utilisateurs. Lorsque vos utilisateurs sont inscrits pour l’authentification multifacteur, lors de leur connexion suivante, ils verront un message leur demandant de définir leur méthode de vérification supplémentaire. 

Pour plus d’informations, reportez-vous à la rubrique [authentification multifacteur pour Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/multi-factor-authentication-microsoft-365).
