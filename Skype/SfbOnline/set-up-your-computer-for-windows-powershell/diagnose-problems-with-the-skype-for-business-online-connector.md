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
localization_priority: Normal
f1keywords: None
ms.custom:
- PowerShell
description: Résoudre les problèmes de création d’une session PowerShell distante pour se connecter à Skype entreprise Online, y compris les erreurs d’importation-module, d’interpréteur de commande et d’autorisation.
ms.openlocfilehash: 863593c3068136f4b2332a55d8e0c293d2acc1d8
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991309"
---
# <a name="diagnose-connection-problems-with-the-skype-for-business-online-connector"></a>Diagnostiquer des problèmes de connexion avec le connecteur Skype Entreprise Online

Cette rubrique fournit des informations pour vous aider à diagnostiquer et résoudre les problèmes qui peuvent se produire lorsque vous essayez de créer une session Microsoft PowerShell distante qui se connecte à Skype entreprise online. Voir les sections suivantes :
  
- [Erreur d’importation-module provoquée par la stratégie d’exécution Windows PowerShell](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKPowerShellExecutionPolicy)
    
- [Erreur d’importation-module provoquée par une version incorrecte de Windows PowerShell](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKIncorrectVersion)
    
- [Échec de l’authentification moderne lors de la désactivation de l’authentification de base WinRM](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKWinRMBasicAuth)
    
- [Échec de la connexion à Live ID Server](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKFailedConnect)
    
- [Échec du chargement du module d’ID Live ID](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKFailedLoad)
    
- [Échec de l’ouverture de session pour l’utilisateur](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKLogonFailed)
    
- [L’utilisateur n’est pas autorisé à gérer ce client](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKUserPermission)
    
- [La possibilité de se connecter au client a été désactivée dans Skype entreprise Online](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKAbilityConnect)
    
- [Le nombre maximal d’interpréteurs simultanés pour cet utilisateur dans Skype entreprise Online a été dépassé.](#the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded)

- [Le nombre maximal d’interpréteurs simultanés pour ce client dans Skype entreprise Online a été dépassé.](#the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded)
    

> [!IMPORTANT]
> Par défaut, les sessions PowerShell expirent après 60 minutes. Pour vous reconnecter, vous devez fermer la session et lancer une nouvelle session PowerShell. Une nouvelle version de [Skype entreprise Online, module Windows PowerShell (2046,123-publié 10/2/2019)](https://www.microsoft.com/download/details.aspx?id=39366), a été lancée récemment et inclut une nouvelle applet de contrôle appelée **Enable-CsOnlineSessionForReconnection** qui atténue le délai de 60 minutes.
> La session PowerShell se reconnecte et s’authentifie, ce qui permet de la réutiliser sans avoir à lancer une nouvelle instance pour s’y reconnecter.



## <a name="import-module-error-caused-by-windows-powershell-execution-policy"></a>Erreur d’importation-module provoquée par la stratégie d’exécution Windows PowerShell
<a name="BKMKPowerShellExecutionPolicy"> </a>

La stratégie d’exécution PowerShell vous permet de déterminer les fichiers de configuration qui peuvent être chargés dans la console PowerShell et les scripts qu’un utilisateur peut exécuter à partir de cette console. Le module Skype entreprise Online Connector ne peut pas être importé au minimum tant que la stratégie d’exécution n’a pas été définie sur RemoteSigned. Si ce n’est pas le cas, vous recevrez le message d’erreur suivant lorsque vous essayez d’importer le module :
  
- **Erreur**: <em>import-module : fichier C :\\Program Files\\fichiers\\communs Microsoft Lync Server 2013\\modules\\LyncOnlineConnector\\LyncOnlineConnectorStartup. psm1 ne peut pas être chargé car l’exécution de scripts est désactivée sur ce système. Pour plus d’informations, consultez about_Execution_Policies https://go.microsoft.com/fwlink/?LinkID=135170à l’adresse.</em>

- **Résolution** Pour résoudre ce problème, démarrez PowerShell en tant qu’administrateur, puis exécutez la commande suivante :
    ```PowerShell
    Set-ExecutionPolicy RemoteSigned
    ```
    Pour plus d’informations sur la stratégie d’exécution, voir [à propos des stratégies d’exécution](https://go.microsoft.com/fwlink/?LinkID=135170).
  
## <a name="import-module-error-caused-by-incorrect-version-of-windows-powershell"></a>Erreur d’importation-module provoquée par une version incorrecte de Windows PowerShell
<a name="BKMKIncorrectVersion"> </a>

Le module Skype entreprise Online Connector ne peut être exécuté que sous Windows PowerShell 3,0. Si vous essayez d’importer le module sous une version antérieure de PowerShell, le processus d’importation échoue avec un message d’erreur semblable à ce qui suit :
  
  - **Erreur**: *import-module : la version de PowerShell chargée est « 2,0 ». Le module-programme\\: fichiers\\fichiers communs\\Microsoft Lync Server 2013\\modules\\LyncOnlineConnector\\LyncOnlineConnector. psd1 'nécessite une version PowerShell minimum de' 3,0 'pour s’exécuter. Veuillez vérifier l’installation de PowerShell, puis réessayez.*

- **Résolution**: la seule façon de résoudre ce problème consiste à installer Windows PowerShell 3,0, disponible dans le centre de téléchargement Microsoft à l' [https://www.microsoft.com/en-us/download/details.aspx?id=34595](https://www.microsoft.com/en-us/download/details.aspx?id=34595)adresse.
  
## <a name="modern-authentication-fails-when-winrm-basic-authentication-has-been-disabled"></a>Échec de l’authentification moderne lors de la désactivation de l’authentification de base WinRM
<a name="BKMKWinRMBasicAuth"> </a>

La dernière version du module Skype entreprise Online Connector utilise l’authentification moderne, mais le client de gestion à distance Windows sous-jacent (WinRM) doit être configuré pour autoriser l’authentification de base.  L’authentification moderne utilise les jetons du porteur qui sont généralement transmis dans l’en-tête *Authorization : porteur* . Windows PowerShell, sur lequel est intégré Skype entreprise PowerShell, ne permet pas de manipuler cet en-tête.  Au lieu de cela, Skype entreprise PowerShell utilise l’en-tête *autorisation : Basic* pour transmettre le jeton du porteur.

Pour obtenir des instructions sur l’activation de l’authentification WinRM de base, voir [Télécharger et installer Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-windows-powershell-5-1) .

## <a name="failed-to-connect-to-live-id-server"></a>Échec de la connexion à Live ID Server
<a name="BKMKFailedConnect"> </a>

Il existe généralement trois raisons pour lesquelles votre tentative de connexion peut échouer avec le message d’erreur suivant :

  - **Erreur**: *Get-CsWebTicket : échec de connexion aux serveurs d’ID Live. Assurez-vous que l’option proxy est activée ou que l’ordinateur dispose d’une connexion réseau à des serveurs d’ID Live.*

- **Solution**: il est souvent possible que l’Assistant de connexion de Microsoft Online Services ne s’exécute pas. Vous pouvez vérifier l’état de ce service en exécutant la commande suivante à partir de l’invite PowerShell : 
    ```PowerShell
    Get-Service "msoidsvc"
    ```
    Si le service n’est pas en cours d’exécution, démarrez le service à l’aide de la commande suivante :
    ```PowerShell
    Start-Service "msoidsvc"
    ```

    Si le service est en cours d’exécution, il est possible que vous rencontriez des problèmes avec la connexion réseau entre votre ordinateur et le serveur d’authentification Microsoft Live ID. Pour cela, ouvrez Internet Explorer et accédez à [ https://login.microsoftonline.com/.](https://login.microsoftonline.com/.) Essayez de vous connecter à Office 365 à partir de cet emplacement. Si le problème persiste, cela signifie probablement que vous rencontrez des problèmes de connexion réseau.
  
    Moins souvent, il est possible que l’URI de connexion du serveur d’authentification Microsoft Live ID ait été configuré sur une valeur incorrecte. Si vous avez déjà déterminé que l’Assistant de connexion s’exécute et que vous n’êtes pas confronté à des problèmes de connectivité réseau, il peut s’agir de la cause du problème. Dans ce cas, contactez le support technique d’Office 365.
  
## <a name="failed-to-load-live-id-module"></a>Échec du chargement du module d’ID Live ID
<a name="BKMKFailedLoad"> </a>

L’une des conditions préalables à l’utilisation de PowerShell pour gérer Skype entreprise Online consiste à installer l’Assistant de connexion Microsoft Online Services. Si l’Assistant de connexion n’est pas installé, vous recevez le message d’erreur suivant lorsque vous essayez d’établir une session à distance avec Skype entreprise Online :

- **Erreur**: *Get-CsWebTicket : il est impossible de charger le module d’ID actif. Assurez-vous que la version correcte de l’Assistant de connexion Live ID est installée.*

- **Résolution**: l’Assistant de connexion de Microsoft Online Services est disponible dans le centre de téléchargement Microsoft de l' [Assistant de connexion de Microsoft Online Services pour les informaticiens RTW](https://www.microsoft.com/en-us/download/details.aspx?id=28177)

## <a name="logon-failed-for-the-user"></a>Échec de l’ouverture de session pour l’utilisateur
<a name="BKMKLogonFailed"> </a>

Lorsque vous tentez d’établir une connexion à distance à Skype entreprise Online, vous devez fournir le nom d’utilisateur et le mot de passe d’un compte d’utilisateur Skype entreprise Online valide. Si ce n’est pas le cas, l’ouverture de session échoue avec un message d’erreur semblable à ce qui suit :

- **Erreur**: *Get-CsWebTicket : échec de l’ouverture de session de l’utilisateur’kenmyer@litwareinc.com'. Créez un nouvel objet PSCredential en veillant à utiliser le nom d’utilisateur et le mot de passe appropriés.*

- **Résolution**: Si vous pensez que vous utilisez un compte d’utilisateur valide et que vous avez le mot de passe correct, essayez de vous reconnecter. Si ce n’est pas le cas, utilisez les mêmes informations d’identification et [https://login.microsoftonline.com/](https://login.microsoftonline.com/)essayez de vous connecter à. Si vous ne parvenez pas à vous connecter à cet emplacement, contactez le support technique d’Office 365. 

  
## <a name="the-user-does-not-have-permission-to-manage-this-tenant"></a>L’utilisateur n’est pas autorisé à gérer ce client
<a name="BKMKUserPermission"> </a>

Vous ne pouvez pas créer une connexion PowerShell distante toSkype entreprise Online sauf si vous êtes membre du groupe administrateurs de clients. Si ce n’est pas le cas, votre tentative de connexion échoue et vous recevez le message d’erreur suivant :

- **Erreur**: *nouveauté-PSSession : [admin.vDomain.com] le traitement des données à partir du serveur distant admin.vDomain.com a échoué avec le message d’erreur suivant : l’utilisateur’user@foo.com’n’est pas autorisé à gérer ce client. Les autorisations peuvent être accordées en attribuant l’utilisateur au rôle RBAC approprié. Pour plus d’informations, consultez la rubrique [résolution des problèmes distants](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1).*

- **Résolution**: Si vous pensez que vous êtes un membre du groupe administrateurs de clients, vous devez contacter le support technique d’Office 365.
  
## <a name="ability-to-connect-to-tenant-has-been-disabled-in-skype-for-business-online"></a>La possibilité de se connecter au client a été désactivée dans Skype entreprise Online
<a name="BKMKAbilityConnect"> </a>

Pour utiliser PowerShell pour gérer Skype entreprise Online, la propriété EnableRemotePowerShellAccess de votre stratégie PowerShell client doit être définie sur `True`. Si ce n’est pas le cas, votre connexion échoue et vous recevez le message d’erreur suivant :

- **Erreur**: *New-PSSession : [admin.vDomain.com] le traitement des données à partir du serveur distant admin.vDomain.com a échoué avec le message d’erreur suivant : la possibilité de se connecter à ce client à l’aide d’une session PowerShell distante a été désactivée. Veuillez contacter l’aide de Lync pour vérifier la stratégie PowerShell du client de ce client. Pour plus d’informations, consultez la rubrique [résolution des problèmes distants](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1).*

- **Solution**: Si vous voyez ce message d’erreur, vous devez contacter le support technique d’Office 365 et bénéficier de l’accès distant PowerShell.
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded"></a>Le nombre maximal d’interpréteurs simultanés pour cet utilisateur dans Skype entreprise Online a été dépassé.
<a name="BKMKMaxNumberShellsUser"> </a>

Chaque administrateur dispose d’au maximum trois connexions à distance simultanées à Skype entreprise online. Si trois connexions PowerShell distantes sont opérationnelles, toute tentative de création d’une quatrième connexion simultanée échoue, avec le message d’erreur suivant :

- **Erreur**: *New-PSSession : [admin.vDomain.com] la connexion à Remote Server Admin.vDomain.com a échoué avec le message d’erreur suivant : le service WS-Management ne peut pas traiter la demande. Le nombre maximal d’interpréteurs simultanés pour cet utilisateur a été dépassé. Fermez les coques existantes ou augmentez le quota de cet utilisateur. Pour plus d’informations, reportez-vous àhttps://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1 [Remote Troubleshoot] (*

- **Résolution**: la seule façon de résoudre ce problème consiste à fermer une ou plusieurs des connexions précédentes. Lorsque vous avez terminé d’utiliser une session Skype entreprise Online, nous vous recommandons d’utiliser l’applet de commande **Remove-PSSession** pour mettre fin à la session. Cela vous permettra d’éviter ce problème.
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded"></a>Le nombre maximal d’interpréteurs simultanés pour ce client dans Skype entreprise Online a été dépassé.
<a name="BKMKMaxNumberShellsTenant"> </a>

Bien que les administrateurs aient autant de connexions simultanées qu’un client Skype entreprise Online, il est possible qu’aucun client ne dispose de plus de 20 connexions simultanées. Par exemple, six administrateurs peuvent chacun avoir trois sessions ouvertes. Si un quatrième administrateur tente de faire plus de 2 connexions (ce qui donne un total de 21 connexions simultanées), cette tentative échoue, avec le message d’erreur suivant :
  
- **Erreur**: *New-PSSession : [admin.vDomain.com] la connexion à Remote Server Admin.vDomain.com a échoué avec le message d’erreur suivant : le service WS-Management ne peut pas traiter la demande. Le nombre maximal d’interpréteurs simultanés pour ce client a été dépassé. Fermez les coques existantes ou augmentez le quota pour ce client. Pour plus d’informations, reportez-vous àhttps://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1 [Remote Troubleshoot] (*

- **Résolution**: la seule façon de résoudre ce problème consiste à fermer une ou plusieurs des connexions précédentes. Lorsque vous avez terminé d’utiliser une session Skype entreprise Online, nous vous recommandons d’utiliser l’applet de commande **Remove-PSSession** pour mettre fin à la session. Cela vous permettra d’éviter ce problème.  
 
## <a name="related-topics"></a>Voir aussi
[Configurer votre ordinateur pour la gestion de Skype entreprise Online à l’aide de Windows PowerShell](set-up-your-computer-for-windows-powershell.md)

  
 
