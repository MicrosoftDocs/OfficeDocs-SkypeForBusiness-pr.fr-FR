---
title: Planifier les clients Meetings (application Web et application réunions)
ms.author: serdars
author: SerdarSoysal
ms.reviewer: PhillipGarding
manager: serdars
ms.date: 2/16/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 31e95e16-f79f-46c6-b123-973fa56a824e
description: 'Résumé : Les professionnels de l’informatique doivent examiner les exigences de prise en charge de l’application Application Web Skype Entreprise et Skype Meetings lors de la planification de Skype Entreprise Server. Cet article n’est pas destiné aux utilisateurs de ces applications.'
ms.openlocfilehash: bf6eb62291309500c942e83c41e898b5a4d25531
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62395156"
---
# <a name="plan-for-meetings-clients-web-app-and-meetings-app"></a>Planifier les clients Meetings (application Web et application réunions)
 
**Résumé :** Les professionnels de l’informatique doivent examiner les exigences de prise en charge Application Web Skype Entreprise et Skype l’application Réunions lors de la planification de Skype Entreprise Server. Cet article n’est pas destiné aux utilisateurs de ces applications.
  
Une fois que vous avez implémenté Skype Entreprise Server, les utilisateurs de votre organisation auront probablement le client Skype Entreprise installé dans le cadre du processus de déploiement. 
  
Par la suite, ces utilisateurs peuvent créer des réunions et inviter des utilisateurs extérieurs à l’organisation, et ces invités peuvent ne pas avoir de version du client Skype Entreprise client. Lorsque ces utilisateurs cliquent sur l’URL de l’invitation à la réunion, l’absence de client est détectée et l’invité sans client Skype Entreprise est invité à télécharger et installer un client léger, uniquement pour les réunions, afin qu’il puisse participer à la réunion.
  
> [!NOTE]
> L Application Web Skype Entreprise et Skype Meetings App sont disponibles uniquement lorsque vous essayez de vous connecter à une réunion sans avoir Skype Entreprise. L’aide de l’utilisateur pour ces applications est sur [https://aka.ms/smahelp](https://aka.ms/smahelp). 
  
> [!NOTE]
> Vous ne pouvez pas préinstaller l’application Application Web Skype Entreprise ou Skype Meetings, mais les utilisateurs de smartphones [](https://products.office.com/skype-for-business/download-app?tab=tabs-1) et de tablettes peuvent installer des clients mobiles peu coûteux qu’ils peuvent utiliser pour participer à des réunions.[](https://products.office.com/skype-for-business/download-app?tab=tabs-2)
  
Par défaut, le serveur hébergeant la réunion dirige l’utilisateur vers le téléchargement et l’installation Application Web Skype Entreprise pour participer à la réunion. Le Application Web Skype Entreprise est stocké sur le serveur frontal et est envoyé au participant à la réunion. 
  
Par Skype Entreprise Server, Skype Meetings App (sur Windows) et Skype Entreprise pour Mac (sur Mac) sont disponibles en remplacement de Application Web Skype Entreprise  à partir de CU5, mais la fourniture des applications de remplacement nécessite la configuration supplémentaire décrite dans [Enable Skype Meetings App pour remplacer Application Web Skype Entreprise (facultatif).](../../deploy/deploy-clients/deploy-web-downloadable-clients.md#SMA_Enable). Si Skype Application réunions et Skype Entreprise pour Mac sont activés, les utilisateurs téléchargent la dernière version des applications à partir du Microsoft 365 ou Office 365 réseau de distribution de contenu (CDN) que depuis votre Skype Entreprise serveur. Pour Skype Entreprise Server 2019, l’utilisation Skype l’application Meetings Skype Entreprise pour Mac est la seule option.
  
Skype Meetings App offre une expérience de navigateur simplifiée pour télécharger et installer l’application et participer à des réunions, notamment en un clic pour les utilisateurs d’Internet Explorer. Skype Meetings App présente également de nombreuses améliorations par rapport à la Application Web Skype Entreprise en matière de fiabilité et d’expérience de réunion. 
  
> [!NOTE]
> À Skype Entreprise Server CU5 2015 ou version ultérieure, les réunions organisées à l’aide de Skype Entreprise Online n’envoient plus l’Application Web Skype Entreprise à un utilisateur sans client, mais elles sont envoyées Skype Meetings App (sur Windows) ou Skype Entreprise pour Mac (sur Mac). À partir de Skype Entreprise Server CU5 2015 ou ultérieure, si vous activez l’application réunions Skype pour remplacer [Application Web Skype Entreprise (facultatif),](../../deploy/deploy-clients/deploy-web-downloadable-clients.md#SMA_Enable) les utilisateurs sans client seront Skype l’application Réunions ou Skype Entreprise pour Mac au lieu de Application Web Skype Entreprise. 
  
## <a name="software-requirements"></a>Configuration logicielle requise
<a name="OS-Browser"> </a>

Pour utiliser le Application Web Skype Entreprise, un utilisateur doit avoir l’une des combinaisons de navigateur et de système d’exploitation prise en charge suivantes. 
  
**Prise en charge minimale du système d’exploitation et du navigateur pour Application Web Skype Entreprise**

| Système d’exploitation | Microsoft Edge | Internet Explorer 11 32 et 64 bits ou ultérieur | 32 bits et 64 bits Internet Explorer 10 ou ultérieure | Internet Explorer 9 32 et 64 bits ou ultérieur | Version 32 et 64 bits de Safari 6.2.8 - 11.X | Version 32 et 64 bits de Chrome 18.X ou version ultérieure |
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Windows 10  <br/> |Oui  <br/> |Oui  <br/> |N/A  <br/> |N/A  <br/> |S/O  <br/> |Oui, &#x2778; <br/> |
|Windows 8.1 &#x2776; <br/> |N/D  <br/> |Oui  <br/> |N/A  <br/> |N/A  <br/> |S/O <br/> |Oui, &#x2778; <br/> |
|Windows 8 (basé sur Intel) &#x2776; <br/> |N/A  <br/> |N/A  <br/> |Oui  <br/> |N/A <br/> |N/A  <br/> |Oui, &#x2778; <br/> |
|Windows 7 avec sp1 &#x2777; <br/> |N/D  <br/> |Oui  <br/> |Non  <br/> |Non  <br/> |N/D <br/>|Oui, &#x2778; <br/> |
|Windows Server 2008 R2 avec SP1 &#x2777; <br/> |N/D  <br/> |Oui  <br/> |Oui  <br/> |Oui  <br/> |N/A <br/>|Oui, &#x2778; <br/> |
|MacOS 10.8 et les ultérieures (basés sur Intel) &#x2777; <br/> |N/A  <br/> |N/A  <br/> |N/A  <br/> |S/O  <br/> |Oui  <br/> |Oui <br/> |
   
&#x2776; le plug-in du navigateur Application Web Skype Entreprise nécessite un plug-in de partage spécifique pour utiliser la voix, la vidéo, le partage et l’affichage en continu du partage d’écran et d’autres fonctionnalités basées sur l’ordinateur. Un participant à la réunion a la possibilité d’installer le plug-in de partage lorsqu’il rejoint la réunion ou lorsqu’il lance l’une de ces fonctionnalités. Sur Windows 8 et Windows 8.1, le plug-in de partage ne peut être installé que si vous exécutez Internet Explorer 10 ou Internet Explorer 11 pour le Bureau. Ces fonctionnalités ne sont pas disponibles avec les versions non de bureau de Internet Explorer 10 et 11. Notez que Firefox et Safari version 12.0 et ultérieures ne sont plus pris en charge.
  
&#x2777; Sur les systèmes d’exploitation Windows 7, Windows Server 2008 R2 et Macintosh pris en charge, toutes les fonctionnalités sont disponibles, notamment la voix sur ordinateur, la vidéo, l’affichage d’applications, le partage d’applications, l’affichage de bureau et le partage de bureau. Pour utiliser ces fonctionnalités, vous devez installer un plug-in lorsque vous y êtes invité. Notez que Mac OS X version 10.7 n’est plus pris en charge.  Notez également que l’application web ne s’installera pas sur OS X 10.15 ou une ultérieure.  Nous vous recommandons d’utiliser la dernière version de Skype Entreprise pour Mac qui prend en charge les scénarios de jointeurs anonymes à l’avenir.
  
&#x2778;'accès à l’application Web à partir de Chrome sur Windows lance un petit programme qui charge l’application web dans un cadre Internet Explorer incorporé. Ce programme nécessite l’installation de l’une des versions d’Internet Explorer pris en charge pour que Web App se charge correctement.
  
> [!NOTE]
> Microsoft 365 et Office 365 utilisateurs peuvent utiliser Internet Explorer 10 ou une Skype Entreprise. 
  
### <a name="skype-meetings-app"></a>Application Réunions Skype

Skype Meetings App s’exécute en tant qu’application sur des ordinateurs utilisant Windows 10, Windows 8.1, Windows 8, Windows 7, avec Internet Explorer 11 32 et 64 bits ou ultérieur installé. 
  
Pour toute autre dépendance, reportez-vous aux plateformes prise en charge [pour Skype Meetings App](https://support.office.com/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)
  
### <a name="skype-for-business-for-mac"></a>Skype Entreprise pour Mac

Skype Entreprise pour Mac s’exécute sur des ordinateurs utilisant macOS version 10.8 ou ultérieure. 

## <a name="hardware-requirements"></a>Configuration matérielle requise
<a name="OS-Browser"> </a>

La configuration matérielle requise est déterminée par le système d’exploitation et le navigateur. Les fonctionnalités vocales et téléphoniques nécessitent un microphone et des haut-parleurs, un casque avec microphone ou un périphérique équivalent compatible avec l’ordinateur. Les fonctionnalités vidéo nécessitent un périphérique vidéo compatible avec l’ordinateur. Pour plus d’informations sur la prise en charge du matériel vidéo et la qualité vidéo attendue, voir [Skype Entreprise résolutions vidéo clientes](video-resolutions.md).
  
## <a name="network-requirements"></a>Configuration réseau requise
<a name="Network"> </a>

Si un utilisateur de l’application réunions Application Web Skype Entreprise ou Skype rencontre des problèmes de connexion, il est fort possible que l’infrastructure réseau de son organisation ne soit pas configurée pour prendre en charge les Office 365 comme décrit dans les URL et [plages d’adresses IP Office 365](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US). C’est le cas si la réunion a été créée par un utilisateur de Skype Entreprise Online ou Skype Entreprise Server. 
  
Si l’utilisateur se trouve sur un réseau qui n’est pas configuré comme décrit, de nombreuses fonctionnalités d’application peuvent ou non fonctionner et ne pas être en mesure de se connecter à la réunion.
  
## <a name="supported-meetings-features"></a>Fonctionnalités de réunions prise en charge
<a name="BKMK_Conferencing"> </a>

Ce tableau compare les fonctionnalités Meetings disponibles pour les utilisateurs du client Skype Entreprise, Application Web Skype Entreprise, Skype Meetings App et Lync Web App. Lync Web App est répertorié à des fins de comparaison des fonctionnalités : un utilisateur téléchargerait et utiliserait uniquement Lync Web App si la réunion était hébergée sur un serveur Lync 2013.

| Fonctionnalité/fonctionnalité | Skype Entreprise client 2016 ou 2019 | Skype Entreprise client mac | Application Réunions Skype | Skype Entreprise Web App | Lync Web App |
|:-----|:-----|:-----|:-----|:-----|:-----|
|Ajouter l’audio de l’ordinateur  <br/> |&#x2714;|&#x2714;|&#x2714; (nécessite un plug-in)  <br/> |&#x2714; (nécessite un plug-in)  <br/> |&#x2714; (nécessite un plug-in)  <br/> |
|Ajouter la vidéo  <br/> |&#x2714;|&#x2714;|&#x2714; (nécessite un plug-in)  <br/> |&#x2714; (nécessite un plug-in)  <br/> |&#x2714; (nécessite un plug-in)  <br/> |
|Basculer l’audio vers un téléphone pour les participants authentifiés  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Basculer l’audio vers un téléphone pour les participants invités  <br/> |&#x2714;|&#x2714;|&#x2714;|||
|Afficher la vidéo à plusieurs (vue galerie)  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Partage d'écran sur vidéo  <br/> |&#x2714;|&#x2714; <br/> |&#x2714;(Affichage seul)  <br/> |||
|Utiliser des commandes de présentateur lors des réunions  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Accéder à une liste de réunions détaillée  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Prendre part à une conversation par messagerie instantanée à plusieurs  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Définir les messages instantanés comme étant de haute importance  <br/> |&#x2714;|||||
|Partager le Bureau (si activée)  <br/> |&#x2714;|&#x2714;|&#x2714; (nécessite un plug-in)  <br/> |&#x2714; (nécessite un plug-in)  <br/> |&#x2714; (nécessite un plug-in)  <br/> |
|Partager un programme (si activée)  <br/> |&#x2714;||&#x2714;(Sur Windows uniquement ; nécessite un plug-in)  <br/> |&#x2714;(Sur Windows uniquement ; nécessite un plug-in)  <br/> |&#x2714;(Sur Windows uniquement ; nécessite un plug-in)  <br/> |
|Prendre le contrôle du bureau ou du programme partagé d’un autre utilisateur  <br/> |&#x2714;||&#x2714; (&#x2776; sur Windows uniquement ; nécessite un plug-in)  <br/> |&#x2714; (&#x2776; sur Windows uniquement ; nécessite un plug-in)  <br/> |&#x2714; (&#x2776; sur Windows uniquement ; nécessite un plug-in)  <br/> |
|Laisser un autre utilisateur prendre le contrôle de votre bureau ou programme partagé  <br/> |&#x2714;|||||
|Ajouter des participants anonymes (si activée)  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Inviter des participants par nom  <br/> |&#x2714;|&#x2714;||||
|Inviter des participants par numéro de téléphone  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Inviter des participants par courrier électronique  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Utiliser les réunions audio rendez-vous  <br/> |&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |&#x2714; &#x2777; |
|Lancer une réunion Conférence maintenant  <br/> |&#x2714;|&#x2714;||||
|Enregistrer une réunion  <br/> |&#x2714;|||||
|Ajouter et télécharger des pièces jointes  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Ajouter et présenter des fichiers Microsoft PowerPoint  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Naviguer dans les fichiers PowerPoint Microsoft  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Ajouter et modifier des OneNote de réunion  <br/> |&#x2714;||Modifier uniquement (pas ajouter)  <br/> |Modifier uniquement (pas ajouter)  <br/> |Modifier uniquement (pas ajouter)  <br/> |
|Utiliser un tableau blanc  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Mener des sondages  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Télécharger fichiers à partager avec d’autres personnes  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Planifier une réunion ou une conférence  <br/> |Outlook ou Planificateur Web Skype Entreprise  <br/> |Outlook ou Planificateur Web Skype Entreprise  <br/> |Planificateur Web Skype Entreprise  <br/> |Planificateur Web Skype Entreprise  <br/> |Planificateur Web Skype Entreprise  <br/> |
|Gestionnaire de QA&amp;  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Désactiver la vidéo du participant  <br/> |&#x2714;|||||
|Désactiver la messagerie instantanée de réunion  <br/> |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Désactiver le son de l’audience  <br/> |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Faire de tout le monde un participant  <br/> |&#x2714;|||||
|Produire une Réunion Skype diffusion  <br/> |&#x2714;|||||
   
 &#x2776; participants ne peuvent pas contrôler les bureaux partagés par les utilisateurs de Skype Entreprise pour Mac, Lync pour Mac 2011 ou Communicator pour Mac 2011. Cela ne fonctionne pas non plus pour les Application Web Skype Entreprise sur Max OSX.
  
 &#x2777; pour Skype Entreprise Online, cette fonctionnalité nécessite la conférence PSTN Microsoft, la messagerie unifiée Exchange ou un fournisseur tiers de services d’audioconférence.
  
 &#x2778; le client Lync pour Mac 2011 ne peut pas afficher les présentations Microsoft Office 2013 PowerPoint lorsqu’elles ont été partagées dans une conférence par le Application Web Skype Entreprise.
  
## <a name="known-issues-and-troubleshooting"></a>Problèmes connus et résolution des problèmes
<a name="BKMK_Conferencing"> </a>

Pour les utilisateurs finaux, [l’aide en ligne](https://aka.ms/smahelp) pour ces applications est facilement disponible. Les professionnels de l’informatique doivent être conscients des problèmes suivants :
  
- Si l’utilisateur se trouve sur un réseau qui n’est pas configuré pour répondre à la configuration [réseau requise,](meetings-clients.md#Network) de nombreuses fonctionnalités d’application peuvent ou non fonctionner et il est possible qu’ils ne puissent pas du tout se connecter à la réunion.
    
- Certains utilisateurs peuvent avoir des ordinateurs administrés par l’entreprise avec l’autorisation désactivée d’installer des applications. Pour ces utilisateurs, aucune des deux applications n’est une option[](https://products.office.com/skype-for-business/download-app?tab=tabs-2), mais les utilisateurs de smartphones et de tablettes peuvent être en mesure d’installer des clients mobiles peu coûteux qu’ils peuvent utiliser pour participer à des réunions.[](https://products.office.com/skype-for-business/download-app?tab=tabs-1)
    
    D’autres problèmes d’installation sont également traités dans les [rubriques d’aide](https://support.office.com/article/Trouble-installing-the-Skype-for-Business-Web-App-plug-in-958fc5f1-2d6f-42e3-815d-a9516c591274?ui=en-US&amp;rs=en-US&amp;ad=US). 
    
- Les utilisateurs peuvent voir un avertissement de pare-feu la première fois qu’ils exécutent l’application de réunions. Ils peuvent être invités à ouvrir des ports pour optimiser l’expérience, ce qui peut nécessiter des privilèges d’administrateur sur l’ordinateur dont ils n’ont peut-être pas. L’application doit toujours fonctionner et l’utilisateur peut refuser en toute sécurité d’ouvrir les ports demandés. 
    
- Vous devez avoir activé [ActiveX](https://support.office.com/article/Turn-off-ActiveX-filtering-for-Skype-for-Business-Web-App-b6de8ff6-ac7e-4e2f-b18c-2f13db643c41?ui=en-US&amp;rs=en-US&amp;ad=US) sans filtrage dans Internet Explorer, même si Internet Explorer n’est pas votre navigateur par défaut. Dans Application Web Skype Entreprise, un contrôle ActiveX (un petit module qui ajoute des fonctionnalités supplémentaires à une application web ou à un autre programme) est requis pour l’audio, la vidéo et le partage d’écran.
    
- Pour que certaines fonctionnalités Application Web Skype Entreprise fonctionnent correctement, vous devez autoriser votre navigateur à enregistrer les [cookies](https://support.office.com/article/Allow-cookies-for-Skype-Meetings-App-Skype-for-Business-Web-App-2108276b-b5c3-484b-bf2b-dac6eeba4c93) sur votre ordinateur ou appareil.
    
- Vous devrez peut-être activer la prise en charge [de JavaScript](https://support.office.com/article/Turn-on-JavaScript-for-Skype-Meetings-App-Skype-for-Business-Web-App-3d997bf9-637c-4fe6-8ee3-9e62bfda52cd) dans votre navigateur pour que certaines fonctionnalités Application Web Skype Entreprise fonctionnent comme prévu.
    
### <a name="aes-support"></a>Prise en charge d’AES 

Depuis Skype Entreprise Server CU5 2015, AES n’est pas pris en charge pour ASP.NET 4.6, ce qui peut entraîner l’échec du démarrage de Skype Meetings App. [Les exigences en matière de chiffrement ASP.NET 4.5](../security/user-and-client-authentication.md#cryptographic-requirements-due-to-asp-net-45) ont plus de détails.
  
## <a name="see-also"></a>Voir aussi
<a name="BKMK_Conferencing"> </a>

[Déployer des clients web téléchargeables dans Skype Entreprise Server](../../deploy/deploy-clients/deploy-web-downloadable-clients.md)

[Plateformes prise en charge pour Skype Application Réunions](https://support.office.com/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)
