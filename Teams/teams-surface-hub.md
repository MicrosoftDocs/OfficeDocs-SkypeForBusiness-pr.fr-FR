---
title: Déployer les équipes Microsoft Surface concentrateur
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 08/29/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: jatpatel
description: Configurer les paramètres d’administration pour Microsoft Teams concentrateur de la surface d’exposition.
localization_priority: Normal
search.appverid: MET150
ms.custom:
- Devices
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 251cc2d12dfdab2e9bc4c9bcc928e80a9c43e2c2
ms.sourcegitcommit: 6732f56535d60a46e6998cde64103e8530dd6452
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 09/11/2018
ms.locfileid: "23937999"
---
<a name="deploy-microsoft-teams-for-surface-hub"></a>Déployer les équipes Microsoft Surface concentrateur
======================================

Avant de déployer Microsoft Teams Microsoft Surface concentrateur, assurez-vous que le matériel, système d’exploitation et autres conditions sont réunies. Pour plus d’informations, consultez le [guide d’administration de Microsoft Surface Hub](https://docs.microsoft.com/surface-hub/).

## <a name="set-up-user-accounts"></a>Configurer les comptes d’utilisateurs
 
Pour configurer des comptes d’utilisateur qui peuvent être utilisés avec les équipes de Surface concentrateur, créez le compte de périphérique comme vous le feriez pour la prise en charge avec Skype pour les entreprises. Le compte de l’appareil doit avoir l’authentification multifacteur désactivée (pour autoriser l’ouverture de session automatique) pour les services dépendants suivants d’équipes dans Office 365 :  
- Exchange 
- SharePoint 
- Applications Office 

## <a name="add-a-device-account"></a>Ajout d’un compte d’appareil 

1\. Démarrer une session Windows PowerShell à distance sur un PC et se connecter à Exchange. Assurez-vous que vous disposez des autorisations correctes définies pour s’exécuter les applets de commande associée. Voici quelques exemples d’applets de commande pouvant être utilisés et modifiés dans votre environnement.

```
Set-ExecutionPolicy Unrestricted
$org='contoso.com'
$cred=Get-Credential $admin@$org
$sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ 
-Credential $cred -Authentication Basic -AllowRedirection
Import-PSSession $sess
```

2\. Une fois la session établie, créez une boîte aux lettres et activez-la comme compte de boîte aux lettres pour une salle (RoomMailboxAccount), ou modifiez les paramètres d’une boîte aux lettres de salle existante. Ainsi, le compte pour l’authentification auprès des équipes.

Si vous modifiez une boîte aux lettre de ressource :

```
Set-Mailbox -Identity 'TEAMS01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
```

Si vous créez une boîte aux lettres de ressource :

```
New-Mailbox -MicrosoftOnlineServicesID TEAMS01@contoso.com -Alias TEAMS01 
-Name "Teams-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword
 (ConvertTo-SecureString -String <password> -AsPlainText -Force)
```

3\. Plusieurs propriétés Exchange doivent être définies sur le compte d’appareil pour optimiser l’expérience de réunion. Vous pouvez consulter les propriétés qui doivent être définies dans la section Propriétés Exchange.

```
Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false
 -DeleteSubject $false -RemovePrivateProperty $false
Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
```

4\. Vous devrez vous connecter à Azure Active Directory pour appliquer certains paramètres de compte. Pour vous connecter à Azure AD, exécutez l’applet de commande suivante :

```
Connect-MsolService -Credential $cred
```

5\. 	Pour empêcher l’expiration du mot de passe, exécutez l’applet de commande Set-MsolUser cmdlet avec l’option Le mot de passe n’expire jamais, comme suit :   

```
Set-MsolUser -UserPrincipalName $acctUpn -PasswordNeverExpires $true
```

Vous pouvez également définir un numéro de téléphone pour la salle comme suit :

```
Set-MsolUser -UniversalPrincipalName <upn> -PhoneNumber <phone number>
```

6\. Le compte de l’appareil doit avoir une licence Office 365 ou Exchange et Skype pour les entreprises ne fonctionnent pas. Si vous disposez de la licence, vous devez affecter un emplacement d’utilisation à votre compte d’appareil ; cela permet de déterminer les SKU de licence disponibles pour votre compte. Vous pouvez utiliser Get-MsolAccountSku pour récupérer une liste de références disponibles pour votre client Office 365 comme suit :
 
```
Get-MsolAccountSku
```

Puis, vous pouvez ajouter une licence à l’aide de l’applet de commande Set-MsolUserLicense. Dans ce cas, $strLicense est le code de SKU qui s’affiche (par exemple, contoso:STANDARDPACK).

```
Set-MsolUser -UserPrincipalName $acctUpn -UsageLocation "US"
Get-MsolAccountSku
Set-MsolUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
```

7\. Ensuite, vous devez activer le compte de l’appareil avec des équipes pour le Hub de la surface d’exposition. Assurez-vous que votre environnement répond aux exigences définies dans le [guide d’administration de Microsoft Surface Hub](https://docs.microsoft.com/surface-hub/).

Démarrer une session Windows PowerShell à distance comme suit (veillez à installer Skype pour les composants Business Online PowerShell) :

```
Import-Module LyncOnlineConnector
$cssess=New-CsOnlineSession -Credential $cred  
Import-PSSession $cssess -AllowClobber
```

Ensuite, activez vos équipes compte Hub Surface en exécutant l’applet de commande suivante :

```
Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
```

Obtenir les informations de RegistrarPool à partir du nouveau compte d’utilisateur en cours d’installation, comme indiqué dans cet exemple :

```
Get-CsOnlineUser -Identity $rm | Select -Expand RegistrarPool
```

> [!NOTE]
> Nouveaux comptes d’utilisateur ne peuvent pas être créés sur le même pool de serveurs d’inscriptions en tant que comptes d’utilisateurs existants dans le client. La commande ci-dessus empêchera les erreurs de configuration de compte en raison de cette situation. 

Une fois que vous avez terminé les étapes précédentes pour activer vos équipes compte Hub Surface, vous devez attribuer une licence à l’appareil de v2 Hub de la surface d’exposition. À l’aide du portail d’administration d’Office 365, attribuer une licence Hub de la surface d’exposition les équipes au périphérique.

### <a name="assign-a-license-to-the-account"></a>Attribuer une licence pour le compte

1. Ouvrez une session en tant qu’un administrateur client, ouvrez le centre d’administration Office 365 et cliquez sur l’application d’administration.
2. Cliquez sur **utilisateurs et groupes**, puis cliquez sur **Ajouter des utilisateurs, de réinitialiser les mots de passe et bien plus encore**.
3. Sélectionnez les équipes pour le compte de la Surface Hub, puis cliquez ou appuyez sur l’icône crayon, ce qui signifie que modifier.
4. Cliquez sur l’option de **licences** .
5. Dans la section **attribution de licences** , vous devez sélectionner le plan, en fonction de vos licences.
6. Cliquez sur **Enregistrer** pour terminer la tâche.

## <a name="install-teams-for-surface-hub-from-the-microsoft-store"></a>Installer des équipes pour exposer Hub à partir du magasin de Microsoft 

Ces instructions sont pour l’installation des équipes concentrateur de Surface à partir de Microsoft Store. 
 
1. Démarrer la banque Microsoft :<br>
   a. Cliquez sur **Démarrer** > **toutes les applications** > **paramètres**.<br> b. Cliquez sur **compte de Surface Hub DISPOSITIF, la gestion**.<br>
   c. Sur la gauche, cliquez sur l’onglet **applications et fonctionnalités** .<br> d. Sur la droite, appuyez sur le bouton **Ouvrir un magasin** . 
2. Dans le Store Microsoft, recherchez les *Équipes Microsoft*. Les **Équipes Microsoft Surface concentrateur** s’affichera. Appuyez sur le bouton **obtenir l’application** à installer.  
3. Une fois l’installation terminée, redémarrez le Hub de la surface d’exposition. 

> [!NOTE]
> Ne cliquez pas sur la **barre de lancement** de la page de liste des magasins.

## <a name="make-teams-the-default-calling-and-meetings-application"></a>Rendre les équipes l’appel par défaut et l’application de réunions
 
Il existe deux options pour la configuration de la stratégie d’application appelant et réunions par défaut : 

- **Option 1**: configurer via une clé USB. 
- **Option 2**: configurer via Mobile Device Manager tels que Intune.
 
### <a name="option-1-configure-via-usb-key"></a>Option 1 : Configurer via une clé USB 
 
Les packages se trouvent sur cette [page de téléchargement](https://1drv.ms/f/s!ArcnbnREun0Vnp9Wps9MlWB-UJZw3g). Choisissez celui qui convient pour le programme que vous prévoyez d’installer et de le copier sur une clé USB. Le fichier .ppkg correct à utiliser dépend de la stratégie d’application par défaut que voulez-vous appliquer comme suit : 

|Numéro  |Description  |
|---------|---------|
|0     | Application préférée Skype sur l’écran de démarrage, équipes de réunions disponibles        |
|1     | Application préférée équipes sur l’écran de démarrage, Skype réunions disponibles        |
|2     | Application exclusive équipes sur l’écran d’accueil (Skype app n’est pas disponible)        |
 
1. Attacher la clé USB à l’appareil Hub de la surface d’exposition. 
2. Ouvrez l’application de **paramètres** sur un appareil Hub de la surface d’exposition. 
3. Ouvrez **gestion de compte Hub Surface périphérique**.
4. Ouvrez **Gestion des périphériques**. 
5. Cliquez sur **Ajouter ou supprimer un package de mise en service**. 
6. Cliquez sur **Ajouter un Package**.
7. Sélectionnez l’option **Support amovible** dans le menu déroulant. 
8. Ajoutez le package **TeamsRTMMode*.ppkg** approprié qui a été précédemment copié à la clé USB. 
9. Redémarrez le dispositif Hub de la surface d’exposition. 
10. Après le redémarrage de l’appareil, vous devez être en mesure de démarrer l’application des équipes à partir de l’écran d’accueil et participer à une réunion à partir du calendrier. 

### <a name="option-2-configure-via-mdm-such-as-intune"></a>Option 2 : Configurer via Mobile Device Manager tels que Intune 

Utilisez ce qui suit pour configurer la stratégie par défaut les réunions et les appels d’application via Intune.

|Paramètre   |Valeur    |Description    |
|----------|---------|---------|
| Path      | ./Vendor/MSFT/SurfaceHub/Properties/SurfaceHubMeetingMode        |
|Type de données | nombre entier (0-2)   |0 - application préféré Skype sur l’écran de démarrage, équipes de réunions disponibles<br>1 - teams préféré application sur l’écran de démarrage, Skype réunions disponibles<br>2 - application exclusive d’équipes sur l’écran d’accueil (Skype app n’est pas disponible) |
|Opérations| Obtenir, définir        |

|Paramètre   |Valeur    |
|----------|---------|
| Path      | ./Vendor/MSFT/SurfaceHub/Properties/VtcAppPackageId        |
|Type de données | chaîne - ensemble chaîne aux équipes des ID de package d’application en tant que **Microsoft.MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe ! Les équipes** |
|Opérations| Obtenir, définir        |

Redémarrez le dispositif Hub de la surface d’exposition. Après le redémarrage de l’appareil, vous devez être en mesure de démarrer l’application des équipes à partir de l’écran d’accueil et participer à une réunion à partir du calendrier.

> [!NOTE]
> Si votre appareil ou périphériques de votre organisation n’appartiennent pas actuellement du programme interne Windows et que vous participez à pays couverts par général règlement de Protection des données (PIBR) (ou si vous avez modifié manuellement vos paramètres de télémétrie sur de base), vous devez renouveler vérifier que vous avez autorisé la télémétrie complète avant de participer à la programme initiés. PIBR modifié le comportement par défaut des périphériques Hub de la surface d’exposition dans l’Union européenne pour définir la télémétrie de base.
