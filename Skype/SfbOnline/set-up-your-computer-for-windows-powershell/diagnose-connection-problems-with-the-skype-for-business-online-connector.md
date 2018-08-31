---
title: Diagnostiquer des problèmes de connexion avec le connecteur Skype Entreprise Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 866fadfd-16e2-4134-95db-c6aed7678416
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- PowerShell
description: Résoudre les problèmes de création d’une session PowerShell distante pour se connecter à Skype pour Business Online, notamment Import-Module, shell simultané, Live ID et les erreurs d’autorisation.
ms.openlocfilehash: 60ed4be1d4c20426a645002f1b7a71f65f120774
ms.sourcegitcommit: cbb4738e119cf366c3aad9aad7f7b369bcd86c19
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/30/2018
ms.locfileid: "23779094"
---
# <a name="diagnose-connection-problems-with-the-skype-for-business-online-connector"></a>Diagnostiquer des problèmes de connexion avec le connecteur Skype Entreprise Online

Cette rubrique fournit des informations qui vous aideront à diagnostiquer et résoudre les problèmes qui peuvent se produire lorsque vous essayez de créer une session Microsoft PowerShell à distance qui se connecte à Skype pour Business Online. Consultez les sections suivantes :
  
- [Erreur de Import-Module provoquée par la stratégie d’exécution Windows PowerShell](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKPowerShellExecutionPolicy)
    
- [Erreur Import-Module provoqué par une version incorrecte de Windows PowerShell](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKIncorrectVersion)
    
- [Impossible de se connecter à Live ID serveur](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKFailedConnect)
    
- [Impossible de charger le module Live ID](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKFailedLoad)
    
- [Ouverture de session a échoué pour l’utilisateur](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKLogonFailed)
    
- [L’utilisateur n’est pas autorisé à gérer ce client](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKUserPermission)
    
- [Possibilité de se connecter au client a été désactivée dans Skype pour Business en ligne](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKAbilityConnect)
    
- [Le nombre maximal de shells simultanés pour cet utilisateur dans Skype pour Business Online a été dépassé.](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKMaxNumberShellsUser)
    
- [Le nombre maximal de shells simultanés pour ce client dans Skype pour Business Online a été dépassé.](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMK_MaxNumberShellsTenant)
    
## <a name="import-module-error-caused-by-windows-powershell-execution-policy"></a>Erreur de Import-Module provoquée par la stratégie d’exécution Windows PowerShell
<a name="BKMKPowerShellExecutionPolicy"> </a>

La stratégie d’exécution PowerShell permet de déterminer les fichiers de configuration peuvent être chargées dans la console PowerShell et les scripts d’un utilisateur peut exécuter à partir de la console. Au minimum, le Skype pour le module Business Connector en ligne ne peut pas être importé, sauf si la stratégie d’exécution RemoteSigned a été définie. Si ce n’est pas le cas, vous recevez le message d’erreur suivant lorsque vous essayez d’importer le module :
  
- **Erreur**: *Import-Module : c : fichier\\Program Files\\Common Files\\Microsoft Lync Server 2013\\Modules\\LyncOnlineConnector\\LyncOnlineConnectorStartup.psm1 ne peut pas être chargé, car il est en cours d’exécution scripts est désactivé sur ce système. Pour plus d’informations, voir about_Execution_Policies à https://go.microsoft.com/fwlink/?LinkID=135170.*

- **Résolution**: pour résoudre ce problème, démarrer PowerShell en tant qu’administrateur et exécutez la commande suivante :
    ```
    Set-ExecutionPolicy RemoteSigned
    ```
    Pour plus d’informations sur la stratégie d’exécution, consultez la rubrique [Sur les stratégies d’exécution](https://go.microsoft.com/fwlink/?LinkID=135170).
  
## <a name="import-module-error-caused-by-incorrect-version-of-windows-powershell"></a>Erreur Import-Module provoqué par une version incorrecte de Windows PowerShell
<a name="BKMKIncorrectVersion"> </a>

Le Skype pour le module Business Online Connector peut être exécutée que sous Windows PowerShell 3.0. Si vous essayez d’importer le module dans une version antérieure de PowerShell, le processus d’importation échouera avec un message d’erreur similaire à celle-ci :
  
  - **Erreur**: *Import-Module : la version de PowerShell chargé est « 2.0 ». Le module'd :\\Program Files\\Common Files\\Microsoft Lync Server 2013\\Modules\\LyncOnlineConnector\\LyncOnlineConnector.psd1' nécessite une version minimale PowerShell « 3.0 ». Vérifiez l’installation de PowerShell et réessayez.*

- **Résolution**: la seule façon de résoudre ce problème consiste à installer Windows PowerShell 3.0, qui est disponible à partir de la Center Download Microsoft à [https://www.microsoft.com/en-us/download/details.aspx?id=34595](https://www.microsoft.com/en-us/download/details.aspx?id=34595).
  
## <a name="failed-to-connect-to-live-id-server"></a>Impossible de se connecter à Live ID serveur
<a name="BKMKFailedConnect"> </a>

Il existe généralement trois raisons pourquoi votre tentative de connexion peut échouer avec le message d’erreur suivant :

  - **Erreur**: *Get-CsWebTicket : Impossible de se connecter des serveurs Windows live id. Assurez-vous que proxy est activé ou ordinateur a connexion réseau à live serveurs id.*

- **Résolution**: souvent cette erreur signifie que l’Assistant de connexion Microsoft Online Services n’est pas en cours d’exécution. Vous pouvez vérifier l’état de ce service en exécutant la commande suivante à partir de l’invite de commandes PowerShell : 
    ```
    Get-Service "msoidsvc"
    ```
    Si le service n’est pas en cours d’exécution, démarrez le service à l’aide de cette commande :
    ```
    Start-Service "msoidsvc"
    ```

    Si le service est en cours d’exécution, vous pourrez rencontrer des problèmes avec la connexion réseau entre votre ordinateur et le serveur de l’authentification Microsoft Live ID. Pour vérifier cela, ouvrez Internet Explorer et accédez à [ https://login.microsoftonline.com/.](https://login.microsoftonline.com/.) Essayer de se connecter à Office 365 à partir de là. En cas d’échec, vous avez sans doute les problèmes de connexion réseau.
  
    Moins fréquemment, il est possible que l’URI de connexion de Microsoft Live ID d’authentification du serveur a été configuré avec la valeur incorrecte. Si vous avez déjà déterminé que l’Assistant de connexion est en cours d’exécution et que vous rencontrez pas les problèmes de connectivité réseau, il peut être le problème. Dans ce cas, contactez le Support de Office 365.
  
## <a name="failed-to-load-live-id-module"></a>Impossible de charger le module Live ID
<a name="BKMKFailedLoad"> </a>

Une des conditions requises pour l’utilisation de PowerShell pour gérer Skype pour Business Online consiste à installer l’Assistant de connexion Microsoft Online Services. Si l’Assistant de connexion n’est pas installé, vous recevrez le message d’erreur suivant lorsque vous essayez d’ouvrir une session à distance avec Skype pour Business Online :

- **Erreur**: *Get-CsWebTicket : module Live Id ne peut pas charger. Vérifiez adéquates version de Live Id assistant de connexion est installée.*

- **Résolution**: Assistant de connexion des Services en ligne Microsoft est disponible dans le Center Download Microsoft à [Microsoft Online Services Assistant de connexion pour les professionnels de l’informatique RTW](https://www.microsoft.com/en-us/download/details.aspx?id=28177)

## <a name="logon-failed-for-the-user"></a>Ouverture de session a échoué pour l’utilisateur
<a name="BKMKLogonFailed"> </a>

Lorsque vous essayez d’établir une connexion à Skype pour Business Online, vous devez fournir le nom d’utilisateur et le mot de passe d’un Skype Business en ligne compte d’utilisateur valide. Si vous le faites pas, ouverture de session échoue avec un message d’erreur similaire à celle-ci :

- **Erreur**: *Get-CsWebTicket : échec d’ouverture de session pour l’utilisateur 'kenmyer@litwareinc.com'. Créez un nouvel objet PSCredential, en veillant à ce que vous avez utilisé le nom d’utilisateur et le mot de passe.*

- **Résolution**: Si vous pensez que vous utilisez un compte d’utilisateur valide et que vous avez le mot de passe, réessayez de vous connecter. En cas d’échec, utilisez les mêmes informations d’identification et essayez d’ouvrir une session sur [https://login.microsoftonline.com/](https://login.microsoftonline.com/). Si vous ne parvenez pas à se connecter il, contactez le support technique de Office 365. 

  
## <a name="the-user-does-not-have-permission-to-manage-this-tenant"></a>L’utilisateur n’est pas autorisé à gérer ce client
<a name="BKMKUserPermission"> </a>

Impossible d’effectuer une toSkype de connexion à distance PowerShell pour l’entreprise en ligne, sauf si vous êtes membre du groupe Administrateurs de clients. Si vous n’êtes pas le cas, votre tentative de connexion échoue et vous recevez le message d’erreur suivant :

- **Erreur**: *New-PSSession : [admin.vdomain.com] traitement des données à partir du serveur distant admin.vdomain.com a échoué avec le message d’erreur suivant : l’utilisateur 'user@foo.com' n’est pas autorisé à gérer ce client. Autorisations peuvent être accordées en affectant l’utilisateur au rôle RBAC approprié. Pour plus d’informations, voir le [Dépannage à distance](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1).*

- **Résolution**: Si vous pensez que vous, ou sont censés être, un membre du groupe Administrateurs de clients, vous devez contacter le support technique de Office 365.
  
## <a name="ability-to-connect-to-tenant-has-been-disabled-in-skype-for-business-online"></a>Possibilité de se connecter au client a été désactivée dans Skype pour Business en ligne
<a name="BKMKAbilityConnect"> </a>

Pour utiliser PowerShell pour gérer Skype pour Business en ligne, la propriété de EnableRemotePowerShellAccess de votre client PowerShell stratégie doit être définie `True`. S’il n’est pas le cas, la connexion échoue et vous recevez le message d’erreur suivant :

- **Erreur**: *New-PSSession : [admin.vdomain.com] traitement des données à partir du serveur distant admin.vdomain.com a échoué avec le message d’erreur suivant : la possibilité de se connecter à ce client à l’aide d’une session PowerShell distante a été désactivée. Contactez l’aide de Lync pour vérifier la stratégie de Powershell client de ce client. Pour plus d’informations, voir le [Dépannage à distance](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1).*

- **Résolution**: Si vous voyez ce message d’erreur, vous devez contacter le support technique de Office 365 et d’accéder à distance PowerShell activé.
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded"></a>Le nombre maximal de shells simultanés pour cet utilisateur dans Skype pour Business Online a été dépassé.
<a name="BKMKMaxNumberShellsUser"> </a>

Chaque administrateur est autorisé à un maximum de trois connexions à distance simultanées à Skype pour Business Online. Si vous avez trois sessions PowerShell distantes haut et en cours d’exécution, toute tentative d’effectuer une quatrième simultanées connexion échoue, avec le message d’erreur suivant :

- **Erreur**: *New-PSSession : Échec de la connexion au serveur distant admin.vdomain.com [admin.vdomain.com] avec le message d’erreur suivant : service de la gestion des services Web ne peut pas traiter la demande. Le nombre maximal de shells simultanés pour cet utilisateur a été dépassé. Fermez les environnements existants ou augmenter le quota de cet utilisateur. Pour plus d’informations, voir le [dépannage à distance] (https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1 *

- **Résolution**: la seule façon de résoudre ce problème est de fermer une ou plusieurs des connexions précédentes. Lorsque vous avez terminé avec un Skype pour la session Business en ligne, nous vous recommandons d’utiliser l’applet de commande **Remove-PSSession** pour mettre fin à la session. Cela vous aidera à éviter ce problème.
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded"></a>Le nombre maximal de shells simultanés pour ce client dans Skype pour Business Online a été dépassé.
<a name="BKMKMaxNumberShellsTenant"> </a>

Bien que chaque administrateur est autorisé à avoir jusqu'à trois connexions simultanées à un Skype pour client d’entreprise en ligne, sans un seul client est autorisé à avoir plus de neuf connexions simultanées. Par exemple, trois administrateurs peuvent chacun avoir trois sessions ouvertes. Si un administrateur quatrième tente d’établir une connexion (soit un total de 10 connexions simultanées), cette tentative échouera, avec le message d’erreur suivant :
  
- **Erreur**: *New-PSSession : Échec de la connexion au serveur distant admin.vdomain.com [admin.vdomain.com] avec le message d’erreur suivant : service de la gestion des services Web ne peut pas traiter la demande. Le nombre maximal de shells simultanés pour ce client a été dépassé. Fermez les environnements existants ou augmenter le quota pour ce client. Pour plus d’informations, voir le [dépannage à distance] (https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1 *

- **Résolution**: la seule façon de résoudre ce problème est de fermer une ou plusieurs des connexions précédentes. Lorsque vous avez terminé avec un Skype pour la session Business en ligne, nous vous recommandons d’utiliser l’applet de commande **Remove-PSSession** pour mettre fin à cette session. Cela vous aidera à éviter ce problème.  
 
## <a name="related-topics"></a>Rubriques connexes
[Configurer votre ordinateur pour Skype pour la gestion en ligne à l’aide de Windows PowerShell](set-up-your-computer-for-windows-powershell.md)

  
 
