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
description: Découvrez comment Microsoft collecte des données de recensement, d’utilisation et d’erreur pour comprendre les activités des équipes et les problèmes liés à l’utilisation de Skype entreprise pour planifier des améliorations du produit.
ms.openlocfilehash: a7bc6066304bfc8d221678f0c37b484e602d1bbd
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/03/2020
ms.locfileid: "43137354"
---
# <a name="skype-for-business-and-microsoft-teams-data-collection-practices"></a>Pratiques de collecte de données Skype entreprise et Microsoft teams

Skype entreprise Server et Skype entreprise Online, de même que les applications Skype entreprise et Microsoft Teams, recueillez des données pour aider Microsoft à comprendre la façon dont ces produits sont utilisés et les types d’erreur, tels que les erreurs de connexion, qui se sont produites. Ces informations nous aident à comprendre les modèles d’utilisation, à planifier de nouvelles fonctionnalités et à résoudre les problèmes liés aux problèmes.

Lorsque certaines données d’utilisation sont collectées automatiquement, les autres données peuvent uniquement être collectées lorsque l’administrateur et/ou l’utilisateur choisit de l’autoriser. La collecte des données appartient aux trois catégories suivantes :

- Données de recensement

- Données d’utilisation

- Données du rapport d’erreurs

## <a name="census-data"></a>Données de recensement

Les données de recensement sont acquises uniquement pour fournir, soutenir et améliorer Skype entreprise. Microsoft teams et Skype entreprise online. Il inclut des informations sur l’environnement telles que les versions de périphériques et de systèmes d’exploitation, ainsi que les paramètres régionaux et linguistiques. Il inclut également des compteurs pour les tentatives de connexion et les échecs. Voici quelques exemples spécifiques des données de recensement collectées :

|**Type de données**|**Exemple**|**Remarques**|
|:-----|:-----|:-----|
|Nomapp  <br/> |iPhone Skype  <br/> ||
|Modèle  <br/> |iPhone  <br/> ||
|OSName  <br/> |iPhone iOS  <br/> ||
|OSVersion  <br/> |8,3  <br/> ||
|UserLanguage  <br/> |FR-FR  <br/> ||
|UserID  <br/> |E296D735-4F36-4E18-7C3B-52E1A02A0164  <br/> |L’ID est haché deux fois : une fois sur le client et de nouveau sur le service de télémétrie. Le hachage vérifie que l’ID ne peut pas être lié à un utilisateur spécifique.  <br/> |
|DeviceID  <br/> |5E872200-F546-4CCD-8F23-AF5F507AA2DD  <br/> |L’ID d’appareil est un GUID généré de façon aléatoire une fois sur l’appareil et envoyé vers le service de télémétrie.  <br/> |

Les données de recensement ne contiennent aucune information identifiant votre organisation ou vos utilisateurs. Pour plus d’informations, consultez la [déclaration de confidentialité de Skype entreprise](https://www.microsoft.com/privacystatement/SkypeforBusiness/Default.aspx) .

Les données de recensement sont activées par défaut et ne peuvent pas être désactivées par les administrateurs ou les utilisateurs finaux.

## <a name="usage-data"></a>Données d’utilisation

Les données d’utilisation incluent des informations telles que le nombre d’appels passés, le nombre de messages instantanés envoyés ou reçus, le nombre de réunions jointes, la fréquence des fonctionnalités utilisées et les problèmes de stabilité.

Les données d’utilisation peuvent contenir des informations identifiant votre organisation, telles que contoso.com. Voici quelques exemples spécifiques des données d’utilisation collectées :

|**Type de données**|**Exemple**|**Remarques**|
|:-----|:-----|:-----|
|Messages instantanés envoyés  <br/> |midi  <br/> ||
|Messages instantanés reçus  <br/> |5  <br/> ||
|Participation à une réunion (tentatives)  <br/> |5  <br/> ||
|Participation à une réunion (réussite)  <br/> |4  <br/> ||
|Minutes d’appel/de réunion  <br/> |30 minutes  <br/> ||
|Partenaire de Fédération  <br/> |Microsoft.com  <br/> |Il s’agit du nom de l’organisation enregistré dans Office 365 et transmis en texte clair, ce qui signifie qu’il n’est pas masqué.  <br/> |

Les données d’utilisation ne contiennent aucune information identifiant les utilisateurs.

La collecte des données d’utilisation est activée par défaut, mais les administrateurs locaux peuvent la désactiver à l’aide du paramètre de stratégie de groupe DisableAutomaticSendTracing sur Skype entreprise Server. La désactivation de ce paramètre affecte tous les utilisateurs de l’organisation. Pour plus d’informations, voir [configurer les stratégies d’amorçage du client](/skypeforbusiness/deploy/deploy-clients/configure-client-bootstrapping-policies) .

Les utilisateurs finaux ne peuvent ni activer ni désactiver la collecte des données d’utilisation.

Pour l’application réunions Skype et les pages Web de lancement de jointure, le mode de contrôle de la télémétrie est le suivant :

`Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True`

Ce paramètre est défini sur false par défaut, la collection de télémétrie est désdésactivée par défaut. Ce paramètre est défini par pool et contrôle tous les utilisateurs qui se connectent avec l’application réunions Skype à une réunion hébergée sur ce serveur.

## <a name="error-reporting-data"></a>Données du rapport d’erreurs

Les données du rapport d’erreurs peuvent inclure des informations sur les performances et la fiabilité, la configuration des appareils, la qualité de connexion réseau, les codes d’erreur, les journaux d’erreur et les exceptions. Voici quelques exemples spécifiques des données de rapport d’erreur collectées :

|**Type de données**|**Exemple**|**Remarques**|
|:-----|:-----|:-----|
|Direction du message  <br/> |Reçu  <br/> ||
|État de conversation  <br/> |Inactif  <br/> ||
|ID du thread de conversation  <br/> |AdDO8hsJqilU93hQHC3OZaPR2saEA = =  <br/> ||
|UserID  <br/> |amosmarble <br/> |L’IDENTIFIant est envoyé en texte clair et le service de télémétrie le hache avant de le stocker  <br/> |

Les données du rapport d’erreurs contiennent également des informations d’identification personnelle telles que l’adresse IP de l’utilisateur et le protocole URI SIP (Uniform Resource Identifier). Consultez la [déclaration de confidentialité de Skype entreprise](https://www.microsoft.com/privacystatement/SkypeforBusiness/Default.aspx) pour obtenir une explication détaillée de ce qui est collecté.

Le signalement des erreurs nécessite deux éléments :

- Le paramètre de stratégie de groupe DisableAutomaticSendTracing est défini sur false sur le serveur ou dans le centre d’administration client (il s’agit de l’État par défaut). Pour plus d’informations, voir [configurer les stratégies d’amorçage du client](/skypeforbusiness/deploy/deploy-clients/configure-client-bootstrapping-policies) .
    
- Les utilisateurs finaux choisissent individuellement à partir de l’onglet général (cliquez sur ![l’icône d’engrenage, une ](media/70f1b43f-16d6-4172-9139-71d845c4ed5c.png) icône représentant un engrenage, puis la boîte de dialogue **options** s’ouvre avec l’onglet **général** affiché) dans le client Skype entreprise.
    
 
![Capture d’écran de la case à cocher collection de données dans la boîte de dialogue Options](media/68bc8f77-deaa-478c-9977-a5259b88df3e.png)
  
Pour l’application réunions Skype, le MeetingUxEnableTelemetry contrôle également le signalement d’erreurs, même si le problème se bloque sur Windows, les paramètres Watson contrôlent le téléchargement des informations de blocage. Il n’y a aucun paramètre d’utilisateur pour l’application réunions Skype, comme vous le voyez dans la boîte de dialogue client de bureau.

Pour plus d’informations, reportez-vous à la rubrique [définition des options générales dans Skype entreprise](https://support.office.com/article/e1a46d3e-dcea-437a-ba7b-6d442a40f439) .

Pour configurer votre réseau, vous pouvez vous reporter à [la rubrique Configuration de votre réseau pour Skype entreprise Online](https://support.office.com/article/81fa5e16-418d-4698-a5f0-e666211c5c66) .

Si vous utilisez Office 365 géré par 21Vianet en Chine, reportez-vous à [la rubrique Configuration de votre réseau pour Skype entreprise Online géré par 21ViaNet](https://support.office.com/article/d21f89b0-3afc-432e-b735-036b2432fdbf).

## <a name="related-topics"></a>Rubriques connexes
[Disponibilité des offres d'appels et d'audioconférence selon les régions et les pays](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
