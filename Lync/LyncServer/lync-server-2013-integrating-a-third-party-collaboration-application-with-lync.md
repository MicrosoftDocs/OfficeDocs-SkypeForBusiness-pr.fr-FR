---
title: Intégration d’une application de collaboration tierce à Lync
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Integrating a third-party collaboration application with Lync
ms:assetid: 00b9312c-b0c8-4f79-8b76-05b2d820e197
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398068(v=OCS.15)
ms:contentKeyID: 48183224
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7bbe3f6439b357253ae49a5c1609319b6a91bfb
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534754"
---
# <a name="integrating-a-third-party-collaboration-application-with-lync-server-2013"></a>Intégration d’une application de collaboration tierce avec Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-02-20_

Vous pouvez intégrer Lync 2013 avec n’importe quelle application de collaboration en ligne tierce en ajoutant des informations sur l’application au registre. Vous pouvez utiliser Lync 2013 pour démarrer des sessions de conférence de données hébergées sur un serveur interne, un service basé sur Internet ou les deux. Vous pouvez démarrer la session de collaboration ou de conférence de données directement à partir de la liste des contacts, ou bien à partir d’une session existante (vocale, messagerie instantanée ou vidéo). Lync 2013 agit uniquement en tant que véhicule pour le démarrage de l’application. Toute conversation Lync 2013 existante reste active après le début de la session de collaboration en ligne.

Les sections suivantes décrivent comment intégrer Lync 2013 avec des applications de collaboration basées sur Internet et sur le serveur.

<div>

## <a name="integrating-an-internet-based-collaboration-application-with-lync-2013"></a>Intégration d’une application de collaboration Internet-Based avec Lync 2013

En règle générale, les étapes requises pour l’intégration d’une application de collaboration tierce sont les suivantes :

1.  Les informations relatives à l’application sont ajoutées au Registre.

2.  L’organisateur se connecte à Lync 2013 et sélectionne les contacts pour le partage et la collaboration de données. L’organisateur peut également ajouter une conférence de données à une conversation à laquelle il participe déjà.

3.  Lync 2013 lit le registre, démarre l’application de collaboration, puis envoie un message SIP personnalisé, un appINVITE, aux participants sélectionnés.

4.  Les participants acceptent l’invitation et l’application de collaboration démarre sur l’ordinateur de chaque personne. Lync 2013 utilise le registre pour déterminer l’application de collaboration à utiliser, puis démarre cette application en utilisant les paramètres inclus dans le message appINVITE.

Le tableau suivant décrit les entrées de Registre requises pour intégrer une application de collaboration basée sur Internet à Lync 2013. Ces entrées sont placées dans le registre à l’emplacement suivant :

  - HKEY \_ \_ Software local \\ Software \\ Microsoft \\ Office \\ 15,0 \\ Lync \\ sessionmanager \\ apps \\ Parameters

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
<td><p>Chemin d’accès de l’icône (BMP ou PNG de 16 pixels sur 16).</p></td>
</tr>
<tr class="odd">
<td><p>Path</p></td>
<td><p>REG_SZ</p></td>
<td><p>Chemin à utiliser pour le démarrage de l’application de collaboration en ligne sur l’ordinateur du participant.</p></td>
</tr>
<tr class="even">
<td><p>OriginatorPath</p></td>
<td><p>REG_SZ</p></td>
<td><p>Chemin à utiliser pour le démarrage de l’application de collaboration en ligne par l’organisateur. Ce chemin peut contenir un ou plusieurs paramètres personnalisés définis dans la sous-clé Parameters. Par exemple, <code>https://meetserv.adatum.com/cc/%param1%/join?id=%param2%&amp;role=present&amp;pw=%param3%</code></p></td>
</tr>
<tr class="odd">
<td><p>SessionType</p></td>
<td><p>DWORD</p></td>
<td><p>0 = Session locale. L’application démarre sur l’ordinateur local.</p>
<p>1 = Session à deux personnes (par défaut). Lync 2013 démarre l’application localement, puis envoie une notification système à l’autre utilisateur. Ce dernier clique alors sur la notification pour démarrer l’application spécifiée sur son ordinateur.</p>
<p>2 = Session à plusieurs. Lync 2013 démarre l’application localement, puis envoie des notifications système aux autres utilisateurs, en les invitant à démarrer l’application spécifiée sur leur propre ordinateur.</p></td>
</tr>
<tr class="even">
<td><p>ExensibleMenu</p></td>
<td><p>REG_SZ</p></td>
<td><p>Liste des menus dans lesquels cette commande apparaîtra. Les menus sont séparés par un point-virgule. Les valeurs possibles sont les suivantes :</p>
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


Le tableau suivant décrit les entrées de Registre pour les paramètres. Ces entrées sont placées dans HKEY \_ Current \_ User \\ Software \\ Microsoft \\ Office \\ 15,0 \\ Lync \\ sessionmanager \\ apps \\ Parameters.

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
<td><p>Param1</p></td>
<td><p>REG_SZ</p></td>
<td><p>Utilisé dans le format sous forme de jeton ( <code>%Parm1%</code> ) pour ajouter des valeurs spécifiques à l’utilisateur à la clé de Registre OriginatorPath.</p></td>
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


Les exemples de paramètres de registre suivants intègrent le client de collaboration adatum avec Lync 2013 :

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

## <a name="integrating-a-server-based-collaboration-application-with-lync-2013"></a>Intégration d’une application de collaboration Server-Based avec Lync 2013

Les paramètres permettant d’ajouter des commandes de démarrage d’une application de collaboration basée sur un serveur à partir de Lync 2013 sont similaires à ceux décrits dans la section précédente, intégrant une application de collaboration Internet-Based avec Lync 2013. Toutefois, OriginatorPath n’est pas requis et certaines valeurs changent. Les entrées de Registre sont placées à l’emplacement suivant :

  - HKEY \_ \_ Software local \\ Software \\ Microsoft \\ Office \\ 15,0 \\ Lync \\ sessionmanager \\ apps \\ Parameters

### <a name="registry-entries-for-a-server-based-collaboration-application"></a>Entrées de Registre pour une application de collaboration basée sur un serveur

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
<td><p>DWORD</p></td>
<td><p>Valeur = 1. Définit le type de l’application comme protocole. Les autres valeurs possibles ne sont pas applicables dans ce cas. S’il n’est pas présent, ApplicationType est défini sur 0 (exécutable).</p></td>
</tr>
<tr class="odd">
<td><p>Path</p></td>
<td><p>REG_SZ</p></td>
<td><p>Protocole utilisé pour démarrer l’application de collaboration. Pour Live Meeting 2007, la valeur de path est définie sur <code>meet:%conf-uri%</code> .</p></td>
</tr>
<tr class="even">
<td><p>SessionType</p></td>
<td><p>DWORD</p></td>
<td><p>0 = Session locale. L’application démarre sur l’ordinateur local.</p>
<p>1 = Session à deux personnes (par défaut). Lync 2013 démarre l’application localement, puis envoie une notification système à l’autre utilisateur. Ce dernier clique alors sur la notification pour démarrer l’application spécifiée sur son ordinateur.</p>
<p>2 = Session à plusieurs. Lync 2013 démarre l’application localement, puis envoie des notifications système aux autres utilisateurs, en les invitant à démarrer l’application spécifiée sur leur ordinateur.</p></td>
</tr>
<tr class="odd">
<td><p>MCUType</p></td>
<td><p>REG_SZ</p></td>
<td><p>DATA = Type du serveur.</p></td>
</tr>
<tr class="even">
<td><p>ExtensibleMenu</p></td>
<td><p>REG_SZ</p></td>
<td><p>Liste des menus dans lesquels cette commande apparaît, séparés par des points-virgules. Les valeurs possibles sont les suivantes :</p>
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


L’exemple suivant ajoute des commandes pour démarrer le client de collaboration adatum à partir de Lync 2013 :

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

