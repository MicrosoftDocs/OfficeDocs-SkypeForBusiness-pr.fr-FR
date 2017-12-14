---
title: "Skype pour les entreprises et Microsoft Teams pratique de collecte des données"
ms.author: tonysmit
author: tonysmit
ms.date: 5/31/2017
ms.audience: Admin
ms.topic: reference
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom: Adm_O365_FullSet
ms.assetid: c17e8ea6-b83b-4345-9401-47a6c8b13aad
description: "Microsoft collects census, usage, and error data to understand how Skype for Business is being used and where users encounter problems. The data is used to plan product improvements."
---

# Skype pour les entreprises et Microsoft Teams pratique de collecte des données

> [!IMPORTANT]
> Cet article a été traduit automatiquement, voir l'[avertissement](c17e8ea6-b83b-4345-9401-47a6c8b13aad.md#MT_Footer). Vous pouvez consulter la version en anglais de cet article [ici](https://support.office.com/en-us/article/c17e8ea6-b83b-4345-9401-47a6c8b13aad). 
  
les clients Skype Entreprise Server 2015, Skype Entreprise Online et Skype Entreprise collectent des données pour aider Microsoft à comprendre comment ces produits sont utilisés et quels types d'erreurs, tels que des erreurs de connexion, se sont produites. Ces informations nous permettent de comprendre les modèles d'utilisation, planifier des nouvelles fonctionnalités et résoudre les problèmes et corriger les zones à problème.
  
Certaines données d'utilisation sont collectées automatiquement alors que d'autres données ne peuvent être collectées que lorsque l'administrateur et/ou l'utilisateur choisissent de l'autoriser. La collecte de données comprend trois catégories : 
  
- Données de recensement
    
- Données d'utilisation
    
- Données des rapports d'erreur
    
## Données de recensement

Données recensement sont acquise uniquement pour fournir, prend en charge et améliorer Skype Entreprise et Skype Entreprise Online. Il inclut l'environnement informations telles que les versions de système d'exploitation et l'appareil et paramètres régionaux et linguistiques. Il inclut également des compteurs pour se connecter tentatives et les échecs. Voici quelques exemples des données recensement qui sont collectées spécifiques :
  
|
|
|****Type de données****|****Exemple****|****Remarques****|
|:-----|:-----|:-----|
|Nom de l'application  <br/> |iPhone Skype  <br/> ||
|Modèle de l'appareil  <br/> |iPhone  <br/> ||
|Nom du système d'exploitation  <br/> |iPhone iOS  <br/> ||
|Version du système d'exploitation  <br/> |8.3  <br/> ||
|Langue de l'utilisateur  <br/> |EN-US  <br/> ||
|ID utilisateur  <br/> |E296D735-4F36-4E18-7C3B-52E1A02A0164  <br/> |L'ID est haché deux fois : une fois sur le client et à nouveau sur le service de télémétrie. Le hachage garantit que l'ID ne peut pas être lié à un utilisateur particulier.  <br/> |
|ID de l'appareil  <br/> |5E872200-F546-4CCD-8F23-AF5F507AA2DD  <br/> |L'ID de périphérique est un GUID qui a généré une seule fois sur l'appareil et envoyées au service de télémétrie de manière aléatoire.  <br/> |
   
Données recensement ne prend pas contient d'informations qui identifie votre organisation ou des utilisateurs. Voir [Skype déclaration de confidentialité d'entreprise](https://www.microsoft.com/privacystatement/en-us/SkypeforBusiness/Default.aspx) pour plus d'informations.
  
La collecte des données de recensement est activée par défaut, et les administrateurs ou les utilisateurs finaux ne peuvent pas la désactiver.
  
## Données d'utilisation

Les données d'utilisation incluent les informations, comme le nombre d'appels effectués, le nombre de messages instantanés envoyés ou reçus, le nombre de participations à des réunions, la fréquence des fonctionnalités utilisées et les problèmes de stabilité.
  
Les données d'utilisation peuvent contenir des informations identifiant votre organisation, comme, contoso.com. Voici quelques exemples spécifiques de données d'utilisation collectées :
  
|
|
|****Type de données****|****Exemple****|****Remarques****|
|:-----|:-----|:-----|
|Messages instantanés envoyés  <br/> |12  <br/> ||
|Messages instantanés reçus  <br/> |5  <br/> ||
|Participation à une réunion (tentatives)  <br/> |5  <br/> ||
|Participations à une réunion (réussies)  <br/> |4  <br/> ||
|Minutes d'appel/de réunion  <br/> |30 minutes  <br/> ||
|Partenaire de fédération  <br/> |Microsoft.com  <br/> |Il s'agit du nom de l'organisation enregistré dans Office 365 et transmis en texte clair, ce qui signifie qu'il n'est pas masqué.  <br/> |
   
Les données d'utilisation ne contiennent AUCUNE information identifiant les utilisateurs.
  
Collecte de données de l'utilisation est activée par défaut, mais les administrateurs peuvent désactiver cette option en utilisant le paramètre de stratégie de groupe DisableAutomaticSendTracing sur Skype Entreprise Server 2015 locaux. Désactivation de ce paramètre affecte tous les utilisateurs de l'organisation. Pour plus d'informations, voir [configurer les stratégies amorçage client dans Skype entreprise Server 2015](https://technet.microsoft.com/EN-US/library/gg425941.aspx) .
  
Les utilisateurs finaux ne peut pas activer la collecte de données de l'utilisation ou désactiver.
  
Pour application de réunions Skype et les pages jointure Lanceur d'applications web, la manière de contrôler télémétrie consiste à cette stratégie :
  
Set-CsWebServiceConfiguration - MeetingUxEnableTelemetry $True
  
Cette stratégie par défaut est false, afin de la collection de sites de télémétrie est désactivée par défaut. Ce paramètre est par groupe et contrôle de tous les utilisateurs qui se connectent avec application des réunions Skype à une réunion hébergée sur ce serveur.
  
## Données des rapports d'erreur

Les données des rapports d'erreur peuvent inclure des informations sur les performances et la fiabilité, la configuration de l'appareil, la qualité de la connexion réseau, les codes d'erreur, les journaux d'erreur et les exceptions. Voici quelques exemples spécifiques de données des rapports d'erreur collectées :
  
|
|
|****Type de données****|****Exemple****||
|:-----|:-----|:-----|
|Direction du message  <br/> |Entrant  <br/> ||
|État de la conversation  <br/> |Inactif  <br/> ||
|ID du thread de conversation  <br/> |AdDO8hsJqilU93hQHC3OZaPR2saEA==  <br/> ||
|ID utilisateur  <br/> ||L'identifiant est envoyé en texte clair et le service de télémétrie le hache avant de le stocker  <br/> |
   
Données de rapport d'erreur peuvent également contenir des informations d'identification personnelle comme adresse IP et la Session d'Initiation Protocol Uniform Resource Identifier (URI SIP) de l'utilisateur. Voir [Skype déclaration de confidentialité d'entreprise](https://www.microsoft.com/privacystatement/en-us/SkypeforBusiness/Default.aspx) pour une description détaillée de ce que sont collecté.
  
Les rapports d'erreur nécessitent deux conditions : 
  
- Le paramètre de stratégie de groupe DisableAutomaticSendTracing être définis sur False sur le serveur ou dans le centre d'administration client (il s'agit de l'état par défaut). Pour plus d'informations, voir [configurer les stratégies amorçage client dans Skype entreprise Server 2015](https://technet.microsoft.com/EN-US/library/gg425941.aspx) .
    
- Les utilisateurs finaux individuellement participer à partir de l'onglet Général (cliquez sur l'icône d'engrenage et la boîte de dialogue Option s'ouvre avec l'onglet Général) dans le client Skype Entreprise.
    
     ![Icône d'engrenage](../images/70f1b43f-16d6-4172-9139-71d845c4ed5c.png)
  
![Skype for Business data collection checkbox in the Options > General dialog](../images/68bc8f77-deaa-478c-9977-a5259b88df3e.png)
  
Application de réunions Skype, la MeetingUxEnableTelemetry contrôles rapport d'erreurs, bien que pour se bloque dans Windows, les paramètres Watson contrôlent les informations de blocage chargés. Il n'existe aucun paramètre utilisateur pour l'application Skype comme vous voyez dans la boîte de dialogue client de bureau.
  
Pour plus d'informations, reportez-vous à la rubrique [Définition des options générales dans Skype Entreprise](https://support.office.com/article/e1a46d3e-dcea-437a-ba7b-6d442a40f439).
  
Pour configurer votre réseau, vous pouvez vous reporter à la rubrique [Configuration de votre réseau pour Skype Entreprise Online](https://support.office.com/article/81fa5e16-418d-4698-a5f0-e666211c5c66).
  
Si vous utilisez Office 365 géré par l'opérateur 21Vianet en Chine, reportez-vous à la rubrique [Set up your network for Lync Online](https://support.office.com/article/d21f89b0-3afc-432e-b735-036b2432fdbf).
  
## Rubriques connexes

[Programme d'amélioration du produit](https://www.microsoft.com/products/ceip/en-US/default.mspx)
  
[URL et plages d'adresses IP Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Avertissement traduction automatique**: cet article a été traduit par un ordinateur, sans intervention humaine. Microsoft propose cette traduction automatique pour offrir aux personnes ne maîtrisant pas l'anglais l'accès au contenu relatif aux produits, services et technologies Microsoft. Comme cet article a été traduit automatiquement, il risque de contenir des erreurs de grammaire, de syntaxe ou de terminologie.
  

