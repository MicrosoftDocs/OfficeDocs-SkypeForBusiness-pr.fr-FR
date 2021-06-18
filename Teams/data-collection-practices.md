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
ms.collection:
- M365-collaboration
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Legal
- seo-marvel-mar2020
hideEdit: true
description: Découvrez comment Microsoft collecte les données relatives au recensement, à l’utilisation et aux erreurs de façon à comprendre l’utilisation de Teams et de Skype Entreprise, ainsi que les problèmes liés, afin d’améliorer ces produits.
ms.openlocfilehash: b7f1f7b63645adfb0cfa0c492a680059ef383402
ms.sourcegitcommit: f5ad0fc5be7201b71da4f13586972831c9961e51
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/14/2020
ms.locfileid: "47651226"
---
# <a name="skype-for-business-and-microsoft-teams-data-collection-practices"></a>Pratiques de collecte de données Skype Entreprise et Microsoft Teams

Skype Entreprise Server et Skype Entreprise Online, ainsi que les applications Skype Entreprise et Microsoft Teams, collectent des données afin d’aider Microsoft à comprendre comment ces produits sont utilisés et quels types d’erreurs, telles que les erreurs de connexion, se produisent. Ces informations nous aident à comprendre les modèles d’utilisation, à planifier de nouvelles fonctionnalités et à résoudre les problèmes.

Si certaines données d’utilisation sont collectées automatiquement, les autres données ne peuvent être collectées que lorsque l’administrateur et/ou l’utilisateur choisissent de l’autoriser. La collecte de données se divise en trois catégories :

- Données de recensement

- Données d’utilisation

- Données de signalement d'erreurs

## <a name="census-data"></a>Données de recensement

Les données de recensement servent uniquement à fournir, prendre en charge et améliorer Skype Entreprise. Microsoft Teams et Skype Entreprise Online. Elles incluent des informations environnementales telles que les versions de système d’exploitation et d’appareil, ainsi que les paramètres régionaux et linguistiques. Elles incluent également des compteurs pour les échecs et tentatives de connexion. Voici quelques exemples spécifiques de données de recensement collectées :

|**Type de données**|**Exemple**|**Notes**|
|:-----|:-----|:-----|
|AppName  <br/> |iPhoneSkype  <br/> ||
|DeviceModel  <br/> |iPhone  <br/> ||
|OSName  <br/> |iPhoneiOS  <br/> ||
|OSVersion  <br/> |8.3  <br/> ||
|UserLanguage  <br/> |EN-US  <br/> ||
|UserID  <br/> |E296D735-4F36-4E18-7C3B-52E1A02A0164  <br/> |L’ID est haché deux fois : une fois sur le client, puis de nouveau sur le service de télémétrie. Le hachage garantit que l’ID ne peut pas être lié à un utilisateur spécifique.  <br/> |
|DeviceID  <br/> |5E872200-F546-4CCD-8F23-AF5F507AA2DD  <br/> |L’ID d’appareil est un GUID généré de façon aléatoire une fois sur l’appareil et envoyé au service de télémétrie.  <br/> |

Les données de recensement ne contiennent AUCUNE information qui identifie votre organisation ou vos utilisateurs. Pour plus d’informations, voir la [Déclaration de confidentialité Skype Entreprise](https://www.microsoft.com/privacystatement/SkypeforBusiness/Default.aspx).

Les données de recensement sont activées par défaut et ne peuvent pas être désactivées par les administrateurs ni par les utilisateurs finaux.

## <a name="usage-data"></a>Données d’utilisation

Les données d’utilisation incluent des informations telles que le nombre d’appels effectués, le nombre de messages instantanés envoyés ou reçus, le nombre de réunions auxquelles vous avez participé, la fréquence d’utilisation des fonctionnalités ainsi que les problèmes de stabilité.

Les données d’utilisation peuvent contenir des informations qui identifient votre organisation, par exemple, contoso.com. Voici quelques exemples spécifiques de données d’utilisation collectées :

|**Type de données**|**Exemple**|**Notes**|
|:-----|:-----|:-----|
|Message instantané envoyé  <br/> |12  <br/> ||
|Message instantané reçu  <br/> |5  <br/> ||
|Participation à une réunion (tentatives)  <br/> |5  <br/> ||
|Participation à une réunion (réussites)  <br/> |4  <br/> ||
|Durée de l’appel/de la réunion en minutes  <br/> |30 minutes  <br/> ||
|FederationPartner  <br/> |Microsoft.com  <br/> |Il s’agit du nom de l’organisation enregistré dans Office 365 qui est transmis en texte clair (ce qui signifie qu’il n’est pas masqué).  <br/> |

Les données d’utilisation ne contiennent AUCUNE information qui identifie les utilisateurs.

La collecte de données d’utilisation est activée par défaut, mais les administrateurs locaux peuvent la désactiver à l’aide du paramètre de stratégie de groupe DisableAutomaticSendTracing sur Skype Entreprise Server. La désactivation de ce paramètre affecte tous les utilisateurs de l’organisation. Pour plus d’informations, voir [Configuration des stratégies de démarrage de clients](/skypeforbusiness/deploy/deploy-clients/configure-client-bootstrapping-policies).

L’utilisateur final ne peut pas activer ni désactiver la collecte de données d’utilisation.

Pour les pages web du lanceur de participation et l’application Réunions Skype, le contrôle de la télémétrie se fait au moyen de cette stratégie :

`Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True`

Par défaut, cette stratégie possède la valeur false. La collecte de la télémétrie est alors désactivée par défaut. Ce paramètre s’applique par pool et contrôle tous les utilisateurs qui se connectent avec l’application Réunions Skype à une réunion hébergée sur ce serveur.

## <a name="error-reporting-data"></a>Données de signalement d'erreurs

Les données de signalement d’erreurs peuvent inclure des informations sur les performances et la fiabilité, la configuration des appareils, la qualité de la connexion réseau, les codes d’erreur, les journaux d’erreurs et les exceptions. Voici quelques exemples spécifiques de données de signalement d’erreurs collectées :

|**Type de données**|**Exemple**|**Notes**|
|:-----|:-----|:-----|
|Direction du message  <br/> |Entrant  <br/> ||
|État de la conversation  <br/> |Inactive  <br/> ||
|ID de thread de conversation  <br/> |AdDO8hsJqilU93hQHC3OZaPR2saEA==  <br/> ||
|UserID  <br/> |amosmarble <br/> |L’ID est envoyé en texte clair, que le service de télémétrie hache avant de le stocker  <br/> |

Les données de signalement d’erreurs peuvent également contenir des informations d’identification d’un utilisateur final telles que l’adresse IP de l’utilisateur et l’URI SIP (Session Initiation Protocol). Pour obtenir une explication détaillée de ce qui est collecté, voir la [Déclaration de confidentialité de Skype Entreprise](https://www.microsoft.com/privacystatement/SkypeforBusiness/Default.aspx).

Le signalement d’erreurs nécessite deux éléments :

- Le paramètre de stratégie de groupe DisableAutomaticSendTracing est défini sur false sur le serveur ou dans le centre d’administration des clients (il s’agit de l’état par défaut). Pour plus d’informations, voir [Configuration des stratégies de démarrage de clients](/skypeforbusiness/deploy/deploy-clients/configure-client-bootstrapping-policies).
    
- Les utilisateurs finaux acceptent individuellement à partir de l’onglet général (cliquez sur l’icône d’engrenage ![une icône représentant un engrenage ](media/70f1b43f-16d6-4172-9139-71d845c4ed5c.png) pour ouvrir la boîte de dialogue **Options** affichant l’onglet **Général**) dans le client Skype Entreprise.
    
 
![Capture d’écran de la case à cocher Collecte de données dans la boîte de dialogue Options](media/68bc8f77-deaa-478c-9977-a5259b88df3e.png)
  
Pour l’application Réunions Skype, MeetingUxEnableTelemetry contrôle également le signalement d’erreurs, même si pour les blocages sur Windows, les paramètres Watson contrôlent le chargement des informations sur le blocage. Il n’existe aucun paramètre d’utilisateur pour l’application Réunions Skype, comme vous pouvez le voir dans la boîte de dialogue du client de bureau.

Pour plus d’informations, voir [Définition des options générales dans Skype Entreprise](https://support.office.com/article/e1a46d3e-dcea-437a-ba7b-6d442a40f439).

Vous pouvez vous reporter à [Configurer votre réseau pour Skype Entreprise Online](https://support.office.com/article/81fa5e16-418d-4698-a5f0-e666211c5c66) pour configurer votre réseau.

Si vous utilisez Microsoft 365 ou Office 365 géré par 21Vianet en Chine, voir [Configurer votre réseau pour Skype Entreprise Online géré par 21Vianet](https://support.office.com/article/d21f89b0-3afc-432e-b735-036b2432fdbf).

## <a name="related-topics"></a>Voir aussi
[Disponibilité des forfaits d’appels et de l’audioconférence selon les régions et les pays](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
