---
title: "Pratiques de collecte des données"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, allancar
ms.date: 01/22/2018
ms.topic: article
ms.assetid: c17e8ea6-b83b-4345-9401-47a6c8b13aad
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Legal
hideEdit: 
description: "Microsoft collecte les données de recensement et d’utilisation erreur afin de comprendre comment est utilisé Skype pour les entreprises et où les utilisateurs rencontrent des problèmes. Les données sont utilisées pour planifier les améliorations de produit."
ms.openlocfilehash: f58a5650da1b6f489c63fdb5e5870321e0f06727
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2018
---
# <a name="skype-for-business-and-microsoft-teams-data-collection-practices"></a>Skype pour les pratiques de collection des données métier et Teams de Microsoft

Skype pour Business Server 2015, Skype pour professionnels en ligne, avec Skype pour les applications d’entreprise et Microsoft Teams collecter des données pour aider Microsoft à comprendre la manière dont ces produits sont utilisés et quels types d’erreurs, telles que des erreurs de connexion, ont eu lieu. Ces informations nous permettent de comprendre les modèles d’utilisation, planifier de nouvelles fonctionnalités et dépanner et résoudre des zones à problème.
  
Lors de l’utilisation des données collectées automatiquement, autres données peuvent uniquement être collectées lorsque l’administrateur et/ou l’utilisateur choisit pour l’autoriser. Collecte de données se divise en trois catégories :
  
- Données de recensement
    
- Données d’utilisation
    
- Données de rapport d’erreurs
    
## <a name="census-data"></a>Données de recensement

Données de recensement sont acquise uniquement pour fournir, prise en charge et améliorer Skype pour les entreprises. Les équipes Microsoft et Skype pour les entreprises en ligne. Il inclut des informations environnementales telles que les versions de système d’exploitation et les périphériques et les paramètres régionaux et linguistiques. Il inclut également des compteurs pour les défaillances et les tentatives de connexion. Voici quelques exemples spécifiques de données recensement collectées :

|**Type de données**|**Exemple**|**Remarques**|
|:-----|:-----|:-----|
|AppName  <br/> |iPhoneSkype  <br/> ||
|DeviceModel  <br/> |iPhone  <br/> ||
|OSName  <br/> |iPhoneiOS  <br/> ||
|OSVersion  <br/> |8.3  <br/> ||
|UserLanguage  <br/> |EN-US  <br/> ||
|ID utilisateur  <br/> |E296D735-4F36-4E18-7C3B-52E1A02A0164  <br/> |L’ID est haché deux fois : une première fois sur le client et sur le service de télémétrie. Le hachage garantit que l’ID ne peut pas être lié à un utilisateur spécifique.  <br/> |
|ID de périphérique  <br/> |5E872200-F546-4CCD-8F23-AF5F507AA2DD  <br/> |L’ID de périphérique est un GUID qui a généré une seule fois sur le périphérique et envoyée au service de télémétrie de manière aléatoire.  <br/> |
   
Données de recensement est pas contient toute information qui identifie votre organisation ou des utilisateurs. Consultez le [Skype pour la déclaration de confidentialité d’entreprise](https://www.microsoft.com/privacystatement/en-us/SkypeforBusiness/Default.aspx) pour plus d’informations.
  
Données de recensement sont activée par défaut et ne peut pas être désactivées par les administrateurs ou les utilisateurs finaux.
  
## <a name="usage-data"></a>Données d’utilisation

Les données d’utilisation contient des informations telles que le nombre d’appels effectués, nombre de IMs envoyé ou reçu, nombre de réunions joint, fréquence des fonctions utilisées et des problèmes de stabilité.
  
Les données d’utilisation peuvent contenir des informations qui identifient votre organisation, par exemple, contoso.com. Voici quelques exemples spécifiques des données d’utilisation collectées :
  
|**Type de données**|**Exemple**|**Remarques**|
|:-----|:-----|:-----|
|Messagerie instantanée envoyée  <br/> |12  <br/> ||
|Message instantané reçu  <br/> |5  <br/> ||
|Participer à une réunion (tentatives)  <br/> |5  <br/> ||
|Participer à une réunion (succès)  <br/> |4  <br/> ||
|Appel/compte-rendu  <br/> |30 minutes  <br/> ||
|FederationPartner  <br/> |Microsoft.com  <br/> |Ceci est le nom de l’organisation enregistrée dans Office 365 et est transmis en clair, ce qui signifie qu’il n’est pas obscurcie.  <br/> |
   
Données d’utilisation est pas contient toute information qui identifie les utilisateurs.
  
Collection des données d’utilisation est activée par défaut, mais en local admins peut désactiver à l’aide du paramètre de stratégie de groupe DisableAutomaticSendTracing sur Skype pour Business Server 2015. La désactivation de ce paramètre affecte tous les utilisateurs de l’organisation. Pour plus d’informations, reportez-vous à la section [Configuration des stratégies amorçage client dans Skype pour Business Server 2015](https://technet.microsoft.com/EN-US/library/gg425941.aspx) .
  
Les utilisateurs finaux ne peut pas activer la collection des données d’utilisation ou désactiver.
  
Pour l’application de réunions Skype et les pages web du Lanceur jointure, la manière de contrôler la télémétrie est par le biais de cette stratégie :
  
Set-CsWebServiceConfiguration - MeetingUxEnableTelemetry $True
  
Cette stratégie par défaut est false, afin que la collection de télémétrie est désactivée par défaut. Ce paramètre est par groupe et contrôle de tous les utilisateurs qui se connectent avec application de réunions Skype à une conférence hébergée sur ce serveur.
  
## <a name="error-reporting-data"></a>Données de rapport d’erreurs

Données de rapport d’erreur peuvent inclure des informations sur les performances et la fiabilité, la configuration de périphérique, qualité de la connexion réseau, les codes d’erreur, journaux d’erreurs et exceptions. Voici quelques exemples spécifiques de données qui sont collectées de rapport d’erreurs :

|**Type de données**|**Exemple**|**Remarques**|
|:-----|:-----|:-----|
|Direction du message  <br/> |Entrant  <br/> ||
|État de la conversation  <br/> |Inactif  <br/> ||
|ID de thread de conversation  <br/> |AdDO8hsJqilU93hQHC3OZaPR2saEA ==  <br/> ||
|ID utilisateur  <br/> |amosmarble <br/> |L’ID est envoyé en texte clair, ce qui le service télémétrie hache avant de les stocker  <br/> |
   
Données de rapport d’erreur peuvent également contenir des informations d’identification personnelle comme adresse IP de l’utilisateur et Session Initiation Protocol Uniform Resource Identifier (URI SIP). Voir le pour une explication détaillée de ce qui est collecté [Skype pour la déclaration de confidentialité commerciale](https://www.microsoft.com/privacystatement/en-us/SkypeforBusiness/Default.aspx) .
  
Rapport d’erreur nécessite deux choses :
  
- Le paramètre de stratégie de groupe de DisableAutomaticSendTracing être définie sur False sur le serveur ou dans le centre d’administration client (il s’agit de l’état par défaut). Pour plus d’informations, reportez-vous à la section [Configuration des stratégies amorçage client dans Skype pour Business Server 2015](https://technet.microsoft.com/EN-US/library/gg425941.aspx) .
    
- Les utilisateurs finaux individuellement participer à partir de l’onglet Général (cliquez sur l’icône de vitesse et de la boîte de dialogue Options s’ouvre avec l’onglet Général) dans le Skype pour client d’entreprise.
    
     ![Icône d’engrenage](../images/70f1b43f-16d6-4172-9139-71d845c4ed5c.png)
  
![Skype pour la case de la collection données métier dans les Options > boîte de dialogue Général](../images/68bc8f77-deaa-478c-9977-a5259b88df3e.png)
  
Pour l’application de réunions Skype, la MeetingUxEnableTelemetry contrôle également rapport d’erreurs, bien que pour des incidents sur Windows, les paramètres Watson contrôlent téléchargement info de blocage. Il n’y a aucun paramètre d’utilisateur pour l’application de réunions Skype que vous voyez dans la boîte de dialogue client de bureau.
  
Pour plus d’informations, reportez-vous à la section [des options définir générales dans Skype pour les entreprises](http://support.office.com/article/e1a46d3e-dcea-437a-ba7b-6d442a40f439) .
  
Vous pouvez voir [configurer votre réseau pour Skype pour l’activité en ligne](http://support.office.com/article/81fa5e16-418d-4698-a5f0-e666211c5c66) pour configurer votre réseau.
  
Si vous utilisez Office 365 exploités par 21Vianet en Chine, consultez [configurer votre réseau pour Skype pour Business Online exploités par 21Vianet](http://support.office.com/article/d21f89b0-3afc-432e-b735-036b2432fdbf).
  
## <a name="related-topics"></a>Rubriques connexes
[Programme d’amélioration du produit](https://www.microsoft.com/products/ceip/en-US/default.mspx)

[Disponibilité des offres d'appels et d'audioconférence selon les régions et les pays](../country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)
