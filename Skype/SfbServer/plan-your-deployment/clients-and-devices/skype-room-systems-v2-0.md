---
title: Planification de Skype Room Systems v2
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b4e0ad1e-12e5-4130-aec1-d8c9cd3a5965
description: Cet article explique les considérations de planification pertinentes pour le déploiement de systèmes de salle Skype v2, la nouvelle génération de systèmes de salle Skype.
ms.openlocfilehash: 7b36e9bc9c85a57b81be542f09d65c357f6020c0
ms.sourcegitcommit: 5cc51e2d3898fccd1969accedb5e185a332e83bf
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/27/2018
---
# <a name="plan-for-skype-room-systems-v2"></a>Planification de Skype Room Systems v2
 
Cet article explique les considérations de planification pertinentes pour le déploiement de systèmes de salle Skype v2, la nouvelle génération de systèmes de salle Skype. 
  
 Systèmes de salle Skype v2 est conçue pour transformer la salle de réunion en une riche, collaborative Skype pour une expérience la solution conférence le plus récent de Microsoft. Les utilisateurs apprécieront son interface Skype Entreprise familière, et les administrateurs informatiques approuveront la facilité de déploiement et de gestion de l’application de réunion Skype sous Windows 10. Systèmes de salle Skype v2 est conçu pour tirer parti de l’équipement existant comme panneaux LCD pour faciliter d’installation pour intégrer Skype pour les entreprises à la salle de réunion.
  
Systèmes de salle Skype v2 utilise une application UWP spécialisée qui sert à l’interface utilisateur de réunion Skype. Il s’exécute sur une Surface Pro 4 ou Surface Pro en mode console (après le déploiement de l’application UWP est la seule application qui s’exécute sur l’appareil) et nécessite son propre compte de périphérique sur votre Skype pour l’implémentation de l’activité. Il tire parti des équipements existants tels que les panneaux LCD et caméras périphériques relativement peu coûteux et microphones pour fournir une salle de réunion qualité d’expérience. Est mis à jour par le biais du Windows store et de mise à jour de Windows.
  
Avant de commencer la préparation de votre environnement, assurez-vous que les logiciels et le matériel nécessaire. Pour plus d’informations, voir [v2 Skype salle requise](requirements.md). 
  
> [!NOTE]
> Systèmes de salle Skype v2 est destiné à utiliser avec Skype Business Server 2015 ou Skype pour Business Online. Plates-formes de versions antérieures à Lync Server 2013 ne devraient pas fonctionner avec les systèmes de salle Skype v2. 
  

  
 **Conçue pour Skype Entreprise**
  
- Participation aux réunions Skype en un clic
    
- Optimisation de l’expérience de réunion Skype pour les espaces équipés de vidéo HD plein écran et d’audio HD large bande
    
- Tous les participants peuvent se connecter à la réunion Skype à l’aide du dispositif de leur choix où qu’ils soient
    
- Invitez des contacts via votre annuaire qui vous indiquera leur disponibilité, ou via un appel téléphonique
    
- Prise en charge de la conférence PSTN Skype Entreprise et de la fonction d’appel PSTN pour remplacer le téléphone de conférence autonome de votre salle de réunion
    
 **Conversion d’un espace de réunion**
  
- Optimisation de l’application de réunion Skype dédiée pour le centre du contrôleur tactile et large écran d’affichage
    
- Réutilisation des investissements existants de votre écran d’affichage ou vos projecteurs
    
- Fonctionne avec tout type d’espace de réunion, allant des petites salles aux vastes espaces de conférence
    
- Des périphériques audio et vidéo Skype Entreprise certifiés sont disponibles pour différentes tailles d’espace
    
- Réception par câble intégrée pour la projection du bureau partagé vers la salle et la réunion Skype
    
- Salle de sélection de l’utilisateur dans l’application de conférence audio et vidéo périphériques USB & #x 2776 ;
    
- Double écran prise en charge (parité système hérité) & #x 2777 ;
    
- Themability (thèmes intégrés et la possibilité de définir le thème personnalisé) & #x 2777 ;
    
 **Facilité de déploiement, simplicité de gestion**
  
- Appareil fonctionnant en continu qui active l’écran d’affichage lorsqu’il détecte des personnes dans la salle
    
- Déploiement simple et mise à jour de l’application de réunion Skype UWP (plateforme Windows universelle)
    
- L’AppLocker de Windows verrouille l’appareil sur l’application de réunion Skype
    
- Contrôle et gestion similaires à un appareil Windows 10 Enterprise via Intune et SCCM (MDM)
    
- Fiabilité pour l’entreprise
    
- Effort de formation minime des utilisateurs finaux, grâce à l’interface utilisateur Skype familière
    
- S’exécute sur des tablettes Surface Pro 4
    
- Intégré salle console rapports d’état les clients qui utilisent Microsoft Operations Management Suite (voir [planifier Skype salle v2 SMS avec OMS](oms-management.md)) & #x 2776 ;
    
- Possibilité de faire part de vos commentaires pour les builds publiques & #x 2777 ;
    
- Amélioration de télémétrie autour de réunion Rejoignez la fiabilité et #x 2777 ;
    
- Création de rapports OMS supplémentaires & la #x 2777 ;
    
- Possibilité pour l’administrateur informatique pour configurer les périphériques à distance & #x 2777 ;
    <!--  - Front-of-Room UX shows room details pre-meeting U2  -->
- S’exécute sur des tablettes Surface Pro & #x 2778 ;
    
- Prend en charge Windows 10 entreprise Creator mise à jour (en anglais, build 1703) & #x 2778 ;
    
- Prise en charge des [Crestron SR](http://www.crestron.com/products/line/sr-for-skype-for-business-room-system) ancre matériel & #x 2778 ;
    
- Codage OEM tel prise en charge pour les contrôles de l’environnement (Crestron) & #x 2778 ;
    
- Prise en charge de [Polycom MSR série](http://www.polycom.com/hd-video-conferencing/microsoft-video/msr-series.mdl) ancre matériel & #x 2779 ;
    
- Prise en charge [Logitech Brio](https://www.logitech.com/en-us/product/brio) & #x 2779 ;

- Prise en charge de [Lenovo Hub 500](https://www3.lenovo.com/us/en/hub500) ancre matériel & #x277A ;  
    
& #x 2776 ; -Fonction introduite dans la mise à jour 1 (SW Ver. 2.0.2.0).
  
& #x 2777 ; -Fonction introduite dans la mise à jour 2 (SW Ver. 3.0.6.0). 
  
& #x 2778 ; -Fonction introduite dans la mise à jour 3 (SW Ver. 3.0.12.0). 
  
& #x 2779 ; -Fonction introduite dans la mise à jour 4 (SW Ver. 3.0.15.0). 

& #x277A ; -Fonction introduite dans la mise à jour 5 (SW Ver. 3.1.98.0). 
  
## <a name="preparing-your-skype-for-business-environment"></a>Préparation de votre environnement Skype Entreprise

Cette section contient une vue d’ensemble des étapes requises pour préparer votre environnement afin que vous puissiez utiliser toutes les fonctionnalités de systèmes de salle Skype v2.
  
1. Préparer un compte de périphérique pour chaque console v2 de systèmes de salle Skype. Pour plus d’informations, voir [déployer Skype salle systèmes v2](../../deploy/deploy-clients/room-systems-v2.md) .
    
2. Vérifiez qu’une connexion réseau/Internet fonctionne et peut être utilisée par l’appareil.  
    
  - Il doit être en mesure de recevoir une adresse IP à l’aide de DHCP (Remarque : Skype salle systèmes v2 ne peut pas être configuré avec une adresse IP statique au premier démarrage de l’unité)
    
  - Les ports suivants doivent être ouverts (en plus de l’ouverture des ports normaux pour le support de Skype Entreprise) :
    
  - HTTPS : 443
    
  - HTTP : 80
    
  - Si votre réseau fonctionne via un proxy, vous aurez également besoin de l’adresse du proxy ou des informations de script.
    
    > [!NOTE]
    > Systèmes de salle Skype v2 ne prend pas en charge entrée HDCP, qui a été observée pour provoquer des problèmes avec HDMI acquisition des fonctionnalités (vidéo, audio). Veiller à ce que les commutateurs connectés à des systèmes de salle Skype v2 ont options HDCP désactivées. 
  
3. Pour améliorer votre expérience, Microsoft collecte des données. Pour collecter des données, les sites suivants doivent figurer dans la liste approuvée :
    
  - Point de terminaison client télémétrie :https://vortex.data.microsoft.com/
    
  - Point de terminaison de télémétrie paramètres :https://settings.data.microsoft.com/
    
### <a name="create-and-test-a-device-account"></a>Création et test d’un compte d’appareil

Un *compte de périphérique* est un compte client Skype salle systèmes v2 utilise pour accéder aux fonctionnalités d’Exchange, comme le calendrier et pour permettre à Skype pour les entreprises. Pour plus d’informations, voir [déployer Skype salle systèmes v2](../../deploy/deploy-clients/room-systems-v2.md) .
  
### <a name="check-network-availability"></a>Vérification de la disponibilité du réseau

Pour fonctionner correctement, le périphérique v2 Skype salle systèmes doit avoir accès à un réseau câblé qui répond aux conditions suivantes :
  
- Accès à votre instance Active Directory ou Azure Active Directory (Azure AD), ainsi qu’à vos serveurs Microsoft Exchange et Skype Entreprise.
    
- Accès à un serveur pouvant fournir une adresse IP à l’aide du protocole DHCP. Systèmes de salle Skype v2 ne peut pas être configuré avec une adresse IP statique.
    
- Accès aux ports HTTP 80 et 443.
    
- Ports TCP et UDP configurées comme décrit dans les [ports requis pour Lync Server 2013](https://technet.microsoft.com/en-us/library/gg398798%28v=ocs.15%29.aspx) pour sur site Skype pour des implémentations en entreprise ou [Office 365 URL et plages d’adresses IP](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US) pour Skype pour les implémentations d’entreprise en ligne.
    
> [!IMPORTANT]
> Veillez à utiliser une connexion réseau câblée de 1 Gbits/s afin d’être sûr de disposer de la bande passante nécessaire.  
  
### <a name="certificates"></a>Certificats

Périphérique Skype salle systèmes v2 utilise des certificats pour les Services Web Exchange, Skype pour les entreprises, l’utilisation du réseau et d’authentification. Si des serveurs associés utilisent des certificats publics, ce qui est le cas des déploiements en ligne et de certains sur site, aucune autre action de l’administrateur n’est requise pour l’installation des certificats. En revanche, si l’autorité de certification (CA) est privée (généralement le cas des déploiements sur site), l’appareil devra l’approuver, ce qui implique une installation de certificats en chaîne (CA + CA). L’ajout de l’appareil au domaine peut permettre d’automatiser cette tâche.
  
Vous installerez les certificats comme vous le feriez pour tout autre client Windows.  
  
> [!NOTE]
> Certificats peuvent être nécessaire afin que les systèmes de salle Skype v2 utiliser Skype pour Business Server. 
  
### <a name="proxy"></a>Proxy

Systèmes de salle Skype v2 est conçu pour hériter les paramètres de Proxy à partir du système d’exploitation Windows. Accédez au système d’exploitation Windows de la manière suivante :
  
1. Dans l’interface utilisateur v2 de systèmes de salle Skype, cliquez sur l’icône d’engrenage de paramètres où vous serez invité pour le mot de passe de l’administrateur local sur l’appareil (le mot de passe par défaut est « sfb »).
    
2. Cliquez sur « Paramètres », puis en cliquant sur le bouton « Aller à Windows » et puis en cliquant sur le » pour la connexion d’administration dans « bouton, puis cliquez sur le bouton « Administrateur » (si l’ordinateur est joint au domaine choisissez « Un autre utilisateur », puis utilisez. \admin comme nom d’utilisateur).
    
3. Dans la « recherche Windows » de la zone type de gauche inférieur regedit (long appuyez sur l’écran ou à droite cliquez sur et choisissez « Exécuter en tant qu’administrateur »).
    
4. Cliquez sur le dossier HKEY_USERS (vous verrez une liste de SID de l’utilisateur d’ordinateur), assurez-vous que le dossier racine HKEY_USERS est sélectionné.
    
    Vous serez invité pour un nom de clé pour votre ruche chargée ; Tapez dans Skype (vous devez maintenant voir les paramètres de Registre de l’utilisateur Skype).
    
5. Cliquez sur Fichier, puis choisissez Charger Hive.
    
6. Accédez au dossier suivant "C:\Users\Skype" et saisissez le nom du fichier dans la zone NTUSER.dat et appuyez sur le bouton d’ouverture
    
7. Ouvrez la clé Skype et accédez à paramètres HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet, puis vérifiez la que configuration de ces paramètres : 
    
    [HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings]
    
    « MigrateProxy » = DWORD : 00000001
    
    « ProxyEnable » = DWORD : 00000001
    
    « ProxyServer"="xx.xx.xx.xx:8080 »
    
    Si ProxyServer n’existe pas, vous devrez peut-être ajouter cette clé en tant qu’une chaîne, changez xx.xx.xx.xx:8080 pour ip/host et port de votre serveur Proxy.
    
8. Une fois que vous avez terminé d’apporter les modifications de mise en surbrillance de l’utilisateur Skype principales (dossier racine de Skype), puis choisissez décharger la ruche dans le menu fichier de Registre (vous serez invité à confirmer - sélectionnez **Oui** ).
    
9. Vous pouvez désormais fermer l’éditeur de registre et saisissez déconnexion dans la zone de recherche Windows.
    
10. De retour dans l’écran de connexion, choisissez l’utilisateur **Skype**. Si toutes les étapes précédentes ont réussi, l’appareil v2 de systèmes de salle Skype système reconnectez-vous avec succès.
    
Pour utiliser cette application, vous devez être en mesure de vous connecter aux points de terminaison décrits ci-après. Pour consulter les adresses IP, développez la section d’adresses IP sous la table de description de flux de trafic.
  
**Exemples de pare-feu Proxy hôte nom/Port**

|**Objectif**|**Informations d’identification ou source**|**Port source**|**Destination**|**CDN**|**ExpressRoute pour Office 365**|**Destination IP**|**Port de destination**|
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
|Télémétrie Skype  <br/> |Ordinateur client ou utilisateur connecté  <br/> |Ports éphémères  <br/> |skypemaprdsitus.trafficmanager.NET  <br/> pipe.Skype.com  <br/> |Non  <br/> |Non  <br/> |N/A  <br/> |TCP 443  <br/> |
|Conseils rapides pour les clients Skype  <br/> |Ordinateur client ou utilisateur connecté  <br/> |Ports éphémères  <br/> |quicktips.skypeforbusiness.com  <br/> |Non  <br/> |Non  <br/> |N/A  <br/> |TCP 443  <br/> |
   
> [!NOTE]
> Le caractère générique de contoso.com et broadcast.skype.com représente une longue liste de nœuds exclusivement utilisés avec Office 365. 
  
### <a name="create-provisioning-packages"></a>Création de packages de mise en service

Vous allez utiliser des packages de mise en service pour authentifier à Exchange Server ou Skype pour Business Server.
  
### <a name="admin-group-management"></a>Gestion du groupe d’administrateurs

Après la jonction du domaine, vous pouvez utiliser la stratégie de groupe ou la gestion de l’ordinateur local pour définir un groupe de sécurité en tant qu’administrateur local comme vous le feriez pour un ordinateur Windows dans votre domaine. Tous les membres de ce groupe de sécurité peuvent saisir leurs informations d’identification et déverrouiller les paramètres.
  
> [!NOTE]
> Si votre appareil v2 de systèmes de salle Skype perd approbation avec le domaine (par exemple, si vous supprimez le v2 Skype salle systèmes du domaine une fois qu’il est joint au domaine), vous ne pourrez pas s’authentifier sur le périphérique et ouvrir des paramètres. La méthode de contournement consiste à vous connecter avec le compte d’administrateur local. 
  
## <a name="local-accounts"></a>Comptes locaux

### <a name="skype-room-systems-local-user-account"></a>Compte d’utilisateur local de Skype Room Systems

Le compte d’appareil n’utilise généralement pas de mot de passe. Il est possible d’attribuer un mot de passe, mais cela aura un impact, notamment la possibilité d’empêcher les utilisateurs d’accéder à l’application de la console lorsque le mot de passe expire. Par conséquent, l’administrateur doit prendre des mesures pour éviter l’expiration du mot de passe.
  
### <a name="admin---local-administrator-account"></a>"Admin" - Compte d’administrateur local

Mot de passe Skype salle systèmes v2 par défaut est défini sur « sfb ». Le mot de passe peut être modifié localement en accédant à paramètres Windows \> Go pour Windows ou dans le fichier AutoUnattend.xml (utilisez le Gestionnaire de l’Image du système Windows à partir de ADK pour que la modification du fichier xml).
  
> [!CAUTION]
> Veillez à modifier le mot de passe Skype salle systèmes v2 dès que possible. 
  
Vous pouvez également gérer le mot de passe de l’administrateur local en configurant une stratégie de groupe qui définit les administrateurs de domaine comme administrateurs locaux.
  
Le mot de passe de l’administrateur local n’est pas inclus comme alternative lors de l’installation.
  
### <a name="machine-account"></a>Compte d’ordinateur

Beaucoup comme n’importe quel appareil Windows, le nom de l’ordinateur peut être renommé en cliquant avec le bouton droit sur paramètres \> sur \> PC renommer.
  
 Si vous souhaitez renommer l’ordinateur après l’intégration à un domaine, utilisez la commande Renommer-ordinateur PowerShell suivie d’un nouveau nom de l’ordinateur.
  
## <a name="see-also"></a>Voir aussi

#### 

[V2 Skype salle requise](requirements.md)
  
[Déployer la salle Skype systèmes v2](../../deploy/deploy-clients/room-systems-v2.md)
  
[Configurer une console v2 de systèmes de salle de Skype](../../deploy/deploy-clients/console.md)
  
[Gérer les salles Skype systèmes v2](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)

