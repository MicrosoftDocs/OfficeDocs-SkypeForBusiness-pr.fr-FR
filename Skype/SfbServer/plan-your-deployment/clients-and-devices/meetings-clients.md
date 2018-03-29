---
title: Planifier des clients de réunions (Web App et réunions App)
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 31e95e16-f79f-46c6-b123-973fa56a824e
description: 'Résumé : Les professionnels de l’informatique doivent vérifier la prise en charge requise pour le Skype pour Business Web App et Skype réunions App lors de la planification pour Skype pour Business Server 2015. Cet article n’est pas conçu pour les utilisateurs de ces applications.'
ms.openlocfilehash: 608a85e36d436bbcee21e4ed86dc9b5c815088ed
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-meetings-clients-web-app-and-meetings-app"></a>Planifier des clients de réunions (Web App et réunions App)
 
**Résumé :** Professionnels de l’informatique doivent vérifier la prise en charge requise pour le Skype pour Business Web App et Skype réunions App lors de la planification pour Skype pour Business Server 2015. Cet article n’est pas conçu pour les utilisateurs de ces applications.
  
Une fois que vous avez implémenté Skype pour Business Server, les utilisateurs de votre organisation auront sans doute le Skype pour client d’entreprise installé dans le cadre du processus de déploiement. 
  
Les utilisateurs peuvent créer des réunions et inviter des utilisateurs à partir de l’extérieur de l’organisation et les participants de la réunion n’est peut-être pas n’importe quelle version de la Skype pour client d’entreprise. Lorsque ces utilisateurs cliquez sur l’URL de l’invitation à une réunion, l’absence d’un client sera détecté et l’invité sans un Skype pour client d’entreprise sera demandée pour télécharger et installer un client léger, réunions uniquement afin de pouvoir se joindre à la réunion.
  
> [!NOTE]
> Le Skype pour Business Web App et application de réunions Skype ne sont disponibles que lorsque vous tentez de connecter à une réunion sans avoir un Skype pour les entreprises. Aide de l’utilisateur pour ces applications est à [https://aka.ms/smahelp](https://aka.ms/smahelp). 
  
> [!NOTE]
> Vous ne peut pas pré-installer le soit Skype pour Business Web App ou application de réunions Skype, mais les utilisateurs de [Tablet PC](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-2) et de [Smartphone](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-1) peuvent être en mesure d’installer des clients mobiles peu coûteux, qu'ils peuvent utiliser pour assister aux réunions.
  
Par défaut, le serveur qui héberge la réunion dirige l’utilisateur à télécharger et installer Skype pour Business Web App joindre la réunion. Le Skype pour Business Web App est stocké sur le serveur frontal et est envoyée au participant à la réunion. 
  
Commençant par Skype pour Business Server CU5, application de réunions Skype est disponible comme un remplacement pour Skype pour Business Web App, mais l’application de réunions Skype exige la configuration supplémentaire décrite dans [Activer Skype réunions App pour remplacer Skype pour Business Web App (facultatif)](../../deploy/deploy-clients/deploy-web-downloadable-clients.md#SMA_Enable). Si Skype réunions App est activée, les utilisateurs télécharge la dernière version de l’application à partir de l’Office 365 réseau CDN (Content Delivery) et non à partir de votre Skype pour Business server.
  
Application de réunions Skype offre un navigateur simplifié pour le téléchargement et l’installation de l’application et participation à des réunions, y compris la jointure d’un seul clic pour les utilisateurs d’Internet Explorer. App de réunions Skype dispose également de nombreuses améliorations sur theSkype pour Business Web App pour la fiabilité et l’expérience de la réunion. 
  
> [!NOTE]
> À Skype pour Business Server 2015 CU5 ou version ultérieure, réunions tenues d’entreprise en ligne à l’aide de Skype n’envoie plus un utilisateur sans le Skype pour Business Web App, ils seront envoyées à la place application de réunions Skype. À partir de Skype pour Business Server 2015 CU5 ou version ultérieure, si vous [Activez Skype réunions App pour remplacer Skype pour Business Web App (facultatif)](../../deploy/deploy-clients/deploy-web-downloadable-clients.md#SMA_Enable), les utilisateurs sans s’être envoyé App de réunions Skype au lieu de Skype pour Business Web App. 
  
## <a name="software-requirements"></a>Configuration logicielle requise
<a name="OS-Browser"> </a>

Pour utiliser le Skype pour l’application Web de l’entreprise, un utilisateur doit avoir une des opérations suivantes pris en charge les combinaisons de navigateur et de système d’exploitation. 
  
**Système d’exploitation et navigateur minimale prise en charge Skype pour Business Web App**


|**Système d'exploitation**|**Bord**|**Internet Explorer 11 ou version ultérieure 32 et 64 bits**|**32 bits et 64 bits Internet Explorer 10 ou une version ultérieure**|**32 bits et 64 bits Internet Explorer 9 ou version ultérieure**|**32 bits et 64 bits Version de Firefox 12.X ou ultérieur**|**32 bits et 64 bits Version de Chrome 18.X ou version ultérieure**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Windows 10  <br/> |Oui  <br/> |Oui  <br/> |N/A  <br/> |N/A  <br/> |Oui  <br/> |Oui & #x 2778 ; <br/> |
| Windows 8.1 & #x 2776 ; <br/> |N/A  <br/> |Oui  <br/> |N/A  <br/> |N/A  <br/> |Oui  <br/> |Oui & #x 2778 ; <br/> |
| Windows 8 (Intel basé) & #x 2776 ; <br/> |N/A  <br/> |N/A  <br/> |Oui  <br/> |N/A  <br/> |Oui  <br/> |Oui & #x 2778 ; <br/> |
|Windows 7 avec SP1 & #x 2777 ; <br/> |N/A  <br/> |Oui  <br/> |Non  <br/> |Non  <br/> |Oui  <br/> |Oui & #x 2778 ; <br/> |
|Windows Server 2008 R2 avec SP1 & #x 2777 ; <br/> |N/A  <br/> |Oui  <br/> |Oui  <br/> |Oui  <br/> |Oui  <br/> |Oui & #x 2778 ; <br/> |
|macOS 10,8 et versions ultérieures (basé sur Intel) & #x 2777 ; <br/> |N/A  <br/> |N/A  <br/> |N/A  <br/> |N/A  <br/> |Oui  <br/> |Oui & #x 2779 ; <br/> |
   
& #x 2776 ; Le Skype plug-in du navigateur Business Web App nécessite un plug-in Partage spécifique à utiliser sur ordinateur de voix, vidéo, partage et affichage de partage d’écran en cours et autres fonctionnalités. Un participant à la réunion est donné la possibilité d’installer le partage de plug-in lorsqu’ils joignent la réunion ou lorsqu’ils engagent une de ces fonctionnalités. Sur Windows 8 et Windows 8.1, le plug-in de partage peut être installé uniquement si vous exécutez Internet Explorer 10 ou 11 de l’Explorateur Internet pour le bureau. Ces fonctionnalités ne sont pas disponibles avec Internet Explorer 10 ou Internet Explorer 11, version non-bureau.
  
& #x 2777 ; Sur la prise en charge de Windows 7, Windows Server 2008 R2 et les systèmes d’exploitation Macintosh, toutes les fonctionnalités sont disponibles, y compris vocales basées sur l’ordinateur, vidéo, affichage de l’application, le partage d’application, bureau d’affichage et le partage de bureau. Pour utiliser ces fonctionnalités, vous devez installer un plug-in quand vous y êtes invité. Veuillez noter que la version Mac OS X 10.7 n’est plus prise en charge.
  
& #x 2778 ; L’accès à l’application Web à partir de Chrome sous Windows lancera un petit programme qui charge l’application Web dans un cadre Internet Explorer incorporé. Ce programme requiert l'une des versions d'Internet Explorer prises en charge pour charger correctement l'application Web.
  
& #x 2779 ; L’accès à l’application Web à partir de Chrome sur Mac lancera un petit programme qui charge l’application Web dans un cadre de Safari incorporé. Ce programme nécessite la prise en charge des versions de Safari être installé pour l’application Web se charge correctement.
  
> [!NOTE]
> Les utilisateurs d’Office 365 peuvent utiliser Internet Explorer 10 ou une version ultérieure avec Skype pour les entreprises. 
  
### <a name="skype-meetings-app"></a>Application Réunions Skype

L’application de réunions Skype s’exécute comme une application sur les ordinateurs utilisant Windows 10, Windows 8.1, Windows 8, Windows 7, avec 32 et 64 bits Internet Explorer 11 ou ultérieur installé. 
  
L’application s’exécute également sur macOS 10.10 ou ultérieure systèmes d’exploitation avec aucune dépendance de navigateur spécifique. 
  
Pour toutes les autres dépendances, reportez-vous aux [plates-formes prises en charge pour l’application de réunions Skype](https://support.office.com/en-US/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)
  
## <a name="hardware-requirements"></a>Configuration matérielle requise
<a name="OS-Browser"> </a>

La configuration matérielle requise est déterminée par le système d'exploitation et le navigateur. Les fonctionnalités vocales et de téléphonie nécessitent un micro et des haut-parleurs, un casque équipé d'un micro, ou un périphérique équivalent compatible avec l'ordinateur. Les fonctionnalités vidéo nécessitent un périphérique vidéo compatible avec l'ordinateur. Pour obtenir des informations détaillées sur la prise en charge du matériel vidéo et de la qualité vidéo attendue, consultez [Skype pour les résolutions vidéo du client entreprise](video-resolutions.md).
  
## <a name="network-requirements"></a>Conditions de réseau requises
<a name="Network"> </a>

Si un utilisateur de Skype pour des expériences Business Web App ou application de réunions Skype réunion des problèmes de connexion, il est probable qu’est le qu'infrastructure de réseau de leur organisation n’est pas configuré pour prendre en charge Office 365 comme décrit dans [les URL d’Office 365 et de plages d’adresses IP](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US). C’est le cas si la réunion a été créée par un utilisateur de Skype pour Business Online ou Skype pour Business Server 2015. 
  
Si l’utilisateur est sur un réseau non configuré comme décrit, de nombreuses fonctionnalités de l’application peuvent ou peut ne pas fonctionnent et qu’ils ne soient pas en mesure de se connecter à la réunion à tous.
  
## <a name="supported-meetings-features"></a>Fonctionnalités des réunions prises en charge
<a name="BKMK_Conferencing"> </a>

Ce tableau compare les fonctionnalités de réunions disponibles pour les utilisateurs de Skype pour client d’entreprise, Skype pour Business Web App, application de réunions Skype et Lync Web App. Lync Web App est répertorié pour la fonctionnalité comparaison : un utilisateur peut uniquement être téléchargement et l’utilisation Lync Web App si la réunion a été hébergée sur un serveur Lync 2013.
  

|**Fonctionnalité**|**Skype pour client d’entreprise 2016**|**Skype pour le commerce sur le client Mac**|**Application de réunions Skype**|**Skype pour Business Web App**|**Lync Web App**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Ajouter l'audio de l'ordinateur  <br/> |![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)(requiert un plug-in)  <br/> |![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)(requiert un plug-in)  <br/> |![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)(requiert un plug-in)  <br/> |
|Ajouter la vidéo  <br/> |![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)(requiert un plug-in)  <br/> |![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)(requiert un plug-in)  <br/> |![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)(requiert un plug-in)  <br/> |
|Commutateur audio pour un téléphone pour que les participants authentifiés  <br/> |![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|
|Commutateur audio pour un téléphone pour les participants de l’invité  <br/> |![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|||
|Afficher une vidéo à plusieurs (vue galerie)  <br/> |![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|
|Partage d'écran vidéo  <br/> |![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png) (pour les réunions hébergées dans Skype pour Business Online uniquement) <br/> |![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)(Lecture seule)  <br/> |||
|Utiliser des commandes de présentateur lors des réunions  <br/> |![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|
|Accéder à une liste détaillée des réunions  <br/> |![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|
|Participer à une conversation par messagerie instantanée à plusieurs  <br/> |![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|
|Définir les messages instantanés sur Importance haute  <br/> |![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|||||
|Partager le bureau (si option activée)  <br/> |![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)![pied de page de lecture 1](../../media/817e529d-a5e1-4969-a195-f3ba3c6a2e7f.png)(requiert un plug-in)  <br/> |![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)![pied de page de lecture 1](../../media/817e529d-a5e1-4969-a195-f3ba3c6a2e7f.png)(requiert un plug-in)  <br/> |![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)![pied de page de lecture 1](../../media/817e529d-a5e1-4969-a195-f3ba3c6a2e7f.png)(requiert un plug-in)  <br/> |
|Partager un programme (si option activée)  <br/> |![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)||![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)(Sous Windows uniquement ; nécessite un plug-in)  <br/> |![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)(Sous Windows uniquement ; nécessite un plug-in)  <br/> |![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)(Sous Windows uniquement ; nécessite un plug-in)  <br/> |
|Prendre le contrôle d’un bureau partagé d’un autre utilisateur ou un programme  <br/> |![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)||![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)(Sous Windows uniquement ; nécessite un plug-in)  <br/> |![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)(Sous Windows uniquement ; nécessite un plug-in)  <br/> |![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)(Sous Windows uniquement ; nécessite un plug-in)  <br/> |
|Autoriser un autre utilisateur de prendre le contrôle de votre programme ou votre bureau partagé  <br/> |![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|||||
|Ajouter des participants anonymes (si option activée)  <br/> |![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|
|Inviter des participants par nom  <br/> |![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)||||
|Inviter des participants, par numéro de téléphone  <br/> |![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|
|Inviter des participants par courrier électronique  <br/> |![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)||![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|
|Utiliser les réunions audio rendez-vous  <br/> |![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)![pied de page de lecture 2](../../media/e366e0ee-8e3f-4e83-8009-2e7eb5674a18.png)|![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)![pied de page de lecture 2](../../media/e366e0ee-8e3f-4e83-8009-2e7eb5674a18.png)|![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)![pied de page de lecture 2](../../media/e366e0ee-8e3f-4e83-8009-2e7eb5674a18.png)|![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)![pied de page de lecture 2](../../media/e366e0ee-8e3f-4e83-8009-2e7eb5674a18.png)|![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)![pied de page de lecture 2](../../media/e366e0ee-8e3f-4e83-8009-2e7eb5674a18.png)|
|Démarrer une réunion Conférence maintenant  <br/> |![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)||||
|Enregistrer une réunion  <br/> |![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|||||
|Ajouter et télécharger les pièces jointes  <br/> |![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)||![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|
|Ajouter et présenter des fichiers Microsoft PowerPoint  <br/> |![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|
|Parcourir des fichiers Microsoft PowerPoint  <br/> |![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|
|Ajouter et modifier des notes de réunion OneNote  <br/> |![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)||Modifier uniquement (pas ajouter)  <br/> |Modifier uniquement (pas ajouter)  <br/> |Modifier uniquement (pas ajouter)  <br/> |
|Utiliser un tableau blanc  <br/> |![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)||![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|
|Mener des sondages  <br/> |![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)||![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|
|Télécharger des fichiers pour les partager avec des tiers  <br/> |![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)||![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|
|Planifier une réunion ou une conférence  <br/> |Outlook ou Skype pour le Planificateur Web de professionnels  <br/> |Outlook ou Skype pour le Planificateur Web de professionnels  <br/> |Skype pour le Planificateur Web de professionnels  <br/> |Skype pour le Planificateur Web de professionnels  <br/> |Skype pour le Planificateur Web de professionnels  <br/> |
|Q&amp;un gestionnaire  <br/> |![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)||![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|
|Désactiver la vidéo des participants  <br/> |![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|||||
|Désactiver la messagerie instantanée pour la réunion  <br/> |![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)||![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|
|Public muet  <br/> |![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|
|Inviter tout le monde à participer  <br/> |![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|||||
|Produire une diffusion de réunion Skype  <br/> |![liste de contrôle associée](../../media/d551a87b-3ffe-4d16-b190-352a2042f65d.png)|||||
   
![pied de page de lecture 1](../../media/817e529d-a5e1-4969-a195-f3ba3c6a2e7f.png) Les participants ne peuvent pas contrôler les postes de travail qui sont partagés par Lync pour Mac 2011 ou Communicator pour Mac 2011 utilisateurs. Les utilisateurs Lync pour Mac 2011 et Communicator pour Mac 2011 peuvent contrôler les bureaux partagés par les utilisateurs Windows. Cela ne peut fonctionner pour lʼapplication Skype Entreprise Web sur Max OSX.
  
![pied de page de lecture 2](../../media/e366e0ee-8e3f-4e83-8009-2e7eb5674a18.png) Pour Skype pour professionnels en ligne, cette fonctionnalité requiert Microsoft RTPC Conferencing, la messagerie unifiée Exchange, ou une 3ème partie fournisseur de conférence audio.
  
![pied de page de lecture 3](../../media/f58a4c2c-e4b3-4954-9eee-1d5f7a89da53.png) Le Lync pour Mac 2011 client ne peut pas afficher des présentations PowerPoint de Microsoft Office 2013 lorsqu’ils ont été partagées dans une conférence par le Skype pour Business Web App.
  
## <a name="known-issues-and-troubleshooting"></a>Problèmes connus et dépannage
<a name="BKMK_Conferencing"> </a>

Pour les utilisateurs finaux, l' [aide en ligne](https://aka.ms/smahelp) pour ces applications est immédiatement disponible. Professionnels de l’informatique doivent être conscients des problèmes suivants :
  
- Si l’utilisateur n’est pas sur un réseau configuré pour répondre aux [exigences en matière de réseau](meetings-clients.md#Network), de nombreuses fonctionnalités de l’application peuvent ou peut ne pas fonctionnent et qu’ils ne soient pas en mesure de se connecter à la réunion à tous.
    
- Certains utilisateurs peuvent avoir des ordinateurs d’entreprise administré désactivé autorisé à installer des applications. pour les utilisateurs, ni app est une option, mais les utilisateurs de [Tablet PC](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-2) et de [Smartphone](https://products.office.com/en-us/skype-for-business/download-app?tab=tabs-1) peuvent être en mesure d’installer des clients mobiles peu coûteux, qu'ils peuvent utiliser pour assister aux réunions.
    
    Autres problèmes d’installation sont aussi couverts par les [rubriques d’aide](https://support.office.com/en-us/article/Trouble-installing-the-Skype-for-Business-Web-App-plug-in-958fc5f1-2d6f-42e3-815d-a9516c591274?ui=en-US&amp;rs=en-US&amp;ad=US). 
    
- Les utilisateurs peuvent voir un pare-feu avertissement la première fois qu’ils s’exécutent à l’application de réunions. Il peut être invité à ouvrir des ports pour optimiser l’expérience, et cela peut nécessiter des privilèges d’administrateur sur l’ordinateur que ne disposent pas. L’application doit toujours fonctionner, et l’utilisateur peut refuser en toute sécurité ouvrir les ports requis. 
    
- Vous devez avoir [ActiveX est activé sans le filtrage](https://support.office.com/en-us/article/Turn-off-ActiveX-filtering-for-Skype-for-Business-Web-App-b6de8ff6-ac7e-4e2f-b18c-2f13db643c41?ui=en-US&amp;rs=en-US&amp;ad=US) dans Internet Explorer, même si Internet Explorer n’est pas votre navigateur par défaut. Dans Skype pour l’application Web de l’entreprise, un contrôle ActiveX, un petit module qui ajoute des fonctionnalités supplémentaires à une application web ou un autre programme, est requis pour l’audio, vidéo et partage d’écran.
    
- Pour certaines fonctionnalités de Skype pour Business Web App fonctionne correctement, vous devez autoriser votre navigateur à [Enregistrer des cookies](https://support.office.com/en-us/article/Allow-cookies-for-Skype-Meetings-App-Skype-for-Business-Web-App-2108276b-b5c3-484b-bf2b-dac6eeba4c93) sur votre ordinateur ou le périphérique.
    
- Vous pouvez est nécessaire pour [Activer JavaScript](https://support.office.com/en-us/article/Turn-on-JavaScript-for-Skype-Meetings-App-Skype-for-Business-Web-App-3d997bf9-637c-4fe6-8ee3-9e62bfda52cd) prend en charge dans votre navigateur pour certains Skype pour les fonctionnalités d’entreprise Web App à fonctionner comme prévu.
    
### <a name="cryptographic-requirements-due-to-asp-net-45"></a>Exigences cryptographiques en raison d’ASP .NET 4.5

À Skype pour Business Server 2015 CU5, AES n’est pas prise en charge de ASP.NET 4.6 et cela peut entraîner des App de réunions Skype pour ne pas démarrer. Si un client utilise AES comme la valeur de validation de la clé machine que vous devez rétablir la valeur de la clé machine SHA-1 ou un autre algorithme pris en charge au niveau du site d’application de réunions Skype sur IIS. Si nécessaire, reportez-vous à la section [Gestion de la Configuration IIS 8.0 ASP.NET](https://docs.microsoft.com/en-us/iis/get-started/whats-new-in-iis-8/iis-80-aspnet-configuration-management) pour obtenir des instructions.
  
Autres valeurs prises en charge sont :
  
- HMACSHA256
    
- HMACSHA384
    
- HMACSHA512
    
 Les valeurs MD5, 3DES et AES ne sont plus autorisées, comme une seule fois dans ASP.NET 4. [Améliorations de chiffrement dans ASP.NET 4.5, pt 2](https://blogs.msdn.microsoft.com/webdev/2012/10/23/cryptographic-improvements-in-asp-net-4-5-pt-2/) a plus de détails.
  
## <a name="see-also"></a>Voir aussi
<a name="BKMK_Conferencing"> </a>

#### 

[Déployer des clients Web téléchargeables Skype pour Business Server 2015](../../deploy/deploy-clients/deploy-web-downloadable-clients.md)
#### 

[Plates-formes prises en charge pour l’application de réunions Skype](https://support.office.com/en-US/client/results?Shownav=true&amp;lcid=1033&amp;ns=SKFBWA&amp;version=15&amp;omkt=en-US&amp;ver=15&amp;HelpID=SfBWebApp4001)

