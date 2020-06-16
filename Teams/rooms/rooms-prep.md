---
title: Préparer votre environnement
ms.author: v-lanac
author: lanachin
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b4e0ad1e-12e5-4130-aec1-d8c9cd3a5965
ms.collection:
- M365-collaboration
description: Apprenez-en davantage sur la préparation de votre infrastructure pour le déploiement de Microsoft Teams, afin de pouvoir tirer parti de toutes les fonctionnalités.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8551bc625b270b8b61de4be71ceb772a1d1ede47
ms.sourcegitcommit: d0d37351c37c2b4db9b0fc51b286dd548f5b9542
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/15/2020
ms.locfileid: "44735424"
---
# <a name="prepare-your-environment"></a>Préparer votre environnement

Cette section fournit une vue d’ensemble des étapes nécessaires pour préparer votre environnement afin que vous puissiez utiliser toutes les fonctionnalités des salles de Microsoft Teams.
  
1. Préparez un compte d’appareil pour chaque console de salle Microsoft Teams. Pour plus d’informations, voir [déployer des salles Microsoft teams](rooms-deploy.md) .
    
2. Vérifiez qu’une connexion réseau/Internet fonctionne et peut être utilisée par l’appareil.  
    
   - Il doit être en mesure de recevoir une adresse IP à l’aide du protocole DHCP. (Les salles de Microsoft Teams ne peuvent pas être configurées à l’aide d’une adresse IP statique lors du premier démarrage de l’unité, mais le protocole IP statique pour l’appareil peut être configuré sur l’appareil ou sur le commutateur ou le routeur en amont.)
   - Ce port doit être ouvert (en plus de l’ouverture des ports normaux pour le média) :
   - HTTPS : 443
   - HTTP : 80
   - Si votre réseau fonctionne via un proxy, vous aurez également besoin de l’adresse du proxy ou des informations de script.
    
     > [!NOTE]
     > Microsoft Teams Rooms ne prend pas en charge les entrées HDCP, qui entraînent visiblement des problèmes avec la fonctionnalité de réception HDMI (vidéo, audio). Assurez-vous que les options HDCP des commutateurs connectés à Microsoft Teams sont désactivées.
  
3. Pour améliorer votre expérience, Microsoft collecte des données. Pour permettre à Microsoft de recueillir des données, liste d’autorisation sur ces sites :

   - Point de terminaison du client de télémétrie :https://vortex.data.microsoft.com/
   - Point de terminaison des paramètres de télémétrie :https://settings.data.microsoft.com/
    
### <a name="create-and-test-a-device-account"></a>Création et test d’un compte d’appareil

Un *compte d’appareil* est un compte qu’utilise le client Microsoft teams pour accéder aux fonctions à partir d’Exchange, comme le calendrier et pour activer Skype entreprise. Pour plus d’informations, voir [déployer des salles Microsoft teams](rooms-deploy.md) .
  
### <a name="check-network-availability"></a>Vérification de la disponibilité du réseau

Pour fonctionner correctement, l’appareil de salle Microsoft teams doit avoir accès à un réseau câblé qui répond à la configuration requise suivante :
  
- Accès à votre instance Active Directory ou Azure Active Directory (Azure AD), ainsi qu’à vos serveurs Microsoft Exchange et Skype Entreprise.
- Accès à un serveur pouvant fournir une adresse IP à l’aide du protocole DHCP. Les salles de Microsoft Teams ne peuvent pas être configurées à l’aide d’une adresse IP statique lors du premier démarrage de l’unité.
- Accès aux ports HTTP 80 et 443.
- Ports TCP et UDP configurés comme décrit dans la section exigences relatives aux [ports et aux protocoles pour les serveurs](/skypeforbusiness/plan-your-deployment/network-requirements/ports-and-protocols) pour les mises à niveau de Skype entreprise Server sur site, ou les [URL et plages d’adresses IP de Microsoft 365 et Office 365](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US) pour les mises à niveau de Microsoft teams ou Skype entreprise online.

> [!IMPORTANT]
> Veillez à utiliser une connexion réseau câblée de 1 Gbits/s afin d’être sûr de disposer de la bande passante nécessaire. 

> [!NOTE]
> Les mises à jour logicielles des salles de Microsoft teams sont téléchargées automatiquement à partir du Microsoft Store pour entreprises. Voir les [conditions préalables pour le Microsoft Store pour les entreprises et l’éducation](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business) pour vérifier que la console de salle est en mesure d’accéder au Windows Store et à la mise à jour automatique.
  
### <a name="certificates"></a>Certificats

Votre appareil Microsoft teams salles utilise des certificats pour les services Web Exchange, Microsoft teams ou Skype entreprise, l’utilisation du réseau et l’authentification. Si des serveurs associés utilisent des certificats publics, ce qui est le cas des déploiements en ligne et de certains sur site, aucune autre action de l’administrateur n’est requise pour l’installation des certificats. En revanche, si l’autorité de certification (CA) est privée (généralement le cas des déploiements sur site), l’appareil devra l’approuver, ce qui implique une installation de certificats en chaîne (CA + CA). L’ajout de l’appareil au domaine peut permettre d’automatiser cette tâche.
  
Vous installerez les certificats comme vous le feriez pour tout autre client Windows.  
  
> [!NOTE]
> Des certificats peuvent être requis pour que les salles de Microsoft teams utilisent Skype entreprise Server.
  
### <a name="proxy"></a>Proxy

Les salles de Microsoft teams sont conçues pour hériter des paramètres de proxy du système d’exploitation Windows. Accédez au système d’exploitation Windows de la manière suivante :
  
1. Dans l’interface utilisateur de Microsoft Teams, cliquez sur l’icône d’engrenage paramètres dans laquelle vous serez invité à entrer le mot de passe d’administrateur local sur l’appareil (le mot de passe par défaut est **marketing**).
2. Pour ce faire, appuyez sur **paramètres** , puis appuyez sur le bouton **accéder à Windows** , puis appuyez sur le bouton **se connecter à l’administrateur** , puis cliquez sur le bouton **administrateur** (si le nom de l’ordinateur est joint à un domaine **, sélectionnez autre utilisateur,** puis utilisez .\Admin comme nom d’utilisateur).
3. Dans la zone de recherche en bas à gauche du texte de la zone de **recherche** , appuyez sur l’écran ou cliquez avec le bouton droit et sélectionnez **exécuter en tant qu’administrateur**.
4. Cliquez sur le dossier HKEY_USERS (vous verrez une liste de SID de l’utilisateur d’ordinateur), assurez-vous que le dossier racine HKEY_USERS est sélectionné.
       
5. Cliquez sur fichier, puis sur **charger la ruche.**
6. Accédez au dossier **C:\Users\Skype** et tapez dans la zone nom de fichier Ntuser. dat, puis appuyez sur le bouton Ouvrir.

7. Vous serez invité à entrer un nom de clé pour votre nouvelle ruche. Entrez dans Skype (les paramètres de registre de l’utilisateur Skype apparaissent désormais).
 
8. Ouvrez la clé Skype et naviguez jusqu’à HKEY_USERS paramètres \Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet, puis vérifiez que les paramètres suivants sont renseignés : 
    
    `[HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings]`
    
    `"MigrateProxy"=dword:00000001`
    
    `"ProxyEnable"=dword:00000001`
    
    `"ProxyServer"="xx.xx.xx.xx:8080"`
    
    Si ProxyServer n’existe pas, vous devrez peut-être ajouter cette clé en tant qu’une chaîne, changez xx.xx.xx.xx:8080 pour ip/host et port de votre serveur Proxy.
    
9. Lorsque vous avez terminé d’apporter vos modifications, mettez en surbrillance la clé d’utilisateur Skype (le dossier racine de Skype) et sélectionnez décharger la ruche dans le menu fichier du Registre (vous êtes invité à confirmer-sélectionnez **Oui** ).
    
10. Vous pouvez désormais fermer l’éditeur de registre et saisissez déconnexion dans la zone de recherche Windows.
    
11. De retour dans l’écran de connexion, choisissez l’utilisateur **Skype**. Si les étapes précédentes n’ont pas abouti, l’appareil de salle Microsoft teams se connecte correctement.
    
To use this application, you must be able to connect to the endpoints described below. To see the IP addresses, expand the IP address section below the table describing the traffic flow.
  
**Exemple de noms d’hôte/ports de proxy de pare-feu**

|Objectif|Source ou informations d’identification|Port source|Destination|CDN|ExpressRoute pour Office 365|Adresse IP de destination|Port de destination|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Authentification et identité  <br/> |Voir [Microsoft 365 et authentification et identité d’Office 365](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_Identity) <br/> |||
|Portail et services partagés  <br/> |Voir [Centre d’administration Microsoft 365 et services partagés](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_Portal-identity) <br/> |||
|Signalisation SIP  <br/> |Ordinateur client ou utilisateur connecté  <br/> |Ports éphémères  <br/> |\*. contoso.com  <br/> |Non  <br/> |Oui  <br/> |[Plages d’adresses IP de Skype entreprise](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443  <br/> |
|Conférence web avec connexions PSOM (Persistent Shared Object Model)  <br/> |Ordinateur client ou utilisateur connecté  <br/> |Ports éphémères  <br/> |\*. contoso.com  <br/> |Non  <br/> |Oui  <br/> |[Plages d’adresses IP de Skype entreprise](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443  <br/> |
|Téléchargements HTTPS  <br/> |Ordinateur client ou utilisateur connecté  <br/> |Ports éphémères  <br/> |\*. contoso.com  <br/> |Non  <br/> |Oui  <br/> |[Plages d’adresses IP de Skype entreprise](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443  <br/> |
|Audio  <br/> |Ordinateur client ou utilisateur connecté  <br/> |TCP/UDP 50 000-50019  <br/> |\*. contoso.com  <br/> |Non  <br/> |Oui  <br/> |[Plages d’adresses IP de Skype entreprise](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443, UDP 3478, TCP/UDP 50 000-59 999  <br/> |
|Vidéo  <br/> |Ordinateur client ou utilisateur connecté  <br/> |TCP/UDP 50 020-50039  <br/> |\*. contoso.com  <br/> |Non  <br/> |Oui  <br/> |[Plages d’adresses IP de Skype entreprise](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443, UDP 3478, TCP/UDP 50 000-59 999  <br/> |
|Partage de bureau  <br/> |Ordinateur client ou utilisateur connecté  <br/> |TCP/UDP 50 040-50059  <br/> |\*. contoso.com  <br/> |Non  <br/> |Oui  <br/> |[Plages d’adresses IP de Skype entreprise](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443, 50 000-59 999  <br/> |
|Lync Mobile push notifications for Lync Mobile 2010 on iOS devices. You don't need this for Android, Nokia Symbian or Windows Phone mobile devices.  <br/> |Ordinateur client ou utilisateur connecté  <br/> |Ports éphémères  <br/> |\*. contoso.com  <br/> |Non  <br/> |Oui  <br/> |[Plages d’adresses IP de Skype entreprise](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 5223  <br/> |
|Télémétrie Skype  <br/> |Ordinateur client ou utilisateur connecté  <br/> |Ports éphémères  <br/> |skypemaprdsitus.trafficmanager.net  <br/> pipe.skype.com  <br/> |Non  <br/> |Non  <br/> |N/A  <br/> |TCP 443  <br/> |
|Conseils rapides du client Skype  <br/> |Ordinateur client ou utilisateur connecté  <br/> |Ports éphémères  <br/> |quicktips.skypeforbusiness.com  <br/> |Non  <br/> |Non  <br/> |N/A  <br/> |TCP 443  <br/> |

> [!NOTE]
> Le caractère générique pour contoso.com et broadcast.skype.com représente une longue liste de nœuds utilisés exclusivement pour Microsoft 365 ou Office 365. 
  
### <a name="create-provisioning-packages"></a>Création de packages de mise en service

Vous utiliserez des packages de configuration pour s’authentifier auprès d’Exchange Server, de Microsoft 365 ou d’Office 365.
  
### <a name="admin-group-management"></a>Gestion du groupe d’administrateurs

Après la jonction du domaine, vous pouvez utiliser la stratégie de groupe ou la gestion de l’ordinateur local pour définir un groupe de sécurité en tant qu’administrateur local comme vous le feriez pour un ordinateur Windows dans votre domaine. Tous les membres de ce groupe de sécurité peuvent saisir leurs informations d’identification et déverrouiller les paramètres.
  
> [!NOTE]
> Si votre appareil Microsoft Teams Rooms n’approuve plus le domaine (par exemple, si vous supprimez Microsoft Teams Rooms du domaine après la jonction), vous ne pourrez pas vous authentifier dans l’appareil et ouvrir les paramètres. La solution consiste à se connecter avec le compte d’administrateur local. 
  
## <a name="local-accounts"></a>Comptes locaux

### <a name="microsoft-teams-rooms-local-user-account"></a>Compte d’utilisateur local de Microsoft teams

Le compte d’appareil n’utilise généralement pas de mot de passe. Il est possible d’attribuer un mot de passe, mais cela aura un impact, notamment la possibilité d’empêcher les utilisateurs d’accéder à l’application de la console lorsque le mot de passe expire. Par conséquent, l’administrateur doit prendre des mesures pour éviter l’expiration du mot de passe.
  
### <a name="admin---local-administrator-account"></a>"Admin" - Compte d’administrateur local

Le mot de passe par défaut de Microsoft teams est défini sur « marketing ». Le mot de passe peut être modifié localement en accédant à paramètres Windows, puis \> sélectionnez Windows ou dans le fichier AutoUnattend.xml (utilisez le gestionnaire d’image Windows de ADK pour apporter la modification au fichier XML).
  
> [!CAUTION]
> N’hésitez pas à modifier le mot de passe des salles de Microsoft teams dès que possible. 
  
Vous pouvez également gérer le mot de passe de l’administrateur local en configurant une stratégie de groupe qui définit les administrateurs de domaine comme administrateurs locaux.
  
Le mot de passe de l’administrateur local n’est pas inclus comme alternative lors de l’installation.
  
### <a name="machine-account"></a>Compte d’ordinateur

Comme n’importe quel appareil Windows, le nom de l’ordinateur peut être renommé en cliquant avec le bouton droit sur les paramètres relatifs au changement de \> \> nom du PC.
  
 Si vous souhaitez renommer l’ordinateur après l’avoir rejointe à un domaine, utilisez la commande PowerShell d’ordinateur renommé suivie du nouveau nom de l’ordinateur.
  
## <a name="related-topics"></a>Voir aussi

[Planifier les salles de Microsoft teams](rooms-plan.md)

[Spécifications des salles Microsoft Teams](requirements.md)
  
[Déployer les Salles Microsoft Teams](rooms-deploy.md)
  
[Configurer une console des salles Microsoft Teams](console.md)
  
[Gérer les Salles Microsoft Teams](rooms-manage.md)

[Conditions préalables pour le Microsoft Store pour les entreprises et l’éducation](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business) 
