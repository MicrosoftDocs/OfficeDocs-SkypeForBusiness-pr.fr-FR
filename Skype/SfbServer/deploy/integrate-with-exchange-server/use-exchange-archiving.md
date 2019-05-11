---
title: Configurer Skype pour Business Server utilisant l’archivage d’Exchange Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 260346d1-edc8-4a0c-8ad2-6c2401c3c377
description: 'Résumé : Configurez les transcriptions de messagerie instantanée pour Exchange Server 2016 ou Exchange Server 2013 et Skype pour Business Server.'
ms.openlocfilehash: a810f2e3eb3546eae5b3e04b2b1a9e83b7f9dbab
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33894231"
---
# <a name="configure-skype-for-business-server-to-use-exchange-server-archiving"></a>Configurer Skype pour Business Server utilisant l’archivage d’Exchange Server

**Résumé :** Configurez les transcriptions de messagerie instantanée pour Exchange Server 2016 ou Exchange Server 2013 et Skype pour Business Server.

Skype pour Business Server permet aux administrateurs la possibilité de messagerie instantanée et les transcriptions de conférence Web archivées dans la boîte aux lettres Exchange Server 2016 ou Exchange Server 2013 d’un utilisateur plutôt que dans une base de données SQL Server. Si vous activez cette option, les transcriptions sont écrites dans le dossier Purges de la boîte aux lettres de l’utilisateur. Il s’agit d’un dossier masqué qui se trouve dans le dossier Purges. Bien que ce dossier n’est pas visible pour les utilisateurs finaux, le dossier est indexé par le moteur de recherche Exchange et peut être découverts à l’aide de la recherche de boîte aux lettres Exchange et/ou Microsoft SharePoint Server 2013. Étant donné que les informations sont stockées dans le même dossier utilisé par la fonctionnalité de blocage sur Place Exchange (responsable de l’archivage de messagerie et autres communications Exchange), les administrateurs peuvent utiliser un seul outil pour rechercher toutes les communications électroniques archivés pour un utilisateur.

> [!IMPORTANT]
> Vous devez désactiver l’historique des conversations pour en désactiver complètement l’archivage. Pour plus d’informations, consultez les rubriques suivantes : [gestion de l’archivage des communications internes et externes dans Skype pour Business Server](https://technet.microsoft.com/library/6c2cf941-3204-4f1a-a7e0-416c828056d9.aspx), [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/new-csclientpolicy?view=skype-ps)et [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/set-csclientpolicy?view=skype-ps).

Afin d’archiver les transcriptions pour Exchange Server, vous devez commencer par la configuration de l’authentification serveur à serveur entre Skype pour Business Server et Exchange Server. Une fois que l’authentification de serveur à serveur est en place, vous pouvez ensuite effectuer les tâches suivantes dans Skype pour Business Server (Notez que, en fonction de votre installation et la configuration, vous ayez pas à exécuter toutes ces tâches) :

1. Activer l’archivage Exchange en modifiant votre Skype pour les paramètres de configuration d’archivage Business Server. Cette étape est nécessaire pour tous les déploiements.

2. Activez l’archivage des communications internes et/ou externes pour les utilisateurs. Cette étape est nécessaire pour tous les déploiements.

3. Configurez la propriété ExchangeArchivingPolicy pour chaque utilisateur. Cette étape est uniquement requise si Skype pour Business Server et Exchange Server sont situés dans des forêts différentes.

## <a name="step-1-enabling-exchange-archiving"></a>Étape 1 : Activation de l’archivage Exchange

L’archivage dans Skype pour Business Server est principalement gérée par les paramètres de configuration d’archivage. Lorsque vous installez Skype pour Business Server vous reçoivent automatiquement une collection unique et globale de ces paramètres. (Les administrateurs peuvent créer éventuellement les nouvelles collections de paramètres d’archivage au niveau du site). Par défaut, l’archivage n’est pas activée dans les paramètres globaux, ni est l’archivage Exchange activé dans ces paramètres. Pour pouvoir utiliser l’archivage Exchange, les administrateurs doivent configurer à la fois le EnableArchiving et EnableExchangeArchiving dans ces paramètres de configuration. La propriété EnableArchiving peut avoir l’une des trois valeurs suivantes :

- **Aucun**. L’archivage est désactivé. Il s’agit de la valeur par défaut. Si EnableArchiving est défini sur None, puis nothing seront archivées dans soit votre Skype pour Business Server d’archivage de base de données ou dans Exchange Server.

- **ImOnly**. Seules les transcriptions de message instantané sont archivées. Si l’archivage Exchange est activé, ces transcriptions seront archivées dans Exchange Server. Si l’archivage Exchange est désactivé ces transcriptions seront archivées dans Skype pour Business Server.

- **ImAndWebConf**. À la fois les transcriptions de messages instantanés et celles de conférences web sont archivées. Si l’archivage Exchange est activé ces transcriptions seront archivées dans Exchange Server. Si l’archivage Exchange est désactivé ces transcriptions seront archivées dans Skype pour Business Server.

La propriété EnableExchangeArchiving est une valeur booléenne : EnableExchangeArchiving sur True ($True) pour activer l’archivage Exchange ou définir EnableExchangeArchiving la valeur False ($False) pour désactiver l’archivage Exchange. Par exemple, cette commande active l’archivage des transcriptions de messagerie instantanées et permet également à l’archivage Exchange :

```
Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $True
```

Pour désactiver l’archivage Exchange, utilisez une commande semblable à la suivante, qui permet l’archivage de messagerie instantanée mais désactive l’archivage dans Exchange (en d’autres termes, les transcriptions seront archivées à Skype pour Business Server) :

```
Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $False
```

> [!NOTE]
> Si la propriété EnableArchiving est définie sur None, puis Skype pour Business Server n’archive pas les transcriptions de conférence Web et de messagerie instantanée tout. Dans ce cas, le serveur ignorera simplement la valeur configurée pour EnableExchangeArchiving.

L’archivage Exchange peut également être activé (ou désactivé) à l’aide de la Skype pour Business Server. Pour ce faire, procédez de la manière suivante :

1. Dans le Panneau de configuration, cliquez sur **Surveillance et archivage**, puis sur **Configuration de l’archivage**.

2. Sous l’onglet **Configuration de l’archivage**, double-cliquez sur la collection de paramètres d’archivage à modifier (par exemple, la collection **Global**).

3. Dans le volet **Paramètre d’archivage**, cliquez sur la liste déroulante **Paramètre d’archivage**, puis sélectionnez **Archiver les sessions de messagerie instantanée** (pour archiver uniquement les sessions de messagerie instantanée) ou **Archiver les sessions de messagerie instantanée et de conférence web** (pour archiver les sessions de messagerie instantanée et les sessions de conférence web).

4. Après avoir sélectionné les éléments à archiver, activez la case à cocher de **l’intégration d’Exchange Server** pour activer l’archivage Exchange. Pour désactiver l’archivage Exchange, désactivez cette case à cocher.

> [!NOTE]
> La case à cocher **Intégration Exchange Server** n’est pas disponible si **Paramètre d’archivage** est défini sur **Désactiver l’archivage**. Vous devez activer l’archivage préalable et activer l’archivage Exchange.

Si Skype pour Business Server et Exchange Server se trouvent dans la même forêt, puis l’archivage pour des utilisateurs individuels (ou au moins les utilisateurs de messagerie comptes sur Exchange Server) est géré à l’aide de stratégies de blocage sur Place Exchange. Si vous avez des utilisateurs qui sont hébergés sur une version antérieure d’Exchange, puis l’archivage pour les utilisateurs sont gérés à l’aide de Skype pour les stratégies d’archivage Business Server. Notez que seuls les utilisateurs disposant de comptes dans Exchange Server 2016 ou Exchange Server 2013 peuvent avoir leur Skype pour transcriptions Business archivées dans Exchange.

Si Skype pour Business Server et Exchange Server est situé dans des forêts différentes, puis l’archivage pour des utilisateurs individuels est géré par la configuration de la propriété ExchangeArchivingPolicy pour chaque compte d’utilisateur. Pour plus d’informations, reportez-vous à l’étape 3.

## <a name="step-2-enabling-the-archiving-of-internal-andor-external-communications"></a>Étape 2 : activation de l’archivage des communications internes et/ou externes

Une fois que vous avez activé l’archivage (et Exchange d’archivage) vous devez ensuite modifier les stratégies d’archivage appropriées pour vous assurer que les sessions utilisateur sont archivées réellement. Notez que l’activation de l’archivage (étape 1) simplement n’entraîne pas Skype pour Business Server pour lancer l’archivage de messagerie instantanée et les transcriptions de conférence Web. Vous devez utiliser les stratégies d’archivage pour activer l’archivage interne et/ou externe. Lorsque vous installez Skype pour Business Server vous installez également une stratégie d’archivage globale et unique, qui contient deux propriétés :

- **ArchiveInternal**. Quand cette propriété a la valeur Vrai ($True), indique que les sessions de communication interne (celles qui impliquent uniquement des utilisateurs disposant d’un compte Active Directory dans votre organisation) seront archivées.

- **ArchiveExternal**. Quand cette propriété a la valeur Vrai ($True), indique que les sessions de communication externe (les sessions qui impliquent au moins un utilisateur ne disposant pas d’un compte Active Directory dans votre organisation) seront archivées.

Par défaut, ces deux propriétés ont la valeur Faux, ce qui signifie que ni les sessions de communication interne, ni les sessions de communication externe ne sont archivées. Pour modifier la stratégie globale, vous pouvez utiliser la Skype pour Business Server Management Shell et l’applet de commande Set-CsArchivingPolicy. Cette commande permet d’archiver à la fois les sessions de communication interne et externe :

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

Les stratégies d’archivage peuvent également être gérés à l’aide de la Skype pour le panneau de configuration serveur Business. Dans le Panneau de configuration, cliquez sur **Surveillance et archivage**, puis sur **Stratégie d’archivage**. Pour modifier une stratégie existante, double-cliquez sur la stratégie (par exemple, Global) puis, dans le volet **Stratégie d’archivage**, activez ou désactivez les cases à cocher **Archiver les communications internes** et **Archiver les communications externes** en fonction des besoins. Pour créer une stratégie d’archivage, cliquez sur **Nouveau** , puis sélectionnez **stratégie de Site** ou **stratégie utilisateur**. Si vous créez une nouvelle stratégie d’utilisateur, vous devez accéder aux comptes d’utilisateurs appropriés (sous l’onglet **Utilisateurs**), puis affecter les nouvelles stratégies à ces utilisateurs.

## <a name="step-3-configuring-the-exchangearchivingpolicy-property"></a>Étape 3 : configuration de la propriété ExchangeArchivingPolicy

Si Skype pour Business Server et Exchange Server se trouvent dans des forêts différentes, puis il n’est pas assez pour simplement que Exchange l’archivage dans les paramètres de configuration d’archivage ; qui n’implique pas de messagerie instantanée et les transcriptions de conférence Web soient archivées dans Exchange. Au lieu de cela, vous devez également configurer la propriété ExchangeArchivingPolicy sur chaque serveur de la Skype pertinent pour les comptes d’utilisateur Business Server. Cette propriété peut avoir l’une des valeurs suivantes :

1. **Non initialisée**. Indique que l’archivage être basée sur les paramètres In-Place Hold configurés pour les boîtes aux lettres de l’utilisateur Exchange ; Si le blocage sur Place n’a pas été activé sur boîte aux lettres de l’utilisateur, l’utilisateur aura sa messagerie et Web transcriptions de conférence archivées dans Skype pour Business Server.

2. **UseLyncArchivingPolicy**. Indique que l’utilisateur de messagerie instantanée et des transcriptions de conférence Web doivent être archivées dans Skype pour Business Server plutôt que dans Exchange.

3. **NoArchiving**. Indique que les transcriptions de messagerie instantanée et de conférence web de l’utilisateur ne doivent pas être archivées. Notez que ce paramètre remplace tout Skype pour Business Server affectés à l’utilisateur des stratégies d’archivage.

4. **ArchivingToExchange**. Indique que l’utilisateur de messagerie instantanée et les conférences Web transcriptions doivent être archivées dans Exchange, quel que soit les paramètres In-Place Hold (ou n’ont pas) affectés à la boîte aux lettres de l’utilisateur.

Par exemple, pour configurer un compte d’utilisateur afin que les transcriptions de conférence Web et de messagerie instantanée sont archivées toujours à Exchange, vous pouvez utiliser une commande similaire à celle-ci à partir de la Skype pour Business Server Management Shell :

```
Set-CsUser -Identity "Ken Myer" -ExchangeArchivingPolicy ArchivingToExchange
```

Si vous souhaitez définir la même stratégie d’archivage pour un groupe d’utilisateurs (par exemple, tous les utilisateurs hébergés sur un pool de serveurs d’inscriptions), vous pouvez utiliser une commande similaire à la suivante :

```
Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Set-CsUser -ExchangeArchivingPolicy ArchivingToExchange
```

Notez que vous devez utiliser le Skype pour Business Server Management Shell (et Windows PowerShell) afin de configurer la valeur de la propriété ExchangeArchivingPolicy. Cette propriété n’est pas exposée aux administrateurs dans le Skype pour Business Server.

Si vous voulez afficher la liste de tous les utilisateurs auxquels une stratégie spécifique a été attribuée, vous pouvez utiliser une commande semblable à la suivante, qui renvoie le nom d’affichage Active Directory de tous les utilisateurs dont la propriété ExchangeArchivingPolicy a la valeur Uninitialized :

```
Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -eq "Uninitialized"} | Select-Object DisplayName
```

De même, cette commande renvoie le nom d’affichage des utilisateurs dont la propriété ExchangeArchivingPolicy n’a pas la valeur UseLyncArchivingPolicy :

```
Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -ne "UseLyncArchivingPolicy"} | Select-Object DisplayName
```


