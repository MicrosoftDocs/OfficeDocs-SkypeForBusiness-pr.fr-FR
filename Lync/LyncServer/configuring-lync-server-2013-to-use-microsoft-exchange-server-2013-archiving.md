---
title: "Conf. de Lync Server 2013 pour ut. l’archivage Microsoft Exchange Server 2013"
TOCTitle: Configuration de Lync Server 2013 pour utiliser l’archivage Exchange Server 2013
ms:assetid: 260346d1-edc8-4a0c-8ad2-6c2401c3c377
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/JJ679896(v=OCS.15)
ms:contentKeyID: 49891270
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Configuration de Microsoft Lync Server 2013 pour utiliser l’archivage Microsoft Exchange Server 2013

 

_**Dernière rubrique modifiée :** 2014-06-24_

Microsoft Lync Server 2013 donne aux administrateurs la possibilité d’archiver la messagerie instantanée et les transcriptions de conférence web dans la boîte aux lettres Microsoft Exchange Server 2013 d’un utilisateur plutôt que dans une base de données SQL Server. Si vous activez cette option, les transcriptions sont écrites dans le dossier Purges de la boîte aux lettres de l’utilisateur. Il s’agit d’un dossier masqué qui se trouve dans le dossier Purges. Même si les utilisateurs finaux ne peuvent pas le voir, il est indexé par le moteur de recherche Exchange et peut être découvert à l’aide de la recherche de boîte aux lettres Exchange et/ou Microsoft SharePoint Server 2013. Étant donné que les informations sont stockées dans le même dossier que celui utilisée par la fonctionnalité d’archive permanente de Exchange (responsable de l’archivage des e-mails et autres communications Exchange), les administrateurs n’ont besoin que d’un seul outil pour rechercher toutes les communications électroniques archivées d’un utilisateur.

> [!IMPORTANT]  
> Vous devez désactiver l’historique des conversations Lync pour en désactiver complètement l’archivage. Pour plus d’informations, reportez-vous aux rubriques suivantes : <a href="lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md">Gestion de l'archivage des communications internes et externes dans Lync Server 2013</a>, <a href="https://docs.microsoft.com/en-us/powershell/module/skype/New-CsClientPolicy">New-CsClientPolicy</a> et <a href="https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsClientPolicy">Set-CsClientPolicy</a>.

Pour archiver les transcriptions dans Exchange 2013, vous devez commencer par configurer l’authentification serveur à serveur entre les deux serveurs. Une fois l’authentification configuré, vous pouvez effectuer les tâches suivantes dans Microsoft Lync Server 2013 (notez que, selon l’installation et la configuration, vous n’aurez peut-être pas besoin d’effectuer toutes ces tâches) :

1.  Activer l’archivage Exchange en modifiant les paramètres de configuration d’archivage Lync Server. Cette étape est nécessaire pour tous les déploiements.

2.  Activer l’archivage des communications internes et/ou externes pour les utilisateurs. Cette étape est nécessaire pour tous les déploiements.

3.  Configurer la propriété ExchangeArchivingPolicy pour chaque utilisateur. Cette étape est uniquement requise si Lync Server et Exchange sont situés dans des forêts différentes.

## Étape 1 : Activation de l’archivage Exchange

L’archivage dans Lync Server est principalement géré à l’aide des paramètres de configuration de l’archivage. Quand vous installez Lync Server 2013, une seule collection globale de ces paramètres vous est automatiquement octroyée. (Les administrateurs peuvent éventuellement créer de nouvelles collections de paramètres d’archivage sur l’étendue du site.) Par défaut, l’archivage n’est pas activé dans les paramètres globaux et l’archivage Exchange n’est pas non plus activé dans ces paramètres. Pour pouvoir utiliser l’archivage Exchange, les administrateurs doivent configurer à la fois la propriété EnableArchiving et la propriété EnableExchangeArchiving dans ces paramètres de configuration. La propriété EnableArchiving peut avoir l’une des trois valeurs suivantes :

  - **Aucun** . L’archivage est désactivé. Il s’agit de la valeur par défaut. Si EnableArchiving a la valeur Aucun, rien ne sera archivé dans votre base de données d’archivage Lync Server ou dans Exchange 2013.

  - **ImOnly** . Seules les transcriptions de message instantané sont archivées. Si l’archivage Exchange est activé, ces transcriptions seront archivées dans Exchange 2013. Si l’archivage Exchange est désactivé, ces transcriptions seront archivées dans Lync Server.

  - **ImAndWebConf** . À la fois les transcriptions de message instantanée et celles de conférence web sont archivées. Si l’archivage Exchange est activé, ces transcriptions seront archivées dans Exchange 2013. Si l’archivage Exchange est désactivé, ces transcriptions seront archivées dans Lync Server.

La propriété EnableExchangeArchiving est une valeur booléenne : attribuez à EnableExchangeArchiving la valeur Vrai ($True) pour activer l’archivage Exchange ou attribuez-lui la valeur Faux ($False) pour désactiver l’archivage Exchange. Par exemple, la commande suivante active l’archivage des transcriptions de message instantané et active également l’archivage Exchange :

    Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $True

Pour désactiver l’archivage Exchange, utilisez une commande semblable à la suivante, qui active l’archivage de la messagerie instantanée mais désactive l’archivage dans Exchange (autrement dit, les transcriptions seront archivées dans Lync Server) :

    Set-CsArchivingConfiguration -Identity "global" -EnableArchiving ImOnly -EnableExchangeArchiving $False

> [!NOTE]  
> Si la propriété EnableArchiving a la valeur Aucun, Lync Server n’archivera ni les transcriptions de message instantanée, ni les transcriptions de conférence web. Dans ce cas, le serveur ignorera simplement la valeur configurée pour EnableExchangeArchiving.

L’archivage Exchange peut également être activé (ou désactivé) à l’aide du Panneau de configuration Lync Server. Pour ce faire, procédez de la manière suivante :

1.  Dans le Panneau de configuration, cliquez sur **Surveillance et archivage** , puis sur **Configuration de l’archivage** .

2.  Sous l’onglet **Configuration de l’archivage** , double-cliquez sur la collection de paramètres d’archivage à modifier (par exemple, la collection **Global** ).

3.  Dans le volet **Paramètre d’archivage** , cliquez sur la liste déroulante **Paramètre d’archivage** , puis sélectionnez **Archiver les sessions de messagerie instantanée** (pour archiver uniquement les sessions de messagerie instantanée) ou **Archiver les sessions de messagerie instantanée et de conférence web** (pour archiver les sessions de messagerie instantanée et les sessions de conférence web).

4.  Après avoir choisi les éléments à archiver, activez la case à cocher **Intégration Exchange Server** pour activer l’archivage Exchange. Pour désactiver l’archivage Exchange, désactivez cette case à cocher.

> [!NOTE]  
> La case à cocher <strong>Intégration Exchange Server</strong> n’est pas disponible si <strong>Paramètre d’archivage</strong> est défini sur <strong>Désactiver l’archivage</strong> . Vous devez d’abord activer l’archivage, puis activer l’archivage Exchange.

Si Lync Server 2013 et Exchange 2013 sont situés dans la même forêt, l’archivage des utilisateurs individuels (ou au moins des utilisateurs disposant de comptes de messagerie sur Exchange 2013) est géré à l’aide des stratégies d’archive permanente Exchange. Si des utilisateurs sont hébergés sur une version précédente de Exchange, l’archivage de ces utilisateurs sera géré à l’aide des stratégies d’archivage de Lync Server. Notez que seules les transcriptions Lync des utilisateurs dotés de comptes Exchange 2013 peuvent être archivées sur Exchange.

Si Lync Server 2013 et Exchange 2013 sont situés dans des forêts différentes, l’archivage des utilisateurs individuels est géré en configurant la propriété ExchangeArchivingPolicy de chaque compte d’utilisateur individuel. Pour plus d’informations, reportez-vous à l’étape 3.

## Étape 2 : Activation de l’archivage des communications internes et/ou externes

Après avoir activé l’archivage (et l’archivage Exchange) vous devez modifier les stratégies d’archivage appropriées afin d’avoir la certitude que les sessions utilisateur seront réellement archivées. Notez qu’il ne suffit pas d’activer simplement l’archivage (étape 1) pour que Lync Server commence à archiver les transcriptions de messagerie instantanée et de conférence web. Vous devez utiliser les stratégies d’archivage pour activer l’archivage interne et/ou externe. Quand vous installez Lync Server 2013, vous installez également une stratégie d’archivage global unique contenant deux propriétés :

  - **ArchiveInternal** . Quand cette propriété a la valeur Vrai ($True), indique que les sessions de communication interne (celles qui impliquent uniquement des utilisateurs disposant d’un compte Active Directory dans votre organisation) seront archivées.

  - **ArchiveExternal** . Quand cette propriété a la valeur Vrai ($True), indique que les sessions de communication externe (les sessions qui impliquent au moins un utilisateur ne disposant pas d’un compte Active Directory dans votre organisation) seront archivées.

Par défaut, ces deux propriétés ont la valeur Faux, ce qui signifie que ni les sessions de communication interne, ni les sessions de communication externe ne sont archivées. Pour modifier la stratégie globale, vous pouvez utiliser Lync Server Management Shell et l’applet de commande Set-CsArchivingPolicy. Cette commande permet d’archiver à la fois les sessions de communication interne et externe :

    Set-CsArchivingPolicy -Identity "global" -ArchiveInternal $True -ArchiveExternal $True

Vous pouvez également utiliser New-CsArchivingPolicy pour créer une stratégie au niveau du site ou par utilisateur. Par exemple, la commande suivante crée une stratégie d’archivage par utilisateur appelée RedmondArchivingPolicy :

    New-CsArchivingPolicy -Identity "RedmondArchivingPolicy" -ArchiveInternal $True -ArchiveExternal $True

Si vous créez une stratégie par utilisateur, vous devrez affecter cette stratégie aux utilisateurs appropriés. Par exemple :

    Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName  "RedmondArchivingPolicy"

Les stratégies d’archivage peuvent également être gérées à l’aide du Panneau de configuration Lync Server. Dans le Panneau de configuration, cliquez sur **Surveillance et archivage** , puis sur **Stratégie d’archivage** . Pour modifier une stratégie existante, double-cliquez sur la stratégie (par exemple, Global) puis, dans le volet **Stratégie d’archivage** , activez ou désactivez les cases à cocher **Archiver les communications internes** et **Archiver les communications externes** en fonction des besoins. Pour créer une stratégie d’archivage, cliquez sur **Nouveau** , puis sélectionnez **Stratégie du site** ou **Stratégie de l’utilisateur** . Si vous créez une nouvelle stratégie d’utilisateur, vous devez accéder aux comptes d’utilisateurs appropriés (sous l’onglet **Utilisateurs** ), puis affecter à ces utilisateurs les nouvelles stratégies.

## Étape 3 : Configuration de la propriété ExchangeArchivingPolicy

Si Lync Server 2013 et Exchange 2013 se trouvent dans des forêts différentes, la simple activation de l’archivage Exchange dans les paramètres de configuration de l’archivage ne suffit pas ; cette action n’entraînera pas l’archivage des transcriptions de messagerie instantanée et de conférence web dans Exchange. Vous devez également configurer la propriété ExchangeArchivingPolicy sur chaque compte d’utilisateur Lync Server approprié. Cette propriété peut avoir l’une des valeurs suivantes :

1.  Uninitialized. Indique que l’archivage sera basé sur les paramètres d’archivage permanent configurés pour la boîte aux lettres Exchange de l’utilisateur; si l’archivage permanent n’y a pas été activé ; les transcriptions de messagerie instantanée et de conférence web de l’utilisateur seront archivées dans Lync Server.

2.  **UseLyncArchivingPolicy** . Indique que les transcriptions de messagerie instantanée et de conférence web de l’utilisateur doivent être archivées dans Lync Server et non dans Exchange.

3.  **NoArchiving** . Indique que les transcriptions de messagerie instantanée et de conférence web de l’utilisateur ne doivent pas être archivées. Notez que ce paramètre remplace toutes les stratégies d’archivage Lync Server affectées à l’utilisateur.

4.  **ArchivingToExchange** . Indique que les transcriptions de messagerie instantanée et de conférence web de l’utilisateur doivent être archivées dans Exchange indépendamment du paramètre d’archive permanente ayant (ou non) été affecté à la boîte aux lettres de l’utilisateur.

Par exemple, pour configurer un compte d’utilisateur de manière à toujours archiver les transcriptions de messagerie instantanée et de conférence web dans Exchange, vous pouvez utiliser une commande semblable à la suivante à partir de Lync Server Management Shell :

    Set-CsUser -Identity "Ken Myer" -ExchangeArchivingPolicy ArchivingToExchange

Si vous souhaitez définir la même stratégie d’archivage pour un groupe d’utilisateurs (par exemple, tous les utilisateurs hébergés sur un pool de serveurs d’inscriptions), vous pouvez utiliser une commande similaire à la suivante :

    Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.litwareinc.com"} | Set-CsUser -ExchangeArchivingPolicy ArchivingToExchange

Notez que vous devez utiliser Lync Server Management Shell (et Windows PowerShell) pour configurer la valeur de la propriété ExchangeArchivingPolicy. Cette propriété n’est pas exposée aux administrateurs dans le Panneau de configuration Lync Server.

Si vous voulez afficher la liste de tous les utilisateurs auxquels une stratégie spécifique a été attribuée, vous pouvez utiliser une commande semblable à la suivante, qui renvoie le nom d’affichage Active Directory de tous les utilisateurs dont la propriété ExchangeArchivingPolicy a la valeur Uninitialized :

    Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -eq "Uninitialized"} | Select-Object DisplayName

De même, cette commande renvoie le nom d’affichage des utilisateurs dont la propriété ExchangeArchivingPolicy n’a pas la valeur UseLyncArchivingPolicy :

    Get-CsUser | Where-Object {$_.ExchangeArchivingPolicy -ne "UseLyncArchivingPolicy"} | Select-Object DisplayName

