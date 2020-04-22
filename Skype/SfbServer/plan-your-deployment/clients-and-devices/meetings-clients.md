---
title: Planifier les clients des réunions (application Web et application de réunion)
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
description: 'Résumé : les professionnels de l’informatique doivent consulter les conditions requises en matière de prise en charge de Skype entreprise Web App et de l’application réunions Skype lors de la planification de Skype entreprise Server. Cet article n’est pas destiné aux utilisateurs de ces applications.'
ms.openlocfilehash: 0e1ce225f99a112f11d55d76eb8039a10d9aac6b
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43777789"
---
# <a name="plan-for-meetings-clients-web-app-and-meetings-app"></a>Planifier les clients des réunions (application Web et application de réunion)
 
**Résumé :** Les professionnels de l’informatique doivent consulter les conditions requises en matière de prise en charge de Skype entreprise Web App et de l’application réunions Skype lors de la planification de Skype entreprise Server. Cet article n’est pas destiné aux utilisateurs de ces applications.
  
Une fois que vous avez implémenté Skype entreprise Server, les utilisateurs de votre organisation auront vraisemblablement installé le client Skype entreprise dans le cadre du processus de déploiement. 
  
Par la suite, ces utilisateurs peuvent créer des réunions et inviter des utilisateurs à l’extérieur de l’organisation, et ces invités peuvent ne pas avoir de version du client Skype entreprise. Lorsque ces utilisateurs cliquent sur l’URL de l’invitation à la réunion, l’absence de client est détectée et l’invité sans client Skype entreprise est invité à télécharger et à installer un client léger, uniquement pour les réunions uniquement, afin qu’ils puissent participer à la réunion.
  
> [!NOTE]
> L’application Skype entreprise Web App et Skype meetings ne sont disponibles que lorsque vous tentez de vous connecter à une réunion sans avoir Skype entreprise. Pour obtenir de l’aide pour ces [https://aka.ms/smahelp](https://aka.ms/smahelp)applications, consultez la page. 
  
> [!NOTE]
> Vous ne pouvez pas pré-installer l’application Skype entreprise Web App ou les réunions Skype, mais les utilisateurs de [tablettes](https://products.office.com/skype-for-business/download-app?tab=tabs-2) et de [téléphones intelligents](https://products.office.com/skype-for-business/download-app?tab=tabs-1) peuvent être en mesure d’installer des clients mobiles peu coûteux qu’ils peuvent utiliser pour participer à des réunions.
  
Par défaut, le serveur qui héberge la réunion demande à l’utilisateur de télécharger et d’installer Skype entreprise Web App pour participer à la réunion. Skype entreprise Web App est stocké sur le serveur frontal et est envoyé au participant à la réunion. 
  
Pour Skype entreprise Server, l’application de réunions Skype (sous Windows) et Skype entreprise pour Mac (sur Mac) est disponible sous forme de remplacements pour Skype entreprise Web App à partir de CU5, mais le fait de fournir les applications de remplacement nécessite une configuration supplémentaire décrite dans la rubrique [Enable Skype Meeting app to Replace Skype for Business Web App (optional)](../../deploy/deploy-clients/deploy-web-downloadable-clients.md#SMA_Enable).  Si l’application de réunions Skype et Skype entreprise pour Mac sont activées, les utilisateurs téléchargeront la dernière version des applications à partir du réseau de distribution de contenu (CDN) Office 365 et non à partir de Skype entreprise Server. Pour Skype entreprise Server 2019, l’utilisation de Skype Meeting App et Skype entreprise pour Mac est la seule option.
  
L’application réunions Skype offre une expérience de navigateur simplifiée pour le téléchargement et l’installation de l’application et la participation à des réunions, y compris une jointure en un clic pour les utilisateurs d’Internet Explorer. L’application réunions Skype offre également de nombreuses améliorations par rapport à Skype entreprise Web App pour la fiabilité et l’expérience de réunion. 
  
> [!NOTE]
> À partir de Skype entreprise Server 2015 CU5 ou version ultérieure, les réunions organisées à l’aide de Skype entreprise Online n’enverront plus d’utilisateur sans client l’application Web Skype entreprise, mais elles recevront une application réunions Skype (sur Windows) ou Skype entreprise pour Mac (sur Mac). À partir de Skype entreprise Server 2015 CU5 ou version ultérieure, si vous [activez l’application de réunions Skype pour remplacer Skype entreprise Web App (facultatif)](../../deploy/deploy-clients/deploy-web-downloadable-clients.md#SMA_Enable), les utilisateurs sans client recevront une application de réunion Skype ou Skype entreprise pour Mac au lieu de Skype entreprise Web App. 
  
## <a name="software-requirements"></a>Configuration logicielle requise
<a name="OS-Browser"> </a>

Pour utiliser Skype entreprise Web App, un utilisateur doit disposer de l’une des combinaisons de système d’exploitation et de navigateur prises en charge suivantes. 
  
**Système d’exploitation et prise en charge minimale du navigateur pour Skype entreprise Web App**

| Système d’exploitation | Edge | 32 et 64 bits Internet Explorer 11 ou version ultérieure | 32 et 64 bits Internet Explorer 10 ou version ultérieure | 32 et 64 bits Internet Explorer 9 ou version ultérieure | 32-et 64-bit version de Safari 6.2.8-11. X | 32-et 64-bit version de chrome 18. X ou version ultérieure |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Windows 10  <br/> |Oui  <br/> |Oui  <br/> |N/A  <br/> |N/A  <br/> |N/A  <br/> |Oui &#x2778; <br/> |
|&#x2776; Windows 8,1 <br/> |N/D  <br/> |Oui  <br/> |N/A  <br/> |N/A  <br/> |N/A <br/> |Oui &#x2778; <br/> |
|&#x2776; Windows 8 (basé sur Intel) <br/> |N/A  <br/> |N/A  <br/> |Oui  <br/> |N/A <br/> |N/A  <br/> |Oui &#x2778; <br/> |
|Windows 7 avec SP1 &#x2777; <br/> |N/D  <br/> |Oui  <br/> |Non  <br/> |Non  <br/> |N/A <br/>|Oui &#x2778; <br/> |
|Windows Server 2008 R2 avec SP1 &#x2777; <br/> |N/D  <br/> |Oui  <br/> |Oui  <br/> |Oui  <br/> |N/D <br/>|Oui &#x2778; <br/> |
|macOS 10,8 et versions ultérieures (Intel) &#x2777; <br/> |N/A  <br/> |N/A  <br/> |N/A  <br/> |N/A  <br/> |Oui  <br/> |Oui <br/> |
   
&#x2776; le plug-in de navigateur Skype entreprise Web App nécessite un plug-in de partage spécifique pour utiliser la voix, la vidéo, le partage et l’affichage en continu du partage d’écran et d’autres fonctionnalités. Un participant à la réunion peut installer le plug-in de partage lorsqu’il rejoint la réunion ou lorsqu’il lance l’une de ces fonctionnalités. Sur Windows 8 et Windows 8,1, le plug-in de partage ne peut être installé que si vous utilisez Internet Explorer 10 ou Internet Explorer 11 pour le bureau. Ces fonctionnalités ne sont pas disponibles avec les versions non-Bureau d’Internet Explorer 10 et 11. Notez que Firefox et Safari version 12,0 et versions ultérieures ne sont plus pris en charge.
  
&#x2777; sur les systèmes d’exploitation Windows 7, Windows Server 2008 R2 et Macintosh pris en charge, toutes les fonctionnalités sont disponibles, notamment la voix, la vidéo, l’affichage des applications, le partage d’application, l’affichage de l’ordinateur de bureau et le partage du bureau. Pour utiliser ces fonctionnalités, vous devez installer un plug-in lorsque vous y êtes invité. Notez que Mac OS X version 10,7 n’est plus pris en charge.  Notez également que l’application Web ne sera pas installée sur OS X 10,15 ou version ultérieure.  Nous vous recommandons d’utiliser la dernière version de Skype entreprise pour Mac qui prend en charge les scénarios de participation anonyme.
  
&#x2778; l’accès à l’application Web à partir de chrome sur Windows lancera un petit programme qui charge l’application Web dans un cadre Internet Explorer incorporé. Ce programme nécessite l’installation d’une des versions d’Internet Explorer prises en charge pour le chargement correct de l’application Web.
  
> [!NOTE]
> Les utilisateurs de Microsoft 365 et Office 365 peuvent utiliser Internet Explorer 10 ou version ultérieure avec Skype entreprise. 
  
### <a name="skype-meetings-app"></a>Application Réunions Skype

L’application de réunions Skype s’exécute en tant qu’application sur les ordinateurs utilisant Windows 10, Windows 8,1, Windows 8, Windows 7, 32 et 64 bits Internet Explorer 11 ou version ultérieure. 
  
Pour toute autre dépendance, reportez-vous à la rubrique [plateformes prises en charge pour l’application réunions Skype](https://support.office.com/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)
  
### <a name="skype-for-business-for-mac"></a>Skype Entreprise pour Mac

Skype entreprise pour Mac s’exécute sur des ordinateurs utilisant macOS version 10,8 ou ultérieure. 

## <a name="hardware-requirements"></a>Configuration matérielle requise
<a name="OS-Browser"> </a>

La configuration matérielle requise de l’ordinateur est déterminée par le système d’exploitation et le navigateur. Les fonctionnalités vocales et de téléphonie nécessitent un micro et des haut-parleurs, un casque avec microphone ou un appareil équivalent compatible avec l’ordinateur. Les fonctionnalités vidéo nécessitent un périphérique vidéo compatible avec l’ordinateur. Pour obtenir des informations détaillées sur la prise en charge du matériel vidéo et la qualité vidéo attendue, voir la rubrique relative à la [résolution des vidéos client Skype entreprise](video-resolutions.md).
  
## <a name="network-requirements"></a>Configuration réseau requise
<a name="Network"> </a>

Si un utilisateur de Skype entreprise Web App ou une application de réunions Skype rencontre des problèmes de connexion de réunion, il est probable que l’infrastructure réseau de son organisation ne soit pas configurée pour prendre en charge Office 365, comme décrit dans les [URL et plages d’adresses IP office 365](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US). C’est le cas si la réunion a été créée par un utilisateur de Skype entreprise Online ou Skype entreprise Server. 
  
Si l’utilisateur se trouve sur un réseau qui n’est pas configuré comme décrit, de nombreuses fonctionnalités d’application peuvent ou non fonctionner et ne peuvent pas se connecter à la réunion.
  
## <a name="supported-meetings-features"></a>Fonctionnalités de réunion prises en charge
<a name="BKMK_Conferencing"> </a>

Ce tableau compare les fonctionnalités de réunion disponibles pour les utilisateurs du client Skype entreprise, Skype entreprise Web App, l’application réunions Skype et Lync Web App. Lync Web App est proposé à des fins de comparaison des fonctionnalités : un utilisateur ne peut télécharger et utiliser Lync Web App que si la réunion était hébergée sur un serveur Lync 2013.

| Fonctionnalité/capacité | Client Skype entreprise 2016 ou 2019 | Client Skype entreprise sur Mac | Application Réunions Skype | Skype Entreprise Web App | Lync Web App |
|:-----|:-----|:-----|:-----|:-----|:-----|
|Ajouter l’audio de l’ordinateur  <br/> |&#x2714;|&#x2714;|&#x2714; (requiert un plug-in)  <br/> |&#x2714; (requiert un plug-in)  <br/> |&#x2714; (requiert un plug-in)  <br/> |
|Ajouter la vidéo  <br/> |&#x2714;|&#x2714;|&#x2714; (requiert un plug-in)  <br/> |&#x2714; (requiert un plug-in)  <br/> |&#x2714; (requiert un plug-in)  <br/> |
|Commutation audio sur un téléphone pour les participants authentifiés  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Commutation audio sur un téléphone pour les participants invités  <br/> |&#x2714;|&#x2714;|&#x2714;|||
|Afficher une vidéo à plusieurs (mode Galerie)  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Partage d'écran sur vidéo  <br/> |&#x2714;|&#x2714; <br/> |&#x2714; (lecture seule)  <br/> |||
|Utiliser des commandes de présentateur lors des réunions  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Accéder à une liste de réunions détaillée  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Prendre part à une conversation par messagerie instantanée à plusieurs  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Définir les messages INSTANTANÉs comme haute importance  <br/> |&#x2714;|||||
|Partager le Bureau (si activée)  <br/> |&#x2714;|&#x2714;|&#x2714; (requiert un plug-in)  <br/> |&#x2714; (requiert un plug-in)  <br/> |&#x2714; (requiert un plug-in)  <br/> |
|Partager un programme (si activée)  <br/> |&#x2714;||&#x2714; (sur Windows uniquement ; nécessite un plug-in)  <br/> |&#x2714; (sur Windows uniquement ; nécessite un plug-in)  <br/> |&#x2714; (sur Windows uniquement ; nécessite un plug-in)  <br/> |
|Prendre le contrôle du bureau ou programme partagé d’un autre utilisateur  <br/> |&#x2714;||&#x2714; (&#x2776; sous Windows uniquement ; nécessite un plug-in)  <br/> |&#x2714; (&#x2776; sous Windows uniquement ; nécessite un plug-in)  <br/> |&#x2714; (&#x2776; sous Windows uniquement ; nécessite un plug-in)  <br/> |
|Permettre à un autre utilisateur de prendre le contrôle de votre bureau ou programme partagé  <br/> |&#x2714;|||||
|Ajouter des participants anonymes (si activée)  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Inviter des participants par nom  <br/> |&#x2714;|&#x2714;||||
|Inviter des participants par numéro de téléphone  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Inviter des participants par courrier électronique  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Utiliser des réunions audio de rendez-vous  <br/> |&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |
|Lancer une réunion Conférence maintenant  <br/> |&#x2714;|&#x2714;||||
|Enregistrer une réunion  <br/> |&#x2714;|||||
|Ajouter et télécharger des pièces jointes  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Ajouter et présenter des fichiers Microsoft PowerPoint  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Parcourir les fichiers Microsoft PowerPoint  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Ajouter et modifier des notes de réunion OneNote  <br/> |&#x2714;||Modifier uniquement (pas ajouter)  <br/> |Modifier uniquement (pas ajouter)  <br/> |Modifier uniquement (pas ajouter)  <br/> |
|Utiliser un tableau blanc  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Mener des sondages  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Charger des fichiers à partager avec d’autres personnes  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Planifier une réunion ou une conférence  <br/> |Outlook ou Skype entreprise Web Scheduler  <br/> |Outlook ou Skype entreprise Web Scheduler  <br/> |Web Scheduler Skype entreprise  <br/> |Web Scheduler Skype entreprise  <br/> |Web Scheduler Skype entreprise  <br/> |
|Q&amp;d’un responsable  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Désactivation de la vidéo des participants  <br/> |&#x2714;|||||
|Désactiver la messagerie instantanée de réunion  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Public muet  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Faire de tous les participants un participant  <br/> |&#x2714;|||||
|Produire une diffusion de réunion Skype  <br/> |&#x2714;|||||
   
 &#x2776; participants ne peuvent pas contrôler les bureaux partagés par les utilisateurs de Skype entreprise pour Mac, Lync pour Mac 2011 ou Communicator pour Mac 2011. Cela ne fonctionne pas pour Skype entreprise Web App sur Max OSX.
  
 &#x2777; pour Skype entreprise Online, cette fonctionnalité nécessite la Conférence RTC Microsoft, la messagerie unifiée Exchange ou un fournisseur de services d’audioconférence tiers.
  
 &#x2778; le client Lync pour Mac 2011 ne peut pas afficher les présentations PowerPoint de Microsoft Office 2013 lorsqu’elles ont été partagées dans une conférence par Skype entreprise Web App.
  
## <a name="known-issues-and-troubleshooting"></a>Problèmes connus et dépannage
<a name="BKMK_Conferencing"> </a>

Pour les utilisateurs finaux, l' [aide en ligne](https://aka.ms/smahelp) de ces applications est immédiatement disponible. Les professionnels de l’informatique doivent avoir conscience des problèmes suivants :
  
- Si l’utilisateur se trouve sur un réseau qui n’est pas configuré pour répondre à la [Configuration réseau requise](meetings-clients.md#Network), de nombreuses fonctionnalités d’application peuvent ou non fonctionner et ne peuvent pas se connecter à la réunion du tout.
    
- Certains utilisateurs peuvent avoir des ordinateurs administrés en entreprise avec l’autorisation désactivé pour installer des applications. pour ces utilisateurs, aucune application n’est une option, mais les utilisateurs de [tablettes](https://products.office.com/skype-for-business/download-app?tab=tabs-2) et de [téléphones intelligents](https://products.office.com/skype-for-business/download-app?tab=tabs-1) peuvent installer des clients mobiles bon marché qu’ils peuvent utiliser pour participer à des réunions.
    
    D’autres problèmes d’installation sont également traités dans les [rubriques d’aide](https://support.office.com/article/Trouble-installing-the-Skype-for-Business-Web-App-plug-in-958fc5f1-2d6f-42e3-815d-a9516c591274?ui=en-US&amp;rs=en-US&amp;ad=US). 
    
- Les utilisateurs peuvent voir un avertissement de pare-feu la première fois qu’ils exécutent l’application réunions. Ils peuvent être invités à ouvrir des ports pour optimiser l’expérience et cela peut nécessiter des privilèges d’administrateur sur l’ordinateur dont ils peuvent avoir besoin. L’application doit continuer à fonctionner et l’utilisateur peut refuser d’ouvrir les ports demandés en toute sécurité. 
    
- Vous devez [activer ActiveX sans filtrage](https://support.office.com/article/Turn-off-ActiveX-filtering-for-Skype-for-Business-Web-App-b6de8ff6-ac7e-4e2f-b18c-2f13db643c41?ui=en-US&amp;rs=en-US&amp;ad=US) dans Internet Explorer, même si Internet Explorer n’est pas votre navigateur par défaut. Dans Skype entreprise Web App, un contrôle ActiveX (un petit module qui ajoute des fonctionnalités supplémentaires à une application Web ou un autre programme) est requis pour l’audio, la vidéo et le partage d’écran.
    
- Pour que certaines fonctionnalités de Skype entreprise Web App fonctionnent correctement, vous devez autoriser votre navigateur à [enregistrer des cookies](https://support.office.com/article/Allow-cookies-for-Skype-Meetings-App-Skype-for-Business-Web-App-2108276b-b5c3-484b-bf2b-dac6eeba4c93) sur votre ordinateur ou périphérique.
    
- Il se peut que vous deviez activer la prise en charge de [JavaScript](https://support.office.com/article/Turn-on-JavaScript-for-Skype-Meetings-App-Skype-for-Business-Web-App-3d997bf9-637c-4fe6-8ee3-9e62bfda52cd) dans votre navigateur pour que certaines fonctionnalités de Skype entreprise Web App fonctionnent comme prévu.
    
### <a name="aes-support"></a>Prise en charge AES 

À partir de Skype entreprise Server 2015 CU5, AES n’est pas pris en charge pour ASP.NET 4,6 et cela peut entraîner l’échec du démarrage de l’application réunions Skype. Les [exigences en matière de chiffrement dues à ASP .net 4,5](../security/user-and-client-authentication.md#cryptographic-requirements-due-to-asp-net-45) sont plus détaillées.
  
## <a name="see-also"></a>Voir aussi
<a name="BKMK_Conferencing"> </a>

[Déploiement de clients Web téléchargeables dans Skype entreprise Server](../../deploy/deploy-clients/deploy-web-downloadable-clients.md)

[Plateformes prises en charge pour l’application réunions Skype](https://support.office.com/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)
