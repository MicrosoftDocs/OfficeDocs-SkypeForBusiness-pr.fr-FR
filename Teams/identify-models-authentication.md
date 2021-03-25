---
title: Modèles d’identité et authentification pour Microsoft Teams
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
description: Découvrez les différents modèles d’identité pour Microsoft Teams, tels que le cloud uniquement et l’hybride. En savoir plus sur l’authentification multifacteur.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: dff34a6a56294c8c62295e143f753777875bfbda
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51112360"
---
# <a name="identity-models-and-authentication-for-microsoft-teams"></a>Modèles d’identité et authentification pour Microsoft Teams

Microsoft Teams prend en charge tous les modèles d’identité disponibles avec Microsoft 365 et Office 365, notamment :

- **Cloud uniquement**: les comptes d’utilisateurs sont créés et gérés dans Microsoft 365 ou Office 365, et stockés dans Azure Active Directory (Azure AD). Les informations d’identification de connexion des utilisateurs (nom de compte et mot de passe) sont validées par Azure AD.

- **Hybride**: les comptes d’utilisateurs sont généralement gérés dans une forêt des services de domaine Active Directory (AD DS) en local. Selon la configuration, la validation des informations d’identification peut être effectuée par Azure AD, AD DS ou un fournisseur d’identité fédéré. Ce modèle utilise la synchronisation d’annuaires entre AD DS et Azure AD avec Azure AD Connect.

Pour plus d’informations, voir [les modèles d’identité Microsoft 365 et Azure AD.](/microsoft-365/enterprise/about-microsoft-365-identity)

## <a name="configurations"></a>Configurations

En fonction des décisions de votre organisation concernant le modèle d’identité et la configuration que vous utilisez, les étapes d’implémentation peuvent varier.

Si vous n’avez pas encore déployé Microsoft 365 ou Office 365 et un modèle d’identité, utilisez ce tableau. 

|Modèle d'identité |Liste de contrôle du déploiement  |Informations supplémentaires  |
|---------|---------|---------|
|Tout     |<ol type="1"><li>Comparez les options de l’offre Microsoft 365 et Office 365 et obtenez un abonnement et un client.</li><li>Créez une organisation Microsoft 365 ou Office 365 pour votre client.</li><li>Acheter des licences Microsoft 365 ou Office 365 pour le client</li><li>Configurez des domaines et des comptes d’utilisateurs d’administrateur.</li></ol>  |<ul><li>[Options de l’offre Office 365](/office365/servicedescriptions/office-365-platform-service-description/office-365-plan-options)</li><li>[Comparer les plans Microsoft 365 pour les entreprises](https://go.microsoft.com/fwlink/?linkid=854617)</li><li>[Acheter ou supprimer des licences d’abonnement](https://support.office.com/article/Buy-licenses-for-your-Office-365-for-business-subscription-36081d8d-b3fa-4948-8c34-e217bba825e1)</li><li>[Ajout de licences à un abonnement](https://support.office.com/article/Add-licenses-to-a-subscription-paid-for-using-a-product-key-4fb4bd7e-3920-4ce0-98fb-0c06e3fedf53)</li><li>[Configurer Microsoft 365 Entreprise](https://support.office.com/Article/set-up-Office-365-for-business-6a3a29a0-e616-4713-99d1-15eda62d04fa)</li><li>[Ajouter un domaine à l’aide de l’Assistant Configuration](https://support.office.com/article/Add-users-and-domain-with-the-setup-wizard-6383f56d-3d09-4dcb-9b41-b5f5a5efd611)</li></ul><br>[Microsoft FastTrack](https://www.microsoft.com/fasttrack/microsoft-365) est disponible pour vous aider.  |
|Identité de cloud     |<ul><li>Créer des comptes d’utilisateurs avec le Centre d’administration Microsoft 365</li></ul> |<ul style="list-style-type:none"><li>[Ajouter des utilisateurs et attribuer des licences](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec)</li></ul> |
|Identité hybride     |<ol type="1"><li>Installez Azure AD Connect.</li><li>Configurez la synchronisation d’annuaires.</li><li>Gérez les utilisateurs et les groupes à l’aide d’outils AD DS.</li></ol> |<ul style="list-style-type:none"><li>[Configurer la synchronisation d’annuaires](/microsoft-365/enterprise/set-up-directory-synchronization)</li></ul> |
|Identité hybride avec authentification fédérée    |<ol type="1"><li>Installez et configurez un fournisseur d’identité fédéré tel qu’AD FS.</li><li>Installez Azure AD Connect et configurez la synchronisation d’annuaires et l’authentification fédérée.</li><li>Gérez les utilisateurs et les groupes à l’aide d’outils AD DS.</li></ol> |<ul><li>[Planification de votre déploiement AD FS](/previous-versions/azure/azure-services/dn151324(v=azure.100))</li><li>[Liste de vérification : Déploiement de votre batterie de serveurs de fédération](/previous-versions/azure/azure-services/dn528856(v=azure.100))</li><li>[Configuration de l'accès Extranet pour AD FS](/previous-versions/azure/azure-services/dn528859(v=azure.100))</li><li>[Configuration d'une relation d'approbation entre AD FS et Azure AD](/previous-versions/azure/azure-services/jj205461(v=azure.100))</li><li>[Vérification et gestion de l'authentification unique avec ADFS](/previous-versions/azure/azure-services/jj151809(v=azure.100))</li><li>[Configurer la synchronisation d’annuaires](/microsoft-365/enterprise/set-up-directory-synchronization)</li></ul> |
||||

## <a name="multi-factor-authentication"></a>Authentification multifacteur

Les mots de passe sont la méthode d’authentification la plus courante pour la signature à un ordinateur ou un service en ligne, mais ils sont également les plus vulnérables. Les utilisateurs peuvent choisir des mots de passe faciles et utiliser les mêmes mots de passe pour plusieurs se connectant à différents ordinateurs et services. 

Pour fournir un niveau supplémentaire de sécurité pour les sign-ins, utilisez l’authentification multifacteur (MFA), qui nécessite à la fois un mot de passe et une méthode de vérification supplémentaire telle que :

- Message texte envoyé à un téléphone nécessitant que l’utilisateur tape un code de vérification.
- Appel téléphonique.
- Application pour smartphone Microsoft Authenticator.
- Autres méthodes disponibles avec l’identité hybride et l’authentification fédérée.

L' assurance mfa est prise en charge avec n’importe quelle offre Microsoft 365 ou Office 365 qui inclut Microsoft Teams. Il est vivement recommandé d’avoir besoin d’une [](/microsoft-365/admin/add-users/about-admin-roles?view=o365-worldwide)salaire (MFA) pour les comptes à qui sont attribués des rôles d’administrateur, tels que l’administrateur du service Teams.

Vous devez également déployer l’fafa pour vos utilisateurs. Lorsque vos utilisateurs seront inscrits à l’és mfa, la prochaine fois qu’ils se connectent, ils s’afficheront un message leur demande de configurer leur méthode de vérification supplémentaire. 

Pour plus d’informations, [voir Authentification multifacteur pour Microsoft 365.](/microsoft-365/admin/security-and-compliance/multi-factor-authentication-microsoft-365)