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
ms.localizationpriority: medium
ms.assetid: b4e0ad1e-12e5-4130-aec1-d8c9cd3a5965
ms.collection:
- M365-collaboration
description: Découvrez comment préparer votre infrastructure pour le déploiement d Salles Microsoft Teams de manière à tirer parti de toutes les fonctionnalités.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5003bbb3554436ca388990aeebfec4ce6dfb9f57
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58577958"
---
# <a name="prepare-your-environment"></a>Préparer votre environnement

Cette section contient une vue d’ensemble des étapes requises pour préparer votre environnement afin que vous pouvez utiliser toutes les fonctionnalités de Salles Microsoft Teams.
  
1. Préparez un compte d’appareil pour Salles Microsoft Teams console mobile. Pour [plus d’Salles Microsoft Teams](rooms-deploy.md) consultez La liste des déploiements.
    
2. Vérifiez qu’une connexion réseau/Internet fonctionne et peut être utilisée par l’appareil.  
    
   Il doit être en mesure de recevoir une adresse IP à l’aide de DHCP. (Salles Microsoft Teams ne peut pas être configuré avec une adresse IP statique au démarrage de la première unité, mais par la suite, une adresse IP statique pour l’appareil peut être configurée sur l’appareil ou sur le commutateur ou le routeur en amont.)

   Ces ports doivent être ouverts (en plus des ports normal pour les médias) :
   - HTTPS : 443
   - HTTP : 80

   Si votre réseau fonctionne via un proxy, vous aurez également besoin de l’adresse du proxy ou des informations de script.
    
   > [!IMPORTANT]
   > Salles Microsoft Teams ne prend pas en charge l’authentification du proxy, car elle peut interférer avec les opérations régulières de la salle. Avant de passer en production, assurez-Salles Microsoft Teams avez été exemptés de l’authentification du proxy.
  
3. Pour améliorer votre expérience, Microsoft collecte des données. Pour autoriser Microsoft à collecter des données, autorisez les sites ci-après :

   - Point de terminaison du client de télémétrie : https://vortex.data.microsoft.com/
   - Point de terminaison des paramètres de télémétrie : https://settings.data.microsoft.com/
    
### <a name="create-and-test-a-device-account"></a>Création et test d’un compte d’appareil

Un *compte d’appareil* est un compte que le client Salles Microsoft Teams utilise pour accéder aux fonctionnalités de Exchange, telles que le calendrier, et pour activer Skype Entreprise. Pour [plus d’Salles Microsoft Teams](rooms-deploy.md) consultez La liste des déploiements.
  
### <a name="check-network-availability"></a>Vérification de la disponibilité du réseau

Pour fonctionner correctement, l’Salles Microsoft Teams doit avoir accès à un réseau câblé qui répond aux exigences ci-après :
  
- Accès à votre instance Active Directory ou Azure Active Directory (Azure AD), ainsi qu’à vos serveurs Microsoft Exchange et Skype Entreprise.

- Accès à un serveur pouvant fournir une adresse IP à l’aide du protocole DHCP. Salles Microsoft Teams ne peut pas être configuré avec une adresse IP statique au démarrage de la première unité.

- Accès aux ports HTTP 80 et 443.

- Ports TCP et UDP configurés comme décrit dans la configuration requise pour les ports et protocoles pour les serveurs pour les implémentations Skype Entreprise Server en local, ou les URL et plages d’adresses [IP Microsoft 365](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US) et Office 365 pour les implémentations en ligne Microsoft Teams ou Skype Entreprise. [](/skypeforbusiness/plan-your-deployment/network-requirements/ports-and-protocols)

> [!IMPORTANT]
> Veillez à utiliser une connexion réseau câblée de 1 Gbits/s afin d’être sûr de disposer de la bande passante nécessaire. 

> [!NOTE]
> Les mises à jour logicielles Salles Microsoft Teams sont automatiquement téléchargées à partir du Microsoft Store pour Entreprises. Consultez [les conditions préalables Microsoft Store pour Entreprises et](/microsoft-store/prerequisites-microsoft-store-for-business) Éducation pour vérifier que la console de salle sera en mesure d’accéder au Store et de se mettre à jour.
  
### <a name="certificates"></a>Certificats

Votre Salles Microsoft Teams utilise des certificats pour les services Exchange web, l’Microsoft Teams ou Skype Entreprise, l’utilisation du réseau et l’authentification. Si des serveurs associés utilisent des certificats publics, ce qui est le cas des déploiements en ligne et de certains sur site, aucune autre action de l’administrateur n’est requise pour l’installation des certificats. En revanche, si l’autorité de certification (CA) est privée (généralement le cas des déploiements sur site), l’appareil devra l’approuver, ce qui implique une installation de certificats en chaîne (CA + CA). L’ajout de l’appareil au domaine peut permettre d’automatiser cette tâche.
  
Vous installerez les certificats comme vous le feriez pour tout autre client Windows.  
  
> [!NOTE]
> Des certificats peuvent être nécessaires pour être utilisés Salles Microsoft Teams et Skype Entreprise Server.
  
### <a name="proxy"></a>Proxy

Salles Microsoft Teams est conçu pour hériter des paramètres proxy du système d’Windows système d’exploitation. Accédez au système d’exploitation Windows de la manière suivante :
  
1. Dans l’interface utilisateur Salles Microsoft Teams, cliquez sur l’icône d’engrenage Paramètres dans laquelle vous êtes invité à consulter le mot de passe administrateur local sur l’appareil (le mot de passe par défaut est **sfb).**
2. Appuyez sur **Paramètres** puis sur le bouton Aller à **Windows,** puis  sur le bouton Se connectez-vous à l’administrateur, puis cliquez sur le bouton Administrateur (si l’ordinateur est joint au domaine, sélectionnez Autre  **utilisateur,** puis utilisez .\admin comme nom d’utilisateur).
3. Dans la **zone Rechercher Windows** tapez en bas à gauche dans regedit (appuyez longuement sur l’écran ou cliquez avec le bouton droit et sélectionnez Exécuter en tant **qu’administrateur).**
4. Cliquez sur le dossier HKEY_USERS (vous verrez une liste de SID de l’utilisateur d’ordinateur), assurez-vous que le dossier racine HKEY_USERS est sélectionné.
       
5. Cliquez sur Fichier, puis **sélectionnez Charger la ruche.**
6. Accédez au **dossier C:\Users\Skype,** tapez le nom de fichier dans la zone NOMFAUX.dat, puis appuyez sur le bouton ouvrir

7. Vous êtes invité à nommer la clé de votre ruche nouvellement chargée. tapez dans Skype (vous devez à présent voir les paramètres du Registre de l Skype un utilisateur).
 
8. Ouvrez la Skype clé d’accès et HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings vérifier que ces paramètres sont entrés : 
    
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
    
11. De retour dans l’écran de connexion, choisissez l’utilisateur **Skype**. Si toutes les étapes précédentes ont réussi, l Salles Microsoft Teams appareil se connecte correctement.
    
Pour plus [d’informations](./security.md#network-security) sur les FQDN, ports et plages d’adresses IP requis pour les Salles Microsoft Teams, voir l’article sur la sécurité réseau.
  
  
### <a name="create-provisioning-packages"></a>Création de packages de mise en service

Vous utiliserez des packages d’approvisionnement pour vous authentifier à des Exchange Server, Microsoft 365, ou à Office 365.
  
### <a name="admin-group-management"></a>Gestion du groupe d’administrateurs

Après la jonction du domaine, vous pouvez utiliser la stratégie de groupe ou la gestion de l’ordinateur local pour définir un groupe de sécurité en tant qu’administrateur local comme vous le feriez pour un ordinateur Windows dans votre domaine. Tous les membres de ce groupe de sécurité peuvent saisir leurs informations d’identification et déverrouiller les paramètres.
  
> [!NOTE]
> Si votre appareil Microsoft Teams Rooms n’approuve plus le domaine (par exemple, si vous supprimez Microsoft Teams Rooms du domaine après la jonction), vous ne pourrez pas vous authentifier dans l’appareil et ouvrir les paramètres. La solution consiste à se connecter avec le compte d’administrateur local. 
  
## <a name="local-accounts"></a>Comptes locaux

### <a name="microsoft-teams-rooms-local-user-account"></a>Salles Microsoft Teams Compte d’utilisateur local

Le compte d’appareil n’utilise généralement pas de mot de passe. Il est possible d’attribuer un mot de passe, mais cela aura un impact, notamment la possibilité d’empêcher les utilisateurs d’accéder à l’application de la console lorsque le mot de passe expire. Par conséquent, l’administrateur doit prendre des mesures pour éviter l’expiration du mot de passe.
  
### <a name="admin---local-administrator-account"></a>"Admin" - Compte d’administrateur local

Salles Microsoft Teams mot de passe par défaut est « sfb ». Le mot de passe peut être modifié localement en vous rendant dans Windows Paramètres Go to Windows ou dans le fichier AutoUnattend.xml (utilisez le gestionnaire d’images système Windows de ADK pour apporter la modification au fichier \> xml).
  
> [!CAUTION]
> N’oubliez pas de modifier Salles Microsoft Teams mot de passe dès que possible. 
  
Vous pouvez également gérer le mot de passe de l’administrateur local en configurant une stratégie de groupe qui définit les administrateurs de domaine comme administrateurs locaux.
  
Le mot de passe de l’administrateur local n’est pas inclus comme alternative lors de l’installation.
  
### <a name="machine-account"></a>Compte d’ordinateur

À l’Windows n’importe quel appareil, vous pouvez renommer le nom de l’ordinateur en cliquant avec le bouton droit **Paramètres** À propos de \>  \> **Renommer le PC.**
  
Si vous voulez renommer l’ordinateur après l’avoir joint à un domaine, utilisez **Renommer** l’ordinateur, une commande PowerShell, suivie du nouveau nom de l’ordinateur.
  
## <a name="related-topics"></a>Rubriques connexes

[Planifier Salles Microsoft Teams](rooms-plan.md)

[Spécifications des salles Microsoft Teams](requirements.md)
  
[Déployer les Salles Microsoft Teams](rooms-deploy.md)
  
[Configurer une console des salles Microsoft Teams](console.md)
  
[Gérer les Salles Microsoft Teams](rooms-manage.md)

[Conditions préalables pour les Microsoft Store pour Entreprises et l’éducation](/microsoft-store/prerequisites-microsoft-store-for-business)