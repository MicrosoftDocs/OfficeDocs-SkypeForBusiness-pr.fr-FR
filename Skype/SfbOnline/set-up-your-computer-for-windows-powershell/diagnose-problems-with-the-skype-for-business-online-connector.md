---
title: Diagnostiquer des problèmes de connexion avec le connecteur Skype Entreprise Online
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 866fadfd-16e2-4134-95db-c6aed7678416
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- PowerShell
description: Résoudre les problèmes de création d’une session PowerShell distante pour vous connecter à Skype Entreprise Online, notamment l’importation-module, l’environnement de ligne de commande simultané, l’ID Live ID et les erreurs d’autorisation.
ms.openlocfilehash: 9157c556eaa2952adf2b67a514eebfb1a9d3abff
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58617090"
---
# <a name="diagnose-connection-problems-with-the-skype-for-business-online-connector"></a>Diagnostiquer des problèmes de connexion avec le connecteur Skype Entreprise Online

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Cette rubrique fournit des informations qui vous aideront à diagnostiquer et résoudre les problèmes qui peuvent se produire lorsque vous essayez de créer une session Microsoft PowerShell distante qui se connecte à Skype Entreprise Online. Consultez les sections suivantes :
  
- [Erreur d’importation-module provoquée par une Windows PowerShell d’exécution](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKPowerShellExecutionPolicy)
    
- [Erreur d’importation-module provoquée par une version incorrecte de Windows PowerShell](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKIncorrectVersion)
    
- [L’authentification moderne échoue lorsque l’authentification WinRM Basic est désactivée](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKWinRMBasicAuth)
    
- [Échec de la connexion à Live ID Server](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKFailedConnect)
    
- [Échec du chargement du module Live ID](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKFailedLoad)
    
- [Échec de la connectez-vous pour l’utilisateur](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKLogonFailed)
    
- [L’utilisateur n’est pas autorisé à gérer ce client](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKUserPermission)
    
- [La connexion au client a été désactivée dans Skype Entreprise Online](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKAbilityConnect)
    
- [Le nombre maximal de shells simultanés pour cet utilisateur dans Skype Entreprise Online a été dépassé.](#the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded)

- [Le nombre maximal de shells simultanés pour ce client dans Skype Entreprise Online a été dépassé.](#the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded)
    

> [!IMPORTANT]
> Par défaut, les sessions PowerShell sont en cours de retard après 60 minutes. Pour vous reconnecter, vous devez fermer la session et lancer une nouvelle session PowerShell. Une nouvelle version de [Skype Entreprise Online, module Windows PowerShell (2046.123 - Publié le 02/10/2019)](https://www.microsoft.com/download/details.aspx?id=39366)a été récemment lancée, qui inclut une nouvelle cmdlet appelée **Enable-CsOnlineSessionForReconnection** qui réduit le problème de délai d’utilisation de 60 minutes.
> La session PowerShell se reconnecte et s’authentifier, ce qui permet de la ré-utiliser sans avoir à lancer une nouvelle instance pour se reconnecter.



## <a name="import-module-error-caused-by-windows-powershell-execution-policy"></a>Import-Module provoquée par une stratégie d’Windows PowerShell exécution
<a name="BKMKPowerShellExecutionPolicy"> </a>

La stratégie d’exécution de PowerShell permet de déterminer les fichiers de configuration qui peuvent être chargés dans la console PowerShell et les scripts qu’un utilisateur peut exécuter à partir de cette console. Au minimum, le module Skype Entreprise Online Connector ne peut pas être importé, sauf si la stratégie d’exécution a été définie sur RemoteSigned. Si ce n’est pas le cas, vous recevez le message d’erreur suivant lorsque vous tentez d’importer le module :
  
- **Erreur**: Import-Module : Fichier C : Les fichiers courants de fichiers du programme <em> \\ Microsoft \\ \\ Lync Server 2013 \\ Modules \\ LyncOnlineConnector \\ LyncOnlineConnectorStartup.psm1 ne peuvent pas être chargés, car l’exécution des scripts est désactivée sur ce système. Pour plus d’informations, voir about_Execution_Policies à https://go.microsoft.com/fwlink/?LinkID=135170 .</em>

- **Résolution** Pour résoudre ce problème, démarrez PowerShell en tant qu’administrateur, puis exécutez la commande suivante :
    ```PowerShell
    Set-ExecutionPolicy RemoteSigned
    ```
    Pour plus d’informations sur la stratégie d’exécution, voir [À propos des stratégies d’exécution.](/powershell/module/microsoft.powershell.core/about/about_execution_policies)
  
## <a name="import-module-error-caused-by-incorrect-version-of-windows-powershell"></a>Import-Module'erreur provoquée par une version incorrecte d’Windows PowerShell
<a name="BKMKIncorrectVersion"> </a>

Le Skype Entreprise module Connecteur en ligne ne peut être exécuté qu’Windows PowerShell 3.0. Si vous essayez d’importer le module sous une version précédente de PowerShell, le processus d’importation échoue et un message d’erreur semblable au message suivant s’offre à vous :
  
  - **Erreur**: Import-Module : La version de PowerShell chargée est *« 2.0 ». Le module « D : Program \\ Files Common Files Microsoft \\ \\ Lync Server 2013 \\ Modules \\ LyncOnlineConnectorLyncOnlineConnector.psd1 » nécessite une version PowerShell « \\ 3.0 » minimale à exécuter. Vérifiez l’installation de PowerShell et essayez à nouveau.*

- **Résolution**: la seule façon de résoudre ce problème consiste à installer Windows PowerShell 3.0, accessible à partir du Centre de téléchargement Microsoft sur [https://www.microsoft.com/download/details.aspx?id=34595](https://www.microsoft.com/download/details.aspx?id=34595) .
  
## <a name="modern-authentication-fails-when-winrm-basic-authentication-has-been-disabled"></a>L’authentification moderne échoue lorsque l’authentification WinRM Basic est désactivée
<a name="BKMKWinRMBasicAuth"> </a>

La dernière version du module Skype Entreprise Online Connector utilise l’authentification moderne, mais le client Windows Remote Management (WinRM) sous-jacent doit être configuré pour autoriser l’authentification de base.  L’authentification moderne utilise des jetons de support, qui sont généralement transmis dans l’en-tête *Authorization: Bearer.* Windows PowerShell, sur lequel est Skype Entreprise PowerShell, ne permet pas de manipuler cet en-tête.  À la place, Skype Entreprise PowerShell utilise *l’autorisation :* en-tête de base pour transmettre le jeton de porteur.

Pour obtenir des instructions sur [l’Windows PowerShell](./download-and-install-windows-powershell-5-1.md) de l’authentification de base, voir Télécharger et installer.

## <a name="failed-to-connect-to-live-id-server"></a>Échec de la connexion à Live ID Server
<a name="BKMKFailedConnect"> </a>

> [!WARNING] 
> L’authentification d’ID Live ID est Skype pour business online Connector. Utilisez le Teams module PowerShell pour gérer le client en ligne. Lors de la gestion d’environnements hybrides, mettez à niveau vers la dernière mise à jour cumulative ou utilisez l’authentification oAuth.

Il existe généralement trois raisons pour lesquelles votre tentative de connexion peut échouer avec le message d’erreur suivant :

  - **Erreur**: Get-CsWebTicket : échec de la connexion aux *serveurs d’id live. Assurez-vous que le proxy est activé ou que l’ordinateur dispose d’une connexion réseau à des serveurs d’ID en direct.*

- **Résolution**: souvent, cette erreur signifie que l’Assistant Microsoft Online Services de se connecteur n’est pas en cours d’exécution. Vous pouvez vérifier l’état de ce service en exécutant la commande suivante à partir de l’invite PowerShell : 
    ```PowerShell
    Get-Service "msoidsvc"
    ```
    Si le service n’est pas en cours d’exécution, démarrez-le à l’aide de la commande ci-après :
    ```PowerShell
    Start-Service "msoidsvc"
    ```

    Si le service est en cours d’exécution, vous pouvez rencontrer des problèmes de connexion réseau entre votre ordinateur et le serveur d’authentification d’ID Microsoft Live ID. Pour le vérifier, ouvrez Internet Explorer et accédez à [ https://login.microsoftonline.com/ .](https://login.microsoftonline.com/.) Essayez de vous connecter à Microsoft 365 ou Office 365 connexion à partir de là. En cas d’échec, vous rencontrez probablement des problèmes de connexion réseau.
  
    Moins souvent, il est possible que l’URI de connexion pour le serveur d’authentification d’ID Microsoft Live ID ait été configurée sur une valeur erronée. Si vous avez déjà déterminé que l’Assistant Sign-In est en cours d’exécution et que vous ne rencontrez pas de problèmes de connectivité réseau, il peut s’agit du problème. Dans ce cas, contactez le Support Microsoft.
  
## <a name="failed-to-load-live-id-module"></a>Échec du chargement du module Live ID
<a name="BKMKFailedLoad"> </a>

Une des conditions préalables à l’utilisation de PowerShell pour gérer Skype Entreprise Online consiste à installer l’Assistant de Microsoft Online Services de base. Si l’Assistant de session n’est pas installé, le message d’erreur suivant s’affiche lorsque vous tentez d’établir une session distante avec Skype Entreprise Online :

- **Erreur**: *Get-CsWebTicket : vous ne pouvez pas charger le module Live ID. Assurez-vous que la version correcte de l’Assistant de connect-vous Live Id est installée.*

- **Résolution**: l’Assistant Microsoft Online Services de l’application est disponible dans le Centre de téléchargement Microsoft [Microsoft Online Services Sign-In l’Assistant](https://www.microsoft.com/download/details.aspx?id=28177) de l’it professionals RTW

## <a name="logon-failed-for-the-user"></a>Échec de la logo de l’utilisateur
<a name="BKMKLogonFailed"> </a>

Lorsque vous tentez de établir une connexion à distance à Skype Entreprise Online, vous devez fournir le nom d’utilisateur et le mot de passe d’un compte d’utilisateur Skype Entreprise Online valide. Si ce n’est pas le cas, l’accès échoue et un message d’erreur semblable au message suivant s’affiche :

- **Erreur**: Get-CsWebTicket : Échec de la logo de l’utilisateur *« kenmyer@litwareinc.com ». Créez un objet PSCredential,* en vous assurez d’avoir utilisé le nom d’utilisateur et le mot de passe corrects.

- **Résolution**: si vous pensez utiliser un compte d’utilisateur valide et que vous avez le mot de passe correct, essayez de vous connecter à nouveau. En cas d’échec, utilisez les mêmes informations d’identification et essayez de vous y [https://login.microsoftonline.com/](https://login.microsoftonline.com/) connexion. Si vous ne parvenez pas à vous y connectez, contactez le Support Microsoft. 

  
## <a name="the-user-does-not-have-permission-to-manage-this-tenant"></a>L’utilisateur n’est pas autorisé à gérer ce client
<a name="BKMKUserPermission"> </a>

Vous ne pouvez pas établir de connexion PowerShell distante àSkype Entreprise Online, sauf si vous êtes membre du groupe Administrateurs clients. Si ce n’est pas le cas, votre tentative de connexion échouera et vous recevrez le message d’erreur suivant :

- Erreur **:** *New-PSSession : [admin.vdomain.com] Le traitement des données à partir du serveur distant admin.vdomain.com a échoué avec le message d’erreur suivant : L’utilisateur « user@foo.com » n’est pas autorisé à gérer ce client. Les autorisations peuvent être octroyées en attribuant à l’utilisateur le rôle de CBAC approprié. Pour plus d’informations, voir [la résolution des problèmes à distance.](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting )*

- **Résolution**: si vous pensez que vous êtes ou êtes sensé être membre du groupe Administrateurs client, vous devez contacter le Support Microsoft.
  
## <a name="ability-to-connect-to-tenant-has-been-disabled-in-skype-for-business-online"></a>La connexion au client a été désactivée dans Skype Entreprise Online
<a name="BKMKAbilityConnect"> </a>

Pour utiliser PowerShell pour gérer Skype Entreprise Online, la propriété EnableRemotePowerShellAccess de votre stratégie PowerShell client doit être définie sur `True` . Si ce n’est pas le cas, votre connexion échouera et vous recevrez le message d’erreur suivant :

- Erreur **:** New-PSSession : [admin.vdomain.com] Le traitement des données du serveur distant admin.vdomain.com a échoué avec le message d’erreur suivant : la connexion à ce client à l’aide d’une session PowerShell distante a été *désactivée. Contactez l’aide de Lync pour vérifier la stratégie PowerShell du client. Pour plus d’informations, voir [la résolution des problèmes à distance.](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting )*

- **Résolution**: si vous voyez ce message d’erreur, vous devez contacter le Support Microsoft et activer l’accès à distance à PowerShell.
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded"></a>Le nombre maximal de shells simultanés pour cet utilisateur dans Skype Entreprise Online a été dépassé.
<a name="BKMKMaxNumberShellsUser"> </a>

Chaque administrateur est autorisé à avoir jusqu’à trois connexions distantes simultanées à Skype Entreprise Online. Si vous avez trois connexions PowerShell distantes en cours d’exécution, toute tentative d’établir une quatrième connexion simultanée échouera, avec le message d’erreur suivant : 

- **Erreur**: *New-PSSession : [admin.vdomain.com] La connexion au serveur distant admin.vdomain.com a échoué avec le message d’erreur suivant : le service WS-Management ne peut pas traiter la demande. Le nombre maximal de shells simultanés pour cet utilisateur a été dépassé. Fermez les shells existants ou élèvez le quota pour cet utilisateur. Pour plus d’informations, voir [la résolution des problèmes à distance.](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting )*

- **Résolution**: la seule façon de résoudre ce problème consiste à fermer une ou plusieurs des connexions précédentes. Lorsque vous en avez fini avec une session Skype Entreprise Online, nous vous recommandons d’utiliser l’cmdlet **Remove-PSSession** pour mettre fin à la session. Cela vous permettra d’éviter ce problème.
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded"></a>Le nombre maximal de shells simultanés pour ce client dans Skype Entreprise Online a été dépassé.
<a name="BKMKMaxNumberShellsTenant"> </a>

Bien que chaque administrateur soit autorisé à avoir jusqu’à trois connexions simultanées à un client Skype Entreprise Online, aucun client n’est autorisé à avoir plus de 20 connexions simultanées. Par exemple, six administrateurs peuvent avoir chacun trois sessions ouvertes. Si un quatrième administrateur tente d’établir plus de deux connexions (pour un total de 21 connexions simultanées), cette tentative échoue et le message d’erreur suivant s’agit :
  
- **Erreur**: *New-PSSession : [admin.vdomain.com] La connexion au serveur distant admin.vdomain.com a échoué avec le message d’erreur suivant : le service WS-Management ne peut pas traiter la demande. Le nombre maximal de shells simultanés pour ce client a été dépassé. Fermez des shells existants ou élèvez le quota pour ce client. Pour plus d’informations, voir [le dépannage à distance.](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting )*

- **Résolution**: la seule façon de résoudre ce problème consiste à fermer une ou plusieurs des connexions précédentes. Lorsque vous en avez fini avec une session Skype Entreprise Online, nous vous recommandons d’utiliser l’cmdlet **Remove-PSSession** pour mettre fin à cette session. Cela vous permettra d’éviter ce problème.  
 
## <a name="related-topics"></a>Rubriques connexes
[Configurer votre ordinateur pour la gestion de Skype Entreprise Online à l’aide d’Windows PowerShell](set-up-your-computer-for-windows-powershell.md)

  
