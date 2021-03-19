---
title: Préparer votre environnement
ms.author: dstrome
author: dstrome
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
description: Découvrez comment préparer votre infrastructure pour le déploiement de salles Microsoft Teams afin de tirer parti de toutes les fonctionnalités.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 181599e6b5181f50548621e4895b400f442646a6
ms.sourcegitcommit: 0fddd05334e37b0086ccc0aebe17a26f8e6e8e6c
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/19/2021
ms.locfileid: "50884568"
---
# <a name="prepare-your-environment"></a>Préparer votre environnement

Cette section contient une vue d’ensemble des étapes requises pour préparer votre environnement afin que vous pouvez utiliser toutes les fonctionnalités des salles Microsoft Teams.
  
1. Préparez un compte d’appareil pour chaque console de salle Microsoft Teams. Pour [plus d’informations, voir](rooms-deploy.md) Déployer les salles Microsoft Teams.
    
2. Vérifiez qu’une connexion réseau/Internet fonctionne et peut être utilisée par l’appareil.  
    
   Il doit être en mesure de recevoir une adresse IP à l’aide de DHCP. (Les salles Microsoft Teams ne peuvent pas être configurées avec une adresse IP statique au démarrage de la première unité, mais par la suite, une adresse IP statique pour l’appareil peut être configurée sur l’appareil ou sur le commutateur ou le routeur en amont.)

   Ces ports doivent être ouverts (en plus des ports normaux pour les médias) :
   - HTTPS : 443
   - HTTP : 80

   Si votre réseau fonctionne via un proxy, vous aurez également besoin de l’adresse du proxy ou des informations de script.
    
   > [!IMPORTANT]
   > Les salles Microsoft Teams ne prend pas en charge l’authentification du proxy, car elle peut interférer avec les opérations régulières de la salle. Avant de passer en production, assurez-vous que les salles Microsoft Teams ont été exemptées de l’authentification du proxy.
  
3. Pour améliorer votre expérience, Microsoft collecte des données. Pour autoriser Microsoft à collecter des données, autorisez les sites ci-après :

   - Point de terminaison du client de télémétrie : https://vortex.data.microsoft.com/
   - Point de terminaison des paramètres de télémétrie : https://settings.data.microsoft.com/
    
### <a name="create-and-test-a-device-account"></a>Création et test d’un compte d’appareil

Un  *compte d’appareil*  est un compte que le client Salles Microsoft Teams utilise pour accéder aux fonctionnalités d’Exchange, telles que le calendrier, et activer Skype Entreprise. Pour [plus d’informations, voir](rooms-deploy.md) Déployer les salles Microsoft Teams.
  
### <a name="check-network-availability"></a>Vérification de la disponibilité du réseau

Pour fonctionner correctement, l’appareil Salles Microsoft Teams doit avoir accès à un réseau câblé qui répond aux conditions requises :
  
- Accès à votre instance Active Directory ou Azure Active Directory (Azure AD), ainsi qu’à vos serveurs Microsoft Exchange et Skype Entreprise.

- Accès à un serveur pouvant fournir une adresse IP à l’aide du protocole DHCP. Les salles Microsoft Teams ne peuvent pas être configurées avec une adresse IP statique au démarrage de la première unité.

- Accès aux ports HTTP 80 et 443.

- Ports TCP et UDP configurés comme décrit dans la configuration requise pour les ports et protocoles pour les serveurs pour les implémentations Skype Entreprise Server sur site, ou les URL et plages d’adresses [IP Microsoft 365 et Office 365](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US) pour les implémentations en ligne de Microsoft Teams ou de Skype Entreprise. [](/skypeforbusiness/plan-your-deployment/network-requirements/ports-and-protocols)

> [!IMPORTANT]
> Veillez à utiliser une connexion réseau câblée de 1 Gbits/s afin d’être sûr de disposer de la bande passante nécessaire. 

> [!NOTE]
> Les mises à jour logicielles des salles Microsoft Teams sont automatiquement téléchargées à partir du Microsoft Store pour Entreprises. Consultez [les conditions préalables pour que Microsoft Store](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business) pour Entreprises et Éducation vérifie que la console de salle sera en mesure d’accéder au Store et de se mettre à jour.
  
### <a name="certificates"></a>Certificats

Votre appareil Salles Microsoft Teams utilise des certificats pour les services web Exchange, Microsoft Teams ou Skype Entreprise, l’utilisation du réseau et l’authentification. Si des serveurs associés utilisent des certificats publics, ce qui est le cas des déploiements en ligne et de certains sur site, aucune autre action de l’administrateur n’est requise pour l’installation des certificats. En revanche, si l’autorité de certification (CA) est privée (généralement le cas des déploiements sur site), l’appareil devra l’approuver, ce qui implique une installation de certificats en chaîne (CA + CA). L’ajout de l’appareil au domaine peut permettre d’automatiser cette tâche.
  
Vous installerez les certificats comme vous le feriez pour tout autre client Windows.  
  
> [!NOTE]
> Des certificats peuvent être nécessaires pour que les salles Microsoft Teams utilisent Skype Entreprise Server.
  
### <a name="proxy"></a>Proxy

Les salles Microsoft Teams sont conçues pour hériter des paramètres proxy du système d’exploitation Windows. Accédez au système d’exploitation Windows de la manière suivante :
  
1. Dans l’interface utilisateur de Salles Microsoft Teams, cliquez sur l’icône d’engrenage Paramètres dans laquelle vous serez invité à consulter le mot de passe administrateur local sur l’appareil (le mot de passe par défaut **est sfb).**
2. Appuyez sur **Paramètres,** puis sur le bouton Aller  à **Windows,** puis sur le  bouton Se connectez-vous à l’administrateur, puis cliquez sur le bouton Administrateur (si l’ordinateur est joint au domaine, sélectionnez Autre **utilisateur,** puis utilisez .\admin comme nom d’utilisateur).
3. Dans la **zone Rechercher dans Windows,** tapez le type en bas à gauche dans regedit (appuyez longuement sur l’écran ou cliquez avec le bouton droit et sélectionnez **Exécuter en tant qu’administrateur).**
4. Cliquez sur le dossier HKEY_USERS (vous verrez une liste de SID de l’utilisateur d’ordinateur), assurez-vous que le dossier racine HKEY_USERS est sélectionné.
       
5. Cliquez sur Fichier, puis **sélectionnez Charger la ruche.**
6. Accédez au **dossier C:\Users\Skype,** tapez le nom de fichier dans la zone NOMFAUX.dat, puis appuyez sur le bouton ouvrir.

7. Vous êtes invité à nommer la clé de votre ruche nouvellement chargée. dans Skype (vous devez maintenant voir les paramètres du Registre de l’utilisateur Skype).
 
8. Ouvrez la clé Skype et naviguez jusquHKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings vous assurer que les paramètres sont entrés : 
    
    ```console
    [HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings]
    "MigrateProxy"=dword:00000001
    "ProxyEnable"=dword:00000001
    "ProxyServer"="xx.xx.xx.xx:8080"
    ```
    
    Si ProxyServer n’existe pas, vous devrez peut-être ajouter cette clé en tant qu’une chaîne, changez xx.xx.xx.xx:8080 pour ip/host et port de votre serveur Proxy.
 
    Si le client utilise un fichier PAC, la configuration doit ressembler à l’exemple ci-dessous :

     ```console
    [HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings]
    "MigrateProxy"=dword:00000001
    "ProxyEnable"=dword:00000001
    "AutoConfigURL"=http://contosoproxy.corp.net/proxy.pac
    ```
    
9. Une fois que vous avez terminé vos modifications, mettez en surbrillance la clé Utilisateur Skype (dossier racine pour Skype) et choisissez de décharger Hive du menu de fichier Registre (vous serez invité à confirmer - sélectionnez **Oui**).
    
10. Vous pouvez désormais fermer l’éditeur de registre et saisissez déconnexion dans la zone de recherche Windows.
    
11. De retour dans l’écran de connexion, choisissez l’utilisateur **Skype**. Si toutes les étapes précédentes ont réussi, l’appareil Salles Microsoft Teams se connecte avec succès.
    
Pour plus [d’informations](https://docs.microsoft.com/microsoftteams/rooms/security#network-security) sur les FQDN, ports et plages d’adresses IP requis pour les salles Microsoft Teams, consultez l’article sur la sécurité réseau.
  
  
### <a name="create-provisioning-packages"></a>Création de packages de mise en service

Vous utiliserez des packages d’approvisionnement pour vous authentifier Exchange Server, Microsoft 365 ou Office 365.
  
### <a name="admin-group-management"></a>Gestion du groupe d’administrateurs

Après la jonction du domaine, vous pouvez utiliser la stratégie de groupe ou la gestion de l’ordinateur local pour définir un groupe de sécurité en tant qu’administrateur local comme vous le feriez pour un ordinateur Windows dans votre domaine. Tous les membres de ce groupe de sécurité peuvent saisir leurs informations d’identification et déverrouiller les paramètres.
  
> [!NOTE]
> Si votre appareil Microsoft Teams Rooms n’approuve plus le domaine (par exemple, si vous supprimez Microsoft Teams Rooms du domaine après la jonction), vous ne pourrez pas vous authentifier dans l’appareil et ouvrir les paramètres. La solution consiste à se connecter avec le compte d’administrateur local. 
  
## <a name="local-accounts"></a>Comptes locaux

### <a name="microsoft-teams-rooms-local-user-account"></a>Compte d’utilisateur local salles Microsoft Teams

Le compte d’appareil n’utilise généralement pas de mot de passe. Il est possible d’attribuer un mot de passe, mais cela aura un impact, notamment la possibilité d’empêcher les utilisateurs d’accéder à l’application de la console lorsque le mot de passe expire. Par conséquent, l’administrateur doit prendre des mesures pour éviter l’expiration du mot de passe.
  
### <a name="admin---local-administrator-account"></a>"Admin" - Compte d’administrateur local

Le mot de passe par défaut des salles Microsoft Teams est définie sur « sfb ». Le mot de passe peut être modifié localement en vous rendant dans les Paramètres Windows, dans Windows ou dans le fichier AutoUnattend.xml (utilisez le Gestionnaire d’images système Windows d’ADK pour apporter la modification au fichier \> xml).
  
> [!CAUTION]
> N’oubliez pas de modifier le mot de passe des salles Microsoft Teams dès que possible. 
  
Vous pouvez également gérer le mot de passe de l’administrateur local en configurant une stratégie de groupe qui définit les administrateurs de domaine comme administrateurs locaux.
  
Le mot de passe de l’administrateur local n’est pas inclus comme alternative lors de l’installation.
  
### <a name="machine-account"></a>Compte d’ordinateur

Tout comme sur n’importe quel appareil Windows, vous pouvez renommer le nom de l’ordinateur en cliquant avec le bouton droit dans **Paramètres** À propos \>  \> **de Renommer le PC.**
  
Si vous voulez renommer l’ordinateur après l’avoir joint à un domaine, utilisez **Renommer** l’ordinateur, une commande PowerShell, suivie du nouveau nom de l’ordinateur.
  
## <a name="related-topics"></a>Rubriques connexes

[Planifier des salles Microsoft Teams](rooms-plan.md)

[Spécifications des salles Microsoft Teams](requirements.md)
  
[Déployer les Salles Microsoft Teams](rooms-deploy.md)
  
[Configurer une console des salles Microsoft Teams](console.md)
  
[Gérer les Salles Microsoft Teams](rooms-manage.md)

[Conditions préalables au Microsoft Store pour Entreprises et Éducation](https://docs.microsoft.com/microsoft-store/prerequisites-microsoft-store-for-business) 
