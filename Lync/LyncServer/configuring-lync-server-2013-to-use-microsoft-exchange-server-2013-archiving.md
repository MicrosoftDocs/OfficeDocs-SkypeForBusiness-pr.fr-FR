---
title: Configuration de Lync Server 2013 pour utiliser l’archivage Microsoft Exchange Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Lync Server 2013 to use Exchange Server 2013 archiving
ms:assetid: 260346d1-edc8-4a0c-8ad2-6c2401c3c377
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ679896(v=OCS.15)
ms:contentKeyID: 49557731
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 85a9a1d035994c143336abc83312fb56f67b927d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42180627"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-microsoft-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving"></a>Configuration de Microsoft Lync Server 2013 pour utiliser l’archivage Microsoft Exchange Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2014-06-24_

Microsoft Lync Server 2013 offre aux administrateurs la possibilité d’archiver les transcriptions de messagerie instantanée et de conférence Web dans la boîte aux lettres de Microsoft Exchange Server 2013 d’un utilisateur plutôt que dans une base de données SQL Server. Si vous activez cette option, les transcriptions sont écrites dans le dossier Purges de la boîte aux lettres de l’utilisateur. Il s’agit d’un dossier masqué qui se trouve dans le dossier Purges. Bien que ce dossier ne soit pas visible par les utilisateurs finaux, le dossier est indexé par le moteur de recherche Exchange et peut être découvert à l’aide de la recherche de boîte aux lettres Exchange et/ou de Microsoft SharePoint Server 2013. Étant donné que les informations sont stockées dans le même dossier que celui utilisé par la fonctionnalité de conservation inaltérable d’Exchange (responsable de l’archivage des courriers électroniques et autres communications Exchange), les administrateurs peuvent utiliser un seul outil pour rechercher toutes les communications électroniques archivées pour un Guide.

<div>


> [!IMPORTANT]  
> Pour désactiver complètement l’archivage de conversation Lync, vous devez également désactiver l’historique des conversations Lync. Pour plus d’informations, consultez les rubriques suivantes : <A href="lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md">Managing the Archiving of Internal and External Communications in Lync Server 2013</A>, <A href="https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy">New-CsClientPolicy</A>et <A href="https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy">Set-CsClientPolicy</A>.



</div>

Pour archiver les transcriptions dans Exchange 2013, vous devez commencer par configurer l’authentification de serveur à serveur entre les deux serveurs. Une fois l’authentification de serveur à serveur mise en place, vous pouvez effectuer les tâches suivantes dans Microsoft Lync Server 2013 (Notez que, en fonction de votre configuration et de votre configuration, il se peut que vous n’ayez pas besoin d’effectuer toutes ces tâches) :

1.  Activez l’archivage Exchange en modifiant vos paramètres de configuration de l’archivage Lync Server. Cette étape est nécessaire pour tous les déploiements.

2.  Activer l’archivage des communications internes et/ou externes pour les utilisateurs. Cette étape est nécessaire pour tous les déploiements.

3.  Configurer la propriété ExchangeArchivingPolicy pour chaque utilisateur. Cette étape n’est requise que dans Lync Server et Exchange se situent dans des forêts différentes.

<div>

## <a name="step-1-enabling-exchange-archiving"></a>Étape 1 : activation de l’archivage Exchange

L’archivage dans Lync Server est principalement géré à l’aide des paramètres de configuration de l’archivage. Lors de l’installation de Lync Server 2013, une seule collection globale de ces paramètres vous est automatiquement attribuée. (Les administrateurs peuvent éventuellement créer de nouvelles collections de paramètres d’archivage au niveau de l’étendue site.) Par défaut, l’archivage n’est pas activé dans les paramètres globaux et l’archivage Exchange est activé dans ces paramètres. Pour pouvoir utiliser l’archivage Exchange, les administrateurs doivent configurer les propriétés EnableArchiving et EnableExchangeArchiving dans ces paramètres de configuration. La propriété EnableArchiving peut avoir l’une des trois valeurs suivantes :

  - **Aucun**. L’archivage est désactivé. Il s’agit de la valeur par défaut. Si EnableArchiving est défini sur None, rien ne sera archivé dans votre base de données d’archivage Lync Server ou dans Exchange 2013.

  - **** Impropres. Seules les transcriptions de message instantané sont archivées. Si l’archivage Exchange est activé, ces transcriptions seront archivées dans Exchange 2013. Si l’archivage Exchange est désactivé, ces transcriptions seront archivées dans Lync Server.

  - **ImAndWebConf**. À la fois les transcriptions de message instantanée et celles de conférence web sont archivées. Si l’archivage Exchange est activé, ces transcriptions seront archivées dans Exchange 2013. Si l’archivage Exchange est désactivé, ces transcriptions seront archivées dans Lync Server.

La propriété EnableExchangeArchiving est une valeur booléenne : définissez EnableExchangeArchiving sur true ($True) pour activer l’archivage Exchange ou définissez EnableExchangeArchiving sur false ($False) pour désactiver l’archivage Exchange. Par exemple, cette commande permet l’archivage des transcriptions de messagerie instantanée et active l’archivage Exchange :

    Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $True

Pour désactiver l’archivage Exchange, utilisez une commande semblable à la suivante, qui active l’archivage de la messagerie instantanée mais désactive l’archivage dans Exchange (en d’autres termes, les transcriptions seront archivées dans Lync Server) :

    Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $False

<div>


> [!NOTE]  
> Si la propriété EnableArchiving est définie sur None, Lync Server n’archive pas du tout les transcriptions de messagerie instantanée et de conférence Web. Dans ce cas, le serveur ignorera simplement la valeur configurée pour EnableExchangeArchiving.



</div>

L’archivage Exchange peut également être activé (ou désactivé) à l’aide du panneau de configuration Lync Server. Pour ce faire, procédez de la manière suivante :

1.  Dans le Panneau de configuration, cliquez sur **Surveillance et archivage**, puis sur **Configuration de l’archivage**.

2.  Sous l’onglet **Configuration de l’archivage**, double-cliquez sur la collection de paramètres d’archivage à modifier (par exemple, la collection **Global**).

3.  Dans le volet **Paramètre d’archivage**, cliquez sur la liste déroulante **Paramètre d’archivage**, puis sélectionnez **Archiver les sessions de messagerie instantanée** (pour archiver uniquement les sessions de messagerie instantanée) ou **Archiver les sessions de messagerie instantanée et de conférence web** (pour archiver les sessions de messagerie instantanée et les sessions de conférence web).

4.  Après avoir choisi les éléments à archiver, activez la case à cocher **intégration Exchange Server** pour activer l’archivage Exchange. Pour désactiver l’archivage Exchange, désactivez cette case à cocher.

<div>


> [!NOTE]  
> La case à cocher <STRONG>Intégration Exchange Server</STRONG> n’est pas disponible si <STRONG>Paramètre d’archivage</STRONG> est défini sur <STRONG>Désactiver l’archivage</STRONG>. Vous devez d’abord activer l’archivage, puis activer l’archivage Exchange.



</div>

Si Lync Server 2013 et Exchange 2013 se trouvent dans la même forêt, l’archivage pour des utilisateurs individuels (ou au moins pour les utilisateurs disposant de comptes de messagerie sur Exchange 2013) est géré à l’aide de stratégies de conservation inaltérable Exchange. Si certains de vos utilisateurs sont hébergés sur une version antérieure d’Exchange, l’archivage de ces utilisateurs sera géré à l’aide de stratégies d’archivage Lync Server. Notez que seuls les utilisateurs disposant de comptes sur Exchange 2013 peuvent faire en sorte que leurs transcriptions Lync soient archivées dans Exchange.

Si Lync Server 2013 et Exchange 2013 sont situés dans des forêts différentes, l’archivage pour des utilisateurs individuels est géré en configurant la propriété ExchangeArchivingPolicy pour chaque compte d’utilisateur individuel. Pour plus d’informations, voir l’étape 3.

</div>

<div>

## <a name="step-2-enabling-the-archiving-of-internal-andor-external-communications"></a>Étape 2 : Activation de l’archivage des communications internes et/ou externes

Une fois que vous avez activé l’archivage (et l’archivage Exchange), vous devez modifier les stratégies d’archivage appropriées afin de vous assurer que les sessions utilisateur sont effectivement archivées. Notez que l’activation de l’archivage (étape 1) ne permet pas à Lync Server de commencer l’archivage des transcriptions de messagerie instantanée et de conférence Web. Vous devez utiliser les stratégies d’archivage pour activer l’archivage interne et/ou externe. Lorsque vous installez Lync Server 2013, vous installez également une stratégie d’archivage globale unique qui contient deux propriétés :

  - **ArchiveInternal**. Quand cette propriété a la valeur Vrai ($True), indique que les sessions de communication interne (celles qui impliquent uniquement des utilisateurs disposant d’un compte Active Directory dans votre organisation) seront archivées.

  - **ArchiveExternal**. Quand cette propriété a la valeur Vrai ($True), indique que les sessions de communication externe (les sessions qui impliquent au moins un utilisateur ne disposant pas d’un compte Active Directory dans votre organisation) seront archivées.

Par défaut, ces deux propriétés ont la valeur Faux, ce qui signifie que ni les sessions de communication interne, ni les sessions de communication externe ne sont archivées. Pour modifier la stratégie globale, vous pouvez utiliser Lync Server Management Shell et la cmdlet Set-applet csarchivingpolicy. Cette commande permet d’archiver à la fois les sessions de communication interne et externe :

    Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True -ArchiveExternal $True

Vous pouvez également utiliser New-CsArchivingPolicy pour créer une stratégie au niveau du site ou par utilisateur. Par exemple, la commande suivante crée une stratégie d’archivage par utilisateur appelée RedmondArchivingPolicy :

    New-CsArchivingPolicy -Identity "RedmondArchivingPolicy" -ArchiveInternal $True -ArchiveExternal $True

Si vous créez une stratégie par utilisateur, vous devrez affecter cette stratégie aux utilisateurs appropriés. Par exemple :

    Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName  "RedmondArchivingPolicy"

Les stratégies d’archivage peuvent également être gérées à l’aide du panneau de configuration Lync Server. Dans le Panneau de configuration, cliquez sur **Surveillance et archivage**, puis sur **Stratégie d’archivage**. Pour modifier une stratégie existante, double-cliquez sur la stratégie (par exemple, Global) puis, dans le volet **Stratégie d’archivage**, activez ou désactivez les cases à cocher **Archiver les communications internes** et **Archiver les communications externes** en fonction des besoins. Pour créer une nouvelle stratégie d’archivage, cliquez sur **nouveau** , puis sélectionnez **stratégie de site** ou **stratégie utilisateur**. Si vous créez une nouvelle stratégie d’utilisateur, vous devez accéder aux comptes d’utilisateurs appropriés (sous l’onglet **Utilisateurs**), puis affecter à ces utilisateurs les nouvelles stratégies.

</div>

<div>

## <a name="step-3-configuring-the-exchangearchivingpolicy-property"></a>Étape 3 : Configuration de la propriété ExchangeArchivingPolicy

Si Lync Server 2013 et Exchange 2013 sont situés dans des forêts différentes, il ne suffit pas d’activer simplement l’archivage Exchange dans les paramètres de configuration de l’archivage. Cela n’entraîne pas l’archivage de la messagerie instantanée et des transcriptions de conférence Web dans Exchange. Au lieu de cela, vous devez également configurer la propriété ExchangeArchivingPolicy sur chacun des comptes d’utilisateur Lync Server pertinents. Cette propriété peut avoir l’une des valeurs suivantes :

1.  Non initialisée. Indique que l’archivage sera basé sur les paramètres de conservation inaltérable configurés pour la boîte aux lettres Exchange de l’utilisateur ; Si la conservation inaltérable n’a pas été activée sur la boîte aux lettres de l’utilisateur, les transcriptions de messagerie et de conférence Web de l’utilisateur sont archivées dans Lync Server.

2.  **Valeur uselyncarchivingpolicy**. Indique que les transcriptions de messagerie instantanée et de conférence Web de l’utilisateur doivent être archivées dans Lync Server et non dans Exchange.

3.  **Noarchivage**. Indique que les transcriptions de messagerie instantanée et de conférence web de l’utilisateur ne doivent pas être archivées. Notez que ce paramètre remplace toutes les stratégies d’archivage Lync Server affectées à l’utilisateur.

4.  **ArchivingToExchange**. Indique que les transcriptions de messagerie instantanée et de conférence Web de l’utilisateur doivent être archivées dans Exchange, quels que soient les paramètres de conservation inaltérable ayant (ou non) été affectés à la boîte aux lettres de l’utilisateur.

Par exemple, pour configurer un compte d’utilisateur de manière à toujours archiver les transcriptions de messagerie instantanée et de conférence Web dans Exchange, vous pouvez utiliser une commande semblable à celle-ci à partir de Lync Server Management Shell :

    Set-CsUser -Identity "Ken Myer" -ExchangeArchivingPolicy ArchivingToExchange

Si vous souhaitez définir la même stratégie d’archivage pour un groupe d’utilisateurs (par exemple, tous les utilisateurs hébergés sur un pool de serveurs d’inscriptions), vous pouvez utiliser une commande similaire à la suivante :

    Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Set-CsUser -ExchangeArchivingPolicy ArchivingToExchange

Notez que vous devez utiliser Lync Server Management Shell (et Windows PowerShell) pour configurer la valeur de la propriété ExchangeArchivingPolicy. Cette propriété n’est pas exposée aux administrateurs dans le panneau de configuration Lync Server.

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

