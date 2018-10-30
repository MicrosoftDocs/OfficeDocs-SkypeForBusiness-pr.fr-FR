---
title: Intégration d’une application de collaboration tierce à Lync
TOCTitle: Intégration d’une application de collaboration tierce à Lync
ms:assetid: 00b9312c-b0c8-4f79-8b76-05b2d820e197
ms:mtpsurl: https://technet.microsoft.com/fr-fr/library/Gg398068(v=OCS.15)
ms:contentKeyID: 53095347
ms.date: 05/20/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Intégration d’une application de collaboration tierce à Lync

 

_**Dernière rubrique modifiée :** 2015-03-09_

Vous pouvez intégrer Lync 2013 à n’importe quelle application de collaboration tierce en ligne en ajoutant les informations sur l’application au Registre. Vous pouvez utiliser Lync 2013 pour lancer des sessions de conférence de données hébergées sur un serveur interne, un service basé sur Internet, ou les deux. Vous pouvez démarrer la session de collaboration ou de conférence de données directement à partir de la liste des contacts, ou bien à partir d’une session existante (vocale, messagerie instantanée ou vidéo). Lync 2013 sert uniquement de vecteur pour le démarrage de l’application. Les conversations Lync 2013 existantes restent actives après l’ouverture de la session de collaboration en ligne.

Les sections suivantes décrivent l’intégration de Lync 2013 à des applications de collaboration basées sur Internet ou sur un serveur.

## Intégration d’une application de collaboration basée sur Internet à Lync 2013

En règle générale, les étapes requises pour l’intégration d’une application de collaboration tierce sont les suivantes :

1.  Les informations relatives à l’application sont ajoutées au Registre.

2.  L’organisateur de la session se connecte à Lync 2013 et sélectionne les contacts avec lesquels il souhaite pouvoir partager des données et collaborer. L’organisateur peut également ajouter une conférence de données à une conversation à laquelle il participe déjà.

3.  Lync 2013 lit le Registre, démarre l’application de collaboration et envoie un message SIP personnalisé (appINVITE) aux participants sélectionnés.

4.  Les participants acceptent l’invitation et l’application de collaboration démarre sur l’ordinateur de chaque personne. Lync 2013 utilise le Registre pour déterminer l’application de collaboration à utiliser, puis il démarre cette application en utilisant les paramètres inclus dans le message appINVITE.

Le tableau suivant décrit les entrées de Registre nécessaires pour l’intégration d’une application de collaboration basée sur Internet à Lync 2013. Ces entrées sont placées dans le Registre aux emplacements suivants :

  - HKEY\_LOCAL\_MACHINE\\Software\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\Parameters

### Entrées de Registre pour une application de collaboration basée sur Internet

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
<td><p>Nom de l’application pour les menus de Lync 2013.</p></td>
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
<p>2 = Session à plusieurs. Lync 2013 démarre l’application localement, puis envoie des notifications système aux autres utilisateurs afin de les inviter à démarrer l’application spécifiée sur leur ordinateur.</p></td>
</tr>
<tr class="even">
<td><p>ExensibleMenu</p></td>
<td><p>REG_SZ</p></td>
<td><p>Liste des menus dans lesquels cette commande apparaîtra. Les menus sont séparés par un point-virgule. Les valeurs possibles sont :</p>
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


Le tableau suivant décrit les entrées de Registre pour les paramètres. Ces entrées sont placées à l’emplacement suivant : HKEY\_CURRENT\_USER\\Software\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\Parameters.

### Entrées de Registre pour une application de collaboration basée sur Internet

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
<td><p>Utilisé au format de jeton (<code>%Parm1%</code>) pour ajouter les valeurs spécifiques de l’utilisateur à la clé de Registre OriginatorPath.</p></td>
</tr>
<tr class="even">
<td><p>Param2</p></td>
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


Les paramètres de Registre suivants permettent l’intégration du client de collaboration ADatum à Lync 2013 :

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

## Intégration d’une application de collaboration basée sur un serveur à Lync 2013

Les paramètres nécessaires pour ajouter des commandes permettant de démarrer une application de collaboration basée sur un serveur à partir de Lync 2013 sont similaires à ceux décrits dans la section précédente, Intégration d’une application de collaboration basée sur Internet à Lync 2013. Toutefois, OriginatorPath n’est pas requis et certaines valeurs changent. Les entrées de Registre sont placées à l’emplacement suivant :

  - HKEY\_LOCAL\_MACHINE\\Software\\Microsoft\\Office\\15.0\\Lync\\SessionManager\\Apps\\Parameters

### Entrées de Registre pour une application de collaboration basée sur un serveur

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
<td><p>Valeur = 1. Définit le type de l’application comme protocole. Les autres valeurs possibles ne sont pas applicables dans ce cas. En l’absence d’indication, la valeur par défaut ApplicationType est 0 (exécutable).</p></td>
</tr>
<tr class="odd">
<td><p>Path</p></td>
<td><p>REG_SZ</p></td>
<td><p>Protocole utilisé pour démarrer l’application de collaboration. Pour Live Meeting 2007, la valeur de Path est définie sur <code>meet:%conf-uri%</code>.</p></td>
</tr>
<tr class="even">
<td><p>SessionType</p></td>
<td><p>DWORD</p></td>
<td><p>0 = Session locale. L’application démarre sur l’ordinateur local.</p>
<p>1 = Session à deux personnes (par défaut). Lync 2013 démarre l’application localement, puis envoie une notification système à l’autre utilisateur. Ce dernier clique alors sur la notification pour démarrer l’application spécifiée sur son ordinateur.</p>
<p>2 = Session à plusieurs. Lync 2013 démarre l’application localement, puis envoie des notifications système aux autres utilisateurs afin de les inviter à démarrer l’application spécifiée sur leur ordinateur.</p></td>
</tr>
<tr class="odd">
<td><p>MCUType</p></td>
<td><p>REG_SZ</p></td>
<td><p>DATA = Type du serveur.</p></td>
</tr>
<tr class="even">
<td><p>ExtensibleMenu</p></td>
<td><p>REG_SZ</p></td>
<td><p>Liste des menus dans lesquels cette commande apparaîtra. Les menus sont séparés par un point-virgule. Les valeurs possibles sont :</p>
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


Dans l’exemple suivant des commandes sont ajoutées pour démarrer le client de collaboration ADatum à partir de Lync 2013 :

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

