---
title: Stratégies de conformité des appareils Et Accès conditionnel pris en charge pour les Salles Microsoft Teams
ms.author: czawideh
author: cazawideh
ms.reviewer: kspiess
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
description: Découvrez les stratégies d’accès conditionnel et de conformité aux appareils Intune pris en charge et recommandées pour Salles Microsoft Teams.
ms.openlocfilehash: ea27f71a7d4f64bc1d9e8c8a3cd3d7b2a52151f3
ms.sourcegitcommit: ecc67b7b9378cc72f85517f30c32680045056fda
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2022
ms.locfileid: "64504194"
---
# <a name="supported-conditional-access-and-intune-device-compliance-policies-for-microsoft-teams-rooms"></a>Stratégies de conformité des appareils Et Accès conditionnel pris en charge pour les Salles Microsoft Teams

Cet article fournit des stratégies de conformité aux appareils Intune et Accès conditionnel pris en charge pour Salles Microsoft Teams. Pour consulter des pratiques et des exemples de stratégies, voir Les meilleures pratiques en matière de [conformité avec Intune et Accès conditionnel pour Salles Microsoft Teams](conditional-access-and-compliance-for-devices.md).

> [!NOTE]
> salles Teams les stratégies d’accès conditionnel doivent déjà être déployées sur les appareils à qui vous voulez affecter des stratégies d’accès conditionnel. Si vous n’avez pas encore déployé de salles Teams, consultez Créer des comptes de ressources pour des salles, des appareils [Teams partagés](with-office-365.md) et Déployer Salles Microsoft Teams [sur Android](../devices/collab-bar-deploy.md) pour plus d’informations.

## <a name="supported-conditional-access-policies"></a>Stratégies d’accès conditionnel pris en charge  

La liste suivante présente les stratégies d’accès conditionnel pris en charge pour salles Teams sur Windows sur Android. Les stratégies Android pris en charge s’appliquent à tous les appareils, téléphones et panneaux Android.

| Affectation | Windows | Android |
|------------|---------|---------|
| Identités des utilisateurs ou des charges de travail |Pris en charge | Pris en charge |
|Actions ou applications cloud | Pris en charge <br><br> salles Teams a besoin d’accéder aux trois applications cloud suivantes en mode Teams uniquement : Office 365 Exchange Online, Office 365 SharePoint Online et Microsoft Teams | Pris en charge <br><br> salles Teams a besoin d’accéder aux trois applications cloud suivantes en mode Teams uniquement : Office 365 Exchange Online, Office 365 SharePoint Online et Microsoft Teams |
|**Conditions**| --- | --- |
| Risque pour les utilisateurs | Pris en charge | Pris en charge |
| Risque de sign-in | Pris en charge | Pris en charge |
| Plateformes d’appareil | Pris en charge | Pris en charge |
| Emplacements | Pris en charge | Pris en charge |
|Applications clientes |Non pris en charge| Non pris en charge |
|Filtrer les appareils | Pris en charge | Pris en charge |
|**Grant**| --- | --- |
| Bloquer l’accès | Pris en charge | Pris en charge |
| Accorder l’accès | Pris en charge | Pris en charge | 
| Exiger l’authentification multifacteur | Non pris en charge | Non pris en charge |
| Exiger que l’appareil soit marqué comme conforme | Pris en charge | Pris en charge |
|Exiger l’Azure AD un appareil joint | Non pris en charge | Non pris en charge |
|Exiger l’approbation d’une application cliente | Non pris en charge | Non pris en charge |
| Exiger une stratégie de protection des applications | Non pris en charge |Non pris en charge |
| Exiger la modification du mot de passe | Non pris en charge | Non pris en charge |

> [!NOTE]
> Skype Entreprise Online est retiré et n’est pas pris en charge. Skype Entreprise’application cloud en ligne n’est pas prise en charge pour les stratégies d’accès conditionnel basées sur la conformité des appareils.

> [!NOTE]
> Salles Microsoft Teams sur Windows devez répondre aux exigences suivantes pour prendre en charge les contrôles d’octroi de conformité des appareils :
>
> - Salles Microsoft Teams application 4.8.19.0 ou supérieure
> - Windows 10 version 20H2 et supérieures (10.0.19042)

## <a name="supported-device-compliance-policies"></a>Stratégies de conformité des appareils prise en charge 

Salles Microsoft Teams sur Windows et salles Teams Sur Android supportent différentes stratégies de conformité des appareils.

#### <a name="teams-rooms-on-windows"></a>[salles Teams sur Windows](#tab/mtr-w)

Vous trouverez ci-dessous un tableau des paramètres de conformité des appareils et des recommandations pour leur utilisation avec salles Teams.  

|Stratégie | Disponibilité | Remarques|
|---------|-------------|-------|
| [**État des appareils**](/mem/intune/protect/compliance-policy-create-windows%22%20/l%20%22device-health) | -- | -- |
|Require BitLocker| Pris en charge | Uniquement si vous avez activé BitLocker sur salles Teams. |
|Exiger le démarrage sécurisé pour être activé sur l’appareil |Pris en charge |Le démarrage sécurisé est obligatoire pour les salles Teams. |
|Exiger l’intégrité du code |Pris en charge  | L’intégrité du code est déjà requise pour salles Teams. |
| [**Propriétés de l’appareil**](/mem/intune/protect/compliance-policy-create-windows%22%20/l%20%22device-properties) | -- | -- |
|Version du système d’exploitation (minimum, maximum) |Non pris en charge | salles Teams mises à jour automatiques des versions plus récentes de Windows et de définition des valeurs ici pouvaient empêcher la réussite de la se connecte après une mise à jour du système d’exploitation.|
|Version du système d’exploitation pour les appareils mobiles (minimum, maximum) | Non prise en charge. | N/A |
| Builds de système d’exploitation valides | Non pris en charge | N/A |
| [**Conformité de Configuration Manager**](/mem/intune/protect/compliance-policy-create-windows%22%20/l%20%22device-properties) | -- | -- |
| Exiger la conformité des appareils auprès de Configuration Manager | Pris en charge |  N/A |
| [**Sécurité du système**](/mem/intune/protect/compliance-policy-create-windows%22%20/l%20%22system-security) | -- | -- |
| Toutes les stratégies de mot de passe | Non pris en charge | Les stratégies de mot de passe peuvent empêcher le Skype utilisateur local de se signer automatiquement. |
| Exiger le chiffrement de l’espace de stockage des données sur l’appareil. | Pris en charge  | Uniquement à utiliser si vous avez activé pour la première fois le chiffrement du stockage de données sur salles Teams. |
| Pare-feu | Pris en charge | Le pare-feu est déjà une obligation pour les salles Teams |
| Module de plateforme approuvé (TPM) | Pris en charge | Le module de plateforme approuvé (TPM) est déjà une obligation pour salles Teams. |
| Antivirus | Pris en charge | L’antivirus (Windows Defender) est déjà une obligation pour la salles Teams. |
| Antispyware | Pris en charge | Les logiciels anti-programme malveillant (Windows Defender) sont déjà une obligation pour les salles Teams. |
| Microsoft Defender Antimalware | Pris en charge | Microsoft Defender Anti-programme malveillant est déjà une obligation pour les salles Teams. |
| Version minimale de Microsoft Defender Antimalware | Non prise en charge. | salles Teams mise à jour automatique de ce composant pour vous inutile de définir des stratégies de conformité.|
| Veille de sécurité Microsoft Defender Anti-programme malveillant
à jour | Pris en charge | Vérifier que Microsoft Defender Antimalware est déjà une obligation pour les salles Teams. |
| Protection en temps réel | Pris en charge | Les protections en temps réel sont déjà obligatoires pour salles Teams. |
| [**Microsoft Defender pour Endpoint**](/mem/intune/protect/compliance-policy-create-windows%22%20/l%20%22microsoft-defender-for-endpointws) | -- | -- |
| Exiger que l’appareil soit au niveau ou en dessous du score de risque de l’ordinateur. | Pris en charge |  N/A |

#### <a name="teams-rooms-on-android"></a>[salles Teams sur Android](#tab/mtr-a)

Vous trouverez ci-dessous un tableau des paramètres de conformité des appareils et des recommandations pour leur utilisation avec salles Teams.  

| Stratégie | Disponibilité | Remarques |
|---------|-------------|-------|
| [**Microsoft Defender pour Endpoint**](/mem/intune/protect/compliance-policy-create-android#microsoft-defender-for-endpoint) | -- | -- |
| Exiger que l’appareil soit au niveau ou en dessous du score de risque de l’ordinateur | Non pris en charge |  N/A |
| [**État des appareils**](/mem/intune/protect/compliance-policy-create-android%22%20/l%20%22device-health) | -- | -- |
| Appareil géré avec l’administrateur d’appareil | Non prise en charge. | Teams appareils Android sont gérés avec l’appareil
administrateur. |
| Appareils racines | Pris en charge |  N/A |
| Exiger que l’appareil soit au niveau de menace de l’appareil ou en dessous | Non pris en charge |  N/A |
| [**Google Play Protect**](/mem/intune/protect/compliance-policy-create-android#device-health) | -- | -- |
| Google Play Services est configuré | Non pris en charge | Google Play n’est pas installé sur Teams appareils Android. |
| Fournisseur de sécurité à jour | Non pris en charge | Google Play n’est pas installé sur Teams appareils Android. |
| Analyse des menaces sur les applications | Non pris en charge | Google Play n’est pas installé sur Teams appareils Android. |
| SafetyNet devices | Non pris en charge | Google Play n’est pas installé sur Teams appareils Android.|
| [**Propriétés de l’appareil**](/mem/intune/protect/compliance-policy-create-android#device-properties) | -- | -- |
| Version du système d’exploitation (minimum, maximum) | Pris en charge |  N/A |
[**Sécurité du système**](/mem/intune/protect/compliance-policy-create-android#system-security) | -- | -- |
| Exiger le chiffrement de l’espace de stockage des données sur l’appareil. |Pris en charge |  N/A |
[**Sécurité des appareils**](/mem/intune/protect/compliance-policy-create-android#device-security) | -- | -- |
| Bloquer les applications provenant de sources inconnues | Non pris en charge | Seuls Teams les administrateurs installent des applications ou des outils OEM |
| Portail d'entreprise’intégrité runtime de l’application | Pris en charge |  N/A|
| Applications restreintes | Non pris en charge |  N/A |
| Bloquer le débogage USB sur l’appareil | Pris en charge |  N/A|
[**Tous les appareils Android*](/mem/intune/protect/compliance-policy-create-android#all-android-devices) | -- | -- |
|Nombre maximal de minutes d’inactivité avant l’utilisation du mot de passe | Non pris en charge |  N/A |
| Demander un mot de passe pour déverrouiller des appareils mobiles | Non pris en charge | N/A |
| [**Android 10 et version ultérieure**](/mem/intune/protect/compliance-policy-create-android#android-10-and-later) | -- | -- |
| [**Android 9 et version antérieure ou Samsung Knox**](/mem/intune/protect/compliance-policy-create-android#android-9-and-earlier-or-samsung-knox) | -- | -- |
|Type de mot de passe requis |Non pris en charge | N/A|

---
