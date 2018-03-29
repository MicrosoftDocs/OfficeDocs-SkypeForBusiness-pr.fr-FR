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
description: Cet article explique les considérations de planification appropriées pour le déploiement de systèmes de salle Skype v2, la nouvelle génération de systèmes de salle de Skype.
ms.openlocfilehash: 3d958c5d07cfafd2eeddd6076182a635cfff19de
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-skype-room-systems-v2"></a>Planification de Skype Room Systems v2
 
Cet article explique les considérations de planification appropriées pour le déploiement de systèmes de salle Skype v2, la nouvelle génération de systèmes de salle de Skype. 
  
 Systèmes de salle Skype v2 est la dernière solution de conférence de Microsoft conçue pour transformer votre salle de réunion un Skype riche et de collaboration pour une expérience. Les utilisateurs apprécieront son interface Skype Entreprise familière, et les administrateurs informatiques approuveront la facilité de déploiement et de gestion de l’application de réunion Skype sous Windows 10. Systèmes de salle Skype v2 est conçu pour tirer parti des équipements existants tels que des panneaux LCD pour faciliter d’installation pour mettre Skype pour entreprise dans votre salle de réunion.
  
Systèmes de salle Skype v2 utilise une application UWP spécialisée qui agit comme interface utilisateur Skype réunion. Il s’exécute sur une Surface Pro des 4 ou Surface Pro en mode console (une fois déployé l’application UWP est la seule application qui s’exécute sur le périphérique) et qu’il requiert son propre compte de dispositif sur votre Skype pour la mise en oeuvre de l’entreprise. Il s’appuie sur des équipements existants tels que les écrans LCD et les appareils photo de périphériques relativement peu coûteux et microphones pour fournir une salle de réunion qualité d’expérience. Est mis à jour via Windows Update et le Windows store.
  
Avant de préparer votre environnement, assurez-vous de disposer du matériel et des logiciels nécessaires. Pour plus d’informations, consultez [v2 Skype pièce requise](requirements.md). 
  
> [!NOTE]
> Systèmes de salle Skype v2 est destiné à utiliser avec Skype Business Server 2015 ou Skype pour l’activité en ligne. Les plates-formes antérieures à Lync Server 2013 ne devraient pas travailler avec les systèmes de salle Skype v2. 
  
Systèmes de salle Skype v2 est la dernière solution de conférence de Microsoft conçue pour transformer votre salle de réunion un Skype riche et de collaboration pour une expérience. Les utilisateurs apprécieront son interface Skype Entreprise familière, et les administrateurs informatiques approuveront la facilité de déploiement et de gestion de l’application de réunion Skype sous Windows 10. Systèmes de salle Skype v2 est conçu pour tirer parti des équipements existants tels que des panneaux LCD pour faciliter d’installation pour mettre Skype pour entreprise dans votre salle de réunion.
  
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
    
- Sélection dans l’application utilisateur de réunion espace périphériques audio et vidéo USB U1
    
- Prise en charge de l’affichage sur deux écrans (pour la parité du système hérité) U2
    
- Themability (thèmes intégrés et la possibilité de définir le thème personnalisé) U2
    
 **Facilité de déploiement, simplicité de gestion**
  
- Appareil fonctionnant en continu qui active l’écran d’affichage lorsqu’il détecte des personnes dans la salle
    
- Déploiement simple et mise à jour de l’application de réunion Skype UWP (plateforme Windows universelle)
    
- L’AppLocker de Windows verrouille l’appareil sur l’application de réunion Skype
    
- Contrôle et gestion similaires à un appareil Windows 10 Enterprise via Intune et SCCM (MDM)
    
- Fiabilité pour l’entreprise
    
- Effort de formation minime des utilisateurs finaux, grâce à l’interface utilisateur Skype familière
    
- S’exécute sur les 4 Surface Pro tablet
    
- Intégré salle console rapports d’état à l’aide de Microsoft Operations Management Suite de clients (voir le [Plan Skype salle v2 SMS avec OMS](oms-management.md)) U1
    
- Possibilité de commenter public génère U2
    
- Télémétrie améliorée en vue de satisfaire la fiabilité de la jointure U2
    
- OMS supplémentaires reporting U2
    
- Possibilité pour l’administrateur informatique configurer des périphériques à distance U2
    <!--  - Front-of-Room UX shows room details pre-meeting U2  -->
- S’exécute sur une Surface Pro tablet U3
    
- Prend en charge de mise à jour (en langue anglaise, build 1703) U3 de Windows 10 entreprise Creator
    
- Prise en charge de [Crestron SR](http://www.crestron.com/products/line/sr-for-skype-for-business-room-system) ancrer matériel U3
    
- Prise en charge de l’OEM pour l’environnement (Crestron) de contrôles U3
    
- Prise en charge de [Polycom MSR série](http://www.polycom.com/hd-video-conferencing/microsoft-video/msr-series.mdl) ancrer hardwareU4
    
- Prise en charge de la U4 [Logitech Brio](https://www.logitech.com/en-us/product/brio)

- Prise en charge de [500 de concentrateur de Lenovo](https://www3.lenovo.com/us/en/hub500)U5 ancrer le matériel  
    
U1 - fonctionnalité introduite dans la mise à jour 1 (SW Ver. 2.0.2.0).
  
U2 - fonctionnalité introduite dans la mise à jour 2 (SW Ver. 3.0.6.0). 
  
U3 - fonctionnalité introduite dans la mise à jour 3 (SW Ver. 3.0.12.0). 
  
U4 - fonctionnalité introduite dans la mise à jour 4 (SW Ver. 3.0.15.0). 

U5 - fonctionnalité introduite dans la mise à jour 5 (SW Ver. 3.1.98.0). 
  
## <a name="preparing-your-skype-for-business-environment"></a>Préparation de votre environnement Skype Entreprise

Cette section contient une vue d’ensemble des étapes nécessaires pour préparer votre environnement afin que vous pouvez utiliser toutes les fonctionnalités des systèmes de salle Skype v2.
  
1. Préparer un compte de dispositif pour chaque console v2 de systèmes de salle de Skype. Pour plus d’informations, consultez [déploiement de systèmes de salle Skype v2](../../deploy/deploy-clients/room-systems-v2.md) .
    
2. Vérifiez qu’une connexion réseau/Internet fonctionne et peut être utilisée par l’appareil.  
    
  - Il doit être en mesure de recevoir une adresse IP à l’aide de DHCP (Remarque : systèmes de salle Skype v2 ne peut pas être configuré avec une adresse IP statique au premier démarrage de l’unité)
    
  - Les ports suivants doivent être ouverts (en plus de l’ouverture des ports normaux pour le support de Skype Entreprise) :
    
  - HTTPS : 443
    
  - HTTP : 80
    
  - Si votre réseau fonctionne via un proxy, vous aurez également besoin de l’adresse du proxy ou des informations de script.
    
    > [!NOTE]
    > Systèmes de salle Skype v2 ne gère pas l’entrée d’HDCP, ce qui a été observée pour causer des problèmes avec HDMI réceptionner les fonctionnalités (vidéo, audio). Veillez à vous assurer que les options HDCP désactivées commutateurs reliés à des systèmes de salle Skype v2. 
  
3. Pour améliorer votre expérience, Microsoft collecte des données. Pour collecter des données, les sites suivants doivent figurer dans la liste approuvée :
    
  - Point de terminaison client télémétrie :https://vortex.data.microsoft.com/
    
  - Point de terminaison télémétrie paramètres :https://settings.data.microsoft.com/
    
### <a name="create-and-test-a-device-account"></a>Création et test d’un compte d’appareil

Un *compte de dispositif* est un compte client Skype salle systèmes v2 utilise pour accéder aux fonctionnalités d’Exchange, tels que calendrier et activer Skype pour les entreprises. Pour plus d’informations, consultez [déploiement de systèmes de salle Skype v2](../../deploy/deploy-clients/room-systems-v2.md) .
  
### <a name="check-network-availability"></a>Vérification de la disponibilité du réseau

Pour fonctionner correctement, le périphérique de v2 Skype salle systèmes doit avoir accès à un réseau câblé qui répond à ces exigences :
  
- Accès à votre instance Active Directory ou Azure Active Directory (Azure AD), ainsi qu’à vos serveurs Microsoft Exchange et Skype Entreprise.
    
- Accès à un serveur pouvant fournir une adresse IP à l’aide du protocole DHCP. Systèmes de salle Skype v2 ne peut pas être configuré avec une adresse IP statique.
    
- Accès aux ports HTTP 80 et 443.
    
- Ports TCP et UDP configurés comme indiqué dans la [configuration du Port pour Lync Server 2013](https://technet.microsoft.com/en-us/library/gg398798%28v=ocs.15%29.aspx) pour principe Skype des implémentations en entreprise, [Office 365 URL et les plages d’adresses IP](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US) pour Skype pour des implémentations en entreprise en ligne.
    
> [!IMPORTANT]
> Veillez à utiliser une connexion réseau câblée de 1 Gbits/s afin d’être sûr de disposer de la bande passante nécessaire.  
  
### <a name="certificates"></a>Certificats

Votre périphérique de v2 Skype salle systèmes utilise des certificats pour les Services Web Exchange, Skype pour les entreprises, l’utilisation du réseau et l’authentification. Si des serveurs associés utilisent des certificats publics, ce qui est le cas des déploiements en ligne et de certains sur site, aucune autre action de l’administrateur n’est requise pour l’installation des certificats. En revanche, si l’autorité de certification (CA) est privée (généralement le cas des déploiements sur site), l’appareil devra l’approuver, ce qui implique une installation de certificats en chaîne (CA + CA). L’ajout de l’appareil au domaine peut permettre d’automatiser cette tâche.
  
Vous installerez les certificats comme vous le feriez pour tout autre client Windows.  
  
> [!NOTE]
> Les certificats peuvent être nécessaires pour que les systèmes de salle Skype v2 utiliser Skype pour Business Server. 
  
### <a name="proxy"></a>Proxy

Systèmes de salle Skype v2 est conçu pour hériter des paramètres de Proxy du système d’exploitation Windows. Accédez au système d’exploitation Windows de la manière suivante :
  
1. Dans l’interface utilisateur v2 de systèmes de salle Skype, cliquez sur l’icône d’engrenage de paramètres où vous demandera le mot de passe de l’administrateur local sur le périphérique (le mot de passe par défaut est « sfb »).
    
2. Cliquez sur « Paramètres », puis en cliquant sur le bouton « Aller à Windows » puis cliquer sur le « pour administration signe dans » bouton et puis en cliquant sur le bouton « Administrateur » (si l’ordinateur est joint au domaine choisissez « Autre utilisateur », puis utilisez. \admin comme nom d’utilisateur).
    
3. De la « recherche Windows » la zone type de gauche inférieur dans regedit (long appuyez sur l’écran ou la droite cliquez sur et choisissez « Exécuter en tant qu’administrateur »).
    
4. Cliquez sur le dossier HKEY_USERS (vous verrez une liste de SID de l’utilisateur d’ordinateur), assurez-vous que le dossier racine HKEY_USERS est sélectionné.
    
    Vous serez invité pour un nom de clé pour votre ruche chargée ; Tapez dans Skype (vous devez maintenant voir les paramètres du Registre de l’utilisateur Skype).
    
5. Cliquez sur Fichier, puis choisissez Charger Hive.
    
6. Accédez au dossier suivant "C:\Users\Skype" et saisissez le nom du fichier dans la zone NTUSER.dat et appuyez sur le bouton d’ouverture
    
7. Ouvrir la clé de Skype et accédez à paramètres de HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet, puis assurez-vous que la configuration de ces paramètres : 
    
    [HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings]
    
    « MigrateProxy » = DWORD : 00000001
    
    « ProxyEnable » = DWORD : 00000001
    
    « ProxyServer"="xx.xx.xx.xx:8080 »
    
    Si ProxyServer n’existe pas, vous devrez peut-être ajouter cette clé en tant qu’une chaîne, changez xx.xx.xx.xx:8080 pour ip/host et port de votre serveur Proxy.
    
8. Une fois que vous avez terminé d’apporter vos modifications en surbrillance l’utilisateur Skype (dossier racine pour Skype) de la clé, puis choisissez décharger la ruche dans le menu fichier de Registre (vous serez invité à confirmer - sélectionnez **Oui** ).
    
9. Vous pouvez désormais fermer l’éditeur de registre et saisissez déconnexion dans la zone de recherche Windows.
    
10. De retour dans l’écran de connexion, choisissez l’utilisateur **Skype**. Si toutes les étapes précédentes ont réussi, le périphérique de v2 Skype salle systèmes est reconnectez-vous avec succès.
    
Pour utiliser cette application, vous devez être en mesure de vous connecter aux points de terminaison décrits ci-après. Pour consulter les adresses IP, développez la section d’adresses IP sous la table de description de flux de trafic.
  
**Exemples de pare-feu Proxy hôte nom/Port**

|**Objectif**|**Informations d’identification ou de la source**|**Port source**|**Destination**|**PAIE CANADA-FICHIER**|**ExpressRoute pour Office 365**|**Destination IP**|**Port de destination**|
|:-----|:-----|:-----|:-----|:-----|:-----|:-----|:-----|
|Authentification et identité  <br/> |Consultez [l’identité et authentification d’Office 365](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_Identity) <br/> |||
|Portail et services partagés  <br/> |Reportez-vous à la section [Office 365 portail et partagés](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_Portal-identity) <br/> |||
|Signalisation SIP  <br/> |Ordinateur client ou utilisateur connecté  <br/> |Ports éphémères  <br/> |\*. contoso.com  <br/> |Non  <br/> |Oui  <br/> |[Skype pour les plages IP d’entreprise](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443  <br/> |
|Conférence web avec connexions PSOM (Persistent Shared Object Model)  <br/> |Ordinateur client ou utilisateur connecté  <br/> |Ports éphémères  <br/> |\*. contoso.com  <br/> |Non  <br/> |Oui  <br/> |[Skype pour les plages IP d’entreprise](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443  <br/> |
|Téléchargements HTTPS  <br/> |Ordinateur client ou utilisateur connecté  <br/> |Ports éphémères  <br/> |\*. contoso.com  <br/> |Non  <br/> |Oui  <br/> |[Skype pour les plages IP d’entreprise](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443  <br/> |
|Audio  <br/> |Ordinateur client ou utilisateur connecté  <br/> |TCP/UDP 50 000-50019  <br/> |\*. contoso.com  <br/> |Non  <br/> |Oui  <br/> |[Skype pour les plages IP d’entreprise](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443, UDP 3478, TCP/UDP 50 000-59 999  <br/> |
|Vidéo  <br/> |Ordinateur client ou utilisateur connecté  <br/> |TCP/UDP 50 020-50039  <br/> |\*. contoso.com  <br/> |Non  <br/> |Oui  <br/> |[Skype pour les plages IP d’entreprise](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443, UDP 3478, TCP/UDP 50 000-59 999  <br/> |
|Partage de bureau  <br/> |Ordinateur client ou utilisateur connecté  <br/> |TCP/UDP 50 040-50059  <br/> |\*. contoso.com  <br/> |Non  <br/> |Oui  <br/> |[Skype pour les plages IP d’entreprise](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 443, 50 000-59 999  <br/> |
|Notifications Push pour Lync Mobile 2010 sur des appareils iOS. Cela n’est pas nécessaire pour appareils mobiles Android, Nokia Symbian ou Windows Phone.  <br/> |Ordinateur client ou utilisateur connecté  <br/> |Ports éphémères  <br/> |\*. contoso.com  <br/> |Non  <br/> |Oui  <br/> |[Skype pour les plages IP d’entreprise](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US#BKMK_SfB_IP) <br/> |TCP 5223  <br/> |
|Télémétrie Skype  <br/> |Ordinateur client ou utilisateur connecté  <br/> |Ports éphémères  <br/> |skypemaprdsitus.trafficmanager.NET  <br/> pipe.Skype.com  <br/> |Non  <br/> |Non  <br/> |N/A  <br/> |TCP 443  <br/> |
|Conseils rapides pour les clients Skype  <br/> |Ordinateur client ou utilisateur connecté  <br/> |Ports éphémères  <br/> |quicktips.skypeforbusiness.com  <br/> |Non  <br/> |Non  <br/> |N/A  <br/> |TCP 443  <br/> |
   
> [!NOTE]
> Le caractère générique de contoso.com et broadcast.skype.com représente une longue liste de nœuds exclusivement utilisés avec Office 365. 
  
### <a name="create-provisioning-packages"></a>Création de packages de mise en service

Vous allez utiliser des packages de déploiement pour authentifier à Exchange Server ou Skype pour Business Server.
  
### <a name="admin-group-management"></a>Gestion du groupe d’administrateurs

Après la jonction du domaine, vous pouvez utiliser la stratégie de groupe ou la gestion de l’ordinateur local pour définir un groupe de sécurité en tant qu’administrateur local comme vous le feriez pour un ordinateur Windows dans votre domaine. Tous les membres de ce groupe de sécurité peuvent saisir leurs informations d’identification et déverrouiller les paramètres.
  
> [!NOTE]
> Si votre périphérique de v2 Skype salle systèmes perd la relation d’approbation avec le domaine (par exemple, si vous supprimez le v2 de systèmes de salle de Skype à partir du domaine une fois qu’il est joint au domaine), il se peut que vous ne pourrez pas à s’authentifier sur le périphérique et à ouvrir les paramètres. La méthode de contournement consiste à vous connecter avec le compte d’administrateur local. 
  
## <a name="local-accounts"></a>Comptes locaux

### <a name="skype-room-systems-local-user-account"></a>Compte d’utilisateur local de Skype Room Systems

Le compte d’appareil n’utilise généralement pas de mot de passe. Il est possible d’attribuer un mot de passe, mais cela aura un impact, notamment la possibilité d’empêcher les utilisateurs d’accéder à l’application de la console lorsque le mot de passe expire. Par conséquent, l’administrateur doit prendre des mesures pour éviter l’expiration du mot de passe.
  
### <a name="admin---local-administrator-account"></a>"Admin" - Compte d’administrateur local

Mot de passe Skype salle systèmes v2 par défaut est défini sur « sfb ». Le mot de passe peut être modifié localement à partir de paramètres Windows \> Go pour Windows ou dans le fichier AutoUnattend.xml (utilisez le Gestionnaire de l’Image système de Windows à partir de l’ADK pour effectuer la modification dans le fichier xml).
  
> [!CAUTION]
> Veillez à modifier le mot de passe Skype salle systèmes v2 dès que possible. 
  
Vous pouvez également gérer le mot de passe de l’administrateur local en configurant une stratégie de groupe qui définit les administrateurs de domaine comme administrateurs locaux.
  
Le mot de passe de l’administrateur local n’est pas inclus comme alternative lors de l’installation.
  
### <a name="machine-account"></a>Compte d’ordinateur

Bien comme n’importe quel périphérique Windows, le nom de l’ordinateur peut être renommé en cliquant avec le bouton droit sur paramètres \> sur \> PC de renommer.
  
 Si vous souhaitez renommer l’ordinateur après intégration à un domaine, utilisez la commande de changement de nom-ordinateur PowerShell suivie par le nouveau nom de l’ordinateur.
  
## <a name="see-also"></a>Voir aussi

#### 

[Exigences en matière de systèmes de salle Skype v2](requirements.md)
  
[Déployer Skype salle systèmes v2](../../deploy/deploy-clients/room-systems-v2.md)
  
[Configurer une console v2 de systèmes de salle de Skype](../../deploy/deploy-clients/console.md)
  
[Gérer l’espace de Skype systèmes v2](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)

