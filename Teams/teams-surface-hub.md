---
title: Déployer les équipes Microsoft Surface concentrateur
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 07/02/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: jatpatel
description: Configurer les paramètres d’administration pour Microsoft Teams concentrateur de la surface d’exposition.
localization_priority: Normal
ms.custom:
- Devices
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 948f9f9ed32f4e5846248dfbcd2b96577a0f34ee
ms.sourcegitcommit: 2b15226723c299fe94f1a012aa21222173fe3af8
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 07/03/2018
ms.locfileid: "20192179"
---
<a name="deploy-microsoft-teams-for-surface-hub"></a>Déployer les équipes Microsoft Surface concentrateur
======================================

Avant de déployer Microsoft Teams Microsoft Surface concentrateur, assurez-vous que le matériel, système d’exploitation et autres conditions sont réunies. Pour plus d’informations, consultez le [guide d’administration de Microsoft Surface Hub](https://docs.microsoft.com/en-us/surface-hub/).

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

7\. Ensuite, vous devez activer le compte de l’appareil avec des équipes pour le Hub de la surface d’exposition. Assurez-vous que votre environnement répond aux exigences définies dans le [guide d’administration de Microsoft Surface Hub](https://docs.microsoft.com/en-us/surface-hub/).

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

Ces instructions sont les solutions de contournement pour l’installation des équipes concentrateur de Surface à partir de Microsoft Store. 
 
1. Démarrez le magasin de Windows :<br>
   a. Cliquez sur **Démarrer** > **toutes les applications** > **paramètres**.<br> b. Cliquez sur **compte de Surface Hub DISPOSITIF, la gestion**.<br>
   c. Sur la gauche, cliquez sur l’onglet **applications et fonctionnalités** .<br> d. Sur la droite, appuyez sur le bouton **Ouvrir un magasin** . 
2. Dans le Store Microsoft, recherchez les *Équipes Microsoft*. Les **Équipes Microsoft Surface concentrateur (Preview)** s’affiche. Appuyez sur le bouton **obtenir l’application** à installer.  
3. Une fois l’installation terminée, redémarrez le Hub de la surface d’exposition. 
4. Après le redémarrage de la surface d’exposition Hub, vous devez être en mesure de démarrer l’application d’équipes dans le menu **Démarrer** et joindre une réunion à partir du calendrier. 

## <a name="make-teams-the-default-vtc-application"></a>Rendre les équipes de l’application de VTC par défaut

Équipes peuvent être définies à être application VTC par défaut au lieu de Skype pour les entreprises. Une stratégie de gestion de périphérique Mobile (MDM) doit être appliqué à l’appareil Hub de la surface d’exposition. 
 
Il existe deux options pour configurer des stratégies de Mobile Device Manager : 

- Si vous disposez d’une stratégie configurée, ajoutez-le via l’application de gestion des périphériques. 
- Si vous ne disposez pas d’une stratégie à distance configurée, nous disposons d’un fichier de package mis en service que vous pouvez charger sur une clé USB.

### <a name="device-management-configuration"></a>Configuration de gestion des périphériques

Voici un exemple d’ajout d’une stratégie Mobile Device Manager configurée à partir d’une autorité centralisée de Mobile Device Manager. Si vous êtes sur le réseau d’entreprise, vous pouvez utiliser les instructions suivantes textuel, y compris le compte d’utilisateur. 
 
1. Dans la section **Gestion des périphériques** , cliquez sur **+**.<br>
   La boîte de dialogue **se connecter à travailler ou de l’école** s’ouvre. 
2. Entrez l’adresse de messagerie de stratégie et le mot de passe lorsque vous y êtes invité.<br>
   **Remarque :**  Il existe un bogue dans le système d’exploitation qui n’actualise automatiquement l’interface utilisateur une fois que vous avez entré votre compte de la gestion des périphériques. Vous devez fermer et rouvrir paramètres afin de voir le compte répertorié. 
3. Il vous prendre quelques minutes pour les paramètres de stratégie Mobile Device Manager à synchroniser. Si vous souhaitez forcer une synchronisation, cliquez sur le bouton **compte Mobile Device Manager** , puis appuyez sur le bouton **Info** . La fenêtre Info où vous pouvez puis cliquez sur **synchronisation**s’affiche. 
4. Pour vérifier que vous avez ce dont vous avez besoin, vous pouvez vérifier le Registre. Vous devez voir deux clés sous **HKLM\Software\Microsoft\Windows\CurrentVersion\PPI\VtcCallSettings**. <br><br>
   La valeur DWORD **VtcAppMeetingHandlingMode** indique que les équipes est l’application par défaut. Les valeurs suivantes sont reconnues. <br><br>
    |Numéro | Valeur   |
    |-------|---------|
    |0      | SkypePreferred            |
    |1      | VtcPreferred (équipes)      |
    |2      | VtcExclusive (équipes uniquement) |

    Le **VtcCallAppPackageId** est le nom du package équipes installé. Si cela ne s’affiche pas, vérifiez que vous avez installé le package équipes et resynchronisation. 
 
### <a name="configure-mdm-via-usb-key"></a>Configurer Mobile Device Manager via une clé USB 
 
Les packages se trouvent sur cette [page de téléchargement](https://1drv.ms/f/s!ArcnbnREun0Vnp9Wps9MlWB-UJZw3g). Choisissez celui qui convient pour le programme que vous prévoyez d’installer et de le copier sur une clé USB. Le fichier .ppkg correct à utiliser dépend de package équipes qui a été installé à partir du magasin et la stratégie que vous souhaitez appliquer (Skype exclusif, Skype préféré, par défaut, les équipes exclusif équipes). 
 
1. Attacher la clé USB à l’appareil Hub de la surface d’exposition. 
2. Ouvrez l’application de **paramètres** sur un appareil Hub de la surface d’exposition. 
3. Ouvrez **gestion de compte Hub Surface périphérique**.
4. Ouvrez **Gestion des périphériques**. 
5. Cliquez sur **Ajouter ou supprimer un package de mise en service**. 
6. Cliquez sur **Ajouter un Package**.
7. Sélectionnez l’option **Support amovible** dans le menu déroulant. 
8. Ajouter **Allowbuildspreview.ppkg**, puis sélectionnez le package Hub Surface que vous souhaitez ajouter. 
9. Redémarrez le dispositif Hub de la surface d’exposition. 

> [!NOTE]
> Si votre appareil ou périphériques de votre organisation n’appartiennent pas actuellement du programme interne Windows et que vous participez à pays couverts par général règlement de Protection des données (PIBR) (ou si vous avez modifié manuellement vos paramètres de télémétrie sur de base), vous devez renouveler vérifier que vous avez autorisé la télémétrie complète avant de participer à la programme initiés. PIBR modifié le comportement par défaut des périphériques Hub de la surface d’exposition dans l’Union européenne pour définir la télémétrie de base.