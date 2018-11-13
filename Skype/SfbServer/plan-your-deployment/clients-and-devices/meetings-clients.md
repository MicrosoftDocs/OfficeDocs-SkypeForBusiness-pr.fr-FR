---
title: Planifier pour les clients de réunions (application Web et application de réunions)
ms.author: jambirk
author: jambirk
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 31e95e16-f79f-46c6-b123-973fa56a824e
description: 'Résumé : Les professionnels de l’informatique doivent vérifier les exigences de prise en charge pour la Skype pour Business Web App et Skype réunions application lors de la planification pour Skype pour Business Server. Cet article n’est pas destiné aux utilisateurs de ces applications.'
ms.openlocfilehash: c76770d570aaa1d1c686df7b0845e41a767cfbef
ms.sourcegitcommit: 1cb5a3570032250aecd5a1a839cbbe4daeb77f2c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 11/13/2018
ms.locfileid: "26293672"
---
# <a name="plan-for-meetings-clients-web-app-and-meetings-app"></a>Planifier pour les clients de réunions (application Web et application de réunions)
 
**Résumé :** PROFESSIONNELS de l’informatique doivent vérifier les exigences de prise en charge pour la Skype pour Business Web App et Skype réunions application lors de la planification pour Skype pour Business Server. Cet article n’est pas destiné aux utilisateurs de ces applications.
  
Une fois que vous avez implémenté Skype pour Business Server, les utilisateurs de votre organisation auront sans doute la Skype pour Business client installé dans le cadre du processus de déploiement. 
  
Ces utilisateurs peuvent créer des réunions et inviter des utilisateurs externes à l’organisation et les invités aux réunions peut-être pas n’importe quelle version de la Skype pour client d’entreprise. Lorsque les utilisateurs cliquez sur l’URL de l’invitation à la réunion, l’absence d’un client est détecté et l’invité sans un Skype pour client Business serez invitée à télécharger et installer un client léger, réunions seule afin qu’ils peuvent joindre la réunion.
  
> [!NOTE]
> Le Skype pour l’application Web de gestion et application de réunions Skype ne sont disponibles que lors de la tentative pour vous connecter à une réunion sans avoir Skype pour les entreprises. Aide de l’utilisateur pour ces applications est à [https://aka.ms/smahelp](https://aka.ms/smahelp). 
  
> [!NOTE]
> Vous ne pouvez pas installer préalable soit le Skype pour Business Web App ou réunions Skype, mais les utilisateurs [Smartphone](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-1) et [tablette](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-2) peuvent être en mesure d’installer les clients mobiles économiques qu'ils peuvent utiliser pour participer à des réunions.
  
Par défaut, le serveur qui héberge la réunion vous dirige l’utilisateur à télécharger et installer Skype pour Business Web App joindre la réunion. Le Skype pour l’application Web de gestion est stockée sur le serveur frontal et est envoyée au participant à la réunion. 
  
Skype pour Business Server 2015, Skype réunions application est disponible sous forme d’une solution de remplacement pour Skype pour début Business Web App avec CU5, mais l’application de réunions Skype exige la configuration supplémentaire décrite dans [Activer Skype réunions App pour remplacer Skype pour l’application Web de gestion (facultative)](../../deploy/deploy-clients/deploy-web-downloadable-clients.md#SMA_Enable).  Si l’application de réunions Skype est activée, les utilisateurs seront télécharger la dernière version de l’application à partir de l’Office 365 réseau CDN (Content Delivery) plutôt que votre Skype pour Business server. Skype pour Business Server 2019 Skype réunions application est la seule option.
  
Application de réunions Skype offre une expérience de navigation simplifiée pour le téléchargement et installation de l’application et participer à des réunions, y compris la participation d’un clic pour les utilisateurs d’Internet Explorer. Application de réunions Skype également a nombreuses améliorations sur theSkype pour l’application Web de gestion de fiabilité et de l’expérience. 
  
> [!NOTE]
> À compter de Skype pour Business Server 2015 CU5 ou version ultérieure, les réunions organisées à l’aide de Skype pour Business Online n’est plus enverra un utilisateur sans le Skype pour l’application Web de gestion, ils seront envoyés au lieu de cela Skype réunions application. À compter de Skype pour Business Server 2015 CU5 ou ultérieure, si vous [Activez Skype réunions application remplacer Skype pour l’application Web de gestion (facultatif)](../../deploy/deploy-clients/deploy-web-downloadable-clients.md#SMA_Enable), sans utilisateurs seront envoyés Skype réunions application au lieu de Skype pour l’application Web de gestion. 
  
## <a name="software-requirements"></a>Configuration logicielle requise
<a name="OS-Browser"> </a>

Pour utiliser le Skype pour application de gestion Web, un utilisateur doit avoir une des options suivantes pris en charge combinaisons système d’exploitation / navigateur. 
  
**Système d’exploitation et prise en charge de navigateur minimale de Skype pour Business Web App**

| Système d’exploitation | Edge | Internet Explorer 11 ou version ultérieure 32 et 64 bits | Internet Explorer 10 ou version ultérieure 32 et 64 bits | Internet Explorer 9 ou ultérieure 32 et 64 bits | Version 32 bits et 64 bits de Safari 6.2.8 - 11.X | 32 bits et 64 bits Version de Chrome 18.X ou version ultérieure |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Windows 10  <br/> |Oui  <br/> |Oui  <br/> |N/A  <br/> |N/A  <br/> |N/A  <br/> |Oui & #x 2778 ; <br/> |
|Windows 8.1 & #x 2776 ; <br/> |N/A  <br/> |Oui  <br/> |N/A  <br/> |N/A  <br/> |N/A <br/> |Oui & #x 2778 ; <br/> |
|Windows 8 (processeur Intel) & #x 2776 ; <br/> |N/A  <br/> |N/A  <br/> |Oui  <br/> |N/A <br/> |N/A  <br/> |Oui & #x 2778 ; <br/> |
|Windows 7 avec SP1 & #x 2777 ; <br/> |N/A  <br/> |Oui  <br/> |Non  <br/> |Non  <br/> |N/A <br/>|Oui & #x 2778 ; <br/> |
|Windows Server 2008 R2 avec SP1 & #x 2777 ; <br/> |N/A  <br/> |Oui  <br/> |Oui  <br/> |Oui  <br/> |N/A <br/>|Oui & #x 2778 ; <br/> |
|Mac OS 10,8 et versions ultérieures (processeur Intel) & #x 2777 ; <br/> |N/A  <br/> |N/A  <br/> |N/A  <br/> |N/A  <br/> |Oui  <br/> |Oui <br/> |
   
& #x 2776 ; Le Skype plug-in du navigateur Web Business App requiert un plug-in de partage spécifique à utiliser basés sur ordinateur de voix, vidéo, partage et affichage de partage d’écran en cours et autres fonctionnalités. Participant à une réunion donné la possibilité d’installer le partage du plug-in lorsqu’ils rejoignent la réunion ou lorsqu’ils initient une de ces fonctionnalités. Sur Windows 8 et Windows 8.1, le plug-in de partage peut être installé uniquement si vous utilisez Internet Explorer 10 ou Internet Explorer 11 pour le bureau. Ces fonctionnalités ne sont pas disponibles avec Internet Explorer 10 ou Internet Explorer 11, version non-bureau. Notez que Firefox et Safari version 12.0 ou ultérieure n’est plus pris en charge.
  
& #x 2777 ; Sur la prise en charge de Windows 7, Windows Server 2008 R2 et les systèmes d’exploitation Macintosh, toutes les fonctionnalités sont disponibles, y compris des communications vocales par ordinateur, vidéo, affichage, partage d’application, affichage du bureau et le partage du bureau. Pour utiliser ces fonctionnalités, vous devez installer un plug-in quand vous y êtes invité. Veuillez noter que la version Mac OS X 10.7 n’est plus prise en charge.
  
& #x 2778 ; Accès à l’application Web à partir de Chrome sur Windows lance un petit programme qui charge l’application Web dans un cadre d’Internet Explorer incorporé. Ce programme requiert l'une des versions d'Internet Explorer prises en charge pour charger correctement l'application Web.
  
> [!NOTE]
> Les utilisateurs d’Office 365 peuvent utiliser Internet Explorer 10 ou version ultérieure avec Skype pour les entreprises. 
  
### <a name="skype-meetings-app"></a>Application Réunions Skype

L’application de réunions Skype s’exécute comme une application sur des ordinateurs à l’aide de Windows 10, Windows 8.1, Windows 8, Windows 7, avec 32 bits et 64 bits Internet Explorer 11 ou version ultérieure. 
  
L’application s’exécute également sur Mac OS des systèmes d’exploitation 10.10 ou version ultérieures avec aucune dépendance de navigateur spécifique. 
  
Pour tout autre couplage, veuillez consulter les [plateformes prises en charge pour l’application Réunions Skype ](https://support.office.com/en-US/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)
  
## <a name="hardware-requirements"></a>Configuration matérielle requise
<a name="OS-Browser"> </a>

La configuration matérielle requise est déterminée par le système d'exploitation et le navigateur. Les fonctionnalités vocales et de téléphonie nécessitent un micro et des haut-parleurs, un casque équipé d'un micro, ou un périphérique équivalent compatible avec l'ordinateur. Les fonctionnalités vidéo nécessitent un périphérique vidéo compatible avec l'ordinateur. Pour plus d’informations sur la prise en charge du matériel vidéo et la qualité vidéo attendue, voir [Skype pour la résolution vidéo du client entreprise](video-resolutions.md).
  
## <a name="network-requirements"></a>Conditions de réseau requises
<a name="Network"> </a>

Si un utilisateur de Skype pour Business Web App ou application de réunions Skype expériences de problèmes de connexion de la réunion, sans doute que l’infrastructure réseau de leur organisation n’est pas configuré pour prendre en charge Office 365 comme décrit dans [Office 365 URL et plages d’adresses IP](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US). C’est le cas si la réunion a été créée par un utilisateur de Skype pour Business Online ou Skype pour Business Server. 
  
Si l’utilisateur est sur un réseau n’est ne pas configuré comme indiqué, de nombreuses fonctionnalités de l’application peuvent ou ne pas fonctionneront et qu’ils ne sont peut-être pas en mesure de se connecter à la réunion.
  
## <a name="supported-meetings-features"></a>Fonctionnalités des réunions prises en charge
<a name="BKMK_Conferencing"> </a>

Ce tableau compare les fonctionnalités de réunions accessibles aux utilisateurs de Skype pour client d’entreprise, Skype pour Lync Web App, Skype réunions application et application Web de gestion. Lync Web App est répertorié à des fins de comparaison de fonctionnalité : un utilisateur souhaite uniquement le téléchargement, à l’aide de Lync Web App si la réunion a été hébergée sur un serveur Lync 2013.

| Fonctionnalité | Skype pour 2016 Business ou 2019 client | Skype pour les entreprises sur client Mac | Application Réunions Skype | Skype Entreprise Web App | Lync Web App |
|:-----|:-----|:-----|:-----|:-----|:-----|
|Ajouter l'audio de l'ordinateur  <br/> |& #x 2714 ;|& #x 2714 ;|& #x 2714 ; (nécessite un plug-in)  <br/> |& #x 2714 ; (nécessite un plug-in)  <br/> |& #x 2714 ; (nécessite un plug-in)  <br/> |
|Ajouter la vidéo  <br/> |& #x 2714 ;|& #x 2714 ;|& #x 2714 ; (nécessite un plug-in)  <br/> |& #x 2714 ; (nécessite un plug-in)  <br/> |& #x 2714 ; (nécessite un plug-in)  <br/> |
|Basculer l’audio à un téléphone pour les participants authentifiés  <br/> |& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|
|Basculer l’audio à un téléphone pour les participants invités  <br/> |& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|||
|Afficher une vidéo à plusieurs (vue galerie)  <br/> |& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|
|Partage d'écran vidéo  <br/> |& #x 2714 ;|& #x 2714 ; <br/> |& #x2714;(View-only)  <br/> |||
|Utiliser des commandes de présentateur lors des réunions  <br/> |& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|
|Accéder à une liste détaillée des réunions  <br/> |& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|
|Participer à une conversation par messagerie instantanée à plusieurs  <br/> |& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|
|Définir les messages instantanés sur Importance haute  <br/> |& #x 2714 ;|||||
|Partager le bureau (si option activée)  <br/> |& #x 2714 ;|& #x 2714 ;|& #x 2714 ; (nécessite un plug-in)  <br/> |& #x 2714 ; (nécessite un plug-in)  <br/> |& #x 2714 ; (nécessite un plug-in)  <br/> |
|Partager un programme (si option activée)  <br/> |& #x 2714 ;||& #x 2714 ; (sous Windows uniquement ; nécessite un plug-in)  <br/> |& #x 2714 ; (sous Windows uniquement ; nécessite un plug-in)  <br/> |& #x 2714 ; (sous Windows uniquement ; nécessite un plug-in)  <br/> |
|Prendre le contrôle du bureau partagé ou le programme d’un autre utilisateur  <br/> |& #x 2714 ;||& #x 2714 ; (& #x 2776 ; Sous Windows uniquement ; nécessite un plug-in)  <br/> |& #x 2714 ; (& #x 2776 ; Sous Windows uniquement ; nécessite un plug-in)  <br/> |& #x 2714 ; (& #x 2776 ; Sous Windows uniquement ; nécessite un plug-in)  <br/> |
|Laisser un autre utilisateur de prendre le contrôle de votre bureau partagé ou d’un programme  <br/> |& #x 2714 ;|||||
|Ajouter des participants anonymes (si option activée)  <br/> |& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|
|Inviter des participants par un nom  <br/> |& #x 2714 ;|& #x 2714 ;||||
|Inviter des participants par numéro de téléphone  <br/> |& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|
|Inviter des participants par courrier électronique  <br/> |& #x 2714 ;||& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|
|Utiliser les réunions audio rendez-vous  <br/> |& #x 2714 ; & #x 2777 ; |& #x 2714 ; & #x 2777 ; |& #x 2714 ; & #x 2777 ; |& #x 2714 ; & #x 2777 ; |& #x 2714 ; & #x 2777 ; |
|Démarrer une réunion Conférence maintenant  <br/> |& #x 2714 ;|& #x 2714 ;||||
|Enregistrer une réunion  <br/> |& #x 2714 ;|||||
|Ajouter et télécharger des pièces jointes  <br/> |& #x 2714 ;||& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|
|Ajouter et présenter des fichiers Microsoft PowerPoint  <br/> |& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|
|Parcourir des fichiers Microsoft PowerPoint  <br/> |& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|
|Ajouter et modifier des notes de réunion OneNote  <br/> |& #x 2714 ;||Modifier uniquement (pas ajouter)  <br/> |Modifier uniquement (pas ajouter)  <br/> |Modifier uniquement (pas ajouter)  <br/> |
|Utiliser un tableau blanc  <br/> |& #x 2714 ;||& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|
|Mener des sondages  <br/> |& #x 2714 ;||& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|
|Télécharger des fichiers pour les partager avec des tiers  <br/> |& #x 2714 ;||& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|
|Planifier une réunion ou une conférence  <br/> |Outlook ou Skype pour Business Web Scheduler  <br/> |Outlook ou Skype pour Business Web Scheduler  <br/> |Skype pour Business Web Scheduler  <br/> |Skype pour Business Web Scheduler  <br/> |Skype pour Business Web Scheduler  <br/> |
|Q&amp;un responsable  <br/> |& #x 2714 ;||& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|
|Désactiver la vidéo des participants  <br/> |& #x 2714 ;|||||
|Désactiver la messagerie instantanée pour la réunion  <br/> |& #x 2714 ;||& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|
|Désactiver le micro  <br/> |& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|& #x 2714 ;|
|Inviter tout le monde à participer  <br/> |& #x 2714 ;|||||
|Produire une diffusion de réunion Skype  <br/> |& #x 2714 ;|||||
   
 & #x 2776 ;  Participants ne peut pas contrôler les postes de travail qui sont partagées par Skype pour les entreprises pour Mac, Lync pour Mac 2011 ou Office Communicator pour Mac 2011 utilisateurs. Cela ne peut fonctionner pour lʼapplication Skype Entreprise Web sur Max OSX.
  
 & #x 2777 ;  Pour Skype pour Business Online, cette fonctionnalité nécessite Microsoft PSTN conférence, la messagerie unifiée Exchange, ou un 3ème partie fournisseur de services d’audioconférence.
  
 & #x 2778 ;  Lync pour Mac 2011 client ne peut pas afficher les présentations Microsoft Office PowerPoint 2013 lorsqu’ils ont été partagées dans une conférence par le Skype pour l’application Web de gestion.
  
## <a name="known-issues-and-troubleshooting"></a>Problèmes connus et résolution des problèmes
<a name="BKMK_Conferencing"> </a>

Pour les utilisateurs finaux, l' [aide en ligne](https://aka.ms/smahelp) pour ces applications est toujours disponible. PROFESSIONNELS de l’informatique doivent connaître les problèmes suivants :
  
- Si l’utilisateur n’est pas sur un réseau configuré pour satisfaire les [exigences de réseau](meetings-clients.md#Network), de nombreuses fonctionnalités de l’application peuvent ou peut ne pas fonctionneront et qu’ils ne sont peut-être pas en mesure de se connecter à la réunion.
    
- Certains utilisateurs peuvent avoir des ordinateurs d’entreprise administré avec autorisation désactivée pour installer des applications. pour les utilisateurs, ni application est une option, mais les utilisateurs [Smartphone](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-1) et [tablette](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-2) peuvent être en mesure d’installer les clients mobiles économiques qu'ils peuvent utiliser pour participer à des réunions.
    
    Autres problèmes d’installation sont également abordées dans les [rubriques d’aide](https://support.office.com/en-us/article/Trouble-installing-the-Skype-for-Business-Web-App-plug-in-958fc5f1-2d6f-42e3-815d-a9516c591274?ui=en-US&amp;rs=en-US&amp;ad=US). 
    
- Les utilisateurs peuvent voir un pare-feu avertissement la première fois qu’ils exécutent l’application de réunions. Il peut être invité à ouvrir des ports pour optimiser l’expérience, et cela peut nécessiter des privilèges d’administrateur sur l’ordinateur que ne disposent pas. L’application doit toujours fonctionner et l’utilisateur peut en toute sécurité refuser ouvrir les ports requis. 
    
- Vous devez avoir [ActiveX activé sans filtrage](https://support.office.com/en-us/article/Turn-off-ActiveX-filtering-for-Skype-for-Business-Web-App-b6de8ff6-ac7e-4e2f-b18c-2f13db643c41?ui=en-US&amp;rs=en-US&amp;ad=US) dans Internet Explorer, même si Internet Explorer n’est pas le navigateur par défaut. Dans Skype pour l’application Web de gestion, d’un contrôle ActiveX, un module de petite taille qui ajoute des fonctionnalités supplémentaires à une application web ou un autre programme — est requis pour l’audio, vidéo et partage d’écran.
    
- Pour certaines fonctionnalités de Skype pour Business Web App fonctionne correctement, vous devez autoriser votre navigateur pour [Enregistrer des cookies](https://support.office.com/en-us/article/Allow-cookies-for-Skype-Meetings-App-Skype-for-Business-Web-App-2108276b-b5c3-484b-bf2b-dac6eeba4c93) sur votre ordinateur ou le périphérique.
    
- Vous pouvez nécessaire pour [Activer JavaScript](https://support.office.com/en-us/article/Turn-on-JavaScript-for-Skype-Meetings-App-Skype-for-Business-Web-App-3d997bf9-637c-4fe6-8ee3-9e62bfda52cd) prend en charge dans votre navigateur pour certains Skype pour les fonctionnalités de l’application Web de gestion fonctionnent comme prévu.
    
### <a name="aes-support"></a>Prise en charge AES 

À compter de Skype pour Business Server 2015 CU5, AES n’est pas pris en charge pour ASP.NET 4.6 et cela peut entraîner Skype réunions application Échec de démarrage. [Exigences de chiffrement en raison d’ASP .NET 4.5](../security/user-and-client-authentication.md#cryptographic-requirements-due-to-asp-net-45) a plus de détails.
  
## <a name="see-also"></a>Voir aussi
<a name="BKMK_Conferencing"> </a>

[Déployer des clients Web téléchargeables Skype pour Business Server](../../deploy/deploy-clients/deploy-web-downloadable-clients.md)

[Plateformes prises en charge pour l’application de réunions Skype](https://support.office.com/en-US/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)
