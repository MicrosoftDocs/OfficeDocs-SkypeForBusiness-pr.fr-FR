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
description: Résolvez les problèmes de création d’une session PowerShell distante pour vous connecter à Skype Entreprise Online, notamment import-module, interpréteur de commandes simultané, ID en direct et erreurs d’autorisation.
ms.openlocfilehash: c2092da0324a147b182ce7715e757f1ed039aa65
ms.sourcegitcommit: 1ac37cc27d4ccb3e1dae20ca1929214e17be2075
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 06/07/2022
ms.locfileid: "65913392"
---
# <a name="diagnose-connection-problems-with-the-skype-for-business-online-connector"></a>Diagnostiquer des problèmes de connexion avec le connecteur Skype Entreprise Online

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Cette rubrique fournit des informations qui vous aideront à diagnostiquer et à résoudre les problèmes qui peuvent se produire lorsque vous essayez de créer une session Microsoft PowerShell distante qui se connecte à Skype Entreprise Online. Consultez les sections suivantes :
  
- [Erreur d’importation-module provoquée par la stratégie d’exécution de Windows PowerShell](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKPowerShellExecutionPolicy)
    
- [Erreur d’importation-module due à une version incorrecte de Windows PowerShell](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKIncorrectVersion)
    
- [Échec de l’authentification moderne quand l’authentification WinRM Basic a été désactivée](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKWinRMBasicAuth)
    
- [Échec de la connexion au serveur Live ID](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKFailedConnect)
      
- [Échec de la connexion pour l’utilisateur](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKLogonFailed)
    
- [L’utilisateur n’est pas autorisé à gérer ce locataire](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKUserPermission)
    
- [La possibilité de se connecter au locataire a été désactivée dans Skype Entreprise Online](diagnose-problems-with-the-skype-for-business-online-connector.md#BKMKAbilityConnect)
    
- [Le nombre maximal d’interpréteurs de commandes simultanés pour cet utilisateur dans Skype Entreprise Online a été dépassé](#the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded)

- [Le nombre maximal d’interpréteurs de commandes simultanés pour ce locataire dans Skype Entreprise Online a été dépassé](#the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded)

## <a name="import-module-error-caused-by-windows-powershell-execution-policy"></a>Import-Module erreur provoquée par la stratégie d’exécution de Windows PowerShell
<a name="BKMKPowerShellExecutionPolicy"> </a>

La stratégie d’exécution PowerShell permet de déterminer les fichiers de configuration qui peuvent être chargés dans la console PowerShell et les scripts qu’un utilisateur peut exécuter à partir de cette console. Au minimum, le module connecteur Skype Entreprise Online ne peut pas être importé, sauf si la stratégie d’exécution a été définie sur RemoteSigned. Si ce n’est pas le cas, vous recevrez le message d’erreur suivant lorsque vous tentez d’importer le module :
  
- **Erreur** : <em>Import-Module : Impossible de charger les fichiers\\\\courants fichiers C:\\Program microsoft Lync Server 2013\\Modules\\LyncOnlineConnector\\LyncOnlineConnectorStartup.psm1, car l’exécution de scripts est désactivée sur ce système. Pour plus d’informations, consultez about_Execution_Policies à https://go.microsoft.com/fwlink/?LinkID=135170.</em>

- **Résolution** Pour résoudre ce problème, démarrez PowerShell en tant qu’administrateur, puis exécutez la commande suivante :
    ```PowerShell
    Set-ExecutionPolicy RemoteSigned
    ```
    Pour plus d’informations sur la stratégie d’exécution, consultez [À propos des stratégies d’exécution](/powershell/module/microsoft.powershell.core/about/about_execution_policies).
  
## <a name="import-module-error-caused-by-incorrect-version-of-windows-powershell"></a>Import-Module Erreur provoquée par une version incorrecte de Windows PowerShell
<a name="BKMKIncorrectVersion"> </a>

Le module connecteur Skype Entreprise Online ne peut être exécuté que sous Windows PowerShell 3.0. Si vous essayez d’importer le module sous une version précédente de PowerShell, le processus d’importation échoue avec un message d’erreur similaire à ce message :
  
  - **Erreur** : *Import-Module : la version de PowerShell chargée est « 2.0 ». Le module « D:\\Program Files\\Common Files\\Microsoft Lync Server 2013\\Modules\\LyncOnlineConnector\\LyncOnlineConnector.psd1 » nécessite une version minimale de PowerShell « 3.0 » pour s’exécuter. Vérifiez l’installation de PowerShell et réessayez.*

- **Résolution** : La seule façon de résoudre ce problème est d’installer Windows PowerShell 3.0, qui est disponible à partir du Centre de téléchargement Microsoft à l’adresse [https://www.microsoft.com/download/details.aspx?id=34595](https://www.microsoft.com/download/details.aspx?id=34595).
  
## <a name="modern-authentication-fails-when-winrm-basic-authentication-has-been-disabled"></a>Échec de l’authentification moderne quand l’authentification WinRM Basic a été désactivée
<a name="BKMKWinRMBasicAuth"> </a>

La dernière version du module connecteur Skype Entreprise Online utilise l’authentification moderne, mais le client Windows Remote Management (WinRM) sous-jacent doit être configuré pour autoriser l’authentification de base.  L’authentification moderne utilise des jetons du porteur, qui sont généralement passés dans l’en-tête *Authorization: Bearer* . Windows PowerShell, sur lequel Skype Entreprise PowerShell est généré, ne permet pas la manipulation de cet en-tête.  Au lieu de cela, Skype Entreprise PowerShell utilise *l’en-tête Authorization: Basic* pour passer le jeton du porteur.

Consultez [Télécharger et installer Windows PowerShell](./download-and-install-windows-powershell-5-1.md) pour obtenir des instructions sur l’activation de WinRM pour l’authentification de base.

## <a name="failed-to-connect-to-live-id-server"></a>Échec de la connexion au serveur Live ID
<a name="BKMKFailedConnect"> </a>

> [!WARNING] 
> L’authentification Live ID a été déconseillée pour Skype Entreprise Online Connector. Utilisez le module Teams PowerShell pour gérer le locataire en ligne. Lors de la gestion des environnements hybrides, effectuez une mise à niveau vers la dernière mise à jour cumulative ou utilisez l’authentification oAuth.

Il existe généralement trois raisons pour lesquelles votre tentative de connexion peut échouer avec le message d’erreur suivant :

  - **Erreur** : *Get-CsWebTicket : Échec de la connexion des serveurs d’ID en direct. Assurez-vous que le proxy est activé ou que l’ordinateur dispose d’une connexion réseau à des serveurs d’ID actifs.*

- **Résolution** : souvent, cette erreur signifie que l’Assistant Connexion microsoft Online Services n’est pas en cours d’exécution. Vous pouvez vérifier l’état de ce service en exécutant la commande suivante à partir de l’invite PowerShell : 
    ```PowerShell
    Get-Service "msoidsvc"
    ```
    Si le service n’est pas en cours d’exécution, démarrez le service à l’aide de cette commande :
    ```PowerShell
    Start-Service "msoidsvc"
    ```

    Si le service est en cours d’exécution, il se peut que vous rencontriez des problèmes de connexion réseau entre votre ordinateur et le serveur d’authentification Microsoft Live ID. Pour vérifier cela, ouvrez Internet Explorer et accédez à [https://login.microsoftonline.com/.](https://login.microsoftonline.com/.) Essayez de vous connecter à Microsoft 365 ou Office 365 à partir de là. Si cela échoue, vous rencontrez probablement des problèmes de connexion réseau.
  
    Moins souvent, il est possible que l’URI de connexion pour le serveur d’authentification Microsoft Live ID ait été configuré avec une valeur incorrecte. Si vous avez déjà déterminé que l’Assistant Sign-In est en cours d’exécution et que vous ne rencontrez pas de problèmes de connectivité réseau, il peut s’agir du problème. Dans ce cas, contactez le Support Microsoft.
  
## <a name="logon-failed-for-the-user"></a>Échec de l’ouverture de session pour l’utilisateur
<a name="BKMKLogonFailed"> </a>

Lorsque vous tentez d’établir une connexion à distance à Skype Entreprise Online, vous devez fournir le nom d’utilisateur et le mot de passe d’un compte d’utilisateur Skype Entreprise Online valide. Si ce n’est pas le cas, l’ouverture de session échoue avec un message d’erreur similaire à ce message :

- **Erreur** : *Get-CsWebTicket : l’ouverture de session a échoué pour l’utilisateur « kenmyer@litwareinc.com ». Créez un objet PSCredential, en vous assurant que vous avez utilisé le nom d’utilisateur et le mot de passe corrects.*

- **Résolution** : Si vous pensez que vous utilisez un compte d’utilisateur valide et que vous disposez du mot de passe approprié, réessayez de vous connecter. Si cela échoue, utilisez les mêmes informations d’identification et essayez de vous connecter à l’adresse [https://login.microsoftonline.com/](https://login.microsoftonline.com/). Si vous ne parvenez pas à vous y connecter, contactez le Support Microsoft. 

  
## <a name="the-user-does-not-have-permission-to-manage-this-tenant"></a>L’utilisateur n’est pas autorisé à gérer ce locataire
<a name="BKMKUserPermission"> </a>

Vous ne pouvez pas établir de connexion PowerShell distante àSkype for Business Online, sauf si vous êtes membre du groupe Administrateurs de locataires. Si ce n’est pas le cas, votre tentative de connexion échouera et vous recevrez le message d’erreur suivant :

- **Erreur** : *New-PSSession : [admin.vdomain.com] Échec du traitement des données à partir du serveur distant admin.vdomain.com avec le message d’erreur suivant : l’utilisateur « user@foo.com » n’est pas autorisé à gérer ce locataire. Vous pouvez accorder des autorisations en affectant à l’utilisateur le rôle RBAC approprié. Pour plus d’informations, consultez la [résolution des problèmes à distance](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting ).*

- **Résolution** : Si vous pensez que vous êtes ou êtes censé être membre du groupe Administrateurs locataires, vous devez contacter le Support Microsoft.
  
## <a name="ability-to-connect-to-tenant-has-been-disabled-in-skype-for-business-online"></a>La possibilité de se connecter au locataire a été désactivée dans Skype Entreprise Online
<a name="BKMKAbilityConnect"> </a>

Pour utiliser PowerShell pour gérer Skype Entreprise Online, la propriété EnableRemotePowerShellAccess de votre stratégie PowerShell client doit être définie sur  `True`. Si ce n’est pas le cas, votre connexion échouera et vous recevrez le message d’erreur suivant :

- **Erreur** : *New-PSSession : [admin.vdomain.com] Échec du traitement des données à partir d’un serveur distant admin.vdomain.com avec le message d’erreur suivant : La possibilité de se connecter à ce locataire à l’aide d’une session PowerShell distante a été désactivée. Contactez l’aide de Lync pour vérifier la stratégie PowerShell du locataire de ce locataire. Pour plus d’informations, consultez la [résolution des problèmes à distance](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting ).*

- **Résolution** : si ce message d’erreur s’affiche, vous devez contacter le Support Microsoft et activer l’accès PowerShell distant.
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded"></a>Le nombre maximal d’interpréteurs de commandes simultanés pour cet utilisateur dans Skype Entreprise Online a été dépassé
<a name="BKMKMaxNumberShellsUser"> </a>

Chaque administrateur est autorisé à effectuer un maximum de trois connexions à distance simultanées à Skype Entreprise Online. Si vous disposez de trois connexions PowerShell distantes en cours d’exécution, toute tentative d’établir une quatrième connexion simultanée échoue, avec le message d’erreur suivant : 

- **Erreur** : *New-PSSession : [admin.vdomain.com] Échec de la connexion au serveur distant admin.vdomain.com avec le message d’erreur suivant : le service WS-Management ne peut pas traiter la demande. Le nombre maximal d’interpréteurs de commandes simultanés pour cet utilisateur a été dépassé. Fermez les interpréteurs de commandes existants ou augmentez le quota pour cet utilisateur. Pour plus d’informations, consultez la [résolution des problèmes à distance](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting ).*

- **Résolution** : la seule façon de résoudre ce problème consiste à fermer une ou plusieurs des connexions précédentes. Lorsque vous avez terminé une session Skype Entreprise Online, nous vous recommandons d’utiliser l’applet de commande **Remove-PSSession** pour terminer la session. Cela vous aidera à éviter ce problème.
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded"></a>Le nombre maximal d’interpréteurs de commandes simultanés pour ce locataire dans Skype Entreprise Online a été dépassé
<a name="BKMKMaxNumberShellsTenant"> </a>

Bien que chaque administrateur soit autorisé à avoir jusqu’à trois connexions simultanées à un locataire Skype Entreprise Online, aucun locataire unique n’est autorisé à avoir plus de 20 connexions simultanées. Par exemple, six administrateurs peuvent avoir chacun trois sessions ouvertes. Si un quatrième administrateur tente d’établir plus de deux connexions (ce qui entraîne un total de 21 connexions simultanées), cette tentative échoue, avec le message d’erreur suivant :
  
- **Erreur** : *New-PSSession : [admin.vdomain.com] Échec de la connexion au serveur distant admin.vdomain.com avec le message d’erreur suivant : le service WS-Management ne peut pas traiter la demande. Le nombre maximal d’interpréteurs de commandes simultanés pour ce locataire a été dépassé. Fermez les interpréteurs de commandes existants ou augmentez le quota pour ce locataire. Pour plus d’informations, consultez la [résolution des problèmes à distance](/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting ).*

- **Résolution** : la seule façon de résoudre ce problème consiste à fermer une ou plusieurs des connexions précédentes. Lorsque vous avez terminé une session Skype Entreprise Online, nous vous recommandons d’utiliser l’applet de commande **Remove-PSSession** pour mettre fin à cette session. Cela vous aidera à éviter ce problème.  
 
## <a name="related-topics"></a>Sujets associés
[Configurer votre ordinateur pour la gestion en ligne de Skype Entreprise à l’aide de Windows PowerShell](set-up-your-computer-for-windows-powershell.md)

  
