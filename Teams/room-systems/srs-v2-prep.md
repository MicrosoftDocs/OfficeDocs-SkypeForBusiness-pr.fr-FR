---
title: Préparer votre environnement
ms.author: jambirk
author: jambirk
ms.reviewer: davgroom
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b4e0ad1e-12e5-4130-aec1-d8c9cd3a5965
ms.collection: M365-voice
description: Cet article explique les préparations de l’infrastructure pour le déploiement de salles d’équipes Microsoft.
ms.openlocfilehash: b1830ba68b61c322b6eeef95f29b1e72d2b93303
ms.sourcegitcommit: b2acf18ba6487154ebb4ee46938e96dc56cb2c9a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/09/2019
ms.locfileid: "33865013"
---
# <a name="prepare-your-environment"></a>Préparer votre environnement

Cette section contient une vue d’ensemble des étapes requises pour préparer votre environnement afin que vous puissiez utiliser toutes les fonctionnalités de salles d’équipes Microsoft.
  
1. Préparer un compte de périphérique pour chaque console salles d’équipes Microsoft. Pour plus d’informations, voir [Déployer Microsoft équipes salles](room-systems-v2.md) .
    
2. Vérifiez qu’une connexion réseau/Internet fonctionne et peut être utilisée par l’appareil.  
    
   - Il doit être en mesure de recevoir une adresse IP à l’aide du DHCP. (Salles d’équipes Microsoft ne peut pas être configuré avec une adresse IP statique au premier démarrage de l’unité, mais par la suite des adresses IP statiques pour le périphérique ont pu être configuré sur le périphérique ou sur le routeur ou le commutateur en amont).
    
   - Il doit ouvrir ces ports (en plus de l’ouverture des ports pour le média normales) :
    
   - HTTPS : 443
    
   - HTTP : 80
    
   - Si votre réseau fonctionne via un proxy, vous aurez également besoin de l’adresse du proxy ou des informations de script.
    
     > [!NOTE]
     > Microsoft Teams Rooms ne prend pas en charge les entrées HDCP, qui entraînent visiblement des problèmes avec la fonctionnalité de réception HDMI (vidéo, audio). Assurez-vous que les options HDCP des commutateurs connectés à Microsoft Teams sont désactivées. 
  
3. Pour améliorer votre expérience, Microsoft collecte des données. Pour collecter des données, les sites suivants doivent figurer dans la liste approuvée :
    
   - Point de terminaison client télémétrie :https://vortex.data.microsoft.com/
    
   - Point de terminaison de télémétrie paramètres :https://settings.data.microsoft.com/
    
### <a name="create-and-test-a-device-account"></a>Création et test d’un compte d’appareil

Un *compte de périphérique* est un compte utilisé par le client Microsoft équipes salles d’accéder aux fonctionnalités d’Exchange, comme le calendrier et pour permettre à Skype pour les entreprises. Pour plus d’informations, voir [Déployer Microsoft équipes salles](room-systems-v2.md) .
  
### <a name="check-network-availability"></a>Vérification de la disponibilité du réseau

Pour fonctionner correctement, le périphérique Microsoft équipes salles doit avoir accès à un réseau câblé qui répond aux conditions suivantes :
  
- Accès à votre instance Active Directory ou Azure Active Directory (Azure AD), ainsi qu’à vos serveurs Microsoft Exchange et Skype Entreprise.
- Accès à un serveur pouvant fournir une adresse IP à l’aide du protocole DHCP. Salles d’équipes Microsoft ne peut pas être configuré avec une adresse IP statique.
- Accès aux ports HTTP 80 et 443.
- Les ports TCP et UDP configurés en tant que décrits dans [ports et protocoles requis pour les serveurs](/skypeforbusiness/plan-your-deployment/network-requirements/ports-and-protocols) sur site Skype pour les implémentations Business Server ou [Office 365 URL et plages d’adresses IP](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US) pour Microsoft Teams ou Skype pour les entreprises en ligne implémentations.

> [!IMPORTANT]
> Veillez à utiliser une connexion réseau câblée de 1 Gbits/s afin d’être sûr de disposer de la bande passante nécessaire. 
  
### <a name="certificates"></a>Certificats

Votre appareil salles d’équipes Microsoft utilise des certificats pour les Services Web Exchange, Microsoft Teams ou Skype pour les entreprises, l’utilisation du réseau et d’authentification. Si des serveurs associés utilisent des certificats publics, ce qui est le cas des déploiements en ligne et de certains sur site, aucune autre action de l’administrateur n’est requise pour l’installation des certificats. En revanche, si l’autorité de certification (CA) est privée (généralement le cas des déploiements sur site), l’appareil devra l’approuver, ce qui implique une installation de certificats en chaîne (CA + CA). L’ajout de l’appareil au domaine peut permettre d’automatiser cette tâche.
  
Vous installerez les certificats comme vous le feriez pour tout autre client Windows.  
  
> [!NOTE]
> Certificats peuvent être nécessaire afin que les salles d’équipes Microsoft utiliser Skype pour Business Server.
  
### <a name="proxy"></a>Proxy

Salles d’équipes Microsoft est conçu pour hériter les paramètres de Proxy à partir du système d’exploitation Windows. Accédez au système d’exploitation Windows de la manière suivante :
  
1. Dans l’interface utilisateur salles équipes Microsoft, cliquez sur l’icône d’engrenage de paramètres où vous serez invité pour le mot de passe de l’administrateur local sur l’appareil (le mot de passe par défaut est **sfb**).
2. Cliquez sur **paramètres de** suivi de cliquer sur le bouton **Atteindre Windows** , puis en cliquant sur le bouton **Atteindre Admin connexion dans** et puis en cliquant sur le bouton de **l’administrateur** (si l’ordinateur est joint au domaine choisissez **Un autre utilisateur,** puis utiliser . \admin comme nom d’utilisateur).
3. Dans la **Recherche Windows** zone type gauche inférieur regedit (soit long appuyez sur l’écran ou cliquez avec le bouton droit sur et sélectionnez **Exécuter en tant qu’administrateur**).
4. Cliquez sur le dossier HKEY_USERS (vous verrez une liste de SID de l’utilisateur d’ordinateur), assurez-vous que le dossier racine HKEY_USERS est sélectionné.
       
5. Cliquez sur fichier, puis choisissez **charger la ruche.**
6. Parcourir le pour l' **C:\Users\Skype** dossier et tapez le nom de fichier zone NTUSER.dat et appuyez sur le bouton Ouvrir

7. Vous serez invité pour un nom de clé pour votre ruche chargée ; Tapez dans Skype (vous devez maintenant voir les paramètres de Registre de l’utilisateur Skype).
 
8. Ouvrez la clé Skype et accédez à paramètres HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet, puis vérifiez la que configuration de ces paramètres : 
    
    [HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings]
    
    "MigrateProxy"=dword:00000001
    
    "ProxyEnable"=dword:00000001
    
    "ProxyServer"="xx.xx.xx.xx:8080"
    
    Si ProxyServer n’existe pas, vous devrez peut-être ajouter cette clé en tant qu’une chaîne, changez xx.xx.xx.xx:8080 pour ip/host et port de votre serveur Proxy.
    
9. Une fois que vous avez terminé d’apporter les modifications de mise en surbrillance de l’utilisateur Skype principales (dossier racine de Skype), puis choisissez décharger la ruche dans le menu fichier de Registre (vous serez invité à confirmer - sélectionnez **Oui** ).
    
10. Vous pouvez désormais fermer l’éditeur de registre et saisissez déconnexion dans la zone de recherche Windows.
    
11. De retour dans l’écran de connexion, choisissez l’utilisateur **Skype**. Si toutes les étapes précédentes ont réussi, le périphérique Microsoft équipes salles système reconnectez-vous avec succès.
    
Pour utiliser cette application, vous devez être en mesure de vous connecter aux points de terminaison décrits ci-après. Pour consulter les adresses IP, développez la section d’adresses IP sous la table de description de flux de trafic.
  
**Exemple de noms d’hôte/ports de proxy de pare-feu**

|Objectif|Source ou informations d’identification|Port source|Destination|CDN|ExpressRoute pour Office 365|Adresse IP de destination|Port de destination|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Authentification et identité  <br/> |Voir [identité et authentification Office 365](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_Identity) <br/> |||
|Portail et services partagés  <br/> |Voir [Office 365 portail et partagés](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_Portal-identity) <br/> |||
|Signalisation SIP  <br/> |Ordinateur client ou utilisateur connecté  <br/> |Ports éphémères  <br/> |\*. contoso.com  <br/> |Non  <br/> |Oui  <br/> |[Skype pour les plages d’adresses IP d’entreprise](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443  <br/> |
|Conférence web avec connexions PSOM (Persistent Shared Object Model)  <br/> |Ordinateur client ou utilisateur connecté  <br/> |Ports éphémères  <br/> |\*. contoso.com  <br/> |Non  <br/> |Oui  <br/> |[Skype pour les plages d’adresses IP d’entreprise](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443  <br/> |
|Téléchargements HTTPS  <br/> |Ordinateur client ou utilisateur connecté  <br/> |Ports éphémères  <br/> |\*. contoso.com  <br/> |Non  <br/> |Oui  <br/> |[Skype pour les plages d’adresses IP d’entreprise](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443  <br/> |
|Audio  <br/> |Ordinateur client ou utilisateur connecté  <br/> |TCP/UDP 50 000-50019  <br/> |\*. contoso.com  <br/> |Non  <br/> |Oui  <br/> |[Skype pour les plages d’adresses IP d’entreprise](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443, UDP 3478, TCP/UDP 50 000-59 999  <br/> |
|Vidéo  <br/> |Ordinateur client ou utilisateur connecté  <br/> |TCP/UDP 50 020-50039  <br/> |\*. contoso.com  <br/> |Non  <br/> |Oui  <br/> |[Skype pour les plages d’adresses IP d’entreprise](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443, UDP 3478, TCP/UDP 50 000-59 999  <br/> |
|Partage de bureau  <br/> |Ordinateur client ou utilisateur connecté  <br/> |TCP/UDP 50 040-50059  <br/> |\*. contoso.com  <br/> |Non  <br/> |Oui  <br/> |[Skype pour les plages d’adresses IP d’entreprise](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443, 50 000-59 999  <br/> |
|Notifications Push pour Lync Mobile 2010 sur des appareils iOS. Cela n’est pas nécessaire pour appareils mobiles Android, Nokia Symbian ou Windows Phone.  <br/> |Ordinateur client ou utilisateur connecté  <br/> |Ports éphémères  <br/> |\*. contoso.com  <br/> |Non  <br/> |Oui  <br/> |[Skype pour les plages d’adresses IP d’entreprise](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 5223  <br/> |
|Télémétrie Skype  <br/> |Ordinateur client ou utilisateur connecté  <br/> |Ports éphémères  <br/> |skypemaprdsitus.trafficmanager.net  <br/> pipe.skype.com  <br/> |Non  <br/> |Non  <br/> |N/A  <br/> |TCP 443  <br/> |
|Conseils rapides pour les clients Skype  <br/> |Ordinateur client ou utilisateur connecté  <br/> |Ports éphémères  <br/> |quicktips.skypeforbusiness.com  <br/> |Non  <br/> |Non  <br/> |N/A  <br/> |TCP 443  <br/> |
   
> [!NOTE]
> Le caractère générique de contoso.com et broadcast.skype.com représente une longue liste de nœuds exclusivement utilisés avec Office 365. 
  
### <a name="create-provisioning-packages"></a>Création de packages de mise en service

Vous allez utiliser des packages de mise en service pour s’authentifier auprès d’Exchange Server ou Office 365.
  
### <a name="admin-group-management"></a>Gestion du groupe d’administrateurs

Après la jonction du domaine, vous pouvez utiliser la stratégie de groupe ou la gestion de l’ordinateur local pour définir un groupe de sécurité en tant qu’administrateur local comme vous le feriez pour un ordinateur Windows dans votre domaine. Tous les membres de ce groupe de sécurité peuvent saisir leurs informations d’identification et déverrouiller les paramètres.
  
> [!NOTE]
> Si votre appareil Microsoft Teams Rooms n’approuve plus le domaine (par exemple, si vous supprimez Microsoft Teams Rooms du domaine après la jonction), vous ne pourrez pas vous authentifier dans l’appareil et ouvrir les paramètres. La solution consiste à se connecter avec le compte d’administrateur local. 
  
## <a name="local-accounts"></a>Comptes locaux

### <a name="microsoft-teams-rooms-local-user-account"></a>Compte d’utilisateur Local salles équipes Microsoft

Le compte d’appareil n’utilise généralement pas de mot de passe. Il est possible d’attribuer un mot de passe, mais cela aura un impact, notamment la possibilité d’empêcher les utilisateurs d’accéder à l’application de la console lorsque le mot de passe expire. Par conséquent, l’administrateur doit prendre des mesures pour éviter l’expiration du mot de passe.
  
### <a name="admin---local-administrator-account"></a>"Admin" - Compte d’administrateur local

Le mot de passe Microsoft équipes salles par défaut est défini sur « sfb ». Le mot de passe peut être modifié localement en accédant à paramètres Windows \> Go pour Windows ou dans le fichier AutoUnattend.xml (utilisez le Gestionnaire de l’Image du système Windows à partir de ADK pour que la modification du fichier xml).
  
> [!CAUTION]
> Veillez à modifier le mot de passe Microsoft équipes salles dès que possible. 
  
Vous pouvez également gérer le mot de passe de l’administrateur local en configurant une stratégie de groupe qui définit les administrateurs de domaine comme administrateurs locaux.
  
Le mot de passe de l’administrateur local n’est pas inclus comme alternative lors de l’installation.
  
### <a name="machine-account"></a>Compte d’ordinateur

Beaucoup comme n’importe quel appareil Windows, le nom de l’ordinateur peut être renommé en cliquant avec le bouton droit sur paramètres \> sur \> PC renommer.
  
 Si vous souhaitez renommer l’ordinateur après l’intégration à un domaine, utilisez la commande Renommer-ordinateur PowerShell suivie d’un nouveau nom de l’ordinateur.
  
## <a name="see-also"></a>Voir aussi

[Planifier des équipes Microsoft salles](skype-room-systems-v2-0.md)

[Configuration requise de salles d’équipes Microsoft](requirements.md)
  
[Déployer les équipes Microsoft salles](room-systems-v2.md)
  
[Configurer une console Microsoft équipes salles](console.md)
  
[Gérer Microsoft Teams Rooms](skype-room-systems-v2.md)
