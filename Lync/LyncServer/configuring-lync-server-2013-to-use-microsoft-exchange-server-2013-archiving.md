---
title: Configuration de Lync Server 2013 pour l’utilisation de l’archivage Microsoft Exchange Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Lync Server 2013 to use Exchange Server 2013 archiving
ms:assetid: 260346d1-edc8-4a0c-8ad2-6c2401c3c377
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ679896(v=OCS.15)
ms:contentKeyID: 49557731
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b3f8ab22ed23adbce2d6cbd6ccbf1f378476ff00
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34838844"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-microsoft-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving"></a>Configuration de Microsoft Lync Server 2013 pour l’utilisation de l’archivage Microsoft Exchange Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2014-06-24_

Microsoft Lync Server 2013 donne aux administrateurs la possibilité d’archiver les transcriptions de la messagerie instantanée et des conférences Web dans la boîte aux lettres de 2013 l’utilisateur au lieu d’une base de données SQL Server. Si vous activez cette option, les transcriptions sont écrites dans le dossier Purges de la boîte aux lettres de l’utilisateur. Il s’agit d’un dossier masqué qui se trouve dans le dossier Purges. Même si ce dossier n’est pas visible par les utilisateurs finaux, le dossier est indexé par le moteur de recherche Exchange et peut être détecté à l’aide de la recherche de boîte aux lettres Exchange et/ou de Microsoft SharePoint Server 2013. Étant donné que les informations sont stockées dans le même dossier que celui utilisé par la fonctionnalité de conservation inaltérable Exchange (responsable de l’archivage des messages électroniques et d’autres communications Exchange), les administrateurs peuvent utiliser un seul outil pour rechercher toutes les communications électroniques archivées pour a Il.

<div>


> [!IMPORTANT]  
> Pour désactiver complètement l’archivage des conversations Lync, vous devez également désactiver l’historique des conversations Lync. Pour plus d’informations, consultez les rubriques suivantes: <A href="lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md">gestion de l’archivage des communications internes et externes dans Lync Server 2013</A>, <A href="https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy">New-CsClientPolicy</A>et <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy">Set-CsClientPolicy</A>.



</div>

Afin d’archiver les transcriptions dans Exchange 2013, vous devez commencer par configurer l’authentification de serveur à serveur entre les deux serveurs. Une fois l’authentification de serveur à serveur mise en place, vous pouvez effectuer les tâches suivantes dans Microsoft Lync Server 2013 (Notez que, en fonction de votre installation et de la configuration, il est possible que vous n’ayez pas à effectuer toutes les tâches suivantes):

1.  Activez l’archivage Exchange en modifiant vos paramètres de configuration de l’archivage de Lync Server. Cette étape est nécessaire pour tous les déploiements.

2.  Activez l’archivage des communications internes et/ou externes pour les utilisateurs. Cette étape est nécessaire pour tous les déploiements.

3.  Configurez la propriété ExchangeArchivingPolicy pour chaque utilisateur. Cette étape est uniquement requise dans Lync Server et Exchange se trouve dans différentes forêts.

<div>

## <a name="step-1-enabling-exchange-archiving"></a>Étape 1: activation de l’archivage Exchange

L’archivage dans Lync Server est essentiellement géré à l’aide des paramètres de configuration de l’archivage. Lorsque vous installez Lync Server 2013, une collection globale unique de ces paramètres vous est attribuée automatiquement. (Les administrateurs peuvent éventuellement créer de nouvelles collections de paramètres d’archivage à l’étendue du site.) Par défaut, l’archivage n’est pas activé dans les paramètres globaux et l’archivage Exchange est activé dans ces paramètres. Pour pouvoir utiliser les administrateurs d’archivage Exchange, vous devez configurer les propriétés EnableArchiving et EnableExchangeArchiving dans les paramètres de configuration suivants. La propriété EnableArchiving peut avoir l’une des trois valeurs suivantes :

  - **Aucun**. L’archivage est désactivé. Il s’agit de la valeur par défaut. Si EnableArchiving est défini sur None, rien ne sera archivé dans votre base de données d’archivage Lync Server ou dans Exchange 2013.

  - **ImOnly**. Seules les transcriptions de message instantané sont archivées. Si l’archivage Exchange est activé, ces transcriptions seront archivées dans Exchange 2013. Dans le cas contraire, les transcriptions seront archivées sur Lync Server.

  - **ImAndWebConf**. À la fois les transcriptions de messages instantanés et celles de conférences web sont archivées. Si l’archivage Exchange est activé, ces transcriptions seront archivées dans Exchange 2013. Dans le cas contraire, les transcriptions seront archivées sur Lync Server.

La propriété EnableExchangeArchiving est une valeur booléenne: définissez EnableExchangeArchiving sur true ($True) pour activer l’archivage Exchange ou définissez EnableExchangeArchiving sur false ($False) pour désactiver l’archivage Exchange. Par exemple, la commande suivante permet d’archiver des transcriptions de la messagerie instantanée et d’archiver Exchange:

    Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $True

Pour désactiver l’archivage Exchange, utilisez une commande similaire à ce qui suit, qui permet l’archivage des messages instantanés, mais désactive l’archivage dans Exchange (en d’autres termes, les transcriptions sont archivées sur Lync Server):

    Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $False

<div>


> [!NOTE]  
> Si la propriété EnableArchiving est définie sur None, Lync Server n’archivera pas de messages instantanés et de transcriptions de conférences Web. Dans ce cas, le serveur ignorera simplement la valeur configurée pour EnableExchangeArchiving.



</div>

L’archivage Exchange peut également être activé (ou désactivé) à l’aide du panneau de configuration de Lync Server. Pour ce faire, procédez de la manière suivante :

1.  Dans le Panneau de configuration, cliquez sur **Surveillance et archivage**, puis sur **Configuration de l’archivage**.

2.  Sous l’onglet **Configuration de l’archivage**, double-cliquez sur la collection de paramètres d’archivage à modifier (par exemple, la collection **Global**).

3.  Dans le volet **Paramètre d’archivage**, cliquez sur la liste déroulante **Paramètre d’archivage**, puis sélectionnez **Archiver les sessions de messagerie instantanée** (pour archiver uniquement les sessions de messagerie instantanée) ou **Archiver les sessions de messagerie instantanée et de conférence web** (pour archiver les sessions de messagerie instantanée et les sessions de conférence web).

4.  Après avoir sélectionné les éléments à archiver, activez la case à cocher **intégration Exchange Server** pour activer l’archivage Exchange. Pour désactiver l’archivage Exchange, désactivez cette case à cocher.

<div>


> [!NOTE]  
> La case à cocher <STRONG>Intégration Exchange Server</STRONG> n’est pas disponible si <STRONG>Paramètre d’archivage</STRONG> est défini sur <STRONG>Désactiver l’archivage</STRONG>. Activez d’abord l’archivage, puis activez l’archivage Exchange.



</div>

Si Lync Server 2013 et Exchange 2013 se trouvent dans la même forêt, l’archivage pour les utilisateurs individuels (ou au moins pour les utilisateurs disposant de comptes de messagerie sur Exchange 2013) est géré à l’aide de stratégies de conservation sur place Exchange. Si vous avez des utilisateurs hébergés sur une version antérieure d’Exchange, l’archivage de ces utilisateurs est géré à l’aide de stratégies d’archivage de Lync Server. Notez que seuls les utilisateurs dotés de comptes sur Exchange 2013 peuvent archiver leurs transcriptions Lync dans Exchange.

Si Lync Server 2013 et Exchange 2013 se trouvent dans différentes forêts, l’archivage pour des utilisateurs individuels est géré en configurant la propriété ExchangeArchivingPolicy pour chaque compte d’utilisateur individuel. Pour plus d’informations, reportez-vous à l’étape 3.

</div>

<div>

## <a name="step-2-enabling-the-archiving-of-internal-andor-external-communications"></a>Étape 2 : activation de l’archivage des communications internes et/ou externes

Une fois que vous avez activé l’archivage (et l’archivage Exchange), vous devez modifier les stratégies d’archivage appropriées pour vous assurer que les sessions utilisateur sont bien archivées. Notez que l’activation de l’archivage (étape 1) n’entraîne pas l’archivage de Lync Server lors de l’archivage de messages instantanés et de transcriptions de conférences Web. Vous devez utiliser les stratégies d’archivage pour activer l’archivage interne et/ou externe. Lorsque vous installez Lync Server 2013, vous devez également installer une seule stratégie d’archivage globale qui contient deux propriétés:

  - **ArchiveInternal**. Quand cette propriété a la valeur Vrai ($True), indique que les sessions de communication interne (celles qui impliquent uniquement des utilisateurs disposant d’un compte Active Directory dans votre organisation) seront archivées.

  - **ArchiveExternal**. Quand cette propriété a la valeur Vrai ($True), indique que les sessions de communication externe (les sessions qui impliquent au moins un utilisateur ne disposant pas d’un compte Active Directory dans votre organisation) seront archivées.

Par défaut, ces deux propriétés ont la valeur Faux, ce qui signifie que ni les sessions de communication interne, ni les sessions de communication externe ne sont archivées. Pour modifier la stratégie globale, vous pouvez utiliser Lync Server Management Shell et l’applet de passe Set-CsArchivingPolicy. Cette commande permet d’archiver à la fois les sessions de communication interne et externe :

    Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True -ArchiveExternal $True

Vous pouvez également utiliser New-CsArchivingPolicy pour créer une stratégie au niveau du site ou par utilisateur. Par exemple, la commande suivante crée une stratégie d’archivage par utilisateur appelée RedmondArchivingPolicy :

    New-CsArchivingPolicy -Identity "RedmondArchivingPolicy" -ArchiveInternal $True -ArchiveExternal $True

Si vous créez une stratégie par utilisateur, vous devrez affecter cette stratégie aux utilisateurs appropriés. Par exemple :

    Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName  "RedmondArchivingPolicy"

Les stratégies d’archivage peuvent également être gérées à l’aide du panneau de configuration de Lync Server. Dans le Panneau de configuration, cliquez sur **Surveillance et archivage**, puis sur **Stratégie d’archivage**. Pour modifier une stratégie existante, double-cliquez sur la stratégie (par exemple, Global) puis, dans le volet **Stratégie d’archivage**, activez ou désactivez les cases à cocher **Archiver les communications internes** et **Archiver les communications externes** en fonction des besoins. Pour créer une nouvelle stratégie d’archivage, cliquez sur **nouveau** , puis sélectionnez **stratégie du site** ou stratégie de l' **utilisateur**. Si vous créez une nouvelle stratégie d’utilisateur, vous devez accéder aux comptes d’utilisateurs appropriés (sous l’onglet **Utilisateurs**), puis affecter les nouvelles stratégies à ces utilisateurs.

</div>

<div>

## <a name="step-3-configuring-the-exchangearchivingpolicy-property"></a>Étape 3 : configuration de la propriété ExchangeArchivingPolicy

Si Lync Server 2013 et Exchange 2013 se trouvent dans différentes forêts, il n’y a pas assez d’activation de l’archivage Exchange dans les paramètres de configuration de l’archivage; les transcriptions de messagerie instantanée et de conférence Web ne sont pas archivées dans Exchange. À la place, vous devez également configurer la propriété ExchangeArchivingPolicy sur chacun des comptes d’utilisateurs de Lync Server pertinents. Cette propriété peut avoir l’une des valeurs suivantes :

1.  Non initialisée. Indique que l’archivage sera basé sur les paramètres de conservation inaltérable configurés pour la boîte aux lettres Exchange de l’utilisateur. Si la conservation inaltérable n’a pas été activée sur la boîte aux lettres de l’utilisateur, l’utilisateur aura ses transcriptions de messagerie et de conférence Web archivées dans Lync Server.

2.  **UseLyncArchivingPolicy**. Indique que les transcriptions de messagerie instantanée et de conférence Web de l’utilisateur doivent être archivées dans Lync Server plutôt que dans Exchange.

3.  **NoArchiving**. Indique que les transcriptions de messagerie instantanée et de conférence web de l’utilisateur ne doivent pas être archivées. Notez que ce paramètre remplace toutes les stratégies d’archivage de Lync Server attribuées à l’utilisateur.

4.  **ArchivingToExchange**. Indique que les transcriptions de la messagerie instantanée et des conférences Web de l’utilisateur doivent être archivées sur Exchange, quels que soient les paramètres de conservation inaltérable qui ont (ou non) été attribués à la boîte aux lettres de l’utilisateur.

Par exemple, pour configurer un compte d’utilisateur afin que les transcriptions de la messagerie instantanée et des conférences Web soient toujours archivées sur Exchange, vous pouvez utiliser une commande similaire à celle de Lync Server Management Shell:

    Set-CsUser -Identity "Ken Myer" -ExchangeArchivingPolicy ArchivingToExchange

Si vous souhaitez définir la même stratégie d’archivage pour un groupe d’utilisateurs (par exemple, tous les utilisateurs hébergés sur un pool de serveurs d’inscriptions), vous pouvez utiliser une commande similaire à la suivante :

    Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Set-CsUser -ExchangeArchivingPolicy ArchivingToExchange

Notez que vous devez utiliser Lync Server Management Shell (et Windows PowerShell) pour configurer la valeur de la propriété ExchangeArchivingPolicy. Cette propriété n’est pas exposée aux administrateurs dans le panneau de configuration de Lync Server.

Si vous voulez afficher la liste de tous les utilisateurs auxquels une stratégie spécifique a été attribuée, vous pouvez utiliser une commande semblable à la suivante, qui renvoie le nom d’affichage Active Directory de tous les utilisateurs dont la propriété ExchangeArchivingPolicy a la valeur Uninitialized :

    Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -eq "Uninitialized"} | Select-Object DisplayName

De même, cette commande renvoie le nom d’affichage des utilisateurs dont la propriété ExchangeArchivingPolicy n’a pas la valeur UseLyncArchivingPolicy :

    Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -ne "UseLyncArchivingPolicy"} | Select-Object DisplayName

</div>

</div>

<span> </span>

</div>

</div>

</div>

