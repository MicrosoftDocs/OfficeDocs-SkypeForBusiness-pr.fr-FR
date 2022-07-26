---
title: Inscrire un appareil Salle Teams dans les services managés
author: donnah007
ms.author: v-donnahill
manager: serdars
ms.date: 07/22/2022
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Intégration d’appareils salles Teams à des services managés
f1keywords: ''
ms.openlocfilehash: 124d301a37fde8802b60f3e59ad5f1a1dd19862c
ms.sourcegitcommit: f5d784df59a8010b390691bbb20c4ea66c46280b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/26/2022
ms.locfileid: "67005434"
---
# <a name="enroll-device-into-managed-service"></a>Inscrire un appareil dans le service managé

Le déploiement nécessite l’intégration d’appareils Salles Microsoft Teams aux services managés Salles Microsoft Teams. L’agent de service de surveillance est destiné à être utilisé avec des systèmes et périphériques MTR (Microsoft Teams Room) certifiés.

## <a name="prerequisites"></a>Conditions préalables

Suivez ces procédures pour configurer votre matériel avant de tenter le processus d’inscription :

### <a name="adding-proxy-settings-optional"></a>Ajout de paramètres de proxy (facultatif)

1. Connectez-vous en tant qu’administrateur [en effectuant des opérations en tant qu’utilisateur Administration de l’appareil MTR](#performing-operations-as-the-admin-user-of-the-mtr-device).
1. Dans le champ Windows ***Search** _ (section en bas à gauche de l’écran), entrez _ *cmd** (appuyez longuement sur l’écran ou sélectionnez à droite, puis **_choisissez Exécuter en tant qu’administrateur_**).
1. Exécutez la commande suivante (les guillemets doubles à la fin de la commande sont importants) :

   - Si vous utilisez un ***serveur proxy*** unique : `bitsadmin /Util /SetIEProxy LOCALSYSTEM MANUAL_PROXY <proxyserver>:<port> ""`

     *Exemple :*

     ```DOS
     bitsadmin /Util /SetIEProxy LOCALSYSTEM MANUAL_PROXY contosoproxy.corp.net:8080 ""
     ```

   - Si vous utilisez un fichier ***PAC*** : `bitsadmin /Util /SetIEProxy LOCALSYSTEM AUTOSCRIPT <pac file url>`

     *Exemple :*

     ```DOS
     bitsadmin /Util /SetIEProxy LOCALSYSTEM AUTOSCRIPT `http://contosoproxy.corp.net/proxy.pac`
     ```

### <a name="enabling-tpm-settings"></a>Activation des paramètres TPM

> [!NOTE]
> Le module de plateforme sécurisée doit être activé pour s’inscrire au service managé.

Si le module TPM sur un appareil Intel NUC est désactivé, activez le module de plateforme sécurisée sur ces appareils comme suit :

1. Branchez le clavier à un appareil NUC.
1. Redémarrez l’appareil.
1. Pour afficher l’écran BIOS, appuyez rapidement sur **F2**.
1. Sélectionnez **Avancé**.
1. Sélectionnez **Sécurité**.
1. Sur le côté droit sous Fonctionnalités de sécurité, activez **la technologie d’approbation de plateforme Intel**.
1. Pour enregistrer vos paramètres, appuyez sur **F10**.
1. Dans la zone de confirmation, sélectionnez **Oui**.

## <a name="performing-operations-as-the-admin-user-of-the-mtr-device"></a>Exécution d’opérations en tant qu’utilisateur Administration de l’appareil MTR

Certaines procédures de configuration/installation vous obligent à vous connecter à l’appareil en tant qu’administrateur.

Pour vous connecter à l’appareil en tant qu’administrateur (administrateur local) :

1. Assurez-vous de raccrocher tous les appels en cours et de revenir à l’écran d’accueil.
1. Dans l’interface utilisateur de la salle Microsoft Teams, sélectionnez  **Plus**, puis Sélectionnez **Paramètres**, où vous êtes invité à entrer le mot de passe Administrateur local sur l’appareil (le mot de passe par défaut est **_sfb_**).
1. Sélectionnez **Paramètres**, puis sélectionnez  **Paramètres Windows**  pour accéder à Windows en tant qu’administrateur local.

1. Dans la liste des utilisateurs affichés dans l’écran de connexion Windows, sélectionnez  **Administrateur** (ou l’administrateur local respectif de votre appareil).

> [!NOTE]
> Si l’ordinateur est *joint à un domaine*, choisissez **Autre utilisateur**, puis utilisez **.\admin** ou le nom d’utilisateur de l’administrateur local configuré dans l’appareil comme nom d’utilisateur.

Pour revenir à l’application Salles Microsoft Teams après avoir effectué les tâches administratives nécessaires :

1. Dans le ***menu Démarrer*** de Windows, déconnectez-vous du compte Administration.
1. Revenez à Salles Microsoft Teams en sélectionnant l’icône de compte d’utilisateur à l’extrême gauche de l’écran, puis en sélectionnant **Skype**.

> [!NOTE]
> Si l’utilisateur Skype n’est pas répertorié, sélectionnez Autre utilisateur, entrez ***.\skype*** comme nom d’utilisateur, puis connectez-vous.

## <a name="urls-required-for-communication"></a>URL requises pour la communication

 > [!NOTE]
 > Tout le trafic réseau entre l’agent d’appareils MTR et le Salles Microsoft Teams : le portail de service Managed Services est SSL sur le port 443 *.*  Voir [Office 365 URL et plages d’adresses IP - Microsoft 365 Entreprise | Microsoft Docs](/microsoft-365/enterprise/urls-and-ip-address-ranges?view=o365-worldwide&preserve-view=true).

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

1. Dans la barre de navigation gauche du portail Salles Microsoft Teams – Services [http://portal.rooms.microsoft.com](https://portal.rooms.microsoft.com/)**managés, développez Paramètres** et sélectionnez **Général**.
1. Sous *Inscrire une salle*, **sélectionnez Télécharger le programme d’installation**  pour télécharger le logiciel de l’agent de surveillance.
1. **Optionnel:** Configurer les paramètres de proxy pour l’agent ; voir [Ajout de paramètres de proxy (facultatif).](#adding-proxy-settings-optional)
1. Installez le programme d’installation de l’agent (téléchargé à l’étape 2) sur des unités MTR, soit en exécutant MSI localement sur un appareil MTR, soit en publiant en masse des applications MSI sur des appareils de votre environnement (stratégie de groupe, etc.).
1. La salle s’affiche dans le portail dans un délai de 5 à 10 minutes. Si ce n’est pas le cas, contactez managedroomsupport@microsoft.com.

   ![Capture d’écran des paramètres et des clés d’inscription automatique.](../media/software-installation-005new.png)

> [!NOTE]
> Si vous devez installer l’agent sans que l’application Teams sur le MTR puisse se connecter à Teams, vous pouvez utiliser notre clé d’inscription comme processus facultatif. Accédez à « ? »  (Aide) dans le coin supérieur droit du portail, puis sélectionnez « Télécharger la clé (facultatif) ». Lors de l’installation de l’agent, placez la « clé d’inscription automatique » (précédemment téléchargée à partir du portail) dans le répertoire **C:\Rigel** de l’appareil.

## <a name="installation"></a>Installation

Après avoir téléchargé le programme d’installation à partir de Microsoft (à partir du portail ou à l’aide de l’URL AKA.ms fournie ci-dessus), décompressez son contenu pour accéder au fichier **ManagedRoomsInstaller.msi**.

Il existe deux modes d’installation : 1) l’installation de la machine locale individuelle et 2) le mode de déploiement en masse (généralement via Intune de méthode similaire). Nous vous recommandons d’installer individuellement des ordinateurs non joints à un domaine ou des machines pour lesquelles vous n’avez aucun moyen d’exécuter des programmes d’installation MSI à distance.

En raison des nombreuses façons dont les clients peuvent exécuter des applications MSI en mode de déploiement en masse, ce document décrit uniquement l’installation en mode individuel et en bloc sur Intune appareils inscrits.

### <a name="individual-device-installation"></a>Installation d’un appareil individuel

1. Connectez-vous à l’appareil en tant qu’administrateur. Assurez-vous *que les opérations d’exécution de l’utilisateur Administration des étapes de l’appareil* sont suivies.

1. Copiez le **fichierManagedRoomsInstaller.msi** sur l’appareil MTR.

   Lors de l’exécution de la ***ManagedRoomsInstaller.msi*** est un écran contrat de licence.

1. Après avoir lu le contrat, vérifiez ***J’accepte les termes du contrat de licence** _ et appuyez sur _*Installer**.

    Cela commence l’installation du logiciel de surveillance Salles Microsoft Teams – Managed Services. Une invite d’élévation (exécuter en tant qu’administrateur) s’affiche.

1. Sélectionnez **Oui**.

    L’installation se poursuivra. Pendant la procédure d’installation, une fenêtre de console s’ouvre et commence l’étape finale de l’Salles Microsoft Teams – Installation du logiciel de surveillance des services managés.

    > [!NOTE]
    > Ne fermez pas la fenêtre. Une fois l’installation terminée, l’Assistant affiche un bouton « Terminer ».

### <a name="intune-enrolled-device-bulk-deployment"></a>déploiement en bloc d’appareil inscrit Intune

Les composants suivants sont prérequis pour une installation réussie : 

- **Intune inscription** : salles Teams sur les appareils Windows doivent déjà être inscrits dans Intune.
  Pour plus d’informations sur l’inscription de salles Teams sur des appareils Windows dans Intune, consultez [Inscription de Salles Microsoft Teams sur des appareils Windows avec Microsoft Endpoint Manager - Microsoft Tech Community](https://techcommunity.microsoft.com/t5/intune-customer-success/enrolling-microsoft-teams-rooms-on-windows-devices-with/ba-p/3246986)
- Groupe **Azure AD avec tous les salles Teams sur les appareils Windows en tant que membres** : groupe créé dans Azure AD qui inclut tous les salles Teams sur les appareils Windows qui doivent faire partie du service Salles Microsoft Teams Premium. Ce groupe sera utilisé pour cibler le déploiement de l’agent MTRP.
  
> [!NOTE]
> Vous pouvez envisager d’utiliser des groupes dynamiques dans Azure AD à cet effet, plus d’informations [sur l’inscription de Salles Microsoft Teams sur des appareils Windows avec Microsoft Endpoint Manager - Microsoft Tech Community](https://techcommunity.microsoft.com/t5/intune-customer-success/enrolling-microsoft-teams-rooms-on-windows-devices-with/ba-p/3246986)
- Télécharger le **programme d’installation** de **l’agent MTRP** : téléchargez le fichier zip de <https://aka.ms/serviceportalagentmsi> l’agent et extrayez le contenu du fichier zip (ManagedRoomsInstaller.msi) dans un dossier temporaire local.

**Pour l’installer à l’aide de Intune**

1. Connectez-vous au Centre d’administration [Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431).
1. Sélectionnez **Applications** > **que toutes les applications** > **ajoutent**.
1. Dans le volet **Sélectionner un type d’application** , sous **Autres** types d’application, sélectionnez **Application métier**.
1. Cliquez sur **Sélectionner**. Les étapes **d’ajout d’application s’affichent** . 
1. Dans le volet **Ajouter une application** , cliquez sur **Sélectionner le fichier de package d’application**.
   1. Dans le volet **fichier du package d’application** ,  **sélectionnez Parcourir**. Ensuite, sélectionnez le fichier **ManagedRoomsInstaller.msi** téléchargé précédemment (reportez-vous à la section prérequis).
   1. Lorsque vous avez terminé, sélectionnez **OK** dans le volet du **fichier de package** d’application pour ajouter l’application.
1. Dans la page **d’informations sur l’application** , effectuez les modifications suivantes :
   1. Éditeur : entrez **Microsoft Corporation**.
   1. Ignorer la version de l’application : sélectionnez **Oui**.

      > [!NOTE]
      > L’agent MTRP est automatiquement mis à jour ; Par conséquent, vous devez ignorer explicitement la version de l’application (toute version de référence peut être mise à jour automatiquement).

   1. (Facultatif) Catégorie : Sélectionnez **Gestion de l’ordinateur**.
   
1. Cliquez sur **Suivant** pour afficher la page **Affectations** .
   1. Dans la section **Obligatoire** , cliquez **sur + Ajouter un groupe** pour cibler un groupe d’appareils pour l’installation de l’agent.
   1. Dans le volet **Sélectionner un groupe, tapez** le nom du groupe dans la zone de recherche (reportez-vous aux prérequis ci-dessus), cliquez sur le **groupe** souhaité, puis cliquez sur **Sélectionner**.
      Pour plus d’informations, consultez [Ajouter des groupes pour organiser les utilisateurs et les appareils](https://go.microsoft.com/fwlink/?linkid=2202166) et [attribuer des applications à des groupes avec Microsoft Intune](https://go.microsoft.com/fwlink/?linkid=2202270).
1. Cliquez sur **Suivant** pour afficher la page **Vérifier + créer** .
1. Passez en revue les valeurs et les paramètres que vous avez entrés pour l’application. Lorsque vous avez terminé, cliquez sur **Créer** pour ajouter l’application à Intune.

Une fois le processus terminé, vos appareils commencent à installer l’agent MTRP après quelques minutes.

> [!NOTE]
> Après l’installation, l’agent MTRP peut prendre jusqu’à huit heures pour exécuter une mise à jour automatique vers la dernière version et être répertorié dans le portail MTRP.
Pour accélérer l’inscription automatique dans le portail MTRP, envisagez de redémarrer l’appareil MTR après le déploiement de l’agent.

## <a name="completing-enrollment"></a>Fin de l’inscription

Une fois l’installation terminée, attendez 5 à 10 minutes, puis actualisez le portail pour afficher l’appareil dans la liste, signalé comme état *d’intégration* .

Dans *l’état d’intégration* , l’état de la salle est affiché et mis à jour, mais il ne déclenche pas d’alertes ou ne crée pas de tickets d’enquête.

Choisissez la salle et **sélectionnez Inscrire**  pour commencer à recevoir des alertes d’incident, des tickets d’enquête ou pour signaler un incident.

Pour toute question ou problème, ouvrez un incident signalé par le client dans le portail ou contactez managedroomsupport@microsoft.com.

### <a name="unenrolling-and-uninstalling-monitoring-software"></a>Désinscription et désinstallation des logiciels de surveillance

Pour désinscrire l’appareil, supprimez l’agent de surveillance de l’appareil MTR comme suit :

1. Sur l’appareil surveillé, connectez-vous à l’appareil en tant qu’administrateur. Veillez à suivre les *étapes de l’exécution des opérations en tant qu’utilisateur Administration de l’appareil*.
1. Téléchargez le script de réinitialisation à partir de [aka.ms/MTRPDeviceOffBoarding](https://aka.ms/MTRPDeviceOffBoarding).
1. Extrayez le script quelque part sur l’appareil et copiez le chemin d’accès.
1. Ouvrez PowerShell en tant qu’administrateur : dans le champ Windows ***Search** _ (section en bas à gauche de l’écran), entrez « PowerShell », puis cliquez avec le bouton droit sur _*_Windows PowerShell_**.
1. Sélectionnez *« Exécuter en tant qu’administrateur »* et acceptez l’invite UAC.
1. Entrez *Set-ExecutionPolicy –ExecutionPolicy RemoteSigned* , puis appuyez sur **Y** à l’invite suivante.
1. Collez ou tapez le chemin complet du script de désintégrage décompressé dans la fenêtre PowerShell, puis **appuyez sur Entrée**.

   Exemple :

   ```powershell
   C:\Users\admin\Downloads\MTRP\_Device\_Offboarding\MTRP\_Device\_Offboarding.ps1
   ```

   Cette commande réinitialise l’appareil aux mises à jour MTR standard de l’utilisateur et supprime l’agent et les fichiers de surveillance MTRP.

1. Dans le menu de gauche du portail Salles Microsoft Teams – Services managés, sélectionnez **Salles**.
1. Dans la liste des salles fournies, choisissez la salle que vous souhaitez désinscrire et sélectionnez **Désinscrire** pour arrêter d’obtenir des alertes d’incident ou des tickets d’enquête, ou pour signaler un incident pour la salle.

## <a name="troubleshooting-table"></a>Tableau de résolution des problèmes

> [!NOTE]
> Toutes les Salles Microsoft Teams : les erreurs de surveillance des services managés sont consignées dans un fichier journal des événements spécifique nommé **Salles gérées Microsoft**.

***Emplacement du fichier journal du runtime d’application*** =

C:\Windows\ServiceProfiles\LocalService\AppData\Local\ServicePortalAgent\ app-x.x.x\ServicePortalAgent\ServicePortal\_Verbose\_LogFile.log, où **x.x.x** est le numéro de version de l’application.

|Symptôme|Procédure recommandée|
|---|---|
|Vous recevez un message d’erreur indiquant : </p><p> ***ERREUR : Exécutez cette application avec** _ <br> _ *_privilèges élevés_**|Exécutez l’application avec des privilèges élevés et réessayez.|
|||
|Vous recevez un message d’erreur indiquant : </p><p> ***Les données TPM sont introuvables***|Vérifiez que le module TPM (Trusted Platform Module) est activé sur votre appareil dans son BIOS. Cela se trouve généralement dans les paramètres de sécurité du BIOS de l’appareil.|
|||
|Vous recevez un message d’erreur : </p><p> ***ERREUR : Le compte d’utilisateur local nommé « Administration » ou « Skype » est introuvable***|Assurez-vous que les comptes d’utilisateur existent sur l’appareil certifié microsoft Teams Room.|
|||
|Vous recevez des messages d’état d’erreur qui ne sont pas couverts ci-dessus.|Veuillez fournir une copie de votre journal d’installation à votre agent de support Microsoft Teams System.|
