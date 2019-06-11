---
title: Intégration d’une application de collaboration tierce avec Lync
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Integrating a third-party collaboration application with Lync
ms:assetid: 00b9312c-b0c8-4f79-8b76-05b2d820e197
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398068(v=OCS.15)
ms:contentKeyID: 48183224
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0b56fabbc1bd341e3ba2c5fe535d147c09335b7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830983"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="integrating-a-third-party-collaboration-application-with-lync-server-2013"></a>Intégration d’une application de collaboration tierce avec Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique:** 2013-02-20_

Vous pouvez intégrer Lync 2013 à toute application de collaboration en ligne tierce en ajoutant des informations sur l’application au registre. Vous pouvez utiliser Lync 2013 pour démarrer des sessions de conférence de données hébergées sur un serveur interne, un service basé sur Internet, ou les deux. La session de collaboration ou de conférence de données peut être démarrée à partir de la liste de contacts ou à partir d’une conversation par messagerie instantanée, audio ou vidéo. Lync 2013 agit uniquement comme véhicule pour le démarrage de l’application. Toutes les conversations Lync 2013 existantes restent actives après le démarrage de la session de collaboration en ligne.

Les sections suivantes décrivent comment intégrer Lync 2013 aux applications de collaboration basées sur Internet et celles basées sur le serveur.

<div>

## <a name="integrating-an-internet-based-collaboration-application-with-lync-2013"></a>Intégration d’une application de collaboration basée sur Internet avec Lync 2013

En règle générale, les étapes nécessaires à l’intégration d’une application de collaboration tierce sont les suivantes:

1.  Des informations sur l’application sont ajoutées au registre.

2.  L’organisateur se connecte à Lync 2013 et sélectionne les contacts pour le partage et la collaboration de données. Il est possible que l’organisateur se trouve déjà dans une conversation et décide d’ajouter des conférences de données.

3.  Lync 2013 lit le registre, démarre l’application de collaboration, puis envoie un message SIP personnalisé (appINVITE) aux participants sélectionnés.

4.  Les participants acceptent l’invitation et l’application de collaboration est démarrée sur l’ordinateur de chaque personne. Lync 2013 utilise le registre pour déterminer quelle application de collaboration utiliser, puis démarre cette application en utilisant les paramètres inclus dans le message appINVITE.

Le tableau suivant décrit les entrées de Registre requises pour intégrer une application de collaboration basée sur Internet avec Lync 2013. Ces entrées sont placées dans le registre à l’emplacement suivant:

  - HKEY\_logiciel\_\\de\\l’ordinateur\\local\\Microsoft\\Office\\15,0\\les\\paramètres des applications Lync sessionmanager

### <a name="registry-entries-for-an-internet-based-collaboration-application"></a>Entrées de Registre pour une application de collaboration basée sur Internet

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Nom</th>
<th>Type</th>
<th>Données</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Nom</p></td>
<td><p>REG_SZ</p></td>
<td><p>Nom de l’application pour les menus Lync 2013.</p></td>
</tr>
<tr class="even">
<td><p>SmallIcon</p></td>
<td><p>REG_SZ</p></td>
<td><p>Chemin d’accès à l’icône 16 pixels x 16 pixels, BMP ou PNG.</p></td>
</tr>
<tr class="odd">
<td><p> Path</p></td>
<td><p>REG_SZ</p></td>
<td><p>Chemin du participant pour le démarrage de l’application de collaboration en ligne.</p></td>
</tr>
<tr class="even">
<td><p>OriginatorPath</p></td>
<td><p>REG_SZ</p></td>
<td><p>Chemin d’accès de l’organisateur du démarrage de l’application de collaboration en ligne. Ce chemin peut contenir un ou plusieurs paramètres personnalisés tels qu’ils sont définis dans la sous-clé paramètres. Par exemple,<code>https://meetserv.adatum.com/cc/%param1%/join?id=%param2%&amp;role=present&amp;pw=%param3%</code></p></td>
</tr>
<tr class="odd">
<td><p>SessionType</p></td>
<td><p>INSÉRÉ</p></td>
<td><p>0 = session locale. L’application est démarrée sur l’ordinateur local.</p>
<p>1 = session à deux parties (par défaut). Lync 2013 démarre l’application localement, puis envoie une notification système à l’autre utilisateur. L’autre utilisateur clique sur la notification et démarre l’application spécifiée sur son ordinateur.</p>
<p>2 = session multipartie. Lync 2013 démarre l’application localement, puis envoie des notifications système aux autres utilisateurs, en leur demandant de démarrer l’application spécifiée sur leur ordinateur.</p></td>
</tr>
<tr class="even">
<td><p>ExensibleMenu</p></td>
<td><p>REG_SZ</p></td>
<td><p>Liste des menus dans lesquels cette commande s’affiche, séparés par des points-virgules. Valeurs possibles :</p>
<ul>
<li><p>MainWindowActions</p></li>
<li><p>MainWindowRightClick</p></li>
<li><p>ConversationWindowActions</p></li>
<li><p>ConversationWindowButton</p></li>
<li><p>ConversationWindowRightClick</p></li>
</ul>
<p>Si ExtensibleMenu n’est pas défini, les valeurs par défaut de MainWindowRightClick et ConversationWindowActions sont utilisées.</p></td>
</tr>
</tbody>
</table>


Le tableau suivant décrit les entrées de Registre correspondant aux paramètres. Ces entrées sont placées sur\_HKEY\_logiciel\\\\de l'\\utilisateur\\actuel\\Microsoft\\Office\\15,0\\les paramètres des applications Lync sessionmanager.

### <a name="registry-entries-for-an-internet-based-collaboration-application"></a>Entrées de Registre pour une application de collaboration basée sur Internet

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Nom</th>
<th>Type</th>
<th>Données</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>TypeDonnées</p></td>
<td><p>REG_SZ</p></td>
<td><p>Permet d’ajouter des valeurs spécifiques<code>%Parm1%</code>à l’utilisateur dans la clé de Registre OriginatorPath.</p></td>
</tr>
<tr class="even">
<td><p>TypeDonnées</p></td>
<td><p>REG_SZ</p></td>
<td><p>Voir Param1.</p></td>
</tr>
<tr class="odd">
<td><p>Param3</p></td>
<td><p>REG_SZ</p></td>
<td><p>Voir Param1.</p></td>
</tr>
</tbody>
</table>


Les exemples de paramètres de registre suivants intègrent le client de collaboration adatum avec Lync 2013:

    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager]
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager\Apps]
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager\Apps\{C3F6E17A-855F-44a0-B90D-C0B92D38E5F1}]
    "Path"="https://meetingservice.adatum.com/cc/%param1%/meet/%param2%"
    "OriginatorPath"="https://meetserv.adatum.com/cc/%param1%/join?id=%param2%&role=present&pw=%param3%"
    "SessionType"=dword:00000002
    "ApplicationType"=dword:00000001
    "LiveServerIntegration"=dword:00000000
    "Name"="ADatum Online Collaboration Service"
    "Extensiblemenu"="MainWindowActions;MainWindowRightClick;ConversationWindowActions;ConversationWindowRightClick"
    
    [HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\SessionManager]
    [HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\SessionManager\Apps]
    [HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\SessionManager\Apps\Parameters]
    [HKEY_CURRENT_USER\Software\Microsoft\Office\15.0\Lync\SessionManager\Apps\Parameters\{C3F6E17A-855F-44a0-B90D-C0B92D38E5F1}]
    "Param1"="meetserv"
    "Param2"="admin"
    "Param3"="abcdefg123"

</div>

<div>

## <a name="integrating-a-server-based-collaboration-application-with-lync-2013"></a>Intégration d’une application de collaboration basée sur le serveur avec Lync 2013

Les paramètres permettant d’ajouter des commandes pour le démarrage d’une application de collaboration serveur à partir de Lync 2013 sont similaires à ceux décrits dans la section précédente, intégration d’une application de collaboration basée sur Internet avec Lync 2013. Toutefois, le OriginatorPath n’est pas obligatoire et certaines valeurs sont modifiées. Les entrées de Registre sont placées à l’emplacement suivant:

  - HKEY\_logiciel\_\\de\\l’ordinateur\\local\\Microsoft\\Office\\15,0\\les\\paramètres des applications Lync sessionmanager

### <a name="registry-entries-for-a-server-based-collaboration-application"></a>Entrées de Registre pour une application de collaboration basée sur le serveur

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Nom</th>
<th>Type</th>
<th>Données</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Nom</p></td>
<td><p>REG_SZ</p></td>
<td><p>Nom de l’application tel qu’il apparaît dans le menu.</p></td>
</tr>
<tr class="even">
<td><p>ApplicationType</p></td>
<td><p>INSÉRÉ</p></td>
<td><p>Valeur = 1. Définit le type d’application sur protocole. Les autres valeurs possibles ne s’appliquent pas dans le cas présent. Si ce n’est pas le cas, ApplicationType est défini sur 0 (exécutable).</p></td>
</tr>
<tr class="odd">
<td><p> Path</p></td>
<td><p>REG_SZ</p></td>
<td><p>Protocole utilisé pour démarrer l’application de collaboration. Pour Live Meeting 2007, la valeur de path est définie sur <code>meet:%conf-uri%</code>.</p></td>
</tr>
<tr class="even">
<td><p>SessionType</p></td>
<td><p>INSÉRÉ</p></td>
<td><p>0 = session locale. L’application est démarrée sur l’ordinateur local.</p>
<p>1 = session à deux parties (par défaut). Lync 2013 démarre l’application localement, puis envoie une notification système à l’autre utilisateur. L’autre utilisateur clique sur la notification et démarre l’application spécifiée sur son ordinateur.</p>
<p>2 = session multipartie. Lync 2013 démarre l’application localement, puis envoie des notifications système aux autres utilisateurs, en leur demandant de démarrer l’application spécifiée sur leur ordinateur.</p></td>
</tr>
<tr class="odd">
<td><p>MCUType</p></td>
<td><p>REG_SZ</p></td>
<td><p>DATA = le type du serveur.</p></td>
</tr>
<tr class="even">
<td><p>ExtensibleMenu</p></td>
<td><p>REG_SZ</p></td>
<td><p>Liste des menus dans lesquels cette commande s’affiche, en les séparant par un point-virgule. Valeurs possibles :</p>
<ul>
<li><p>MainWindowActions</p></li>
<li><p>MainWindowRightClick</p></li>
<li><p>ConversationWindowActions</p></li>
<li><p>ConversationWindowButton</p></li>
<li><p>ConversationWindowRightClick</p></li>
</ul>
<p>Si ExtensibleMenu n’est pas défini, les valeurs par défaut de MainWindowRightClick et ConversationWindowActions sont utilisées.</p></td>
</tr>
</tbody>
</table>


L’exemple suivant ajoute des commandes pour démarrer le client de collaboration adatum à partir de Lync 2013:

    Windows Registry Editor Version 5.00
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager]
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager\Apps]
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Office\15.0\Lync\SessionManager\Apps\{27877e66-615c-4582-ab88-0cb2ca05d951}]
    "Path"="meet:%conf-uri%"
    "SessionType"=dword:00000002
    "LiveServerIntegration"=dword:00000001
    "ApplicationType"=dword:00000001
    "Name"="ADatum Collaboration Client"
    "MCUType"="Data"
    "Extensiblemenu"="MainWindowActions;MainWindowRightClick;ConversationWindowActions;ConversationWindowRightClick"

</div>

</div>

<span> </span>

</div>

</div>

</div>

