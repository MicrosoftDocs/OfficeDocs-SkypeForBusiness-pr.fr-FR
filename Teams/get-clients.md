---
title: "Obtenir des clients pour Microsoft Teams"
author: LolaJacobsen
ms.author: lolaj
manager: lolaj
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
ms.reviewer: ninadara
description: "Découvrez comment utiliser les différents clients disponibles pour Microsoft Teams, notamment les clients Web, de bureau (Windows et Mac) et mobiles (Android, iOS, et Windows Phone)."
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6fd2edaa5d751cf323b3a866463811ee0ae633b3
ms.sourcegitcommit: 4b69ae91de3f82912eda3513cec65ae12e1ce2b2
ms.translationtype: HT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/03/2018
---
<a name="get-clients-for-microsoft-teams"></a>Obtenir des clients pour Microsoft Teams 
===========================

Microsoft Teams dispose de clients Web, de bureau (Windows et Mac) et mobiles (Android, iOS et Windows Phone). Ces clients requièrent une connexion Internet active et ne prennent pas en charge le mode hors connexion.

<a name="web-client"></a>Client Web 
----------------

Le client Web ([https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753)) est complet et fonctionnel, et peut être utilisé par divers navigateurs. À ce stade, le client Web ne prend pas en charge les communications en temps réel (c'est-à-dire les réunions et les appels en tête-à-tête). Le navigateur doit également être configuré de manière à autoriser les cookies tiers. 

Aucun plug-in ni téléchargement n'est requis pour exécuter Teams dans un navigateur Web.

Le client Web détecte la version du navigateur en se connectant à [https://teams.microsoft.com](https://go.microsoft.com/fwlink/?linkid=855753) et en cas de version non prise en charge, il bloquera l'accès à l'interface Web et recommandera de télécharger le client de bureau ou l'application mobile.

<a name="internet-browser-support"></a>Prise en charge du navigateur Internet
------------------------------
Microsoft Teams prend en charge les versions de navigateur suivantes : 
- Internet Explorer 11
- Microsoft Edge
- La dernière version de Chrome et les deux versions précédentes
- La dernière version de Firefox et les deux versions précédentes

> [!NOTE]
> Safari n'est pas pris en charge actuellement. Consultez la [Feuille de route de Teams](http://aka.ms/TeamsRoadmap) pour en savoir plus sur les nouvelles fonctionnalités dans Teams. Les utilisateurs qui essayent d’ouvrir Teams sur Safari seront dirigés vers le téléchargement du client de bureau Teams.

<a name="desktop-clients"></a>Clients de bureau
------------------------

Le client de bureau Microsoft Teams est une application autonome qui ne fait actuellement pas partie d'Office Pro Plus. Microsoft Teams est disponible pour Windows (7+), versions 32 bits et 64 bits, et MacOS (10.10+).

Les clients de bureau fournissent la prise en charge de communications en temps réel (audio, vidéo, et partage de contenu) pour les réunions d'équipe, les appels de groupes et les appels en tête-à-tête.

Les clients de bureau peuvent être téléchargés et installés par les utilisateurs finaux directement à partir de [https://teams.microsoft.com/downloads](https://go.microsoft.com/fwlink/?linkid=855754) s'ils disposent des autorisations locales appropriées (les droits d'administration ne sont pas requis pour installer le client Teams sur un PC, mais le sont pour un Mac).

Les administrateurs informatiques peuvent utiliser la méthode de leur choix pour distribuer les fichiers d'installation sur les ordinateurs de leur organisation telle que System Center Configuration Manager (Windows) ou Casper Suite (MacOS).



> [!NOTE]
> La distribution du client via ces systèmes sert uniquement à l'installation initiale des clients Microsoft Teams, non pour les mises à jour futures.


#### <a name="windows"></a>Windows

Les programmes d’installation de Microsoft Teams pour Windows sont téléchargeables en version 32 et 64 bits. L'architecture doit correspondre à celle du système d'exploitation, sur laquelle la version du téléchargement en ligne s'aligne.



> [!NOTE]
> L'architecture (32 bits ou 64 bits) de Microsoft Teams ignore celle d'Office installée.

Le client Windows est déployé dans le dossier AppData situé dans le profil de l'utilisateur. Le déploiement dans le profil local de l'utilisateur permet d'installer le client sans disposer de droits élevés. Le client Windows est installé aux emplacements suivants :

-   %appdata%\\local\\Microsoft\\Teams

-   %appdata%\\roaming\\Microsoft\\Teams

Lorsque les utilisateurs lancent un appel à l'aide du client Microsoft Teams la première fois, un message d'avertissement concernant les paramètres de pare-feu peut s'afficher et requérir l'autorisation de la communication. Les utilisateurs peuvent être invités à ignorer ce message, car l'appel fonctionnera.

![Capture d'écran d'une boîte de dialogue Alerte de sécurité Windows.](media/Get_clients_for_Microsoft_Teams_image3.png)


> [!NOTE]
> La configuration de pare-feu Windows sera modifiée même si l'invite est ignorée en sélectionnant Annuler. Deux règles de trafic entrant pour teams.exe seront créées avec une action de blocage pour les protocoles TCP et UDP.

#### <a name="mac"></a>Mac

Microsoft fournit également un fichier d'installation DMG pour les ordinateurs Mac OSX. L'accès administrateur est obligatoire pour installer le client Mac. Le client Mac OSX est installé dans le dossier /Applications.


<a name="mobile-clients"></a>Clients mobiles
--------------

Les applications mobiles Microsoft Teams mobile sont disponibles pour Android, iOS et Windows Phone ; elles sont destinées aux utilisateurs en déplacement qui participent à des conversations par messagerie et permettent de passer des appels audio P2P. Pour obtenir les applications mobiles, accédez à la boutique mobile adéquate : Google Play, App Store d’Apple ou Microsoft Store.

Les plateformes mobiles prises en charge pour les applications mobiles Microsoft Teams sont les suivantes :

-   **Android** : 4.4 ou version ultérieure

-   **iOS**:  10.0 ou version ultérieure

-   **Windows Phone**:  Windows 10 Mobile

Les applications mobiles sont distribuées et mises à jour uniquement via la boutique d'applications de la plateforme mobile respective et ne peuvent pas être distribuées via des solutions MDM (gestion des périphériques mobiles) ni utilisées comme version de test.


| | | |
|---------|---------|---------|
|![Icône Point de décision.](media/Get_clients_for_Microsoft_Teams_image4.png)      |Point de décision         |Existe-il des restrictions empêchant les utilisateurs d'installer le client Microsoft Teams appropriés sur leur appareil ?         |
|![Icône Étapes suivantes.](media/Get_clients_for_Microsoft_Teams_image5.png)     |Étapes suivantes         |Si votre organisation limite l'installation de logiciels, veillez à ce que ce processus soit compatible avec Microsoft Teams. Note : Les droits d'administration ne sont pas requis pour l'installation d'un client sur PC, mais le sont pour un Mac.         |


  <span id="_Hlk477176062" class="anchor"></span>  Point de décision   Existe-il des restrictions empêchant les utilisateurs d'installer le client Microsoft Teams appropriés sur leur appareil ?

<a name="client-update-management"></a>Gestion des mises à jour du client
------------------------

Actuellement, les clients sont automatiquement mis à jour par le service de Microsoft Teams ; aucune intervention de l'administrateur informatique n'est requise. Si une mise à jour est disponible, le client la téléchargera automatiquement et lorsque l'application est inactive pendant un certain temps, le processus de mise à jour se lancera.

<a name="client-side-configurations"></a>Configurations côté client
---------------------------

Actuellement, aucune option prise en charge n'est disponible pour configurer le client via l'administration des clients, PowerShell, des objets de stratégie de groupe ou le registre.

<a name="notification-settings"></a>Paramètres des notifications
----------------------------

Aucune option n'est actuellement disponible pour les administrateurs informatiques pour configurer les paramètres des notifications côté client. Toutes les options de notification sont définies par l'utilisateur. La figure ci-après présente les paramètres client par défaut.

![Capture d'écran des paramètres Notifications.](media/Get_clients_for_Microsoft_Teams_image6.png)
