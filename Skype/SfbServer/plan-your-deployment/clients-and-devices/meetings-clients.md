---
title: Planifier pour les clients de conférences (application Web et application réunions)
ms.author: v-lanac
author: lanachin
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 31e95e16-f79f-46c6-b123-973fa56a824e
description: 'Résumé : les professionnels de l’informatique doivent consulter la configuration requise pour Skype entreprise Web App et l’application réunions Skype lors de la planification de Skype entreprise Server. Cet article n’est pas destiné aux utilisateurs de ces applications.'
ms.openlocfilehash: 126d8ffc71a2ff1a0bcbf26c744301736d2b47b2
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803554"
---
# <a name="plan-for-meetings-clients-web-app-and-meetings-app"></a>Planifier pour les clients de conférences (application Web et application réunions)
 
**Résumé :** Les professionnels de l’informatique doivent consulter la configuration requise pour Skype entreprise Web App et l’application réunions Skype lors de la planification de Skype entreprise Server. Cet article n’est pas destiné aux utilisateurs de ces applications.
  
Une fois que vous avez implémenté Skype entreprise Server, les utilisateurs de votre organisation ont présumé avoir installé le client Skype entreprise dans le cadre du processus de déploiement. 
  
Par la suite, les utilisateurs peuvent créer des réunions et inviter des utilisateurs de l’extérieur de l’organisation, et ces invités de réunion ne disposent pas nécessairement de la version du client Skype entreprise. Lorsque les utilisateurs cliquent sur l’URL de l’invitation à la réunion, l’absence d’un client est détectée et l’invité sans client Skype entreprise est invité à télécharger et installer un client léger pour les réunions uniquement pour pouvoir participer à la réunion.
  
> [!NOTE]
> Skype entreprise Web App et l’application réunions Skype ne sont disponibles que lorsque vous tentez de vous connecter à une réunion sans avoir Skype entreprise. L’aide de l’utilisateur de ces [https://aka.ms/smahelp](https://aka.ms/smahelp)applications est à. 
  
> [!NOTE]
> Vous ne pouvez pas préinstaller l’application Skype entreprise Web App ou réunions Skype, mais les utilisateurs de [téléphones intelligents](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-1) et de [tablettes](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-2) pourront peut-être installer des clients mobiles économiques qu’ils peuvent utiliser pour participer à des réunions.
  
Par défaut, le serveur qui héberge la réunion dirigera l’utilisateur pour télécharger et installer Skype entreprise Web App afin de participer à la réunion. Skype entreprise Web App est stocké sur le serveur frontal et est envoyé au participant à la réunion. 
  
Pour Skype entreprise Server, l’application réunions Skype (sur Windows) et Skype entreprise pour Mac (sur Mac) sont disponibles en remplacement de Skype entreprise Web App, en commençant par CU5, mais le fait de fournir les applications de remplacement nécessite la configuration supplémentaire décrite dans la section [activer l’application réunions Skype pour le remplacement de Skype entreprise Web App (facultatif)](../../deploy/deploy-clients/deploy-web-downloadable-clients.md#SMA_Enable).  Si l’application réunions Skype et Skype entreprise pour Mac sont activées, les utilisateurs pourront télécharger la version la plus récente des applications à partir du réseau de distribution de contenu (CDN) d’Office 365 plutôt que de Skype entreprise Server. Pour Skype entreprise Server 2019, vous pouvez utiliser l’application réunions Skype et Skype entreprise pour Mac.
  
L’application réunions Skype offre une interface simplifiée pour le téléchargement et l’installation de l’application et la participation aux réunions, y compris la participation en un clic aux utilisateurs d’Internet Explorer. L’application réunions Skype propose également de nombreuses améliorations sur Skype entreprise Web App pour la fiabilité et l’interface de réunion. 
  
> [!NOTE]
> À partir de Skype entreprise Server 2015 CU5 ou version ultérieure, les réunions tenues à l’aide de Skype entreprise Online ne seront plus envoyées à un utilisateur sans client dans Skype entreprise Web App, elles seront alors envoyées à l’application réunions Skype (sous Windows) ou Skype entreprise pour Mac (Mac). Depuis Skype entreprise Server 2015 CU5 ou une version ultérieure, si vous [activez l’application réunions Skype pour remplacer Skype entreprise Web App (facultatif)](../../deploy/deploy-clients/deploy-web-downloadable-clients.md#SMA_Enable), les utilisateurs sans client recevront l’application réunions Skype ou Skype entreprise pour Mac au lieu de Skype entreprise Web App. 
  
## <a name="software-requirements"></a>Configuration logicielle requise
<a name="OS-Browser"> </a>

Pour utiliser l’application Web Skype entreprise, un utilisateur doit disposer de l’une des combinaisons de systèmes d’exploitation et de navigateurs pris en charge ci-dessous. 
  
**Système d’exploitation et prise en charge du navigateur minimum pour Skype entreprise Web App**

| Système d’exploitation | Edge | 32-et 64 bits Internet Explorer 11 ou version ultérieure | 32 et 64 bits Internet Explorer 10 ou version ultérieure | 32 et 64 bits Internet Explorer 9 ou version ultérieure | Version 32 et 64 bits de Safari 6.2.8-11. X | Version 32 et 64 bits de chrome 18. X ou version ultérieure |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Windows 10  <br/> |Oui   <br/> |Oui  <br/> |N/D  <br/> |N/D  <br/> |N/D  <br/> |Oui &#x2778; <br/> |
|Windows 8,1 &#x2776; <br/> |N/A  <br/> |Oui  <br/> |N/D  <br/> |N/D  <br/> |N/D <br/> |Oui &#x2778; <br/> |
|&#x2776; Windows 8 (Intel) <br/> |N/D  <br/> |N/A  <br/> |Oui  <br/> |N/D <br/> |N/D  <br/> |Oui &#x2778; <br/> |
|Windows 7 avec SP1 &#x2777; <br/> |N/A  <br/> |Oui  <br/> |Non  <br/> |Non  <br/> |N/A <br/>|Oui &#x2778; <br/> |
|Windows Server 2008 R2 avec SP1 &#x2777; <br/> |N/A  <br/> |Oui  <br/> |Oui   <br/> |Oui  <br/> |N/D <br/>|Oui &#x2778; <br/> |
|macOS 10,8 et versions ultérieures (Intel) &#x2777; <br/> |N/D  <br/> |N/D  <br/> |N/D  <br/> |N/A  <br/> |Oui  <br/> |Oui <br/> |
   
&#x2776; le plug-in de navigateur Skype entreprise Web App nécessite un plug-in de partage spécifique pour utiliser la voix, la vidéo, le partage et l’affichage en cours du partage d’écran et d’autres fonctionnalités sur un ordinateur. Un participant à une réunion dispose de l’option d’installation du plug-in de partage lors de la réunion ou du lancement de l’une de ces fonctionnalités. Sur Windows 8 et Windows 8,1, le plug-in de partage ne peut être installé que si vous utilisez Internet Explorer 10 ou Internet Explorer 11 pour le bureau. Ces fonctionnalités ne sont pas disponibles pour les versions non de bureau d’Internet Explorer 10 et 11. Notez que Firefox et Safari version 12,0 et les versions ultérieures ne sont plus pris en charge.
  
&#x2777; sur les systèmes d’exploitation Windows 7, Windows Server 2008 R2 et Macintosh pris en charge, toutes les fonctionnalités sont disponibles, notamment la voix, la vidéo et le partage des applications basés sur un ordinateur, le partage d’application, l’affichage du bureau et le partage du bureau. Pour utiliser ces fonctionnalités, vous devez installer un plug-in quand vous y êtes invité. Veuillez noter que la version Mac OS X 10.7 n’est plus prise en charge.
  
&#x2778; l’accès à l’application Web à partir de chrome sur Windows lancera un petit programme qui charge l’application Web dans une image incorporée d’Internet Explorer. Ce programme requiert l'une des versions d'Internet Explorer prises en charge pour charger correctement l'application Web.
  
> [!NOTE]
> Les utilisateurs d’Office 365 peuvent utiliser Internet Explorer 10 ou une version ultérieure de Skype entreprise. 
  
### <a name="skype-meetings-app"></a>Application Réunions Skype

L’application réunions Skype s’exécute en tant qu’application sur les ordinateurs exécutant Windows 10, Windows 8,1, Windows 8, Windows 7, avec 32 et 64 bits d’Internet Explorer 11 ou version ultérieure. 
  
Pour toute autre dépendance, voir [plateformes prises en charge par l’application réunions Skype](https://support.office.com/en-US/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001) .
  
### <a name="skype-for-business-for-mac"></a>Skype entreprise pour Mac

Skype entreprise pour Mac s’exécute sur des ordinateurs utilisant macOS version 10,8 ou ultérieure. 

## <a name="hardware-requirements"></a>Configuration matérielle requise
<a name="OS-Browser"> </a>

La configuration matérielle requise est déterminée par le système d'exploitation et le navigateur. Les fonctionnalités vocales et de téléphonie nécessitent un micro et des haut-parleurs, un casque équipé d'un micro, ou un périphérique équivalent compatible avec l'ordinateur. Les fonctionnalités vidéo nécessitent un périphérique vidéo compatible avec l'ordinateur. Pour plus d’informations sur la prise en charge des matériels vidéo et la qualité vidéo prévue, voir [résolutions vidéo pour les clients Skype entreprise](video-resolutions.md).
  
## <a name="network-requirements"></a>Conditions de réseau requises
<a name="Network"> </a>

Si un utilisateur de l’application Skype entreprise Web App ou réunions Skype rencontre des problèmes de connexion à la réunion, il est possible qu’elle ne soit pas configurée pour prendre en charge Office 365 comme décrit dans les [URL et plages d’adresses IP d’office 365](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US). C’est le cas, si la réunion a été créée par un utilisateur de Skype entreprise Online ou de Skype entreprise Server. 
  
Si l’utilisateur se connecte à partir d’un réseau qui n’est pas configuré comme décrit, il est possible que de nombreuses fonctionnalités d’application puissent ou ne fonctionnent pas et qu’elles ne puissent pas se connecter à la réunion.
  
## <a name="supported-meetings-features"></a>Fonctionnalités des réunions prises en charge
<a name="BKMK_Conferencing"> </a>

Le tableau suivant compare les fonctionnalités de réunion disponibles pour les utilisateurs du client Skype entreprise, Skype entreprise Web App, l’application réunions Skype et Lync Web App. Lync Web App est répertorié à des fins de comparaison des fonctionnalités : un utilisateur ne doit télécharger et utiliser Lync Web App que si la réunion a été hébergée sur un serveur 2013 Lync.

| Fonctionnalité | Client Skype entreprise 2016 ou 2019 | Client Skype entreprise pour Mac | Application Réunions Skype | Skype entreprise Web App | Lync Web App |
|:-----|:-----|:-----|:-----|:-----|:-----|
|Ajouter l'audio de l'ordinateur  <br/> |&#x2714;|&#x2714;|&#x2714; (nécessite un plug-in)  <br/> |&#x2714; (nécessite un plug-in)  <br/> |&#x2714; (nécessite un plug-in)  <br/> |
|Ajouter la vidéo  <br/> |&#x2714;|&#x2714;|&#x2714; (nécessite un plug-in)  <br/> |&#x2714; (nécessite un plug-in)  <br/> |&#x2714; (nécessite un plug-in)  <br/> |
|Basculer l’audio sur un téléphone pour les participants authentifiés  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Basculer l’audio sur un téléphone pour les participants invités  <br/> |&#x2714;|&#x2714;|&#x2714;|||
|Afficher une vidéo à plusieurs (vue galerie)  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Partage d'écran vidéo  <br/> |&#x2714;|&#x2714; <br/> |&#x2714; (lecture seule)  <br/> |||
|Utiliser des commandes de présentateur lors des réunions  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Accéder à une liste détaillée des réunions  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Participer à une conversation par messagerie instantanée à plusieurs  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Définir les messages instantanés sur Importance haute  <br/> |&#x2714;|||||
|Partager le bureau (si option activée)  <br/> |&#x2714;|&#x2714;|&#x2714; (nécessite un plug-in)  <br/> |&#x2714; (nécessite un plug-in)  <br/> |&#x2714; (nécessite un plug-in)  <br/> |
|Partager un programme (si option activée)  <br/> |&#x2714;||&#x2714; (sur Windows uniquement ; nécessite un plug-in)  <br/> |&#x2714; (sur Windows uniquement ; nécessite un plug-in)  <br/> |&#x2714; (sur Windows uniquement ; nécessite un plug-in)  <br/> |
|Prendre le contrôle d’un bureau ou d’un programme partagé d’un autre utilisateur  <br/> |&#x2714;||&#x2714; (&#x2776; sur Windows uniquement ; nécessite un plug-in)  <br/> |&#x2714; (&#x2776; sur Windows uniquement ; nécessite un plug-in)  <br/> |&#x2714; (&#x2776; sur Windows uniquement ; nécessite un plug-in)  <br/> |
|Autoriser un autre utilisateur à prendre le contrôle de votre bureau ou programme partagé  <br/> |&#x2714;|||||
|Ajouter des participants anonymes (si option activée)  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Inviter des participants par nom  <br/> |&#x2714;|&#x2714;||||
|Inviter des participants par numéro de téléphone  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Inviter des participants par courrier électronique  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Utiliser les réunions audio rendez-vous  <br/> |&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |
|Démarrer une réunion Conférence maintenant  <br/> |&#x2714;|&#x2714;||||
|Enregistrer une réunion  <br/> |&#x2714;|||||
|Ajouter et télécharger des pièces jointes  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Ajouter et présenter des fichiers Microsoft PowerPoint  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Parcourir des fichiers Microsoft PowerPoint  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Ajouter et modifier des notes de réunion OneNote  <br/> |&#x2714;||Modifier uniquement (pas ajouter)  <br/> |Modifier uniquement (pas ajouter)  <br/> |Modifier uniquement (pas ajouter)  <br/> |
|Utiliser un tableau blanc  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Mener des sondages  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Télécharger des fichiers pour les partager avec des tiers  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Planifier une réunion ou une conférence  <br/> |Outlook ou Skype entreprise Web Scheduler  <br/> |Outlook ou Skype entreprise Web Scheduler  <br/> |Skype entreprise Web Scheduler  <br/> |Skype entreprise Web Scheduler  <br/> |Skype entreprise Web Scheduler  <br/> |
|Q&amp;A Manager  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Désactiver la vidéo des participants  <br/> |&#x2714;|||||
|Désactiver la messagerie instantanée pour la réunion  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Désactiver le micro des participants  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Inviter tout le monde à participer  <br/> |&#x2714;|||||
|Produire une diffusion de réunion Skype  <br/> |&#x2714;|||||
   
 &#x2776; les participants ne peuvent pas contrôler les bureaux partagés par Skype entreprise pour Mac, Lync pour Mac 2011 ou les utilisateurs de Communicator pour Mac 2011. Cela ne fonctionne pas non plus avec Skype entreprise Web App sur Max OSX.
  
 &#x2777; pour Skype entreprise Online, cette fonctionnalité nécessite Microsoft RTC Conferencing, Exchange Unified Messaging ou un fournisseur de services d’audioconférence tiers.
  
 &#x2778; le client 2011 Lync pour Mac ne peut pas afficher les présentations PowerPoint Microsoft Office 2013 lors de leur partage dans une conférence par le biais de l’application Web Skype entreprise.
  
## <a name="known-issues-and-troubleshooting"></a>Problèmes connus et résolution des problèmes
<a name="BKMK_Conferencing"> </a>

Pour les utilisateurs finaux, l' [aide en ligne](https://aka.ms/smahelp) de ces applications est facilement accessible. Les professionnels de l’informatique doivent prendre en compte les problèmes suivants :
  
- Si l’utilisateur se trouve sur un réseau qui n’est pas configuré en fonction de la [Configuration requise du réseau](meetings-clients.md#Network), il est possible que les fonctionnalités de l’application ne fonctionnent pas et qu’elles ne puissent pas se connecter à la réunion.
    
- Certains utilisateurs peuvent être dotés d’ordinateurs administrés par l’entreprise avec l’autorisation désactivé pour installer des applications. pour ces utilisateurs, aucune application n’est disponible, mais les utilisateurs de [tablettes](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-2) et de [téléphones intelligents](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-1) peuvent installer des clients mobiles économiques qu’ils peuvent utiliser pour participer à des réunions.
    
    D’autres problèmes d’installation sont également abordés dans les [rubriques d’aide](https://support.office.com/en-us/article/Trouble-installing-the-Skype-for-Business-Web-App-plug-in-958fc5f1-2d6f-42e3-815d-a9516c591274?ui=en-US&amp;rs=en-US&amp;ad=US). 
    
- Un pare-feu est susceptible de s’afficher lorsque les utilisateurs exécutent l’application réunions pour la première fois. Il est possible qu’ils soient invités à ouvrir des ports pour optimiser l’utilisation et cela puisse nécessiter des privilèges d’administrateur sur l’ordinateur dont ils peuvent avoir besoin. L’application doit malgré tout fonctionner et l’utilisateur peut refuser en toute sécurité l’ouverture des ports demandés. 
    
- Pour pouvoir utiliser le navigateur par défaut, les [contrôles ActiveX doivent être activés sans filtrage](https://support.office.com/en-us/article/Turn-off-ActiveX-filtering-for-Skype-for-Business-Web-App-b6de8ff6-ac7e-4e2f-b18c-2f13db643c41?ui=en-US&amp;rs=en-US&amp;ad=US) dans Internet Explorer, même s’il ne s’agit pas de votre navigateur par défaut. Dans Skype entreprise Web App, un contrôle ActiveX (un petit module qui ajoute des fonctionnalités à une application Web ou à un autre programme) est nécessaire pour le partage audio et vidéo, et le partage d’écran.
    
- Pour que certaines fonctionnalités de Skype entreprise Web App fonctionnent correctement, vous devez autoriser votre navigateur à [enregistrer les cookies](https://support.office.com/en-us/article/Allow-cookies-for-Skype-Meetings-App-Skype-for-Business-Web-App-2108276b-b5c3-484b-bf2b-dac6eeba4c93) sur votre ordinateur ou appareil.
    
- Il est possible que vous deviez activer la prise en charge [JavaScript](https://support.office.com/en-us/article/Turn-on-JavaScript-for-Skype-Meetings-App-Skype-for-Business-Web-App-3d997bf9-637c-4fe6-8ee3-9e62bfda52cd) dans votre navigateur pour que certaines fonctionnalités de Skype entreprise Web App fonctionnent comme prévu.
    
### <a name="aes-support"></a>Prise en charge AES 

À partir de Skype entreprise Server 2015 CU5, AES n’est pas pris en charge pour ASP.NET 4,6 et cela peut entraîner le démarrage de l’application réunions Skype. Pour plus d’informations, reportez- [vous à la configuration requise en raison d’ASP .net 4,5](../security/user-and-client-authentication.md#cryptographic-requirements-due-to-asp-net-45) .
  
## <a name="see-also"></a>Voir aussi
<a name="BKMK_Conferencing"> </a>

[Déploiement de clients Web à télécharger dans Skype entreprise Server](../../deploy/deploy-clients/deploy-web-downloadable-clients.md)

[Plates-formes prises en charge pour l’application réunions Skype](https://support.office.com/en-US/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)
