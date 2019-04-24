---
title: Pratiques de collecte de données
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, allancar
ms.topic: reference
ms.assetid: c17e8ea6-b83b-4345-9401-47a6c8b13aad
ms.tgt.pltfrm: cloud
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Legal
hideEdit: true
description: Microsoft collecte des données de recensement, d’utilisation et d’erreur pour comprendre comment Skype pour les entreprises est utilisé et où les utilisateurs rencontrent des problèmes. Les données sont utilisées pour planifier les améliorations de produit.
ms.openlocfilehash: 2e9845a9b9ebb294d0d7af1af87fae3165244889
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32218053"
---
# <a name="skype-for-business-and-microsoft-teams-data-collection-practices"></a>Skype pour les pratiques de collection de données métiers et Microsoft Teams

Skype pour Business Server et Skype pour Business Online, ainsi que Skype pour les applications métiers et Microsoft Teams, collecter des données pour permettre à Microsoft de comprendre comment ces produits sont utilisés et les types d’erreurs, telles que des erreurs de connexion, se sont produites. Ces informations nous aident à comprendre les modèles d’utilisation, planifier des nouvelles fonctionnalités et résoudre les problèmes et corriger les problèmes.

Alors que l’utilisation des données collectées automatiquement, autres données ne peuvent être générées lorsque l’administrateur et/ou l’utilisateur choisit pour lui permettre de. Collecte de données se divise en trois catégories :

- Données recensement

- Données d’utilisation

- Données de signalement d’erreurs

## <a name="census-data"></a>Données recensement

Données recensement sont acquise uniquement pour fournir, prennent en charge et améliorer Skype pour les entreprises. Les équipes Microsoft et Skype pour les entreprises en ligne. Il inclut des informations environnementales telles que les versions de périphériques et le système d’exploitation et paramètres régionaux et linguistiques. Il inclut également les compteurs de tentatives de connexion et des échecs. Voici quelques exemples des données recueillies recensement spécifiques :

|**Type de données**|**Exemple**|**Remarques**|
|:-----|:-----|:-----|
|AppName  <br/> |iPhoneSkype  <br/> ||
|DeviceModel  <br/> |iPhone  <br/> ||
|OSName  <br/> |iPhoneiOS  <br/> ||
|OSVersion  <br/> |8.3  <br/> ||
|UserLanguage  <br/> |EN-US  <br/> ||
|Nom d’utilisateur  <br/> |E296D735-4F36-4E18-7C3B-52E1A02A0164  <br/> |L’ID est hacher deux fois : une fois sur le client et à nouveau sur le service de télémétrie. Le hachage garantit QU'ID ne peut pas être liée à un utilisateur spécifique.  <br/> |
|ID de périphérique  <br/> |5E872200-F546-4CCD-8F23-AF5F507AA2DD  <br/> |L’ID de périphérique est un GUID qui a généré une seule fois sur l’appareil et envoyées au service de télémétrie de manière aléatoire.  <br/> |

Ne prend pas les données de recensement contiennent des informations qui identifie votre organisation ou des utilisateurs. Voir la [Skype pour la déclaration de confidentialité d’entreprise](https://www.microsoft.com/privacystatement/SkypeforBusiness/Default.aspx) pour plus d’informations.

Données de recensement sont activée par défaut et ne peuvent pas être désactivées par les administrateurs ou les utilisateurs finaux.

## <a name="usage-data"></a>Données d’utilisation

Les données d’utilisation contient des informations telles que le nombre d’appels effectués, nombre de messages instantanés envoyés ou reçus, nombre de réunions lié, fréquence des fonctionnalités et des problèmes de stabilité.

Les données d’utilisation peuvent contenir des informations qui identifient votre organisation, par exemple contoso.com. Voici quelques exemples spécifiques des données d’utilisation collectées :

|**Type de données**|**Exemple**|**Remarques**|
|:-----|:-----|:-----|
|Messages instantanés envoyés  <br/> |12  <br/> ||
|Message instantané reçu  <br/> |5  <br/> ||
|Participer à une réunion (tentatives)  <br/> |5  <br/> ||
|Participer à une réunion (succès)  <br/> |4  <br/> ||
|Appel/compte-rendu  <br/> |30 minutes  <br/> ||
|FederationPartner  <br/> |Microsoft.com  <br/> |Ceci est le nom de l’organisation enregistrée dans Office 365 et est transmis en texte clair, ce qui signifie qu’il n’est pas obscurcie.  <br/> |

Ne prend pas les données d’utilisation contiennent des informations qui identifie les utilisateurs.

Collecte des données d’utilisation est activée par défaut, mais administrateurs peuvent désactiver utilisant le paramètre de stratégie de groupe DisableAutomaticSendTracing sur Skype pour Business Server local. Désactivation de ce paramètre affecte tous les utilisateurs dans l’organisation. Pour plus d’informations, voir [configuration de stratégies de démarrage du client](/skypeforbusiness/deploy/deploy-clients/configure-client-bootstrapping-policies) .

Les utilisateurs finaux ne peuvent pas activer la collecte de données ou désactiver.

Pour application de réunions Skype et le Lanceur participer à des pages web, la manière de contrôler la télémétrie est par le biais de cette stratégie :

`Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True`

Cette stratégie par défaut est false, afin que la collection de télémétrie est désactivée par défaut. Ce paramètre est par pool et aux contrôles de tous les utilisateurs qui se connectent avec Skype réunions App à une conférence hébergée sur ce serveur.

## <a name="error-reporting-data"></a>Données de signalement d’erreurs

Données de création de rapports d’erreur peuvent inclure des informations sur les performances et la fiabilité, configuration du périphérique, qualité de la connexion réseau, les codes d’erreur, journaux d’erreurs et exceptions. Voici quelques exemples de données recueillies de signalement d’erreurs spécifiques :

|**Type de données**|**Exemple**|**Remarques**|
|:-----|:-----|:-----|
|Direction du message  <br/> |Entrant  <br/> ||
|État de la conversation  <br/> |Inactif  <br/> ||
|ID de thread de conversation  <br/> |AdDO8hsJqilU93hQHC3OZaPR2saEA ==  <br/> ||
|Nom d’utilisateur  <br/> |amosmarble <br/> |L’ID est envoyé en texte clair, lequel le service de télémétrie hachages avant de les stocker  <br/> |

Données de création de rapports d’erreur peuvent également contenir des informations d’identification personnelle comme adresse IP et Session Initiation Protocol Uniform Resource Identifier (URI SIP) de l’utilisateur. Voir la [Skype pour la déclaration de confidentialité d’entreprise](https://www.microsoft.com/privacystatement/SkypeforBusiness/Default.aspx) pour une explication détaillée de la collecte des éléments.

Rapport d’erreurs nécessite deux éléments :

- Le paramètre de stratégie de groupe DisableAutomaticSendTracing est défini sur False sur le serveur ou dans le centre d’administration de client (il s’agit de l’état par défaut). Pour plus d’informations, voir [configuration de stratégies de démarrage du client](/skypeforbusiness/deploy/deploy-clients/configure-client-bootstrapping-policies) .
    
- Les utilisateurs finaux participer individuellement à partir de l’onglet Général (cliquez sur l’icône d’engrenage ![icône d’engrenage](media/70f1b43f-16d6-4172-9139-71d845c4ed5c.png) et ouvre la boîte de dialogue **Options** avec l’onglet **Général** ) dans le Skype pour client d’entreprise.
    
 
![Skype pour case collection des données métiers dans la boîte de dialogue Options > général](media/68bc8f77-deaa-478c-9977-a5259b88df3e.png)
  
Pour l’application de réunions Skype, le MeetingUxEnableTelemetry contrôle signale les erreurs, bien que pour se bloque dans Windows, les paramètres Watson contrôlent téléchargement info incident. Il n’existe aucun paramètre d’utilisateur pour l’application de réunions Skype que vous voyez dans la boîte de dialogue client de bureau.

Pour plus d’informations, voir [les options général défini dans Skype pour les entreprises](https://support.office.com/article/e1a46d3e-dcea-437a-ba7b-6d442a40f439) .

Vous pouvez voir [votre réseau de Skype pour Business Online](https://support.office.com/article/81fa5e16-418d-4698-a5f0-e666211c5c66) pour configurer votre réseau.

Si vous utilisez Office 365 exécuté par 21Vianet en Chine, voir [configurer votre réseau pour Skype pour Business Online exécuté par 21Vianet](https://support.office.com/article/d21f89b0-3afc-432e-b735-036b2432fdbf).

## <a name="related-topics"></a>Voir aussi
[Le programme d’amélioration du produit](https://www.microsoft.com/products/ceip/default.mspx)

[Disponibilité des offres d'appels et d'audioconférence selon les régions et les pays](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
