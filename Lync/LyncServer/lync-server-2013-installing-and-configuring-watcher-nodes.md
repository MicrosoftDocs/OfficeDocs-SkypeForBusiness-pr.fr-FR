---
title: 'Lync Server 2013 : installation et configuration des nœuds observateur'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Installing and configuring watcher nodes
ms:assetid: 61f6deea-e3ef-4468-9be8-a65705815ebb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204943(v=OCS.15)
ms:contentKeyID: 48184284
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 19a4fad29b29dbec895a2c327ce2ddc054b8202b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029525"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="installing-and-configuring-watcher-nodes-in-lync-server-2013"></a>Installation et configuration des nœuds observateur dans Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Dernière modification de la rubrique :** 2013-11-07_

Les *nœuds observateurs* sont des ordinateurs qui exécutent régulièrement des transactions synthétiques Lync Server. Les *transactions synthétiques* sont des applets de commande Windows PowerShell qui vérifient que les scénarios d’utilisateur final clés, tels que la possibilité de se connecter au système ou la possibilité d’échanger des messages instantanés, fonctionnent comme prévu. Pour Lync Server 2013, System Center Operations Manager peut exécuter les transactions synthétiques indiquées dans le tableau suivant. Trois types différents de transactions synthétiques sont répertoriés dans le tableau :

  - **Valeur par défaut**. Il s’agit des transactions synthétiques qu’un nœud observateur exécute par défaut. Lorsque vous créez un nœud observateur, vous avez la possibilité de spécifier les transactions synthétiques qui seront exécutées par ce nœud. (Il s’agit de l’objectif du paramètre tests utilisé par la cmdlet **New-applet cswatchernodeconfiguration** .) Si vous n’utilisez pas le paramètre tests lors de la création du nœud observateur, il exécutera automatiquement toutes les transactions synthétiques par défaut et n’exécutera aucune des transactions synthétiques non par défaut. Cela signifie, par exemple, que le nœud observateur est configuré pour exécuter le test Test-CsAddressBookService, mais qu’il n’est pas configuré pour exécuter le test Test-CsExumConnectivity.

  - **Non défini par défaut**. Comme leur nom l’indique, les transactions synthétiques non par défaut sont des tests qui ne sont pas exécutés par défaut par l’observateur. Cependant, le nœud observateur peut être autorisé à exécuter n’importe laquelle des transactions synthétiques non par défaut. Vous pouvez effectuer cette opération lorsque vous créez le nœud observateur (à l’aide de l’applet de commande **New-CsWatcherNodeConfiguration**) ou à tout moment par la suite. Bon nombre des transactions synthétiques non par défaut nécessitent des étapes de configuration supplémentaires. Pour plus d’informations, reportez-vous à [instructions de configuration spéciales pour les transactions synthétiques dans Lync Server 2013](lync-server-2013-special-setup-instructions-for-synthetic-transactions.md).

  - **Étendue**. Les tests étendus sont un type spécial de transaction synthétique non par défaut. Contrairement à d’autres transactions synthétiques, les tests étendus peuvent être exécutés plusieurs fois à chaque passage. Cela peut s’avérer utile pour vérifier des comportements tels que plusieurs itinéraires des communications vocales PSTN pour un pool. Vous pouvez configurer ceci en ajoutant simplement plusieurs instances d’un test étendu à un nœud observateur.

Pour plus d’informations sur le processus d’ajout d’autres transactions synthétiques à un nœud observateur, voir [Managing Watcher nodes in Lync Server 2013](lync-server-2013-managing-watcher-nodes.md). Vous pouvez utiliser Lync Server Management Shell pour supprimer des transactions synthétiques d’un nœud observateur.

Parmi les transactions synthétiques accessibles aux nœuds observateur, citons les suivantes :


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Nom de l’applet de commande (nom du test)</th>
<th>Description</th>
<th>Type de transaction synthétique</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Test-CsAddressBookService (ABS)</p></td>
<td><p>Confirme que les utilisateurs peuvent rechercher des utilisateurs qui ne figurent pas dans leur liste de contacts.</p></td>
<td><p>Par défaut</p></td>
</tr>
<tr class="even">
<td><p>Test-CsAddressBookWebQuery (ABWQ)</p></td>
<td><p>Confirme que les utilisateurs peuvent rechercher des utilisateurs qui ne figurent pas dans leur liste de contacts via HTTP.</p></td>
<td><p>Par défaut</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsIM (IM)</p></td>
<td><p>Confirme que les utilisateurs peuvent envoyer des messages instantanés d’égal à égal.</p></td>
<td><p>Par défaut</p></td>
</tr>
<tr class="even">
<td><p>Test-CsP2PAV (P2PAV)</p></td>
<td><p>Confirme que les utilisateurs peuvent passer des appels audio d’égal à égal (signalisation uniquement).</p></td>
<td><p>Par défaut</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsPresence (Presence)</p></td>
<td><p>Confirme que les utilisateurs peuvent afficher la présence d’autres utilisateurs.</p></td>
<td><p>Par défaut</p></td>
</tr>
<tr class="even">
<td><p>Test-CsRegistration (Registration)</p></td>
<td><p>Confirme que les utilisateurs peuvent se connecter à Lync.</p></td>
<td><p>Par défaut</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsAudioConferencingProvider (ACP)</p></td>
<td><p>Non utilisé avec la version locale de Lync Server 2013</p></td>
<td><p>Étendue</p></td>
</tr>
<tr class="even">
<td><p>Test-CsPstnPeerToPeerCall (PSTN)</p></td>
<td><p>Confirme que les utilisateurs peuvent passer des appels à des personnes à l’extérieur de l’entreprise et recevoir des appels de celles-ci (numéros PSTN).</p></td>
<td><p>Non par défaut, étendu</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsAVConference (AvConference)</p></td>
<td><p>Confirme que les utilisateurs peuvent créer des conférences audio/vidéo et participer à celles-ci.</p></td>
<td><p>Par défaut</p></td>
</tr>
<tr class="even">
<td><p>Test-CsAVEdgeConnectivity (AVEdgeConnectivity)</p></td>
<td><p>Confirme que les serveurs Edge A/V peuvent accepter des connexions pour les appels et les téléconférences d’égal à égal.</p></td>
<td><p>Non défini par défaut</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsDataConference (DataConference)</p></td>
<td><p>Confirme que les utilisateurs peuvent participer à une conférence de collaboration de données, une réunion en ligne qui comprend des activités telles que des tableaux blancs et des sondages.</p></td>
<td><p>Non défini par défaut</p></td>
</tr>
<tr class="even">
<td><p>Test-CsExumConnectivity (ExumConnectivity)</p></td>
<td><p>Confirme qu’un utilisateur peut se connecter à la messagerie unifiée Exchange.</p></td>
<td><p>Non défini par défaut</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsGroupIM (GroupIM)</p></td>
<td><p>Confirme que les utilisateurs peuvent envoyer des messages instantanés dans des conférences et participer à des conversations par messagerie instantanée comptant trois personnes ou plus.</p></td>
<td><p>Par défaut</p></td>
</tr>
<tr class="even">
<td><p>Test-CsGroupIM – TestJoinLauncher (JoinLauncher)</p></td>
<td><p>Confirme que les utilisateurs peuvent créer des réunions planifiées et y participer via un lien d’adresse web.</p></td>
<td><p>Non défini par défaut</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsMCXP2PIM (MCXP2PIM)</p></td>
<td><p>Confirme que les utilisateurs d’appareil mobile peuvent inscrire et envoyer des messages instantanés.</p></td>
<td><p>Non défini par défaut</p></td>
</tr>
<tr class="even">
<td><p>Test-Cspersistentchatmessage ne (PersistentChatMessage)</p></td>
<td><p>Confirme que les utilisateurs peuvent échanger des messages à l’aide du service de conversation permanente.</p></td>
<td><p>Non défini par défaut</p></td>
</tr>
<tr class="odd">
<td><p>Test-CsUnifiedContactStore (UnifiedContactStore)</p></td>
<td><p>Confirme que les contacts d’un utilisateur sont accessibles via le magasin de contacts unifié. Le magasin de contacts unifié offre aux utilisateurs la possibilité de maintenir un ensemble unique de contacts accessibles via Lync 2013, Outlook et/ou Outlook Web Access.</p></td>
<td><p>Non défini par défaut</p></td>
</tr>
<tr class="even">
<td><p>Test-CsXmppIM (XmppIM)</p></td>
<td><p>Confirme qu’un message instantané peut être envoyé via la passerelle XMPP (Extensible Messaging and Presence Protocol).</p></td>
<td><p>Non défini par défaut</p></td>
</tr>
</tbody>
</table>


Vous n’avez pas besoin d’installer les nœuds observateur afin d’utiliser System Center Operations Manager. Si vous n’installez pas ces nœuds, vous pouvez toujours obtenir des alertes en temps réel à partir des composants Lync Server 2013 lorsqu’un problème se produit. (Le pack d’administration des composants et des utilisateurs n’utilise pas de nœuds observateur.) Toutefois, les nœuds observateurs sont requis si vous souhaitez surveiller des scénarios de bout en bout à l’aide du pack d’administration actif.

<div>


> [!NOTE]  
> Les administrateurs peuvent également exécuter des transactions synthétiques manuellement, et ce sans avoir besoin d’utiliser ou d’installer Operations Manager. Pour plus d’informations sur les différentes cmdlets test-CS, voir l' <A href="https://docs.microsoft.com/powershell/module/skype/?view=skype-ps">index des applets de commande Lync Server 2013</A>.



</div>

En fonction de la taille de votre déploiement, les transactions synthétiques peuvent utiliser une grande quantité de mémoire d’ordinateur et de temps processeur. Pour cette raison, nous vous recommandons d’utiliser un ordinateur dédié comme nœud observateur. Par exemple, vous ne devez pas configurer un serveur frontal pour qu’il serve de nœud observateur. Les nœuds observateurs doivent respecter les spécifications matérielles suivantes :

<div>


> [!NOTE]  
> Un nœud d’observateur Microsoft Lync Server 2010 hérité ne peut pas être colocalisé sur le même ordinateur avec un nœud observateur Lync Server 2013. Cela est dû au fait que les fichiers système principaux de Lync Server 2010 et Lync Server 2013 ne peuvent pas être installés sur le même ordinateur.<BR>Toutefois, les nœuds observateurs Lync Server 2013 peuvent surveiller simultanément Lync Server 2013 et Lync Server 2010. Les transactions synthétiques par défaut sont prises en charge sur les deux versions du produit.



</div>

Les nœuds observateur Lync Server 2013 peuvent être déployés à l’intérieur ou à l’extérieur d’une entreprise pour vérifier les éléments suivants :

  - <span></span>  
    Connectivité aux pools pour les utilisateurs au sein de l’entreprise

  - <span></span>  
    Connectivité par le biais des réseaux de périmètre pour les utilisateurs distants qui travaillent à l’extérieur de l’entreprise

  - <span></span>  
    Connectivité aux Branch Office Appliances

  - <span></span>  
    Connectivité à Lync Server 2010 au sein de l’entreprise et via les réseaux de périmètre.

Différentes options d’authentification sont disponibles pour l’intérieur et l’extérieur de l’entreprise afin de simplifier l’administration. Pour plus d’informations, reportez-vous [à la rubrique Configuration d’un nœud observateur pour exécuter des transactions synthétiques dans Lync Server 2013](lync-server-2013-configuring-a-watcher-node-to-run-synthetic-transactions.md).

Pour configurer un ordinateur pour qu’il serve de nœud observateur, vous devez effectuer les étapes suivantes après avoir installé System Center Operations Manager et importé les packs d’administration Lync Server 2013.

Avant d’installer les fichiers principaux de Lync Server 2013 et les fichiers de l’agent System Center, vous devez également vous assurer que l’ordinateur du nœud observateur remplit toutes les conditions préalables à l’installation de Lync Server 2013. Par ailleurs, les éléments suivants doivent être installés sur l’ordinateur du nœud observateur :


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Composant matériel</th>
<th>Spécification minimale</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>UC</p></td>
<td><p>Un des processeurs suivants :</p>
<ul>
<li><p>processeur 64 bits, quadruple cœur, 2,33 GHz ou supérieur</p></li>
<li><p>processeur double cœur 64 bits, 2 cœurs, 2,33 GHz ou supérieur</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Mémoire</p></td>
<td><p>8 Go</p></td>
</tr>
<tr class="odd">
<td><p>Système d’exploitation réseau</p></td>
<td><ul>
<li><p>1 carte réseau 1 Gbits/s</p></li>
<li><p>Windows Server 2008 R2, Windows Server 2012 ou</p>
<p>Windows Server 2012 R2</p></li>
</ul></td>
</tr>
</tbody>
</table>


  - Version complète du .NET Framework 4.5

  - Windows Identity Foundation

  - Windows PowerShell 3.0.

Dès que toutes ces conditions préalables sont remplies, vous pouvez configurer le nœud observateur en effectuant les opérations suivantes :

  - Installation des fichiers principaux de Lync Server 2013 sur l’ordinateur du nœud observateur.

  - Installation de l’agent System Center Operations Manager sur l’ordinateur du nœud observateur.

  - Exécution du fichier exécutable Watchernode.msi

  - Utilisation des applets de commande **CsWatcherNodeConfiguration** pour configurer les utilisateurs de test qui seront employés par le nœud observateur

</div>

<span> </span>

</div>

</div>

</div>

