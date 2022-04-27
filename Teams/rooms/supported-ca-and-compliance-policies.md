---
title: Stratégies d’accès conditionnel et de conformité des appareils Intune prises en charge pour Salles Microsoft Teams
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
description: Découvrez les stratégies d’accès conditionnel et de conformité Intune des appareils prises en charge et recommandées pour Salles Microsoft Teams.
ms.openlocfilehash: 19e4593a6135c79eb156a1b34847ab518d6e8ea4
ms.sourcegitcommit: bd05783dfb33a63e0eb083a2135f97d110dc81a3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/26/2022
ms.locfileid: "65059235"
---
# <a name="supported-conditional-access-and-intune-device-compliance-policies-for-microsoft-teams-rooms"></a>Stratégies d’accès conditionnel et de conformité des appareils Intune prises en charge pour Salles Microsoft Teams

Cet article fournit des stratégies d’accès conditionnel et de conformité des appareils Intune prises en charge pour Salles Microsoft Teams. Pour connaître les meilleures pratiques et les exemples de stratégies, consultez [les meilleures pratiques en matière d’accès conditionnel et de conformité Intune pour Salles Microsoft Teams](conditional-access-and-compliance-for-devices.md).

> [!NOTE]
> salles Teams doit déjà être déployé sur les appareils auxquels vous souhaitez affecter des stratégies d’accès conditionnel. Si vous n’avez pas encore déployé salles Teams, consultez [Créer des comptes de ressources pour les salles et les appareils Teams partagés](with-office-365.md) et [Déployer Salles Microsoft Teams sur Android](../devices/collab-bar-deploy.md) pour plus d’informations.

## <a name="supported-conditional-access-policies"></a>Stratégies d’accès conditionnel prises en charge  

La liste suivante inclut les stratégies d’accès conditionnel prises en charge pour les salles Teams sur Windows et sur Android. 

> [!NOTE]
> Les stratégies Android prises en charge s’appliquent à tous les appareils Android dans les espaces partagés, y compris les salles Teams sur Andourd, les téléphones de zone commune et les panneaux.

| Affectation | Windows | Android |
|------------|---------|---------|
| Identités d’utilisateur ou de charge de travail |Pris en charge | Pris en charge |
|Applications ou actions cloud | Pris en charge <br><br> salles Teams doit accéder aux trois applications cloud suivantes en mode Teams uniquement : Office 365 Exchange Online, Office 365 SharePoint Online et Microsoft Teams | Pris en charge <br><br> salles Teams doit accéder aux trois applications cloud suivantes en mode Teams uniquement : Office 365 Exchange Online, Office 365 SharePoint Online et Microsoft Teams |
|**Conditions**| --- | --- |
| Risque de l’utilisateur | Pris en charge | Pris en charge |
| Risque de connexion | Pris en charge | Pris en charge |
| Plateformes d’appareils | Pris en charge | Pris en charge |
| Emplacements | Pris en charge | Pris en charge |
|Applications clientes |Non pris en charge| Non pris en charge |
|Filtrer pour les appareils | Pris en charge | Pris en charge |
|**Subvention**| --- | --- |
| Bloquer l’accès | Pris en charge | Pris en charge |
| Accorder l’accès | Pris en charge | Pris en charge | 
| Exiger une authentification multifacteur | Non pris en charge | Non pris en charge |
| Exiger que l’appareil soit marqué comme conforme | Pris en charge | Pris en charge |
|Exiger un appareil hybride Azure AD joint | Non pris en charge | Non pris en charge |
|Exiger une application cliente approuvée | Non pris en charge | Non pris en charge |
| Exiger une stratégie de protection des applications | Non pris en charge |Non pris en charge |
| Exiger la modification du mot de passe | Non pris en charge | Non pris en charge |

> [!NOTE]
> Skype Entreprise Online est mis hors service et n’est pas pris en charge. Skype Entreprise application cloud en ligne n’est pas prise en charge pour les stratégies d’accès conditionnel basées sur la conformité des appareils.

> [!NOTE]
> Salles Microsoft Teams sur Windows doivent respecter les exigences suivantes pour prendre en charge les contrôles d’octroi de conformité des appareils :
>
> - Salles Microsoft Teams application 4.8.19.0 ou ultérieure
> - Windows 10 version 20H2 et ultérieures (10.0.19042)

## <a name="supported-device-compliance-policies"></a>Stratégies de conformité des appareils prises en charge 

Salles Microsoft Teams sur Windows et salles Teams sur Android prennent en charge différentes stratégies de conformité des appareils.

#### <a name="teams-rooms-on-windows"></a>[salles Teams sur Windows](#tab/mtr-w)

Vous trouverez ci-dessous un tableau des paramètres de conformité des appareils et des recommandations pour leur utilisation avec salles Teams.  

|Stratégie | Disponibilité | Remarques|
|---------|-------------|-------|
| [**Intégrité de l’appareil**](/mem/intune/protect/compliance-policy-create-windows%22%20/l%20%22device-health) | -- | -- |
|Exiger BitLocker| Pris en charge | Utilisez uniquement si vous avez d’abord activé BitLocker sur salles Teams. |
|Exiger l’activation du démarrage sécurisé sur l’appareil |Pris en charge |Le démarrage sécurisé est obligatoire pour salles Teams. |
|Exiger l’intégrité du code |Pris en charge  | L’intégrité du code est déjà une exigence pour salles Teams. |
| [**Propriétés de l’appareil**](/mem/intune/protect/compliance-policy-create-windows%22%20/l%20%22device-properties) | -- | -- |
|Version du système d’exploitation (minimum, maximum) |Non pris en charge | salles Teams les mises à jour automatiques des versions plus récentes de Windows et la définition de valeurs ici peuvent empêcher une connexion réussie après une mise à jour du système d’exploitation.|
|Version du système d’exploitation pour les appareils mobiles (minimum, maximum) | Non prise en charge. | N/A |
| Builds de système d’exploitation valides | Non pris en charge | N/A |
| [**conformité Configuration Manager**](/mem/intune/protect/compliance-policy-create-windows%22%20/l%20%22device-properties) | -- | -- |
| Exiger la conformité des appareils à partir de Configuration Manager | Pris en charge |  N/A |
| [**Sécurité du système**](/mem/intune/protect/compliance-policy-create-windows%22%20/l%20%22system-security) | -- | -- |
| Toutes les stratégies de mot de passe | Non pris en charge | Les stratégies de mot de passe peuvent empêcher le compte Skype local de se connecter automatiquement. |
| Exiger le chiffrement du stockage des données sur l’appareil. | Pris en charge  | Utilisez uniquement si vous avez d’abord activé le chiffrement du stockage de données sur salles Teams. |
| Pare-feu | Pris en charge | Le pare-feu est déjà obligatoire pour salles Teams |
| Module de plateforme sécurisée (TPM) | Pris en charge | Le module de plateforme sécurisée (TPM) est déjà requis pour salles Teams. |
| Antivirus | Pris en charge | L’antivirus (Windows Defender) est déjà obligatoire pour salles Teams. |
| Antispyware | Pris en charge | Antispyware (Windows Defender) est déjà une exigence pour salles Teams. |
| Logiciel anti-programme malveillant Microsoft Defender | Pris en charge | Microsoft Defender Antimalware est déjà une exigence pour salles Teams. |
| Version minimale de Microsoft Defender Antimalware | Non prise en charge. | salles Teams met automatiquement à jour ce composant de sorte qu’il n’est pas nécessaire de définir des stratégies de conformité.|
| Renseignement de sécurité microsoft Defender Antimalware
à jour | Pris en charge | Vérifiez que Microsoft Defender Antimalware est déjà une exigence pour salles Teams. |
| Protection en temps réel | Pris en charge | Les protections en temps réel sont déjà requises pour salles Teams. |
| [**Microsoft Defender pour point de terminaison**](/mem/intune/protect/compliance-policy-create-windows%22%20/l%20%22microsoft-defender-for-endpointws) | -- | -- |
| Exiger que l’appareil soit au niveau ou sous le score de risque de l’ordinateur. | Pris en charge |  N/A |

#### <a name="teams-rooms-on-android"></a>[salles Teams sur Android](#tab/mtr-a)

Vous trouverez ci-dessous un tableau des paramètres de conformité des appareils et des recommandations pour leur utilisation avec salles Teams.  

| Stratégie | Disponibilité | Remarques |
|---------|-------------|-------|
| [**Microsoft Defender pour point de terminaison**](/mem/intune/protect/compliance-policy-create-android#microsoft-defender-for-endpoint) | -- | -- |
| Exiger que l’appareil soit au niveau ou sous le score de risque de l’ordinateur | Non pris en charge |  N/A |
| [**Intégrité de l’appareil**](/mem/intune/protect/compliance-policy-create-android%22%20/l%20%22device-health) | -- | -- |
| Appareil géré avec l’administrateur d’appareil | Obligatoire | Teams la gestion des appareils Android nécessite l’activation de l’administrateur d’appareils. |
| Appareils rootés | Pris en charge |  N/A |
| Exiger que l’appareil soit au niveau ou sous le niveau de menace de l’appareil | Non pris en charge |  N/A |
| [**Google Play Protect**](/mem/intune/protect/compliance-policy-create-android#device-health) | -- | -- |
| Google Play Services est configuré | Non pris en charge | Google Play n’est pas installé sur Teams appareils Android. |
| Fournisseur de sécurité à jour | Non pris en charge | Google Play n’est pas installé sur Teams appareils Android. |
| Analyse des menaces sur les applications | Non pris en charge | Google Play n’est pas installé sur Teams appareils Android. |
| Attestation d’appareil SafetyNet | Non pris en charge | Google Play n’est pas installé sur Teams appareils Android.|
| [**Propriétés de l’appareil**](/mem/intune/protect/compliance-policy-create-android#device-properties) | -- | -- |
| Version du système d’exploitation (minimum, maximum) | Pris en charge |  N/A |
[**Sécurité du système**](/mem/intune/protect/compliance-policy-create-android#system-security) | -- | -- |
| Exiger le chiffrement du stockage des données sur l’appareil. |Pris en charge |  N/A |
[**Sécurité des appareils**](/mem/intune/protect/compliance-policy-create-android#device-security) | -- | -- |
| Bloquer des applications à partir de sources inconnues | Non pris en charge | Seuls les administrateurs Teams installent des applications ou des outils OEM |
| Portail d'entreprise intégrité du runtime d’application | Pris en charge |  N/A|
| Applications restreintes | Non pris en charge |  N/A |
| Bloquer le débogage USB sur l’appareil | Pris en charge |  N/A|
[**Tous les appareils Android*](/mem/intune/protect/compliance-policy-create-android#all-android-devices) | -- | -- |
|Nombre maximal de minutes d’inactivité avant que le mot de passe ne soit requis | Non pris en charge |  N/A |
| Exiger un mot de passe pour déverrouiller des appareils mobiles | Non pris en charge | N/A |
| [**Android 10 et versions ultérieures**](/mem/intune/protect/compliance-policy-create-android#android-10-and-later) | -- | -- |
| [**Android 9 et versions antérieures ou Samsung Knox**](/mem/intune/protect/compliance-policy-create-android#android-9-and-earlier-or-samsung-knox) | -- | -- |
|Type de mot de passe requis |Non pris en charge | N/A|

---
