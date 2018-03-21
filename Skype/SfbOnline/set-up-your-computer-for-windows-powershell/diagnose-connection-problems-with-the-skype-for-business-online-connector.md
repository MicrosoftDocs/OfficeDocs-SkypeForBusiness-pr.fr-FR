---
title: "Diagnostiquer les problèmes de connexion avec le Skype pour Business Connector d’en ligne"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
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
description: "Résoudre les problèmes de création d’une session PowerShell à distance pour se connecter sur Skype pour professionnels en ligne, y compris l’Import-Module, shell simultanée, Live ID et erreurs d’autorisation."
ms.openlocfilehash: b98acefed673c08f6b986055fafef82847902f1a
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/19/2018
---
# <a name="diagnose-connection-problems-with-the-skype-for-business-online-connector"></a>Diagnostiquer les problèmes de connexion avec le Skype pour Business Connector d’en ligne

Cette rubrique fournit des informations qui vous aideront à diagnostiquer et à résoudre les problèmes qui peuvent se produire lorsque vous essayez de créer une session de Microsoft PowerShell distante qui se connecte à Skype pour entreprise en ligne. Consultez les sections suivantes :
  
- [Erreur le Module d’importation a provoqué par la stratégie d’exécution de Windows PowerShell](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKPowerShellExecutionPolicy)
    
- [Erreur le Module d’importation provoqué par une version incorrecte de Windows PowerShell](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKIncorrectVersion)
    
- [Impossible de se connecter à Live ID serveur](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKFailedConnect)
    
- [Impossible de charger le module de Live ID](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKFailedLoad)
    
- [Ouverture de session a échoué pour l’utilisateur](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKLogonFailed)
    
- [L’utilisateur n’a pas l’autorisation de gérer ce client](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKUserPermission)
    
- [Possibilité de se connecter à des clients a été désactivée dans Skype pour professionnels en ligne](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKAbilityConnect)
    
- [Le nombre maximal de shells simultanées de cet utilisateur dans Skype pour Business Online a été dépassé.](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMKMaxNumberShellsUser)
    
- [Le nombre maximal de shells simultanées pour ce client dans Skype pour Business Online a été dépassé.](diagnose-connection-problems-with-the-skype-for-business-online-connector.md#BKMK_MaxNumberShellsTenant)
    
## <a name="import-module-error-caused-by-windows-powershell-execution-policy"></a>Erreur le Module d’importation a provoqué par la stratégie d’exécution de Windows PowerShell
<a name="BKMKPowerShellExecutionPolicy"> </a>

La stratégie d’exécution PowerShell permet de déterminer les fichiers de configuration peuvent être chargés dans la console PowerShell et les scripts d’un utilisateur peut exécuter à partir de la console. Au minimum, le Skype pour module de Business Connector d’en ligne Impossible d’importer sauf si la stratégie d’exécution RemoteSigned a valeur. Si ce n’est pas le cas, vous recevez le message d’erreur suivant lorsque vous essayez d’importer le module :
  
- **Erreur**: *le Module d’importation : fichier C:\\Program Files\\fichiers communs\\Microsoft Lync Server 2013\\Modules\\LyncOnlineConnector\\LyncOnlineConnectorStartup.psm1 ne peut pas être chargé, car il est en cours d’exécution scripts est désactivée sur ce système. Pour plus d’informations, reportez-vous à la section about_Execution_Policies à https://go.microsoft.com/fwlink/?LinkID=135170.*

- **Résolution** Pour résoudre ce problème, démarrer PowerShell en tant qu’administrateur, puis exécutez la commande suivante :
    ```
    Set-ExecutionPolicy RemoteSigned
    ```
    Pour plus d’informations sur la stratégie de l’exécution, consultez [à propos de l’exécution de stratégies](https://go.microsoft.com/fwlink/?LinkID=135170).
  
## <a name="import-module-error-caused-by-incorrect-version-of-windows-powershell"></a>Erreur le Module d’importation provoqué par une version incorrecte de Windows PowerShell
<a name="BKMKIncorrectVersion"> </a>

Le Skype pour module de Business Connector d’en ligne peut être exécuté que sous Windows PowerShell 3.0. Si vous essayez d’importer le module sous une version précédente de PowerShell, le processus d’importation échoue avec un message d’erreur semblable à celui-ci :
  
  - **Erreur**: *le Module d’importation : la version de PowerShell chargé est « 2.0 ». Le module « D:\\Program Files\\fichiers communs\\Microsoft Lync Server 2013\\Modules\\LyncOnlineConnector\\LyncOnlineConnector.psd1' nécessite une version de PowerShell minimale de « 3.0 ». Veuillez vérifier l’installation de PowerShell et essayez à nouveau.*

- **Résolution**: la seule façon de résoudre ce problème est d’installer Windows PowerShell 3.0 qui est disponible dans Microsoft Download Center au [https://www.microsoft.com/en-us/download/details.aspx?id=34595](https://www.microsoft.com/en-us/download/details.aspx?id=34595).
  
## <a name="failed-to-connect-to-live-id-server"></a>Impossible de se connecter à Live ID serveur
<a name="BKMKFailedConnect"> </a>

Il existe généralement trois raisons pourquoi votre tentative de connexion peut échouer avec le message d’erreur suivant :

  - **Erreur**: *Get-CsWebTicket : Impossible de se connecter les serveurs live id. Vérifiez que proxy est activé ou machine a la connexion réseau aux serveurs des id de live.*

- **Résolution**: cette erreur indique généralement que l’Assistant de connexion Microsoft Online Services n’est pas en cours d’exécution. Vous pouvez vérifier l’état de ce service en exécutant la commande suivante à partir de l’invite de PowerShell : 
    ```
    Get-Service "msoidsvc"
    ```
    Si le service n’est pas en cours d’exécution, démarrez le service à l’aide de cette commande :
    ```
    Start-Service "msoidsvc"
    ```

    Si le service est en cours d’exécution, vous pouvez rencontrer des problèmes avec la connexion réseau entre votre ordinateur et le serveur de l’authentification Microsoft Live ID. Pour ce faire, ouvrez Internet Explorer et accédez à [https://login.microsoftonline.com/.](https://login.microsoftonline.com/.) Essayez de vous connecter à Office 365 à partir de là. En cas d’échec, vous rencontrez probablement des problèmes de connexion réseau.
  
    Moins fréquemment, il est possible que l’URI de connexion pour Microsoft Live ID de l’authentification de serveur a été configuré pour une valeur incorrecte. Si vous avez déjà déterminé que l’Assistant de connexion est en cours d’exécution et que vous ne rencontrez pas de problèmes de connectivité réseau, cela peut être le problème. Dans ce cas, contactez le Support de Office 365.
  
## <a name="failed-to-load-live-id-module"></a>Impossible de charger le module de Live ID
<a name="BKMKFailedLoad"> </a>

Une des conditions préalables à l’utilisation de PowerShell pour gérer Skype pour entreprise en ligne est pour installer l’Assistant de connexion Microsoft Online Services. Si l’Assistant de connexion n’est pas installé, le message d’erreur suivant s’affiche lorsque vous essayez d’établir une session à distance avec Skype pour entreprise en ligne :

- **Erreur**: *Get-CsWebTicket : module de Live Id ne peut pas charger. Vérifiez qu’adéquates version de Live Id assistant de connexion est installée.*

- **Résolution**: Assistant de connexion Microsoft des Services en ligne est disponible dans Microsoft Download Center au [Microsoft Online Services Assistant de connexion pour RTW de professionnels de l’informatique](https://www.microsoft.com/en-us/download/details.aspx?id=28177)

## <a name="logon-failed-for-the-user"></a>Ouverture de session a échoué pour l’utilisateur
<a name="BKMKLogonFailed"> </a>

Lorsque vous tentez d’établir une connexion à Skype pour professionnels en ligne, vous devez fournir le nom d’utilisateur et le mot de passe d’un Skype valide pour le compte d’utilisateur Business Online. Si vous ne le faites pas, la connexion échoue et un message d’erreur semblable à celui-ci :

- **Erreur**: *Get-CsWebTicket : Échec de l’ouverture de session pour l’utilisateur 'kenmyer@litwareinc.com'. Créez un nouvel objet PSCredential, en veillant à ce que vous avez utilisé le nom d’utilisateur et le mot de passe.*

- **Résolution**: Si vous pensez que vous utilisez un compte d’utilisateur valide et que vous avez le mot de passe, réessayez de vous connecter. En cas d’échec, utiliser les mêmes informations et essayez d’ouvrir une session sur [https://login.microsoftonline.com/](https://login.microsoftonline.com/). Si vous ne parvenez pas à ouvrir une session il, contactez le support technique de Office 365. 

  
## <a name="the-user-does-not-have-permission-to-manage-this-tenant"></a>L’utilisateur n’a pas l’autorisation de gérer ce client
<a name="BKMKUserPermission"> </a>

Impossible d’effectuer une toSkype de connexion PowerShell distant d’entreprise en ligne sauf si vous êtes un membre du groupe Administrateurs de clients. Si vous ne l’êtes pas, votre tentative de connexion échoue et vous recevez le message d’erreur suivant :

- **Erreur**: *Nouveau-PSSession : [admin.vdomain.com] le traitement des données à partir du serveur distant admin.vdomain.com a échoué avec le message d’erreur suivant : l’utilisateur 'user@foo.com' n’a pas l’autorisation de gérer ce client. Les autorisations peuvent être accordées par l’affectation de l’utilisateur au rôle RBAC approprié. Pour plus d’informations, consultez le [Dépannage à distance](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1).*

- **Résolution**: Si vous pensez que vous, ou sont censés pour être, un membre du groupe Administrateurs de clients, vous devez contacter le support technique de Office 365.
  
## <a name="ability-to-connect-to-tenant-has-been-disabled-in-skype-for-business-online"></a>Possibilité de se connecter à des clients a été désactivée dans Skype pour professionnels en ligne
<a name="BKMKAbilityConnect"> </a>

Pour utiliser PowerShell pour gérer Skype pour professionnels en ligne, la propriété EnableRemotePowerShellAccess de votre stratégie de PowerShell de clients doit être définie `True`. S’il n’est pas le cas, la connexion échoue et vous recevez le message d’erreur suivant :

- **Erreur**: *Nouveau-PSSession : [admin.vdomain.com] le traitement des données à partir du serveur distant admin.vdomain.com a échoué avec le message d’erreur suivant : la possibilité de se connecter à ce client en utilisant une session PowerShell à distance a été désactivée. Contactez l’aide de Lync pour vérifier la stratégie de Powershell locataire de ce client. Pour plus d’informations, consultez le [Dépannage à distance](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1).*

- **Résolution**: Si vous voyez ce message d’erreur, vous devrez contacter le support technique de Office 365 et obtenir l’accès PowerShell distant.
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-user-in-skype-for-business-online-has-been-exceeded"></a>Le nombre maximal de shells simultanées de cet utilisateur dans Skype pour Business Online a été dépassé.
<a name="BKMKMaxNumberShellsUser"> </a>

Chaque administrateur est autorisé à un maximum de trois connexions à distance simultanées à Skype pour l’activité en ligne. Si vous avez trois connexions PowerShell distantes des et en cours d’exécution, toute tentative d’effectuer une quatrième simultanées connexion échoue, le message d’erreur suivant :

- **Erreur**: *Nouveau-PSSession : [admin.vdomain.com] connexion à un serveur distant admin.vdomain.com a échoué avec le message d’erreur suivant : service de la gestion ne peut pas traiter la demande. Le nombre maximal de shells simultanées pour cet utilisateur a été dépassé. Fermez les environnements existants ou augmenter le quota de cet utilisateur. Pour plus d’informations, consultez la [dépannage à distance de](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1*

- **Résolution**: la seule façon de résoudre ce problème est de fermer une ou plusieurs des connexions précédentes. Lorsque vous avez terminé un Skype pour session Business en ligne, nous vous recommandons d’utiliser l’applet de commande **Remove-PSSession** pour mettre fin à la session. Cela vous aidera à éviter ce problème.
  
## <a name="the-maximum-number-of-concurrent-shells-for-this-tenant-in-skype-for-business-online-has-been-exceeded"></a>Le nombre maximal de shells simultanées pour ce client dans Skype pour Business Online a été dépassé.
<a name="BKMKMaxNumberShellsTenant"> </a>

Bien que chaque administrateur est autorisé à avoir trois connexions simultanées à un Skype pour clients d’entreprise en ligne, aucun mono-utilisateur n’est autorisé à avoir de plus de neuf connexions simultanées. Par exemple, trois administrateurs peuvent avoir chacun trois sessions ouvertes. Si un administrateur quatrième tente d’établir une connexion (soit un total de 10 connexions simultanées), cette tentative échoue, le message d’erreur suivant :
  
- **Erreur**: *Nouveau-PSSession : [admin.vdomain.com] connexion à un serveur distant admin.vdomain.com a échoué avec le message d’erreur suivant : service de la gestion ne peut pas traiter la demande. Le nombre maximal de shells simultanées pour ce client a été dépassé. Fermez les environnements existants ou augmenter le quota pour ce client. Pour plus d’informations, consultez la [dépannage à distance de](https://docs.microsoft.com/en-us/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-5.1*

- **Résolution**: la seule façon de résoudre ce problème est de fermer une ou plusieurs des connexions précédentes. Lorsque vous avez terminé un Skype pour session Business en ligne, nous vous recommandons d’utiliser l’applet de commande **Remove-PSSession** pour mettre fin à cette session. Cela vous aidera à éviter ce problème.  
 
## <a name="related-topics"></a>Rubriques connexes
[Configurer votre ordinateur pour Skype pour la gestion d’entreprise en ligne à l’aide de Windows PowerShell](set-up-your-computer-for-windows-powershell.md)

