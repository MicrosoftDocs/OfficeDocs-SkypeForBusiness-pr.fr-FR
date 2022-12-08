---
title: Inscrire un appareil de salle Teams dans Pro Management
author: altsou
ms.author: altsou
manager: serdars
ms.date: 09/28/2022
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_MTRP
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Intégration d’appareils salles Teams au portail Pro Management
f1keywords: ''
ms.openlocfilehash: f5994c5ced6097104ee74044ee2441bc8388f5c3
ms.sourcegitcommit: aa398950cc2f10b268c72a2b25caa0cf893e8230
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/08/2022
ms.locfileid: "69307959"
---
# <a name="enroll-device-into-pro-management"></a>Inscrire un appareil dans Pro Management

Le déploiement nécessite l’intégration Salles Microsoft Teams appareils au portail de gestion Salles Microsoft Teams Pro. L’agent de service de surveillance est destiné à être utilisé avec les systèmes et périphériques certifiés Microsoft Teams Room (MTR).

## <a name="prerequisites"></a>Conditions préalables

Suivez ces procédures pour configurer votre matériel avant de tenter le processus d’inscription :

### <a name="adding-proxy-settings-optional"></a>Ajout de paramètres de proxy (facultatif)

1. Connectez-vous en tant qu’administrateur en suivant [Effectuer des opérations en tant qu’utilisateur Administration de l’appareil MTR](#performing-operations-as-the-admin-user-of-the-mtr-device).
1. Dans le champ Windows ***Search** _ (section inférieure gauche de l’écran), entrez _ *cmd** (appuyez longuement sur l’écran ou sélectionnez à droite, puis choisissez **_Exécuter en tant qu’administrateur_**).
1. Exécutez la commande suivante (les guillemets doubles à la fin de la commande sont importants) :

   - Si vous utilisez un ***serveur proxy*** unique : `bitsadmin /Util /SetIEProxy LOCALSYSTEM MANUAL_PROXY <proxyserver>:<port> ""`

     *Exemple:*

     ```DOS
     bitsadmin /Util /SetIEProxy LOCALSYSTEM MANUAL_PROXY contosoproxy.corp.net:8080 ""
     ```

   - Si vous utilisez un fichier ***pac*** : `bitsadmin /Util /SetIEProxy LOCALSYSTEM AUTOSCRIPT <pac file url>`

     *Exemple:*

     ```DOS
     bitsadmin /Util /SetIEProxy LOCALSYSTEM AUTOSCRIPT http://contosoproxy.corp.net/proxy.pac
     ```

### <a name="enabling-tpm-settings"></a>Activation des paramètres TPM

> [!NOTE]
> Le module de plateforme sécurisée doit être activé pour s’inscrire à Pro Management.

Si le module TPM sur un appareil Intel NUC est désactivé, activez TPM sur ces appareils comme suit :

1. Branchez le clavier à un appareil NUC.
1. Redémarrez l’appareil.
1. Pour afficher l’écran du BIOS, appuyez rapidement sur **F2**.
1. Sélectionnez **Avancé**.
1. Sélectionnez **Sécurité**.
1. Sur le côté droit, sous Fonctionnalités de sécurité, activez la **technologie Intel Platform Trust**.
1. Pour enregistrer vos paramètres, appuyez sur **F10**.
1. Dans la zone de confirmation, sélectionnez **Oui**.

## <a name="performing-operations-as-the-admin-user-of-the-mtr-device"></a>Exécution d’opérations en tant qu’utilisateur Administration de l’appareil MTR

Certaines procédures de configuration/installation vous obligent à vous connecter à l’appareil en tant qu’administrateur.

Pour vous connecter à l’appareil en tant qu’administrateur (administrateur local) :

1. Veillez à raccrocher les appels en cours et à revenir à l’écran d’accueil.
1. Dans l’interface utilisateur Microsoft Salle Teams, sélectionnez **Plus**, puis **Paramètres**, où vous êtes invité à entrer le mot de passe administrateur local sur l’appareil (le mot de passe par défaut est **_sfb_**).
1. Sélectionnez **Paramètres**, puis Paramètres  **Windows**  pour accéder à Windows en tant qu’administrateur local.

1. Dans la liste des utilisateurs affichée dans l’écran de connexion Windows, sélectionnez  **Administrateur** (ou l’administrateur local respectif de votre appareil).

> [!NOTE]
> Si l’ordinateur est *joint à un domaine*, choisissez **Autre utilisateur**, puis utilisez **.\admin** ou le nom d’utilisateur de l’administrateur local configuré dans l’appareil comme nom d’utilisateur.

Pour revenir à l’application Salles Microsoft Teams après avoir effectué les tâches d’administration nécessaires :

1. Dans le ***menu Démarrer*** de Windows, déconnectez-vous du compte Administration.
1. Revenez à Salles Microsoft Teams en sélectionnant l’icône de compte d’utilisateur à l’extrême gauche de l’écran, puis en sélectionnant **Skype**.

> [!NOTE]
> Si l’utilisateur Skype n’est pas répertorié, sélectionnez Autre utilisateur, entrez ***.\skype*** comme nom d’utilisateur, puis connectez-vous.

## <a name="urls-required-for-communication"></a>URL requises pour la communication

 > [!NOTE]
 > Tout le trafic réseau entre l’agent d’appareils MTR et le portail de gestion Salles Microsoft Teams Pro est SSL sur le port 443 *.*  Voir [URL Office 365 et plages d’adresses IP - Microsoft 365 Entreprise | Microsoft Docs](/microsoft-365/enterprise/urls-and-ip-address-ranges?view=o365-worldwide&preserve-view=true).

Les hôtes suivants doivent être autorisés si la **liste d’autorisation du trafic** est activée dans votre environnement d’entreprise :

agent.rooms.microsoft.com<br>
global.azure-devices-provisioning.net<br>
gj3ftstorage.blob.core.windows.net<br>
mmrstgnoamiot.azure-devices.net<br>
mmrstgnoamstor.blob.core.windows.net<br>
mmrprodapaciot.azure-devices.net<br>
mmrprodapacstor.blob.core.windows.net<br>
mmrprodemeaiot.azure-devices.net<br>
mmrprodemeastor.blob.core.windows.net<br>
mmrprodnoamiot.azure-devices.net<br>
mmrprodnoamstor.blob.core.windows.net

## <a name="enrollment-process"></a>Processus d’inscription

Le processus d’inscription implique les étapes suivantes :

1. Dans la barre de navigation de gauche du portail [http://portal.rooms.microsoft.com](https://portal.rooms.microsoft.com/)de gestion Salles Microsoft Teams Pro , développez **Paramètres**, puis sélectionnez **Général**.
1. Sous *Inscrire une salle*, sélectionnez **Télécharger le programme d’installation**  pour télécharger le logiciel de l’agent de surveillance.
1. **Optionnel:** Configurer les paramètres de proxy pour l’agent ; consultez [Ajout de paramètres de proxy (facultatif)](#adding-proxy-settings-optional).
1. Installez le programme d’installation de l’agent (téléchargé à l’étape 2) sur les unités MTR, soit en exécutant le MSI localement sur un appareil MTR, soit via vos moyens normaux de publication d’applications MSI en masse sur les appareils de votre environnement (stratégie de groupe, etc.)
1. La salle apparaît dans le portail dans un délai de 5 à 10 minutes.

   ![Capture d’écran des paramètres et des clés d’auto-inscription.](../media/software-installation-005new.png)

> [!NOTE]
> Si vous devez installer l’agent sans que l’application Teams sur le MTR puisse se connecter à Teams, vous pouvez utiliser notre clé d’inscription comme processus facultatif. Accédez à « ? »  (Aide) dans le coin supérieur droit du portail, puis sélectionnez « Télécharger la clé (facultatif) ». Lors de l’installation de l’agent, placez la « clé d’inscription automatique » (précédemment téléchargée à partir du portail) dans le répertoire **C:\Rigel** de l’appareil.

## <a name="installation"></a>Installation

Après avoir téléchargé le programme d’installation à partir de Microsoft (à partir du portail ou à l’aide de l’URL AKA.ms fournie ci-dessus), décompressez son contenu pour accéder au fichier **ManagedRoomsInstaller.msi**.

Il existe deux modes d’installation : 1) installation d’ordinateur local individuel et 2) mode de déploiement en masse (généralement via Intune de méthode similaire). Nous vous recommandons d’effectuer une installation individuelle pour les machines qui ne sont pas jointes à un domaine ou pour les machines pour lesquelles vous n’avez aucun moyen d’exécuter des programmes d’installation MSI à distance.

En raison des nombreuses façons variées dont les clients peuvent exécuter des applications MSI en mode de déploiement en masse, ce document décrit uniquement l’installation en mode individuel ainsi qu’en bloc sur les appareils inscrits Intune.

### <a name="individual-device-installation"></a>Installation d’un appareil individuel

1. Connectez-vous à l’appareil en tant qu’administrateur. Vérifiez que les étapes *Exécution des opérations en tant qu’utilisateur Administration de l’appareil* sont suivies.

1. Copiez le **fichierManagedRoomsInstaller.msi** sur l’appareil MTR.

   Lors de l’exécution du ***ManagedRoomsInstaller.msi*** est un écran Contrat de licence.

1. Après avoir lu le contrat, cochez ***J’accepte les termes du Contrat de licence** _ et appuyez sur _*Installer**.

    Cela commence l’installation du logiciel de surveillance Salles Microsoft Teams Pro. Une invite d’élévation (exécuter en tant qu’administrateur) s’affiche.

1. Sélectionnez **Oui**.

    L’installation se poursuit. Pendant la procédure d’installation, une fenêtre de console s’ouvre et commence la dernière étape de l’installation du logiciel de surveillance Salles Microsoft Teams Pro.

    > [!NOTE]
    > Ne fermez pas la fenêtre. Une fois l’installation terminée, l’Assistant affiche un bouton « Terminer ».

### <a name="intune-enrolled-device-bulk-deployment"></a>Déploiement en bloc d’appareils inscrits Intune

Les composants suivants sont des prérequis pour une installation réussie : 

- **Inscription Intune** : salles Teams sur les appareils Windows doivent déjà être inscrits dans Intune.
  Pour plus d’informations sur l’inscription de salles Teams sur des appareils Windows dans Intune, consultez [Inscription de Salles Microsoft Teams sur des appareils Windows avec Microsoft Endpoint Manager - Microsoft Tech Community](https://techcommunity.microsoft.com/t5/intune-customer-success/enrolling-microsoft-teams-rooms-on-windows-devices-with/ba-p/3246986)
- **Groupe Azure AD avec tous les salles Teams sur les appareils Windows en tant que membres** : groupe créé dans Azure AD qui inclut tous les salles Teams sur les appareils Windows qui doivent faire partie du service Salles Microsoft Teams Premium. Ce groupe sera utilisé pour cibler le déploiement de l’agent MTR Pro.
  
> [!NOTE]
> Vous pouvez envisager d’utiliser des groupes dynamiques dans Azure AD à cet effet. Pour plus d’informations, consultez [Inscription de Salles Microsoft Teams sur des appareils Windows avec Microsoft Endpoint Manager - Microsoft Tech Community](https://techcommunity.microsoft.com/t5/intune-customer-success/enrolling-microsoft-teams-rooms-on-windows-devices-with/ba-p/3246986)
- Télécharger le **programme d’installation** de **l’agent MTR Pro** : téléchargez le fichier zip de l’agent à partir de <https://aka.ms/serviceportalagentmsi> et extrayez le contenu du fichier zip (ManagedRoomsInstaller.msi) dans un dossier temporaire local.

**Pour installer à l’aide de Intune**

1. Connectez-vous au [centre d’administration Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
1. Sélectionnez **Applications** > **Toutes les applications** > **Ajouter**.
1. Dans le volet **Sélectionner un type d’application** , sous **Autres types d’applications** , sélectionnez **Application métier**.
1. Cliquez sur **Sélectionner**. Les étapes **Ajouter une application s’affichent** . 
1. Dans le volet **Ajouter une application** , cliquez sur **Sélectionner le fichier de package d’application**.
   1. Dans le volet **Fichier de package** d’application, sélectionnez  **Parcourir**. Ensuite, sélectionnez le fichier **ManagedRoomsInstaller.msi** téléchargé précédemment (reportez-vous à la section Conditions préalables).
   1. Lorsque vous avez terminé, sélectionnez **OK** dans le volet **Fichier de package** d’application pour ajouter l’application.
1. Dans la page **Informations sur l’application** , effectuez les modifications suivantes :
   1. Éditeur : entrez **Microsoft Corporation**.
   1. Ignorer la version de l’application : sélectionnez **Oui**.

      > [!NOTE]
      > L’agent MTR Pro est en cours de mise à jour automatique ; par conséquent, vous devez ignorer explicitement la version de l’application (toute version de référence peut être mise à jour automatiquement).

   1. (Facultatif) Catégorie : sélectionnez **Gestion de l’ordinateur**.
   
1. Cliquez sur **Suivant** pour afficher la page **Affectations** .
   1. Sous la section **Obligatoire** , cliquez sur **+ ajouter un groupe** pour cibler un groupe d’appareils pour l’installation de l’agent.
   1. Dans le volet **Sélectionner un groupe** , tapez le nom du groupe dans la zone De recherche (reportez-vous aux conditions préalables ci-dessus), cliquez sur le **groupe** souhaité, puis cliquez sur **Sélectionner**.
      Pour plus d’informations, consultez [Ajouter des groupes pour organiser les utilisateurs et les appareils](https://go.microsoft.com/fwlink/?linkid=2202166) et [Affecter des applications à des groupes avec Microsoft Intune](https://go.microsoft.com/fwlink/?linkid=2202270).
1. Cliquez sur **Suivant** pour afficher la page **Vérifier + créer** .
1. Passez en revue les valeurs et les paramètres que vous avez entrés pour l’application. Lorsque vous avez terminé, cliquez sur **Créer** pour ajouter l’application à Intune.

Une fois le processus terminé, vos appareils commencent à installer l’agent MTR Pro après quelques minutes.

> [!NOTE]
> Après l’installation, l’agent MTR Pro peut prendre jusqu’à huit heures pour exécuter une mise à jour automatique vers la dernière version et être répertorié dans le portail MTR Pro.
Pour accélérer l’inscription automatique dans le portail MTR Pro, envisagez de redémarrer l’appareil MTR après le déploiement de l’agent.

## <a name="completing-enrollment"></a>Fin de l’inscription

Une fois l’installation terminée, attendez 5 à 10 minutes, puis actualisez le portail pour afficher l’appareil dans la liste, signalé comme état *d’intégration* .

Dans l’état *Intégration* , l’état de la salle est affiché et mis à jour, mais il ne déclenche pas d’alertes ni ne crée de tickets d’examen.

Choisissez la salle et sélectionnez **Inscrire**  pour commencer à recevoir des alertes d’incident.

### <a name="unenrolling-and-uninstalling-monitoring-software"></a>Désinscription et désinstallation des logiciels de surveillance

Pour désinscrire l’appareil, supprimez l’agent de surveillance de l’appareil MTR comme suit :

1. Sur l’appareil surveillé, connectez-vous à l’appareil en tant qu’administrateur. Veillez à suivre les étapes décrites dans *Exécution d’opérations en tant qu’utilisateur Administration de l’appareil*.
1. Téléchargez le script de réinitialisation à partir de [aka.ms/MTRPDeviceOffBoarding](https://aka.ms/MTRPDeviceOffBoarding).
1. Extrayez le script quelque part sur l’appareil et copiez le chemin d’accès.
1. Ouvrez PowerShell en tant qu’administrateur : dans le champ Windows ***Search** _ (section inférieure gauche de l’écran), entrez « Powershell », puis cliquez avec le bouton droit sur _*_Windows PowerShell_**.
1. Sélectionnez *« Exécuter en tant qu’administrateur »* et acceptez l’invite UAC.
1. Entrez *Set-ExecutionPolicy –ExecutionPolicy RemoteSigned* , puis appuyez sur **Y** à l’invite suivante.
1. Collez ou tapez le chemin complet du script de désintégrage décompressé dans la fenêtre PowerShell, puis **appuyez sur Entrée**.

   Exemple :

   ```powershell
   C:\Users\admin\Downloads\MTRP\_Device\_Offboarding\MTRP\_Device\_Offboarding.ps1
   ```

   Cette commande réinitialise l’appareil aux mises à jour MTR standard de l’utilisateur et supprime les fichiers et l’agent de surveillance MTR Pro.

1. Dans le menu de gauche du portail de gestion Salles Microsoft Teams Pro, sélectionnez **Salles**.
1. Dans la liste des salles fournies, choisissez la salle que vous souhaitez désinscrire, puis sélectionnez **Annuler l’inscription** pour arrêter d’obtenir des alertes d’incident ou des tickets d’enquête, ou pour signaler un incident pour la salle.

## <a name="troubleshooting-table"></a>Table de résolution des problèmes

> [!NOTE]
> Toutes les erreurs de surveillance Salles Microsoft Teams Pro sont consignées dans un fichier journal des événements spécifique nommé **Microsoft Salles gérées**.

***Emplacement du fichier journal du runtime de l’application*** =

C:\Windows\ServiceProfiles\LocalService\AppData\Local\ServicePortalAgent\ app-x.x.x\ServicePortalAgent\ServicePortal\_Verbose\_LogFile.log, où **x.x.x** est le numéro de version de l’application.

|Symptôme|Procédure recommandée|
|---|---|
|Vous recevez un message d’erreur indiquant : </p><p> ***ERREUR : exécutez cette application avec** _ <br> _ *_privilèges élevés_**|Exécutez l’application avec des privilèges élevés, puis réessayez.|
|||
|Vous recevez un message d’erreur indiquant : </p><p> ***Les données TPM sont introuvables***|Vérifiez que le module de plateforme sécurisée (TPM) est activé sur votre appareil dans son BIOS. Cela se trouve généralement dans les paramètres de sécurité du BIOS de l’appareil.|
|||
|Vous recevez un message d’erreur : </p><p> ***ERREUR : le compte d’utilisateur local nommé « Administration » ou « Skype » est introuvable***|Assurez-vous que les comptes d’utilisateur existent sur l’appareil certifié Microsoft système De salle Teams.|
|||
|Vous recevez tous les messages d’état d’erreur qui ne sont pas abordés ci-dessus.|Fournissez une copie de votre journal d’installation à votre agent de support système Microsoft Teams.|
