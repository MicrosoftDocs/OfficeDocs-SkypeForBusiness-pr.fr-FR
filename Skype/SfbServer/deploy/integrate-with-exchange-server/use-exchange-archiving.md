---
title: Configurer Skype Entreprise Server pour utiliser l’archivage Exchange Server’archivage
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/15/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 260346d1-edc8-4a0c-8ad2-6c2401c3c377
description: 'Résumé : Configurez les transcriptions de messagerie instantanée pour Exchange Server 2016 ou Exchange Server 2013 et Skype Entreprise Server.'
ms.openlocfilehash: f264b347660df032b67f06ddf605e99ba97a32b2
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58603061"
---
# <a name="configure-skype-for-business-server-to-use-exchange-server-archiving"></a>Configurer Skype Entreprise Server pour utiliser l’archivage Exchange Server’archivage

**Résumé :** Configurez les transcriptions de messagerie instantanée Exchange Server 2016 ou Exchange Server 2013 et Skype Entreprise Server.

Skype Entreprise Server offre aux administrateurs la possibilité d’archiver les transcriptions de messagerie instantanée et de conférence Web dans la boîte aux lettres Exchange Server 2016 ou Exchange Server 2013 d’un utilisateur plutôt qu’une base de données SQL Server. Si vous activez cette option, les transcriptions sont écrites dans le dossier Purges de la boîte aux lettres de l’utilisateur. Il s’agit d’un dossier masqué qui se trouve dans le dossier Purges. Bien que ce dossier ne soit pas visible par les utilisateurs finaux, il est indexé par le moteur de recherche Exchange et peut être découvert à l’aide de la recherche de boîtes aux lettres Exchange et/ou Microsoft SharePoint Server 2013. Étant donné que les informations sont stockées dans le même dossier que celui utilisé par la fonctionnalité de mise en attente Exchange In-Place (responsable de l’archivage des messages électroniques et autres communications Exchange), les administrateurs peuvent utiliser un seul outil pour rechercher toutes les communications électroniques archivées pour un utilisateur.

> [!IMPORTANT]
> Pour désactiver complètement l’archivage des conversations, vous devez également désactiver l’historique des conversations. Pour plus d’informations, voir les rubriques suivantes : Gestion de l’archivage des communications internes et externes dans [Skype Entreprise Server](/previous-versions/office/lync-server-2013/lync-server-2013-managing-the-archiving-of-internal-and-external-communications), [New-CsClientPolicy](/powershell/module/skype/new-csclientpolicy?view=skype-ps)et [Set-CsClientPolicy](/powershell/module/skype/set-csclientpolicy?view=skype-ps).

Pour archiver les transcriptions Exchange Server vous devez commencer par configurer l’authentification de serveur à serveur entre Skype Entreprise Server et Exchange Server. Une fois l’authentification de serveur à serveur en place, vous pouvez effectuer les tâches suivantes dans Skype Entreprise Server (notez que, en fonction de votre configuration et de votre configuration, vous n’avez peut-être pas besoin d’effectuer toutes ces tâches) :

1. Activez Exchange’archivage en modifiant vos paramètres de configuration Skype Entreprise Server’archivage. Cette étape est nécessaire pour tous les déploiements.

2. Activer l’archivage des communications internes et/ou externes pour les utilisateurs. Cette étape est nécessaire pour tous les déploiements.

3. Configurer la propriété ExchangeArchivingPolicy pour chaque utilisateur. Cette étape est requise uniquement si les Skype Entreprise Server et Exchange Server sont situés dans des forêts différentes.

## <a name="step-1-enabling-exchange-archiving"></a>Étape 1 : Activation de l’archivage Exchange’archivage

L’archivage dans Skype Entreprise Server est principalement géré à l’aide des paramètres de configuration de l’archivage. Lorsque vous installez Skype Entreprise Server vous êtes automatiquement attribué une seule collection globale de ces paramètres. (Les administrateurs peuvent éventuellement créer de nouvelles collections de paramètres d’archivage au niveau de l’étendue Site.) Par défaut, l’archivage n’est pas activé dans les paramètres globaux, Exchange’archivage n’est pas activé dans ces paramètres. Pour utiliser l’archivage Exchange, les administrateurs doivent configurer les propriétés EnableArchiving et EnableExchangeArchiving dans ces paramètres de configuration. La propriété EnableArchiving peut avoir l’une des trois valeurs suivantes :

- **Aucun**. L’archivage est désactivé. Il s’agit de la valeur par défaut. Si EnableArchiving est définie sur Aucun, rien ne sera archivé dans votre base de données d’archivage Skype Entreprise Server ou dans Exchange Server.

- **ImOnly**. Seules les transcriptions de message instantané sont archivées. Si Exchange’archivage est activé, ces transcriptions seront archivées dans Exchange Server. Si Exchange’archivage est désactivé, ces transcriptions seront archivées dans Skype Entreprise Server.

- **ImAndWebConf**. À la fois les transcriptions de message instantanée et celles de conférence web sont archivées. Si Exchange’archivage est activé, ces transcriptions seront archivées dans Exchange Server. Si Exchange’archivage est désactivé, ces transcriptions seront archivées dans Skype Entreprise Server.

La propriété EnableExchangeArchiving est une valeur booléque : définissez EnableExchangeArchiving sur True ($True) pour activer l’archivage Exchange ou définissez EnableExchangeArchiving sur False ($False) pour désactiver l’archivage Exchange. Par exemple, cette commande active l’archivage des transcriptions de messagerie instantanée et active également Exchange’archivage :

```powershell
Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $True
```

Pour désactiver l’archivage Exchange, utilisez une commande semblable à la suivante, qui active l’archivage de la messagerie instantanée, mais désactive l’archivage sur Exchange (en d’autres termes, les transcriptions sont archivées dans Skype Entreprise Server) :

```powershell
Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $False
```

> [!NOTE]
> Si la propriété EnableArchiving est définie sur Aucun, Skype Entreprise Server archivera pas du tout les transcriptions de messagerie instantanée et de conférence Web. Dans ce cas, le serveur ignorera simplement la valeur configurée pour EnableExchangeArchiving.

Exchange’archivage peut également être activé (ou désactivé) à l’aide de la Skype Entreprise Server. Pour ce faire, procédez de la manière suivante :

1. Dans le Panneau de configuration, cliquez sur **Surveillance et archivage**, puis sur **Configuration de l’archivage**.

2. Sous l’onglet **Configuration de l’archivage**, double-cliquez sur la collection de paramètres d’archivage à modifier (par exemple, la collection **Global**).

3. Dans le volet **Paramètre d’archivage**, cliquez sur la liste déroulante **Paramètre d’archivage**, puis sélectionnez **Archiver les sessions de messagerie instantanée** (pour archiver uniquement les sessions de messagerie instantanée) ou **Archiver les sessions de messagerie instantanée et de conférence web** (pour archiver les sessions de messagerie instantanée et les sessions de conférence web).

4. Après avoir choisi les éléments à archiver, activez la case à cocher **Exchange Server’intégration** pour activer Exchange’archivage. Pour désactiver Exchange’archivage, désactivez cette case à cocher.

> [!NOTE]
> La case à cocher **Intégration Exchange Server** n’est pas disponible si **Paramètre d’archivage** est défini sur **Désactiver l’archivage**. Vous devez d’abord activer l’archivage, puis Exchange’archivage.

Si Skype Entreprise Server et Exchange Server sont situés dans la même forêt, l’archivage pour des utilisateurs individuels (ou au moins pour les utilisateurs ayant des comptes de messagerie sur Exchange Server) est géré à l’aide de stratégies de Exchange In-Place. Si vous avez des utilisateurs qui sont homed sur une version antérieure de Exchange l’archivage de ces utilisateurs sera géré à l’aide de Skype Entreprise Server d’archivage. Notez que seuls les utilisateurs ayant des comptes sur Exchange Server 2016 ou Exchange Server 2013 peuvent archiver leurs transcriptions de Skype Entreprise dans Exchange.

Si Skype Entreprise Server et Exchange Server sont situés dans des forêts différentes, l’archivage des utilisateurs individuels est géré en configurant la propriété ExchangeArchivingPolicy pour chaque compte d’utilisateur individuel. Pour plus d’informations, voir l’étape 3.

## <a name="step-2-enabling-the-archiving-of-internal-andor-external-communications"></a>Étape 2 : Activation de l’archivage des communications internes et/ou externes

Après avoir activé l’archivage (et l’archivage Exchange), vous devez modifier les stratégies d’archivage appropriées pour vous assurer que les sessions utilisateur sont réellement archivées. Notez que la simple activation de l’archivage (étape 1) n’entraîne pas le Skype Entreprise Server l’archivage des transcriptions de messagerie instantanée et de conférence Web. Vous devez utiliser les stratégies d’archivage pour activer l’archivage interne et/ou externe. Lorsque vous installez Skype Entreprise Server vous installez également une stratégie d’archivage globale unique qui contient deux propriétés :

- **ArchiveInternal**. Quand cette propriété a la valeur Vrai ($True), indique que les sessions de communication interne (celles qui impliquent uniquement des utilisateurs disposant d’un compte Active Directory dans votre organisation) seront archivées.

- **ArchiveExternal**. Quand cette propriété a la valeur Vrai ($True), indique que les sessions de communication externe (les sessions qui impliquent au moins un utilisateur ne disposant pas d’un compte Active Directory dans votre organisation) seront archivées.

Par défaut, ces deux propriétés ont la valeur Faux, ce qui signifie que ni les sessions de communication interne, ni les sessions de communication externe ne sont archivées. Pour modifier la stratégie globale, vous pouvez utiliser l’environnement de Skype Entreprise Server Management Shell et la cmdlet Set-CsArchivingPolicy de gestion. Cette commande permet d’archiver à la fois les sessions de communication interne et externe :

```powershell
Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True -ArchiveExternal $True
```

Vous pouvez également utiliser New-CsArchivingPolicy pour créer une stratégie au niveau du site ou par utilisateur. Par exemple, la commande suivante crée une stratégie d’archivage par utilisateur appelée RedmondArchivingPolicy :

```powershell
New-CsArchivingPolicy -Identity "RedmondArchivingPolicy" -ArchiveInternal $True -ArchiveExternal $True
```

Si vous créez une stratégie par utilisateur, vous devrez affecter cette stratégie aux utilisateurs appropriés. Par exemple :

```powershell
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName  "RedmondArchivingPolicy"
```

Les stratégies d’archivage peuvent également être gérées à l’aide Skype Entreprise Server panneau de bord. Dans le Panneau de configuration, cliquez sur **Surveillance et archivage**, puis sur **Stratégie d’archivage**. Pour modifier une stratégie existante, double-cliquez sur la stratégie (par exemple, Global) puis, dans le volet **Stratégie d’archivage**, activez ou désactivez les cases à cocher **Archiver les communications internes** et **Archiver les communications externes** en fonction des besoins. Pour créer une stratégie d’archivage, cliquez sur Nouveau, puis sélectionnez Stratégie **de site** ou **Stratégie utilisateur.**  Si vous créez une nouvelle stratégie d’utilisateur, vous devez accéder aux comptes d’utilisateurs appropriés (sous l’onglet **Utilisateurs**), puis affecter à ces utilisateurs les nouvelles stratégies.

## <a name="step-3-configuring-the-exchangearchivingpolicy-property"></a>Étape 3 : Configuration de la propriété ExchangeArchivingPolicy

Si Skype Entreprise Server et Exchange Server sont situés dans des forêts différentes, il ne suffit pas d’activer simplement l’archivage Exchange dans les paramètres de configuration de l’archivage . cela n’entraîne pas l’archivage des transcriptions de messagerie instantanée et de conférence Web dans Exchange. Au lieu de cela, vous devez également configurer la propriété ExchangeArchivingPolicy sur chacun des comptes d’Skype Entreprise Server appropriés. Cette propriété peut avoir l’une des valeurs suivantes :

1. **Nonnitialisé**. Indique que l’archivage sera basé sur les paramètres de In-Place de l’utilisateur configurés pour la boîte aux lettres Exchange’utilisateur ; Si In-Place la boîte aux lettres de l’utilisateur n’a pas été activée, ses transcriptions de messagerie et de conférence Web seront archivées dans Skype Entreprise Server.

2. **UseLyncArchivingPolicy**. Indique que les transcriptions de messagerie instantanée et de conférence Web de l’utilisateur doivent être archivées dans Skype Entreprise Server plutôt que dans Exchange.

3. **NoArchiving**. Indique que les transcriptions de messagerie instantanée et de conférence web de l’utilisateur ne doivent pas être archivées. Notez que ce paramètre remplace toutes les stratégies Skype Entreprise Server’archivage attribuées à l’utilisateur.

4. **ArchivingToExchange**. Indique que les transcriptions de messagerie instantanée et de conférence Web de l’utilisateur doivent être archivées dans Exchange quels que soient les paramètres de mise en attente In-Place qui ont (ou n’ont pas) été affectés à la boîte aux lettres de l’utilisateur.

Par exemple, pour configurer un compte d’utilisateur afin que les transcriptions de messagerie instantanée et de conférence Web soient toujours archivées dans Exchange vous pouvez utiliser une commande semblable à celle-ci à partir de l’Skype Entreprise Server Management Shell :

```powershell
Set-CsUser -Identity "Ken Myer" -ExchangeArchivingPolicy ArchivingToExchange
```

Si vous souhaitez définir la même stratégie d’archivage pour un groupe d’utilisateurs (par exemple, tous les utilisateurs hébergés sur un pool de serveurs d’inscriptions), vous pouvez utiliser une commande similaire à la suivante :

```powershell
Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Set-CsUser -ExchangeArchivingPolicy ArchivingToExchange
```

Notez que vous devez utiliser Skype Entreprise Server Management Shell (et Windows PowerShell) pour configurer la valeur de la propriété ExchangeArchivingPolicy. Cette propriété n’est pas exposée aux administrateurs dans le Skype Entreprise Server.

Si vous voulez afficher la liste de tous les utilisateurs auxquels une stratégie spécifique a été attribuée, vous pouvez utiliser une commande semblable à la suivante, qui renvoie le nom d’affichage Active Directory de tous les utilisateurs dont la propriété ExchangeArchivingPolicy a la valeur Uninitialized :

```powershell
Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -eq "Uninitialized"} | Select-Object DisplayName
```

De même, cette commande renvoie le nom d’affichage des utilisateurs dont la propriété ExchangeArchivingPolicy n’a pas la valeur UseLyncArchivingPolicy :

```powershell
Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -ne "UseLyncArchivingPolicy"} | Select-Object DisplayName
```