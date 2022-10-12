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
- Teams_ITAdmin_Rooms
description: Découvrez comment préparer votre infrastructure pour le déploiement de Salles Microsoft Teams afin de pouvoir tirer parti de toutes les fonctionnalités.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7006f560c5d0991b74c14fc5eb0b13e829b642d9
ms.sourcegitcommit: 8dd36e1e30a47316c15c99e964d0464715bcd742
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/12/2022
ms.locfileid: "68532224"
---
# <a name="prepare-your-environment"></a>Préparer votre environnement

Cette section contient une vue d’ensemble des étapes nécessaires à la préparation de votre environnement afin que vous puissiez utiliser toutes les fonctionnalités de Salles Microsoft Teams.
  
1. Préparez un compte de ressource pour chaque console Salles Microsoft Teams. Pour plus d’informations, consultez [Déployer Salles Microsoft Teams](rooms-deploy.md).
    
2. Vérifiez qu’une connexion réseau/Internet fonctionne et peut être utilisée par l’appareil. 
  
3. Pour améliorer votre expérience, Microsoft collecte des données. Pour permettre à Microsoft de collecter des données, autorisez ces sites :

   - Point de terminaison client de télémétrie : `https://vortex.data.microsoft.com/`
   - Point de terminaison des paramètres de télémétrie :` https://settings.data.microsoft.com/`
    
### <a name="create-and-test-a-resource-account"></a>Créer et tester un compte de ressource

Un *compte de ressource* est un compte que le client Salles Microsoft Teams utilise pour accéder aux fonctionnalités d’Exchange, telles que le calendrier, et pour se connecter à Microsoft Teams. Pour plus d’informations, consultez [Déployer Salles Microsoft Teams](rooms-deploy.md).
  
### <a name="check-network-availability"></a>Vérification de la disponibilité du réseau

Pour fonctionner correctement, Salles Microsoft Teams devez avoir accès à un réseau câblé qui répond aux exigences suivantes :
  
- Accès à votre instance Active Directory ou Azure Active Directory (Azure AD), ainsi qu’à Microsoft Exchange et Microsoft Teams.

- Accès à un serveur pouvant fournir une adresse IP à l’aide du protocole DHCP. Salles Microsoft Teams ne peut pas être configuré avec une adresse IP statique au démarrage de la première unité.

- Accès aux ports HTTP 80 et 443.

- Ports TCP et UDP configurés comme décrit dans [les exigences de port et de protocole pour les serveurs pour](/skypeforbusiness/plan-your-deployment/network-requirements/ports-and-protocols) les implémentations de Skype Entreprise Server locales, ou [Microsoft 365 et Office 365 URL et plages d’adresses IP](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US) pour Microsoft Teams.

Si votre réseau fonctionne via un proxy, vous aurez également besoin de l’adresse du proxy ou des informations de script.
    
> [!IMPORTANT]
> Salles Microsoft Teams ne prend pas en charge l’authentification proxy, car elle peut interférer avec les opérations régulières de la salle. Assurez-vous que Salles Microsoft Teams ont été exemptés de l’authentification par proxy avant de passer en production.

> [!IMPORTANT]
> Veillez à utiliser une connexion réseau câblée de 1 Gbits/s afin d’être sûr de disposer de la bande passante nécessaire. 

> [!NOTE]
> Les mises à jour logicielles pour Salles Microsoft Teams sont automatiquement téléchargées à partir du Microsoft Store pour Entreprises. Consultez [les prérequis pour Microsoft Store pour Entreprises et Éducation](/microsoft-store/prerequisites-microsoft-store-for-business) pour vérifier que la console de salle sera en mesure d’accéder au magasin et d’effectuer une mise à jour automatique.
  
### <a name="certificates"></a>Certificats

Votre appareil Salles Microsoft Teams utilise des certificats pour les services web Exchange, Microsoft Teams ou Skype Entreprise, l’utilisation du réseau et l’authentification. Si les serveurs associés utilisent des certificats publics, ce qui est le cas pour les déploiements en ligne et certains déploiements locaux, aucune autre action n’est requise de la part de l’administrateur pour installer des certificats. En revanche, si l’autorité de certification est une autorité de certification privée, l’appareil doit approuver cette autorité de certification. Cela signifie que les certificats de chaîne d’autorité de certification et d’autorité de certification sont installés sur l’appareil. L’ajout de l’appareil au domaine peut permettre d’automatiser cette tâche.
  
Vous installerez les certificats comme vous le feriez pour tout autre client Windows. 

> [!IMPORTANT]
> Si votre serveur proxy utilise des certificats signés en interne, vous devez installer la chaîne de certificats interne, y compris l’autorité de certification racine, sur l’appareil Salles Microsoft Teams.
  
> [!NOTE]
> Des certificats peuvent être nécessaires pour que Salles Microsoft Teams utiliser Skype Entreprise Server.
  
### <a name="proxy"></a>Proxy

Salles Microsoft Teams est conçu pour hériter des paramètres de proxy du système d’exploitation Windows. Accédez au système d’exploitation Windows de la manière suivante :
  
1. Dans l’interface utilisateur Salles Microsoft Teams, cliquez sur l’icône d’engrenage Paramètres dans laquelle vous êtes invité à entrer le mot de passe Administrateur local sur l’appareil (le mot de passe par défaut est **sfb**).
2. Appuyez sur **Paramètres**, puis appuyez sur le bouton **Accéder à Windows**, puis appuyez sur l’option **Accéder à Administration bouton Se connecter**, puis cliquez sur le bouton **Administrateur** (si l’ordinateur est joint au domaine, choisissez **Autre utilisateur,** puis utilisez .\admin comme nom d’utilisateur).
3. Dans la zone **Windows De recherche** , tapez le type en bas à gauche dans regedit (appuyez longuement sur l’écran ou cliquez avec le bouton droit et choisissez **Exécuter en tant qu’administrateur**).
4. Cliquez sur le dossier HKEY_USERS (vous verrez une liste de SID de l’utilisateur d’ordinateur), assurez-vous que le dossier racine HKEY_USERS est sélectionné.
       
5. Cliquez sur Fichier, puis choisissez **Charger Hive.**
6. Accédez au dossier **C:\Users\Skype** et tapez dans la zone nom de fichier NTUSER.dat, puis appuyez sur le bouton Ouvrir

7. Vous serez invité à entrer un nom de clé pour votre Hive nouvellement chargé ; tapez dans Skype (vous devez maintenant voir les paramètres du Registre pour l’utilisateur Skype).
 
8. Ouvrez la clé Skype et accédez à HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings puis vérifiez que ces paramètres sont entrés : 
    
    ```console
    [HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings]
    "MigrateProxy"=dword:00000001
    "ProxyEnable"=dword:00000001
    "ProxyServer"="xx.xx.xx.xx:8080"
    ```
    
    Si ProxyServer n’existe pas, vous devrez peut-être ajouter cette clé en tant qu’une chaîne, changez xx.xx.xx.xx:8080 pour ip/host et port de votre serveur Proxy.
 
    Si le client utilise un fichier PAC, la configuration ressemble à l’exemple ci-dessous :

     ```console
    [HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings]
    "MigrateProxy"=dword:00000001
    "ProxyEnable"=dword:00000001
    "AutoConfigURL"=http://contosoproxy.corp.net/proxy.pac
    ```
    
9. Une fois que vous avez terminé vos modifications, mettez en surbrillance la clé Utilisateur Skype (dossier racine pour Skype) et choisissez de décharger Hive du menu de fichier Registre (vous serez invité à confirmer - sélectionnez **Oui**).
    
10. Vous pouvez désormais fermer l’éditeur de registre et saisissez déconnexion dans la zone de recherche Windows.
    
11. De retour dans l’écran de connexion, choisissez l’utilisateur **Skype**. Si toutes les étapes précédentes ont réussi, l’appareil Salles Microsoft Teams se connecte correctement.
    
Consultez l’article [Sécurité réseau](./security-windows.md#network-security) pour plus d’informations sur les noms de domaine complets, les ports et les plages d’adresses IP requis pour Salles Microsoft Teams.
  
### <a name="admin-group-management"></a>Gestion du groupe d’administrateurs

Si vous choisissez de rejoindre un domaine (Azure Active Directory ou Active Directory), vous pouvez utiliser Microsoft Endpoint Manager, stratégie de groupe ou Gestion des ordinateurs locaux pour définir un groupe de sécurité en tant qu’administrateur local comme vous le feriez pour un PC Windows dans votre domaine. Tous les membres de ce groupe de sécurité peuvent saisir leurs informations d’identification et déverrouiller les paramètres.
  
> [!NOTE]
> Si votre appareil Microsoft Teams Rooms n’approuve plus le domaine (par exemple, si vous supprimez Microsoft Teams Rooms du domaine après la jonction), vous ne pourrez pas vous authentifier dans l’appareil et ouvrir les paramètres. La solution consiste à se connecter avec le compte d’administrateur local. 
  
## <a name="local-accounts"></a>Comptes locaux

### <a name="microsoft-teams-rooms-local-user-account"></a>Salles Microsoft Teams compte d’utilisateur local

salles Teams inclut un compte local sans mot de passe nommé « Skype ». Ce compte permet de se connecter à Windows pour lancer l’application salles Teams. Il n’est pas pris en charge d’appliquer un mot de passe à ce compte. Pour plus d’informations, consultez [Salles Microsoft Teams Sécurité](security-windows.md).
  
### <a name="admin---local-administrator-account"></a>"Admin" - Compte d’administrateur local

Salles Microsoft Teams mot de passe par défaut est défini sur « sfb ». Le mot de passe peut être modifié localement via le mode Administration ou dans le fichier AutoUnattend.xml (utilisez le gestionnaire d’images système Windows à partir d’ADK pour apporter la modification au fichier xml).
  
> [!CAUTION]
> Veillez à modifier le mot de passe Salles Microsoft Teams dès que possible. 
  
Le mot de passe de l’administrateur local n’est pas inclus comme alternative lors de l’installation.

Vous pouvez en savoir plus sur le compte Administration dans l’article [Salles Microsoft Teams Sécurité](security-windows.md).
  
### <a name="machine-account"></a>Compte d’ordinateur

Tout comme n’importe quel appareil Windows, le nom de la machine peut être renommé en cliquant avec le bouton droit dans **Paramètres** \> **à propos** \> **de renommer le PC**.
  
Si vous souhaitez renommer l’ordinateur après l’avoir joint à un domaine, utilisez [Rename-Computer](/powershell/module/microsoft.powershell.management/rename-computer), une commande PowerShell, suivie du nouveau nom de l’ordinateur.
  
## <a name="related-topics"></a>Rubriques connexes

[Planifier Salles Microsoft Teams](rooms-plan.md)

[Spécifications des salles Microsoft Teams](requirements.md)
  
[Déployer les Salles Microsoft Teams](rooms-deploy.md)
  
[Configurer une console des salles Microsoft Teams](console.md)
  
[Gérer les Salles Microsoft Teams](rooms-manage.md)

[Conditions préalables à l’Microsoft Store pour Entreprises et à l’éducation](/microsoft-store/prerequisites-microsoft-store-for-business)
