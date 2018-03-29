---
title: Configurer Skype pour 2015 de serveur d’entreprise à utiliser Exchange Server d’archivage
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 260346d1-edc8-4a0c-8ad2-6c2401c3c377
description: 'Résumé : Configurez les transcriptions de messagerie instantanée pour 2016 d’Exchange Server ou Exchange Server 2013 et Skype pour Business Server 2015.'
ms.openlocfilehash: 280b86d223cc1dd90eb7fe7bc17e4ab3499e7f5d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/28/2018
---
# <a name="configure-skype-for-business-server-2015-to-use-exchange-server-archiving"></a>Configurer Skype pour 2015 de serveur d’entreprise à utiliser Exchange Server d’archivage
 
**Résumé :** Configurer les transcriptions de messagerie instantanée pour 2016 d’Exchange Server ou Exchange Server 2013 et Skype pour Business Server 2015.
  
Skype pour Business Server 2015 donne aux administrateurs la possibilité de la messagerie instantanée et les transcriptions de conférence Web archivées dans la boîte aux lettres Exchange Server 2016 ou Exchange Server 2013 d’un utilisateur plutôt que dans une base de données SQL Server. Si vous activez cette option, les transcriptions sont écrites dans le dossier Purges de la boîte aux lettres de l’utilisateur. Il s’agit d’un dossier masqué qui se trouve dans le dossier Purges. Bien que ce dossier n’est pas visible aux utilisateurs finaux, le dossier est indexé par le moteur de recherche Exchange et peut être découverts à l’aide de la recherche de boîte aux lettres Exchange et/ou Microsoft SharePoint Server 2013. Dans la mesure où les informations sont stockées dans le même dossier que celui utilisé par la fonctionnalité Exchange Place maintenez la touche (responsable de l’archivage des e-mails et autres communications Exchange), les administrateurs peuvent utiliser un seul outil pour rechercher toutes les communications électroniques archivés pour un utilisateur.
  
> [!IMPORTANT]
> Vous devez désactiver l’historique des conversations pour en désactiver complètement l’archivage. Pour plus d’informations, consultez les rubriques suivantes : [gestion de l’archivage des communications internes et externes dans Skype pour Business Server 2015](http://technet.microsoft.com/library/6c2cf941-3204-4f1a-a7e0-416c828056d9.aspx), [Nouvelle-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicy?view=skype-ps)et [CsClientPolicy de l’ensemble](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps). 
  
Pour archiver les relevés de notes à Exchange Server, vous devez commencer par la configuration d’authentification de serveur à serveur entre Skype pour Business Server et Exchange Server. Une fois l’authentification de serveur à serveur en place, vous pouvez ensuite effectuer les tâches suivantes dans Skype pour Business Server (Notez que, en fonction de votre installation et la configuration, vous n’ayez pas à exécuter toutes ces tâches) :
  
1. Activer l’archivage Exchange en modifiant votre Skype pour les paramètres de configuration d’archivage Business Server. Cette étape est nécessaire pour tous les déploiements.
    
2. Activez l’archivage des communications internes et/ou externes pour les utilisateurs. Cette étape est nécessaire pour tous les déploiements.
    
3. Configurez la propriété ExchangeArchivingPolicy pour chaque utilisateur. Cette étape est uniquement requise si Skype pour Business Server et Exchange Server sont situés dans des forêts différentes.
    
## <a name="step-1-enabling-exchange-archiving"></a>Étape 1 : Activation de l’archivage Exchange

L’archivage dans Skype pour Business Server est principalement gérée par les paramètres de configuration d’archivage. Lorsque vous installez Skype pour Business Server vous reçoivent automatiquement une collection unique et globale de ces paramètres. (Les administrateurs peuvent créer éventuellement les nouvelles collections de paramètres d’archivage au niveau de l’étendue du site). Par défaut, l’archivage n’est pas activé dans les paramètres globaux, ni est l’archivage Exchange activé dans ces paramètres. Pour utiliser l’archivage Exchange, les administrateurs doivent configurer les à la fois le EnableArchiving et EnableExchangeArchiving dans ces paramètres de configuration. La propriété EnableArchiving peut avoir l’une des trois valeurs suivantes :
  
- **Aucun**. L’archivage est désactivé. Il s’agit de la valeur par défaut. Si EnableArchiving est défini sur aucun, alors rien ne sera archivé dans une ou l’autre votre Skype pour l’archivage de base de données de Business Server ou dans Exchange Server.
    
- **ImOnly**. Seules les transcriptions de message instantané sont archivées. Si l’archivage Exchange est activée, ces relevés de notes seront archivées dans Exchange Server. Si l’archivage Exchange est désactivé puis ces relevés de notes seront archivées à Skype pour Business Server.
    
- **ImAndWebConf**. À la fois les transcriptions de messages instantanés et celles de conférences web sont archivées. Si l’archivage Exchange est activé ces relevés de notes seront archivées dans Exchange Server. Si l’archivage Exchange est désactivé puis ces relevés de notes seront archivées à Skype pour Business Server.
    
La propriété EnableExchangeArchiving est une valeur booléenne : la valeur EnableExchangeArchiving sur True ($True) pour activer l’archivage Exchange ou EnableExchangeArchiving la valeur False ($False) pour désactiver l’archivage Exchange. Par exemple, cette commande permet d’archiver des transcriptions de messagerie instantanées et permet également l’archivage Exchange :
  
```
Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $True
```

Pour désactiver l’archivage Exchange, utilisez une commande semblable à la suivante, qui permet l’archivage de messagerie instantanée, mais désactive l’archivage pour Exchange (en d’autres termes, relevés de notes seront archivés à Skype pour Business Server) :
  
```
Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $False
```

> [!NOTE]
> Si la propriété EnableArchiving est définie sur aucun, puis Skype pour Business Server n’archive pas les transcriptions des conférences Web et messagerie instantanée à tout. Dans ce cas, le serveur ignorera simplement la valeur configurée pour EnableExchangeArchiving. 
  
L’archivage Exchange peut également être activé (ou désactivé) en utilisant le Skype pour Business Server. Pour ce faire, procédez de la manière suivante :
  
1. Dans le Panneau de configuration, cliquez sur **Surveillance et archivage**, puis sur **Configuration de l’archivage**. 
    
2. Sous l’onglet **Configuration de l’archivage**, double-cliquez sur la collection de paramètres d’archivage à modifier (par exemple, la collection **Global**).
    
3. Dans le volet **Paramètre d’archivage**, cliquez sur la liste déroulante **Paramètre d’archivage**, puis sélectionnez **Archiver les sessions de messagerie instantanée** (pour archiver uniquement les sessions de messagerie instantanée) ou **Archiver les sessions de messagerie instantanée et de conférence web** (pour archiver les sessions de messagerie instantanée et les sessions de conférence web).
    
4. Après avoir choisi les éléments à archiver, activez la case à cocher de **l’intégration d’Exchange Server** pour activer l’archivage de Exchange. Pour désactiver l’archivage Exchange, désactivez cette case à cocher.
    
> [!NOTE]
> La case à cocher **Intégration Exchange Server** n’est pas disponible si **Paramètre d’archivage** est défini sur **Désactiver l’archivage**. Vous devez activer l’archivage de premier et puis activer l’archivage de Exchange. 
  
Si Skype pour Business Server et Exchange Server se trouvent dans la même forêt, puis l’archivage pour les utilisateurs individuels (ou au moins, les utilisateurs de messagerie comptes sur Exchange Server) est géré par l’utilisation de stratégies de contenir de Exchange sur Place. Si vous avez les utilisateurs qui sont hébergés sur une version antérieure d’Exchange, puis l’archivage pour les utilisateurs seront gérés à l’aide de Skype pour les stratégies d’archivage de serveur d’entreprise. Notez que seuls les utilisateurs possédant des comptes sur 2016 d’Exchange Server ou Exchange Server 2013 peuvent avoir leur Skype pour les transcriptions de professionnels archivés vers Exchange.
  
Si Skype pour Business Server et Exchange Server est situé dans des forêts différentes, puis l’archivage pour les utilisateurs individuels est géré par la configuration de la propriété ExchangeArchivingPolicy pour chaque compte d’utilisateur. Pour plus d’informations, reportez-vous à l’étape 3.
  
## <a name="step-2-enabling-the-archiving-of-internal-andor-external-communications"></a>Étape 2 : activation de l’archivage des communications internes et/ou externes

Une fois que vous avez activé l’archivage (et l’archivage d’Exchange) vous devez ensuite modifier les stratégies d’archivage appropriées pour vous assurer que les sessions utilisateur sont archivées en fait. Notez que la simple activation de l’archivage (étape 1) ne provoque pas Skype pour Business Server pour lancer l’archivage de la messagerie instantanée et les transcriptions des conférences Web. Vous devez utiliser les stratégies d’archivage pour activer l’archivage interne et/ou externe. Lorsque vous installez Skype pour Business Server vous installez également une stratégie d’archivage globale unique, qui contient deux propriétés :
  
- **ArchiveInternal**. Quand cette propriété a la valeur Vrai ($True), indique que les sessions de communication interne (celles qui impliquent uniquement des utilisateurs disposant d’un compte Active Directory dans votre organisation) seront archivées.
    
- **ArchiveExternal**. Quand cette propriété a la valeur Vrai ($True), indique que les sessions de communication externe (les sessions qui impliquent au moins un utilisateur ne disposant pas d’un compte Active Directory dans votre organisation) seront archivées.
    
Par défaut, ces deux propriétés ont la valeur Faux, ce qui signifie que ni les sessions de communication interne, ni les sessions de communication externe ne sont archivées. Pour modifier la stratégie globale, vous pouvez utiliser le Skype pour Business Server Management Shell et l’applet de commande Set-CsArchivingPolicy. Cette commande permet d’archiver à la fois les sessions de communication interne et externe :
  
```
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True -ArchiveExternal $True
```

Vous pouvez également utiliser New-CsArchivingPolicy pour créer une stratégie au niveau du site ou par utilisateur. Par exemple, la commande suivante crée une stratégie d’archivage par utilisateur appelée RedmondArchivingPolicy :
  
```
New-CsArchivingPolicy -Identity "RedmondArchivingPolicy" -ArchiveInternal $True -ArchiveExternal $True
```

Si vous créez une stratégie par utilisateur, vous devrez affecter cette stratégie aux utilisateurs appropriés. Par exemple :
  
```
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName  "RedmondArchivingPolicy"
```

Politiques d’archivage peuvent également être gérés à l’aide de la Skype pour Business Server du Panneau de configuration. Dans le Panneau de configuration, cliquez sur **Surveillance et archivage**, puis sur **Stratégie d’archivage**. Pour modifier une stratégie existante, double-cliquez sur la stratégie (par exemple, Global) puis, dans le volet **Stratégie d’archivage**, activez ou désactivez les cases à cocher **Archiver les communications internes** et **Archiver les communications externes** en fonction des besoins. Pour créer une nouvelle stratégie d’archivage, cliquez sur **Nouveau** et sélectionnez **stratégie de Site** ou de **stratégie de l’utilisateur**. Si vous créez une nouvelle stratégie d’utilisateur, vous devez accéder aux comptes d’utilisateurs appropriés (sous l’onglet **Utilisateurs**), puis affecter les nouvelles stratégies à ces utilisateurs.
  
## <a name="step-3-configuring-the-exchangearchivingpolicy-property"></a>Étape 3 : configuration de la propriété ExchangeArchivingPolicy

Si Skype pour Business Server et Exchange Server est situé dans des forêts différentes, puis il n’est pas suffisant de simplement permettre à Exchange d’archivage dans les paramètres de configuration d’archivage ; qui ne résultent pas de messagerie instantanée et les transcriptions de conférence Web archivées dans Exchange. Au lieu de cela, vous devez également configurer la propriété ExchangeArchivingPolicy de chaque le Skype pertinente pour les comptes d’utilisateur de serveur de l’entreprise. Cette propriété peut avoir l’une des valeurs suivantes :
  
1. **Non initialisé**. Indique que l’archivage se basera sur les paramètres en Place maintenez configurés pour la boîte aux lettres de l’utilisateur Exchange. Si la Place maintenez n’a pas été activée sur la boîte aux lettres de l’utilisateur puis l’utilisateur aura son propre messagerie et Web des transcriptions de conférence archivées dans Skype pour Business Server. 
    
2. **UseLyncArchivingPolicy**. Indique que les transcriptions des conférences Web et messagerie instantanée de l’utilisateur doivent être archivées dans Skype pour Business Server plutôt que dans Exchange.
    
3. **NoArchiving**. Indique que les transcriptions de messagerie instantanée et de conférence web de l’utilisateur ne doivent pas être archivées. Notez que ce paramètre remplace tout Skype pour Business Server affectés à l’utilisateur de politiques d’archivage.
    
4. **ArchivingToExchange**. Indique l’utilisateur de messagerie instantanée et conférences Web transcriptions doivent être archivées pour Exchange, quel que soit les paramètres en Place maintenez (ou non) reçu à la boîte aux lettres de l’utilisateur.
    
Par exemple, pour configurer un compte d’utilisateur de sorte que les transcriptions des conférences Web et messagerie instantanée sont archivées toujours à Exchange, vous pouvez utiliser une commande similaire à celle-ci depuis la Skype pour Business Server Management Shell :
  
```
Set-CsUser -Identity "Ken Myer" -ExchangeArchivingPolicy ArchivingToExchange
```

Si vous souhaitez définir la même stratégie d’archivage pour un groupe d’utilisateurs (par exemple, tous les utilisateurs hébergés sur un pool de serveurs d’inscriptions), vous pouvez utiliser une commande similaire à la suivante :
  
```
Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Set-CsUser -ExchangeArchivingPolicy ArchivingToExchange
```

Notez que vous devez utiliser le Skype pour Business Server Management Shell (et Windows PowerShell) pour configurer la valeur de la propriété ExchangeArchivingPolicy. Cette propriété n’est pas exposée aux administrateurs dans la Skype pour Business Server.
  
Si vous voulez afficher la liste de tous les utilisateurs auxquels une stratégie spécifique a été attribuée, vous pouvez utiliser une commande semblable à la suivante, qui renvoie le nom d’affichage Active Directory de tous les utilisateurs dont la propriété ExchangeArchivingPolicy a la valeur Uninitialized :
  
```
Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -eq "Uninitialized"} | Select-Object DisplayName
```

De même, cette commande renvoie le nom d’affichage des utilisateurs dont la propriété ExchangeArchivingPolicy n’a pas la valeur UseLyncArchivingPolicy :
  
```
Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -ne "UseLyncArchivingPolicy"} | Select-Object DisplayName
```


