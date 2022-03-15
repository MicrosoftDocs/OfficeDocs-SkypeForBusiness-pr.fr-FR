---
title: Préparer votre environnement
ms.author: czawideh
author: cazawideh
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
description: Découvrez comment préparer votre infrastructure pour le déploiement d Salles Microsoft Teams de sorte que vous pouvez tirer parti de toutes les fonctionnalités.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5203972feee8276d9d63c19f65965f62386ee7a0
ms.sourcegitcommit: a894e9397050e09bfaab02e700e943a3bbeb1302
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/15/2022
ms.locfileid: "63503951"
---
# <a name="prepare-your-environment"></a>Préparer votre environnement

Cette section contient une vue d’ensemble des étapes requises pour préparer votre environnement afin que vous pouvez utiliser toutes les fonctionnalités de Salles Microsoft Teams.
  
1. Préparez un compte de ressource pour chaque console Salles Microsoft Teams ressources. Pour [plus d’Salles Microsoft Teams](rooms-deploy.md) consultez La liste des déploiements.
    
2. Vérifiez qu’une connexion réseau/Internet fonctionne et peut être utilisée par l’appareil. 
  
3. Pour améliorer votre expérience, Microsoft collecte des données. Pour autoriser Microsoft à collecter des données, autorisez les sites ci-après :

   - Point de terminaison du client de télémétrie : https://vortex.data.microsoft.com/
   - Point de terminaison des paramètres de télémétrie : https://settings.data.microsoft.com/
    
### <a name="create-and-test-a-resource-account"></a>Créer et tester un compte de ressource

Un *compte de ressource* est un compte que le client Salles Microsoft Teams utilise pour accéder aux fonctionnalités d’Exchange, telles que le calendrier, et se connecter à Microsoft Teams. Pour [plus d’Salles Microsoft Teams](rooms-deploy.md) consultez La liste des déploiements.
  
### <a name="check-network-availability"></a>Vérification de la disponibilité du réseau

Pour fonctionner correctement, les Salles Microsoft Teams doivent avoir accès à un réseau câblé qui répond aux exigences ci-après :
  
- Accédez à votre instance Active Directory ou Azure Active Directory (Azure AD), ainsi qu’à Microsoft Exchange et Microsoft Teams.

- Accès à un serveur pouvant fournir une adresse IP à l’aide du protocole DHCP. Salles Microsoft Teams ne peut pas être configuré avec une adresse IP statique au démarrage de la première unité.

- Accès aux ports HTTP 80 et 443.

- Ports TCP et UDP configurés comme décrit dans [](/skypeforbusiness/plan-your-deployment/network-requirements/ports-and-protocols) les exigences de port et de protocole pour les serveurs pour les implémentations Skype Entreprise Server sur site, ou [URL et plages d’adresses IP Microsoft 365 et Office 365](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&amp;rs=en-US&amp;ad=US) pour les Microsoft Teams.

Si votre réseau fonctionne via un proxy, vous aurez également besoin de l’adresse du proxy ou des informations de script.
    
> [!IMPORTANT]
> Salles Microsoft Teams ne prend pas en charge l’authentification du proxy, car elle peut interférer avec les opérations régulières de la salle. Avant de passer en production, Salles Microsoft Teams avez été exemptés d’authentification du proxy.

> [!IMPORTANT]
> Veillez à utiliser une connexion réseau câblée de 1 Gbits/s afin d’être sûr de disposer de la bande passante nécessaire. 

> [!NOTE]
> Les mises à jour logicielles Salles Microsoft Teams sont automatiquement téléchargées à partir du Microsoft Store pour Entreprises. [Consultez les conditions préalables Microsoft Store pour Entreprises et](/microsoft-store/prerequisites-microsoft-store-for-business) Éducation pour vérifier que la console de salle sera en mesure d’accéder au Store et de se mettre à jour.
  
### <a name="certificates"></a>Certificats

Votre appareil Salles Microsoft Teams utilise des certificats pour les services web Exchange, l’Microsoft Teams, la Skype Entreprise, l’utilisation du réseau et l’authentification. Si les serveurs associés utilisent des certificats publics, comme c’est le cas pour les déploiements en ligne et certains déploiements locaux, l’installation des certificats ne devrait pas avoir lieu de la part de l’administrateur. En revanche, si l’autorité de certification est privée, l’appareil doit faire confiance à cette autorité de certification. Cela signifie que les certificats de chaîne CA + CA sont installés sur l’appareil. L’ajout de l’appareil au domaine peut permettre d’automatiser cette tâche.
  
Vous installerez les certificats comme vous le feriez pour tout autre client Windows.  
  
> [!NOTE]
> Des certificats peuvent être nécessaires pour que les certificats Salles Microsoft Teams’Skype Entreprise Server.
  
### <a name="proxy"></a>Proxy

Salles Microsoft Teams est conçu pour hériter des paramètres proxy du système d’Windows système d’exploitation. Accédez au système d’exploitation Windows de la manière suivante :
  
1. Dans l’interface utilisateur Salles Microsoft Teams, cliquez sur l’icône d’engrenage Paramètres dans laquelle vous êtes invité à consulter le mot de passe administrateur local sur l’appareil (le mot de passe par défaut est **sfb**).
2. Appuyez sur **Paramètres** puis sur le bouton Aller à **Windows**, puis sur le bouton Se connectez-vous  à l’administrateur, puis cliquez sur le bouton Administrateur  (si l’ordinateur est joint au domaine, sélectionnez Autre utilisateur **,** puis utilisez .\admin comme nom d’utilisateur).
3. Dans la **zone Rechercher Windows** tapez en bas à gauche dans regedit (appuyez longuement sur l’écran ou cliquez avec le bouton droit et sélectionnez **Exécuter en tant qu’administrateur**).
4. Cliquez sur le dossier HKEY_USERS (vous verrez une liste de SID de l’utilisateur d’ordinateur), assurez-vous que le dossier racine HKEY_USERS est sélectionné.
       
5. Cliquez sur Fichier, puis **sélectionnez Charger la ruche.**
6. Accédez au **dossier C:\Users\Skype** tapez le nom de fichier dans la zone NOMFAUX.dat, puis appuyez sur le bouton ouvrir.

7. Vous êtes invité à nommer la clé de votre ruche nouvellement chargée. tapez dans Skype (vous devez à présent voir les paramètres du Registre de l Skype un utilisateur).
 
8. Ouvrez la Skype et accédez à HKEY_USERS\Skype\SOFTWARE\Microsoft\Windows\CurrentVersion\Internet Settings vérifier que les paramètres sont entrés : 
    
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
  
### <a name="admin-group-management"></a>Gestion du groupe d’administrateurs

Si vous choisissez de rejoindre un domaine (Azure Active Directory ou Active Directory), vous pouvez utiliser Microsoft Endpoint Manager, stratégie de groupe ou gestion locale d’ordinateurs pour définir un groupe de sécurité en tant qu’administrateur local, comme vous le feriez pour un PC Windows dans votre domaine. Tous les membres de ce groupe de sécurité peuvent saisir leurs informations d’identification et déverrouiller les paramètres.
  
> [!NOTE]
> Si votre appareil Microsoft Teams Rooms n’approuve plus le domaine (par exemple, si vous supprimez Microsoft Teams Rooms du domaine après la jonction), vous ne pourrez pas vous authentifier dans l’appareil et ouvrir les paramètres. La solution consiste à se connecter avec le compte d’administrateur local. 
  
## <a name="local-accounts"></a>Comptes locaux

### <a name="microsoft-teams-rooms-local-user-account"></a>Salles Microsoft Teams d’utilisateur local

salles Teams inclut un compte local sans mot de passe nommé « Skype ». Ce compte est utilisé pour se Windows pour lancer l’salles Teams appappe. L’application d’un mot de passe à ce compte n’est pas prise en charge. Pour [plus d Salles Microsoft Teams, voir Sécurité](security.md) des données.
  
### <a name="admin---local-administrator-account"></a>"Admin" - Compte d’administrateur local

Salles Microsoft Teams mot de passe par défaut est « sfb ». Le mot de passe peut être modifié en local via le mode d’administration ou dans le fichier AutoUnattend.xml (utilisez le gestionnaire d’images système Windows d’ADK pour apporter la modification au fichier xml).
  
> [!CAUTION]
> N’oubliez pas de modifier Salles Microsoft Teams mot de passe dans les plus brefs délais. 
  
Le mot de passe de l’administrateur local n’est pas inclus comme alternative lors de l’installation.

Vous pouvez en savoir plus sur le compte administrateur dans l’article [Salles Microsoft Teams Sécurité](security.md).
  
### <a name="machine-account"></a>Compte d’ordinateur

À l’Windows n’importe quel appareil,  \> vous pouvez renommer le nom de l’ordinateur en cliquant Paramètres **à** \> propos de **Renommer le PC**.
  
Si vous voulez renommer l’ordinateur après l’avoir joint à un domaine, utilisez [Renommer l’ordinateur](/powershell/module/microsoft.powershell.management/rename-computer?view=powershell-7.2), une commande PowerShell, suivie du nouveau nom de l’ordinateur.
  
## <a name="related-topics"></a>Sujets associés

[Planifier Salles Microsoft Teams](rooms-plan.md)

[Spécifications des salles Microsoft Teams](requirements.md)
  
[Déployer les Salles Microsoft Teams](rooms-deploy.md)
  
[Configurer une console des salles Microsoft Teams](console.md)
  
[Gérer les Salles Microsoft Teams](rooms-manage.md)

[Conditions préalables pour la Microsoft Store pour Entreprises et l’éducation](/microsoft-store/prerequisites-microsoft-store-for-business)
