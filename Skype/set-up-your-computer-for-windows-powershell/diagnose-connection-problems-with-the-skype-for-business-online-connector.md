---
title: "Diagnostiquer les problèmes de connexion avec la Skype pour Business Connector en ligne"
ms.author: tonysmit
author: tonysmit
ms.date: 5/17/2017
ms.audience: Admin
ms.topic: troubleshooting
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.assetid: 866fadfd-16e2-4134-95db-c6aed7678416
description: "Troubleshoot creating a remote PowerShell session to connect to Skype for Business Online, including Import-Module, concurrent shell, Live ID, and permission errors."
---

# Diagnostiquer les problèmes de connexion avec la Skype pour Business Connector en ligne

> [!IMPORTANT]
> Cet article a été traduit automatiquement, voir l'avertissement.  
  
Cette rubrique fournit des informations qui vous aidera à diagnostiquer et résoudre les problèmes qui peuvent survenir lorsque vous essayez de créer une session distante Microsoft PowerShell qui se connecte à Skype Entreprise Online. Consultez les sections suivantes :
  
- [Erreur de Module d'importation provoquée par la stratégie d'exécution Windows PowerShell](866fadfd-16e2-4134-95db-c6aed7678416.md#BKMK_PowerShellExecutionPolicy)
    
- [Erreur de Module d'importation provoquée par une version incorrecte de Windows PowerShell](866fadfd-16e2-4134-95db-c6aed7678416.md#BKMK_IncorrectVersion)
    
- [Impossible de se connecter à Live ID Server](866fadfd-16e2-4134-95db-c6aed7678416.md#BKMK_FailedConnect)
    
- [Échec de chargement de module Live ID](866fadfd-16e2-4134-95db-c6aed7678416.md#BKMK_FailedLoad)
    
- [Échoué de l'utilisateur de la connexion](866fadfd-16e2-4134-95db-c6aed7678416.md#BKMK_LogonFailed)
    
- [L'utilisateur n'est pas autorisé à gérer ce client](866fadfd-16e2-4134-95db-c6aed7678416.md#BKMK_UserPermission)
    
- [Possibilité de se connecter au client a été désactivée dans Skype entreprise Online](866fadfd-16e2-4134-95db-c6aed7678416.md#BKMK_AbilityConnect)
    
- [Le nombre maximal de coquillages simultanées pour cet utilisateur dans Skype entreprise Online a été dépassé](866fadfd-16e2-4134-95db-c6aed7678416.md#BKMK_MaxNumberShellsUser)
    
- [Le nombre maximal de coquillages simultanées pour ce client dans Skype entreprise Online a été dépassé](866fadfd-16e2-4134-95db-c6aed7678416.md#BKMK_MaxNumberShellsTenant)
    
## Erreur de Module d'importation provoquée par la stratégie d'exécution Windows PowerShell
<a name="BKMK_PowerShellExecutionPolicy"> </a>

La stratégie d'exécution PowerShell permet de déterminer les fichiers de configuration peuvent être chargées dans la console PowerShell, et les scripts un utilisateur peut exécuter à partir de cette console. Au minimum, le Module Skype Entreprise Online Connector ne peuvent pas être importés, à moins que la stratégie d'exécution a été définie pour RemoteSigned. Si ce n'est pas le cas, vous recevez le message d'erreur suivant lorsque vous essayez d'importer le module :
  
```
Import-Module : File C:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\Modules\\LyncOnlineConnector\\LyncOnlineConnectorStartup.psm1 cannot be loaded because running scripts is disabled on this system. For more information, see about_Execution_Policies at https://go.microsoft.com/fwlink/?LinkID=135170.
```

Pour résoudre ce problème, démarrez PowerShell en tant qu'administrateur, puis exécutez la commande suivante :
  
```
Set-ExecutionPolicy RemoteSigned
```

Pour plus d'informations sur la stratégie d'exécution, voir [à propos de l'exécution de stratégies](https://go.microsoft.com/fwlink/?LinkID=135170).
  
## Erreur de Module d'importation provoquée par une version incorrecte de Windows PowerShell
<a name="BKMK_IncorrectVersion"> </a>

La Module Skype Entreprise Online Connector peut être exécuté uniquement sous Windows PowerShell 3.0. Si vous essayez d'importer le module sous une version antérieure de PowerShell, le processus d'importation échoue avec un message d'erreur semblable à celui-ci :
  
```
Import-Module : The version of the loaded PowerShell is '2.0'. The module 'D:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\Modules\\LyncOnlineConnector\\LyncOnlineConnector.psd1' requires a minimum PowerShell version of '3.0' to execute. Please verify the installation of the PowerShell and try again.
```

La seule façon de résoudre ce problème consiste à installer Windows PowerShell 3.0, qui est disponible à partir de la Centre de téléchargement Microsoft en [http://www.microsoft.com/en-us/download/details.aspx?id=29939](http://www.microsoft.com/en-us/download/details.aspx?id=29939).
  
## Impossible de se connecter à Live ID Server
<a name="BKMK_FailedConnect"> </a>

Il existe généralement trois raisons pourquoi votre tentative de connexion peut échouer avec le message d'erreur suivant :
  
```
Get-CsWebTicket : Failed to connect live id servers. Make sure proxy is enabled or machine has network connection to live id servers.
```

Souvent cette erreur signifie que le Assistant de connexion de Microsoft Online Services ne fonctionne pas. Vous pouvez vérifier l'état de ce service en exécutant la commande suivante à partir de l'invite PowerShell:
  
```
Get-Service "msoidsvc"
```

Si le service n'est pas en cours d'exécution, démarrez le service en utilisant cette commande :
  
```
Start-Service "msoidsvc"
```

Si le service est en cours d'exécution, vous pourriez rencontrer des problèmes avec la connexion réseau entre votre ordinateur et le serveur Microsoft Live ID d'authentification. Pour ce faire, ouvrez Internet Explorer et accédez à [https://login.microsoftonline.com/.](https://login.microsoftonline.com/.) Essayez de vous connecter à Office 365 à partir de là. En cas d'échec, vous rencontrez probablement des problèmes de connexion réseau.
  
Moins souvent, il est possible que l'URI de connexion pour Microsoft Live ID d'authentification serveur a été configuré pour une valeur incorrecte. Si vous avez déjà déterminé que l'Assistant de connexion s'exécute et que vous rencontrez pas les problèmes de connectivité réseau, il peut s'agir le problème. Dans ce cas, contactez Office 365 prise en charge.
  
## Échec de chargement de module Live ID
<a name="BKMK_FailedLoad"> </a>

L'une des conditions d'utilisation de PowerShell pour gérer Skype Entreprise Online consiste à installer le Assistant de connexion de Microsoft Online Services. Si l'Assistant de connexion n'est pas installé, le message d'erreur suivant s'affiche lorsque vous tentez d'établir une session distante avec Skype Entreprise Online:
  
```
Get-CsWebTicket : Can not load Live Id module. Make sure correct version of Live Id Sign-in assistant is installed.
```

Le Assistant de connexion de Microsoft Online Services est disponible dans Centre de téléchargement Microsoft en [Assistant Microsoft Online Services se connecter pour RTW de professionnels de l'informatique](https://www.microsoft.com/en-us/download/details.aspx?id=28177).
  
## Échoué de l'utilisateur de la connexion
<a name="BKMK_LogonFailed"> </a>

Lorsque vous tentez d'établir une connexion à distance à Skype Entreprise Online, vous devez fournir le nom d'utilisateur et mot de passe d'un compte d'utilisateur valide Skype Entreprise Online. Si vous ne pas, ouverture de session échouera avec un message d'erreur semblable à celui-ci :
  
```
Get-CsWebTicket : Logon failed for the user 'kenmyer@litwareinc.com'. Please create a new PSCredential object, making sure that you have used the correct user name and password.
```

Si vous pensez que vous utilisez un compte d'utilisateur valide et que vous avez le mot de passe correct, réessayez de vous connecter. En cas d'échec, utilisez les mêmes informations d'identification et essayez d'ouvrir une session sur [https://login.microsoftonline.com/](https://login.microsoftonline.com/). Si vous ne pouvez pas vous connecter, contactez Office 365 prise en charge.
  
## L'utilisateur n'est pas autorisé à gérer ce client
<a name="BKMK_UserPermission"> </a>

Vous ne pouvez pas établir une connexion à distance PowerShell àSkype Entreprise Online, sauf si vous êtes membre du groupe Administrateurs client. Si vous n'êtes pas le cas, votre tentative de connexion échouera, et vous recevez le message d'erreur suivant :
  
```
New-PSSession : [admin.vdomain.com] Processing data from remote server admin.vdomain.com failed with the following error message: The user 'user@foo.com' does not have permission to manage this tenant. Permissions can be granted by assigning the user to the appropriate RBAC role. For more information, see the about_Remote_Troubleshooting Help topic.
```

Si vous pensez que vous, ou supposé être membre du groupe Administrateurs client, vous devez contacter Office 365 prise en charge.
  
## Possibilité de se connecter au client a été désactivée dans Skype entreprise Online
<a name="BKMK_AbilityConnect"> </a>

Pour utiliser PowerShell pour gérer les Skype Entreprise Online, la propriété EnableRemotePowerShellAccess de votre stratégie de PowerShell client doit être définie à  `True`. Si elle n'est pas le cas, votre connexion échouera, et vous recevez le message d'erreur suivant :
  
```
New-PSSession : [admin.vdomain.com] Processing data from remote server admin.vdomain.com failed with the following error message: The ability to connect to this tenant by using a remote PowerShell session has been disabled. Please contact Lync Help to check Tenant Powershell Policy of this tenant. For more information, see the about_Remote_Troubleshooting Help topic.
```

Si vous voyez ce message d'erreur, vous devez contacter Office 365 prise en charge et d'obtenir l'accès à distance PowerShell.
  
## Le nombre maximal de coquillages simultanées pour cet utilisateur dans Skype entreprise Online a été dépassé
<a name="BKMK_MaxNumberShellsUser"> </a>

Chaque administrateur est autorisé à un maximum de trois connexions à distance simultanées à Skype Entreprise Online. Si vous avez des connexions à distance trois PowerShell vers le haut et en cours d'exécution, toute tentative d'effectuer une quatrième sonnerie connexion échouera, avec le message d'erreur suivant :
  
```
New-PSSession : [admin.vdomain.com] Connecting to remote server admin.vdomain.com failed with the following error message : The WS-Management service cannot process the request. The maximum number of concurrent shells for this user has been exceeded. Close existing shells or raise the quota for this user. For more information, see the about_Remote_Troubleshooting Help topic.
```

La seule façon de résoudre ce problème consiste à fermer une ou plusieurs des connexions précédentes. Lorsque vous avez terminé avec une session Skype Entreprise Online, nous vous recommandons d'utiliser l'applet de commande **Remove-PSSession** pour mettre fin à la session. Cela vous aidera à éviter ce problème.
  
## Le nombre maximal de coquillages simultanées pour ce client dans Skype entreprise Online a été dépassé
<a name="BKMK_MaxNumberShellsTenant"> </a>

Bien que chaque administrateur peut avoir jusqu'à trois connexions simultanées sur un client Skype Entreprise Online, aucun client unique n'est autorisé à avoir plus de neuf connexions simultanées. Par exemple, trois administrateurs peuvent avoir chacun trois sessions ouvertes. Si un administrateur quatrième essaie d'établir une connexion (soit un total de 10 connexions simultanées), cette tentative échouera, avec le message d'erreur suivant :
  
```
New-PSSession : [admin.vdomain.com] Connecting to remote server admin.vdomain.com failed with the following error message : The WS-Management service cannot process the request. The maximum number of concurrent shells for this tenant has been exceeded. Close existing shells or raise the quota for this tenant. For more information, see the about_Remote_Troubleshooting Help topic.
```

La seule façon de résoudre ce problème consiste à fermer une ou plusieurs des connexions précédentes. Lorsque vous avez terminé avec une session Skype Entreprise Online, nous vous recommandons d'utiliser l'applet de commande **Remove-PSSession** pour mettre fin à cette session. Cela vous aidera à éviter ce problème.
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Avertissement traduction automatique**: cet article a été traduit par un ordinateur, sans intervention humaine. Microsoft propose cette traduction automatique pour offrir aux personnes ne maîtrisant pas l'anglais l'accès au contenu relatif aux produits, services et technologies Microsoft. Comme cet article a été traduit automatiquement, il risque de contenir des erreurs de grammaire, de syntaxe ou de terminologie.
  

